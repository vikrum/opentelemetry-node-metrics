# opentelemetry-node-metrics

A modernized set of node metrics for OpenTelemetry. Based on two excellent modules:

* [Marc Bachmann's opentelemetry-node-metrics](https://github.com/marcbachmann/opentelemetry-node-metrics)
* [Simon Nyberg's prom-client](https://github.com/siimon/prom-client)

Usage:
```sh
yarn add @sesamecare-oss/opentelemetry-node-metrics
```

Wire up OTEL as normal - using node auto instrumentations or manual setup as you wish. Then, at an appropriate place, include something like the below:

```ts
import { metrics } from '@opentelemetry/api';
import { setupNodeMetrics } from '@sesamecare-oss/opentelemetry-node-metrics';

const meter = metrics.getMeterProvider().getMeter('node-metrics');
setupNodeMetrics(meter);
```

Now your Prometheus-exported metrics should be included along with whatever other metrics you ahve selected. See [openapi-typescript-infra/service](https://github.com/openapi-typescript-infra/service) for a more complete example of metrics integrated with an express service host.
