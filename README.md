# thingfabric.github.io

Serves `thingfabric.dev`: the start page and the `go-import` meta tags behind
the vanity import paths `thingfabric.dev/<repo>`.

- `<repo>/index.html` answers `go get thingfabric.dev/<repo>`.
- `go-fabric-ui/problems/` answers the RFC 9457 problem `type` URIs of
  go-fabric-ui (contract 0.14.0 and later), one anchor per row of
  `data/go-fabric-ui-problems.tsv`.
- `404.html` carries the tag of every module, so a package or nested-module
  path (`thingfabric.dev/go-fabric/im`, `thingfabric.dev/go-fabric/ble/bluez`)
  resolves too: `cmd/go` parses the tags before it looks at the status code
  (`cmd/go/internal/vcs/vcs.go`, `metaImportsForPrefix`, read at Go 1.27.3).

Every file is generated: edit `MODS` in `generate.sh`, then run
`./generate.sh .` and commit the result.
