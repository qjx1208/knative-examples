# knative-examples

## images
registry.cn-hangzhou.aliyuncs.com/knative_dev/serving_cmd_controller:0.14.0
registry.cn-hangzhou.aliyuncs.com/knative_dev/serving_cmd_webhook:0.14.0
registry.cn-hangzhou.aliyuncs.com/knative_dev/serving_cmd_activator:0.14.0
registry.cn-hangzhou.aliyuncs.com/knative_dev/serving_cmd_autoscaler:0.14.0
registry.cn-hangzhou.aliyuncs.com/knative_dev/serving_cmd_queue:0.14.0
registry.cn-hangzhou.aliyuncs.com/knative_dev/serving_cmd_default-domain:0.14.0
registry.cn-hangzhou.aliyuncs.com/knative_dev/net-istio_cmd_controller:0.14.0
registry.cn-hangzhou.aliyuncs.com/knative_dev/net-istio_cmd_webhook:0.14.0
registry.cn-hangzhou.aliyuncs.com/knative_dev/eventing_cmd_webhook:0.14.0
registry.cn-hangzhou.aliyuncs.com/knative_dev/eventing_cmd_controller:0.14.0
registry.cn-hangzhou.aliyuncs.com/knative_dev/eventing_cmd_ping_adapter:0.14.0
registry.cn-hangzhou.aliyuncs.com/knative_dev/eventing_cmd_ping_jobrunner:0.14.0
registry.cn-hangzhou.aliyuncs.com/knative_dev/eventing_cmd_apiserver_receive_adapter:0.14.0

## install serving
```
kubectl apply -f serving-crds.yaml
kubectl apply -f serving-core.yaml
kubectl apply -f net-istio.yaml
kubectl get pods --namespace knative-serving
```

## install demo
```
kubectl create ns knative-demo
kubectl apply -f helloworld-go-app.yaml -n knative-demo
kubectl get ksvc -n knative-demo
curl -H "Host: helloworld-go.knative-demo.example.com"  http://172.22.31.104
```