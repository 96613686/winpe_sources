# wil::details::close_invoke_helper<1,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wil::details::registry_watcher_state *>::close_reset(wil::details::registry_watcher_state *)

- ea: `0x180030b94`
- end: `0x180030c17`
- name: `?close_reset@?$close_invoke_helper@$00P6AXPEAUregistry_watcher_state@details@wil@@@Z$1?delete_registry_watcher_state@23@YAX0@ZPEAU123@@details@wil@@SAXPEAUregistry_watcher_state@23@@Z`
- size: `131`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800140c8`
- `0x18003092c`
- `0x180030b60`

## callees

- `0x180030b94`
- `0x18004f9dc`
- `0x180063024`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x180030bf9`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180030bf9`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180030bb8`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180030bb8`
- `KERNEL32!SetLastError` at `0x180030c10`
- `KERNEL32!GetLastError` at `0x180030ba6`
- `KERNEL32!GetLastError` at `0x180030ba6`

## pseudocode

```c

```
