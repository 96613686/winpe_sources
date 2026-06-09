# UbpmpAcquireUpdateLockShared

- ea: `0x1800156f0`
- end: `0x180015753`
- name: `UbpmpAcquireUpdateLockShared`
- size: `99`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x1800100b0`
- `0x1800136b0`
- `0x1800158e0`

## callees

- `0x1800156f0`

## import_xrefs

- `ntdll!RtlAcquireSRWLockShared` at `0x180015743`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180015707`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180015718`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180015707`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180015718`

## pseudocode

```c

```
