# CSessionConfigTaskThread::ThreadProc(void)

- ea: `0x18002dc24`
- end: `0x18002dd7a`
- name: `?ThreadProc@CSessionConfigTaskThread@@AEAAJXZ`
- size: `342`
- prototype: `__int64 __fastcall(CSessionConfigTaskThread *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002dd80`

## callees

- `0x180003f30`
- `0x18002dc24`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002dc54`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002dc54`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002dd62`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002dd62`

## string_xrefs

- `0x18002dc69`: `CSessionConfigTaskThread::ThreadProc`
- `0x18002dc9c`: `m_pfnCreateConfigTask failed: 0x%x in %s`

## pseudocode

```c

```
