# Win32Adapters::TransactionManager::Transaction::Transaction(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180034650`
- end: `0x1800348ee`
- name: `??0Transaction@TransactionManager@Win32Adapters@@QEAA@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `670`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007f2a8`
- `0x180088d30`
- `0x180089b20`

## callees

- `0x180004424`
- `0x18000e23c`
- `0x18000f380`
- `0x1800183a0`
- `0x1800183f8`
- `0x180018aa8`
- `0x180034650`
- `0x180150ce8`
- `0x1801c3010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18003470e`
- `KERNEL32!GetProcAddress` at `0x180034743`
- `KERNEL32!GetProcAddress` at `0x180034771`
- `KERNEL32!GetProcAddress` at `0x18003479e`
- `KERNEL32!GetProcAddress` at `0x1800347cc`
- `KERNEL32!GetProcAddress` at `0x18003470e`
- `KERNEL32!GetProcAddress` at `0x180034743`
- `KERNEL32!GetProcAddress` at `0x180034771`
- `KERNEL32!GetProcAddress` at `0x18003479e`
- `KERNEL32!GetProcAddress` at `0x1800347cc`
- `KERNEL32!CloseHandle` at `0x180034849`
- `KERNEL32!CloseHandle` at `0x180034849`
- `KERNEL32!GetLastError` at `0x180034724`
- `KERNEL32!GetLastError` at `0x180034752`
- `KERNEL32!GetLastError` at `0x18003477f`
- `KERNEL32!GetLastError` at `0x1800347ad`
- `KERNEL32!GetLastError` at `0x1800347db`
- `KERNEL32!GetLastError` at `0x18003489d`
- `KERNEL32!GetLastError` at `0x180034724`
- `KERNEL32!GetLastError` at `0x180034752`
- `KERNEL32!GetLastError` at `0x18003477f`
- `KERNEL32!GetLastError` at `0x1800347ad`
- `KERNEL32!GetLastError` at `0x1800347db`
- `KERNEL32!GetLastError` at `0x18003489d`

## string_xrefs

- `0x180034707`: `CreateTransaction`
- `0x1800346b9`: `AdvApi32.dll`
- `0x18003469d`: `KtmW32.dll`
- `0x180034766`: `RegCreateKeyTransactedW`
- `0x180034738`: `CommitTransaction`
- `0x1800348c1`: `CreateTransaction failed for %ws with 0x%x`
- `0x1800347c1`: `RegDeleteKeyTransactedW`
- `0x180034793`: `RegOpenKeyTransactedW`

## pseudocode

```c

```
