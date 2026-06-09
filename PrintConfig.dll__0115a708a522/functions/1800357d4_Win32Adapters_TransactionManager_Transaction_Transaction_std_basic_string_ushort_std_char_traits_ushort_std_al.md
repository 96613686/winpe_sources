# Win32Adapters::TransactionManager::Transaction::Transaction(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800357d4`
- end: `0x180035ac3`
- name: `??0Transaction@TransactionManager@Win32Adapters@@QEAA@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `751`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800821dc`
- `0x18008c120`
- `0x18008d000`

## callees

- `0x180004564`
- `0x18000e644`
- `0x18000f830`
- `0x180018f00`
- `0x180018f58`
- `0x180019698`
- `0x1800357d4`
- `0x180157d60`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180035892`
- `KERNEL32!GetProcAddress` at `0x1800358d3`
- `KERNEL32!GetProcAddress` at `0x18003590d`
- `KERNEL32!GetProcAddress` at `0x180035946`
- `KERNEL32!GetProcAddress` at `0x180035980`
- `KERNEL32!GetProcAddress` at `0x180035892`
- `KERNEL32!GetProcAddress` at `0x1800358d3`
- `KERNEL32!GetProcAddress` at `0x18003590d`
- `KERNEL32!GetProcAddress` at `0x180035946`
- `KERNEL32!GetProcAddress` at `0x180035980`
- `KERNEL32!CloseHandle` at `0x180035a11`
- `KERNEL32!CloseHandle` at `0x180035a11`
- `KERNEL32!GetLastError` at `0x1800358ae`
- `KERNEL32!GetLastError` at `0x1800358e8`
- `KERNEL32!GetLastError` at `0x180035921`
- `KERNEL32!GetLastError` at `0x18003595b`
- `KERNEL32!GetLastError` at `0x180035995`
- `KERNEL32!GetLastError` at `0x180035a6c`
- `KERNEL32!GetLastError` at `0x1800358ae`
- `KERNEL32!GetLastError` at `0x1800358e8`
- `KERNEL32!GetLastError` at `0x180035921`
- `KERNEL32!GetLastError` at `0x18003595b`
- `KERNEL32!GetLastError` at `0x180035995`
- `KERNEL32!GetLastError` at `0x180035a6c`

## string_xrefs

- `0x18003588b`: `CreateTransaction`
- `0x18003583d`: `AdvApi32.dll`
- `0x180035821`: `KtmW32.dll`
- `0x180035902`: `RegCreateKeyTransactedW`
- `0x1800358c8`: `CommitTransaction`
- `0x180035a96`: `CreateTransaction failed for %ws with 0x%x`
- `0x180035975`: `RegDeleteKeyTransactedW`
- `0x18003593b`: `RegOpenKeyTransactedW`

## pseudocode

```c

```
