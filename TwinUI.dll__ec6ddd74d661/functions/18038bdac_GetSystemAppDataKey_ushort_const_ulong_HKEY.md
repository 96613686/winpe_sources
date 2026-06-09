# GetSystemAppDataKey(ushort const *,ulong,HKEY__ * *)

- ea: `0x18038bdac`
- end: `0x18038bf43`
- name: `?GetSystemAppDataKey@@YAJPEBGKPEAPEAUHKEY__@@@Z`
- size: `407`
- prototype: `int(const unsigned __int16 *, unsigned int, HKEY *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180138320`

## callees

- `0x18002fc18`
- `0x18006137c`
- `0x1800a0f20`
- `0x1801437d0`
- `0x180145138`
- `0x18038bdac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18038bdea`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18038bdea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18038bdd2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18038bdd2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18038bee6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18038bee6`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicit` at `0x18038be10`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicit` at `0x18038be10`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x18038be46`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x18038beb6`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x18038be46`
- `api-ms-win-appmodel-state-l1-2-0!GetSystemAppDataKey` at `0x18038beb6`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x18038bf20`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x18038bf20`

## pseudocode

```c

```
