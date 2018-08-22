modtest: minimal repro of mod issues

Reproduction:
```
$ go get -u github.com/voutasaurus/modtest
$ docker run -v $HOME/go/src/github.com/voutasaurus/modtest:/go/src/github.com/voutasaurus/modtest -it golang:rc bash
root@5f0374c50214:/go# export GO111MODULE=on
root@5f0374c50214:/go# cd src/github.com/voutasaurus/modtest/
root@5f0374c50214:/go/src/github.com/voutasaurus/modtest# go mod init
go: creating new go.mod: module github.com/voutasaurus/modtest
root@5f0374c50214:/go/src/github.com/voutasaurus/modtest# go test ./...
go: finding github.com/sirupsen/logrus v1.0.6
go: finding github.com/Sirupsen/logrus v1.0.6
go: downloading github.com/sirupsen/logrus v1.0.6
go: downloading github.com/Sirupsen/logrus v1.0.6
go: finding golang.org/x/sys/unix latest
go: finding golang.org/x/sys latest
go: downloading golang.org/x/sys v0.0.0-20180821140842-3b58ed4ad339
go: finding golang.org/x/crypto/ssh/terminal latest
go: finding golang.org/x/crypto/ssh latest
go: finding golang.org/x/crypto latest
go: downloading golang.org/x/crypto v0.0.0-20180820150726-614d502a4dac
upper/upper.go:4:2: case-insensitive import collision: "github.com/Sirupsen/logrus" and "github.com/sirupsen/logrus"
```
