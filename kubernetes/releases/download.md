# 下载Kubernetes

## 容器镜像

Kubernetes容器镜像注册表：`registry.k8s.io`。

**Kubernetes v1.24 [alpha]特性**

Kubernetes容器镜像签名方式：[cosign](https://github.com/sigstore/cosign)

| 容器镜像                                            | 支持架构                          |
|-------------------------------------------------|-------------------------------|
| registry.k8s.io/kube-apiserver:v1.28.2          | amd64、arm、arm64、ppc64le、s390x |
| registry.k8s.io/kube-controller-manager:v1.28.2 | amd64、arm、arm64、ppc64le、s390x |
| registry.k8s.io/kube-proxy:v1.28.2              | amd64、arm、arm64、ppc64le、s390x |
| registry.k8s.io/kube-scheduler:v1.28.2          | amd64、arm、arm64、ppc64le、s390x |
| registry.k8s.io/conformance:v1.28.2             | amd64、arm、arm64、ppc64le、s390x |

可以拉取指定架构的容器镜像，例如：`registry.k8s.io/kube-apiserver-arm64:v1.28.2`。

获取 [SPDX 2.3](https://spdx.dev/specifications) 签名格式的Kubernetes容器镜像：

```shell
curl -Ls "https://sbom.k8s.io/$(curl -Ls https://dl.k8s.io/release/stable.txt)/release" | grep "SPDXID: SPDXRef-Package-registry.k8s.io" |  grep -v sha256 | cut -d- -f3- | sed 's/-/\//' | sed 's/-v1/:v1/'
```

手动验证Kubernetes签名容器镜像：https://kubernetes.io/docs/tasks/administer-cluster/verify-signed-artifacts

## 二进制文件

+ Kubernetes下载地址：https://github.com/kubernetes/kubernetes/tree/master/CHANGELOG
+ Kubernetes下载地址：https://www.downloadkubernetes.com

### kubectl

Kubernetes命令行工具：https://kubernetes.io/docs/reference/kubectl/kubectl

kubectl参考文档：https://kubernetes.io/docs/reference/kubectl

安装kubectl：
+ 在Linux上安装kubectl：https://kubernetes.io/docs/tasks/tools/install-kubectl-linux
+ 在MacOS上安装kubectl：https://kubernetes.io/docs/tasks/tools/install-kubectl-macos
+ 在Windows上安装kubectl：https://kubernetes.io/docs/tasks/tools/install-kubectl-windows
