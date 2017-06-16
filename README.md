#DigitalTolk Exam
---

## BookingRespository Suggestions for Improvement
Here are some suggestions in regards for both code and architectural improvements:
* Setting default values for variable and array['key'] values was done a lot. It would be nice to have a helper method just to set default value for each of them instead of writing the same statement over and over.
* Warning/Error Notifications could be templated (via helper) instead of writing it's contents over and over again.
* I think it would be nice to have a Wrapper Model called 'BookingRequest', or 'JobRequest', or maybe use the Job Model and store all the validations and behaviors in there so that BookingRepository@store method would be cleaner.
* storeJobEmail, jobToData, and jobEnd would be nicer if its inside the Job model, and then could be labeled/called as $job->storeEmail(), $job->toData(), and $job->end().
* It would be nice if all the mailer notifications behaviours are seperated from 'saving' behaviours. Maybe making the mailers as different Model so that they could be reused.
* I think getPotentialJobIdsWithUserId() should be inside the User Model (UserMeta, and UserLanguage should be used inside the User Model for this instance), and then just call it as $user->getPotentialJobs, which include the job id
* SMS notification and Pushrs could be in another Wrapper Model so that they could be easily reused for other Repositories.
* @line 777, I think it's better to use guzzlehttp/guzzle for reaching out to external API
* updateJob() could be set as Job Model behaviour and call as $job->update();
* changeStatus() could be set as Job Model behaviour and call as $job->changeStatus(), as of its helper methods, they could be merged into just one method and setting $changedTranslator as an optional argument.
* @acceptJob() I think it will be nice if everything will be as $user->acceptJob(Job) where Job is a Job Object, and then reusing the Mailer Notification Model
* @acceptJobWithId could be confusing as acceptJob() should already do the defined behaviour based on the given method name
* @endJob method could be confused with jobEnd() method
* @getAll, I think It will be cleaner if an optional argument called '$filter' with array as data type will be added in the method and then use in_array( -value- ,$filter) to check and add the filters in query. That way getAll() will be more flexible.
* userLoginFailed() might need to be inside User model
* reopen, $job->reopen could be cleaner if this is defined inside Job Model.
