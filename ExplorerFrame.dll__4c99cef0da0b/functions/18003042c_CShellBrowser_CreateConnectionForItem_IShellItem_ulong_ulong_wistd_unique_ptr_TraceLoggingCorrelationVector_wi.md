# CShellBrowser::_CreateConnectionForItem(IShellItem *,ulong,ulong,wistd::unique_ptr<TraceLoggingCorrelationVector,wistd::default_delete<TraceLoggingCorrelationVector>> &&)

- ea: `0x18003042c`
- end: `0x1800309e7`
- name: `?_CreateConnectionForItem@CShellBrowser@@AEAAJPEAUIShellItem@@KK$$QEAV?$unique_ptr@VTraceLoggingCorrelationVector@@U?$default_delete@VTraceLoggingCorrelationVector@@@wistd@@@wistd@@@Z`
- size: `1467`
- prototype: `__int64 __usercall@<rax>(CShellBrowser *this@<rcx>, struct IShellItem *@<rdx>, __int64)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, service_task`

## callers

- `0x1800917a4`

## callees

- `0x18001b8d0`
- `0x18001c560`
- `0x18003042c`
- `0x180047464`
- `0x18006cfbc`
- `0x18006d480`
- `0x180071e30`
- `0x1800730d0`
- `0x18008b7b8`
- `0x1800a82d0`
- `0x1800a8318`
- `0x1800a8380`
- `0x1800e01ac`
- `0x1800ee038`
- `0x18013f7d0`
- `0x18013fcac`
- `0x1801406ec`
- `0x180210010`

## import_xrefs

- `SHCORE!IUnknown_SetSite` at `0x180030913`
- `SHCORE!IUnknown_SetSite` at `0x180030962`
- `SHCORE!IUnknown_SetSite` at `0x180030913`
- `SHCORE!IUnknown_SetSite` at `0x180030962`
- `SHCORE!IUnknown_Set` at `0x1800305e0`
- `SHCORE!IUnknown_Set` at `0x1800307ac`
- `SHCORE!IUnknown_Set` at `0x1800307b9`
- `SHCORE!IUnknown_Set` at `0x1800307c8`
- `SHCORE!IUnknown_Set` at `0x1800307d7`
- `SHCORE!IUnknown_Set` at `0x1800307e6`
- `SHCORE!IUnknown_Set` at `0x1800305e0`
- `SHCORE!IUnknown_Set` at `0x1800307ac`
- `SHCORE!IUnknown_Set` at `0x1800307b9`
- `SHCORE!IUnknown_Set` at `0x1800307c8`
- `SHCORE!IUnknown_Set` at `0x1800307d7`
- `SHCORE!IUnknown_Set` at `0x1800307e6`
- `SHCORE!__imp_IUnknown_ProfferService` at `0x180030996`
- `SHCORE!__imp_IUnknown_ProfferService` at `0x180030996`
- `SHCORE!__imp_IUnknown_GetClassID` at `0x18003055a`
- `SHCORE!__imp_IUnknown_GetClassID` at `0x18003055a`
- `SHLWAPI!__imp_SHStringFromGUIDW` at `0x1800306b8`
- `SHLWAPI!__imp_SHStringFromGUIDW` at `0x1800306b8`
- `SHLWAPI!__imp_QISearch` at `0x18003064d`
- `SHLWAPI!__imp_QISearch` at `0x18003064d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003047b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003047b`

## pseudocode

```c

```
