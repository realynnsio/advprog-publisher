## How many data your publisher program will send to the message broker in one run?  
Five, since there are 5 calls to `publish_event` within the main() function. With one message per call to publish_event, the publisher program sends a total of 5 messages to the message broker in one run.

## The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean? 
Having the same URL in the subscriber and publisher program means that they're both connecting to the same AMQP server instance. It uses the same username, the same password, and the same hostname & port number. This is done so both programs are connected to the same message broker and can communicate with one another through it.

![Running RabbitMQ](img\running_rabbitmq.jpg "Running RabbitMQ")

![Sending and Processing Event](img\sending_processing_event.jpg "Sending and Processing Event")

The screenshot above shows me running `cargo run` twice on the publisher in the **left window**, which sends 5 events twice (a total of 10 messages) through the message broker, which are then received and processed by the subscriber as seen in the **right window**.