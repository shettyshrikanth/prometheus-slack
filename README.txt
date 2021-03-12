Prometheus
—————
docker run \
    -p 9090:9090 \
    -v ~/services/prometheus/prometheus.yml:/etc/prometheus/prometheus.yml \
    -v ~/services/prometheus/alert.rules.yml:/etc/prometheus/alertmanager/alert.rules.yml \
	prom/prometheus


AlertManager
————
docker run \
    -p 9093:9093 \
    -v ~/services/prometheus/alertmanager/data:/alertmanager:rw \
    -v ~/services/prometheus/alertmanager/conf:/etc/alertmanager/:ro \
	prom/alertmanager


Docs
----
https://pracucci.com/prometheus-understanding-the-delays-on-alerting.html
https://awesome-prometheus-alerts.grep.to/rules.html