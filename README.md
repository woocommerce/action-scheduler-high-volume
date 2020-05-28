> **Note:** With the major improvements added to Action Scheduler 3.0, most notably the migration to custom tables for storing actions and loopback requests to chain the processing of actions, the tweaks available in this plugin should be required far less often than with earlier versions of Action Scheduler.

> The code here remains mostly to demonstrate how to tweak some of the configuration that influences throughput.


### Action Scheduler High Volume

Increase the processing thresholds for Action Scheduler to process large queues of actions more quickly. Handy for high volume websites with more server resources.

This plugin will change the Action Scheduler:

* [Time Limit](https://actionscheduler.org/perf/#increasing-time-limit): to process queues for up to 120 seconds, instead of the default limit of 30 seconds*.
* [Batch Size](https://actionscheduler.org/perf/#increasing-batch-size): to process batches of 100 actions and reduce time taken to claim additional actions.
* [Concurrency](https://actionscheduler.org/perf/#increasing-concurrent-batches): to allow 10 concurrent queues to process actions, up from 5.
* [Runner Initialization Rate](https://actionscheduler.org/perf/#increasing-initialisation-rate-of-runners): to start 5 queues every time WP Cron triggers Action Scheduler (scheduled to be every minute) instead of one queue.

For more details on these changes, refer to the [Action Scheduler Performance Tuning guide](https://actionscheduler.org/perf/).

> <sup>*</sup> WP Engine only supports a maximum of 60 seconds per request - if using WP Engine, the time limit set by this plugin in the `ashp_increase_time_limit()` function will need to be decreased from 120 to 60.

