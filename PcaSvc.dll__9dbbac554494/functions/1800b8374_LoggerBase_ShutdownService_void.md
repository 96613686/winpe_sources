# LoggerBase_ShutdownService(void)

- ea: `0x1800b8374`
- end: `0x1800b8668`
- name: `?LoggerBase_ShutdownService@@YAKXZ`
- size: `756`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, loader_planting, service_task`

## callers

- `0x1800ad8d0`

## callees

- `0x180012920`
- `0x18001b320`
- `0x1800212b0`
- `0x180025b9c`
- `0x180027710`
- `0x18002be54`
- `0x180094238`
- `0x1800b827c`
- `0x1800b82cc`
- `0x1800b833c`
- `0x1800b8374`
- `0x1800b8d5c`
- `0x1800b8e1c`
- `0x1800f7010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800b85e3`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800b85e3`
- `ntdll!RtlFreeHeap` at `0x1800b84ab`
- `ntdll!RtlFreeHeap` at `0x1800b85a2`
- `ntdll!RtlFreeHeap` at `0x1800b85ca`
- `ntdll!RtlFreeHeap` at `0x1800b84ab`
- `ntdll!RtlFreeHeap` at `0x1800b85a2`
- `ntdll!RtlFreeHeap` at `0x1800b85ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b863e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b863e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b8653`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b8653`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b839a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b839a`

## string_xrefs

- `0x1800b8522`: `ServiceShutdown unable to remove tracked processId %d, error: %d`
- `0x1800b852f`: `LoggerBase_ShutdownService`
- `0x1800b861f`: `Shutting down logger service extension`

## pseudocode

```c

```
