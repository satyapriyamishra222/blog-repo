## Second and targets

For a proper understanding of this blog post, we first need to take a look at how
Prometheus labels targets.

There are various places in the configuration file where target labels may be
set. They are applied in the following order, with later stages overwriting any
labels set by an earlier stage:

1. Global labels, which are assigned to every target scraped by the Prometheus instance.
2. The `job` label, which is configured as a default value for each scrape configuration.
3. Labels that are set per target group within a scrape configuration.
4. Advanced label manipulation via [_relabeling_](/docs/operating/configuration/#relabel_config).