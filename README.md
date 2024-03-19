## Airflow 

### Components

- Scheduler: Manages both the activation of scheduled workflows and the dispatching of tasks to the executor for execution. The worker is a scheduler configuration property, not a separate component, and runs within the scheduler process.
- Webserver: Presents a convenient user interface for inspecting, activating and debugging the behavior of DAGs and tasks.
- Dag Folder: A folder of files that the scheduler reads to figure out which tasks to run and when and execute them.
- Metadata Database: Used by airflow components to store the status of workflows and tasks. The configuration of a metadata database is described in Configuring a database backend and is required for airflow to work.

### Optional Components

Some Airflow components are optional and can enable greater extensibility, scalability and performance in your Airflow:

- Worker: executes the tasks assigned to it by the scheduler. In the basic installation, the worker can be part of the scheduler and not be a standalone component.
- Trigger: Executes deferred tasks in an asynchronous event loop. In a basic installation where no deferred tasks are used, a triggerer is not required.
- Dag Processor: Parses the DAG files and serializes them in the metadata database. By default, the dag processor process is part of the scheduler, but it can be run as a separate component for scalability and security reasons. If the dag processor is present the scheduler does not need to read the DAG files directly.
- Plugin folder: Plugins are a way to extend the functionality of Airflow (similar to installed packages). Plugins are read by the scheduler, the dag processor, the trigger and the web server.
