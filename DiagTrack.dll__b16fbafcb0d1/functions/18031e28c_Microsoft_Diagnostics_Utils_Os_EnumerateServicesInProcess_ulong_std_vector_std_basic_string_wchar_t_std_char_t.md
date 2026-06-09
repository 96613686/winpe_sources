# Microsoft::Diagnostics::Utils::Os::EnumerateServicesInProcess(ulong,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> &)

- ea: `0x18031e28c`
- end: `0x18031e9f2`
- name: `?EnumerateServicesInProcess@Os@Utils@Diagnostics@Microsoft@@SAJKAEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@Z`
- size: `1894`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18031ccb0`

## callees

- `0x18001b374`
- `0x18002afd8`
- `0x18002df00`
- `0x1800346b0`
- `0x1800346dc`
- `0x180034c78`
- `0x180034e50`
- `0x180035088`
- `0x180048254`
- `0x180064e8c`
- `0x18008abf4`
- `0x180101424`
- `0x180124dcc`
- `0x180133e1c`
- `0x18020aac0`
- `0x18031e28c`
- `0x180369010`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@K@Z` at `0x18031e464`
- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@K@Z` at `0x18031e464`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18031e2d9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18031e2d9`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18031e3d8`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18031e3d8`
- `OLEAUT32!__imp_SysAllocString` at `0x18031e8ab`
- `OLEAUT32!__imp_SysAllocString` at `0x18031e8ab`
- `OLEAUT32!__imp_SysStringLen` at `0x18031e8d1`
- `OLEAUT32!__imp_SysStringLen` at `0x18031e8d1`
- `OLEAUT32!__imp_VariantInit` at `0x18031e884`
- `OLEAUT32!__imp_VariantInit` at `0x18031e884`
- `OLEAUT32!__imp_VariantClear` at `0x18031e7d7`
- `OLEAUT32!__imp_VariantClear` at `0x18031e91b`
- `OLEAUT32!__imp_VariantClear` at `0x18031e95e`
- `OLEAUT32!__imp_VariantClear` at `0x18031e7d7`
- `OLEAUT32!__imp_VariantClear` at `0x18031e91b`
- `OLEAUT32!__imp_VariantClear` at `0x18031e95e`

## string_xrefs

- `0x18031e44b`: `SELECT Name FROM Win32_Service WHERE ProcessId = `

## pseudocode

```c

```
