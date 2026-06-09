# ATL::CAtlModule::UpdateRegistryFromResource(wchar_t const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x18000918c`
- end: `0x180009548`
- name: `?UpdateRegistryFromResource@CAtlModule@ATL@@QEAAJPEB_WHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `956`
- prototype: `int(ATL::CAtlModule *__hidden this, const wchar_t *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callers

- `0x180007010`

## callees

- `0x180006d40`
- `0x180007310`
- `0x180007654`
- `0x1800077ac`
- `0x18000918c`
- `0x18056bd00`
- `0x18056c5f8`
- `0x18056d170`
- `0x18056dce0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180009246`
- `KERNEL32!EnterCriticalSection` at `0x180009336`
- `KERNEL32!EnterCriticalSection` at `0x180009404`
- `KERNEL32!EnterCriticalSection` at `0x180009461`
- `KERNEL32!EnterCriticalSection` at `0x180009246`
- `KERNEL32!EnterCriticalSection` at `0x180009336`
- `KERNEL32!EnterCriticalSection` at `0x180009404`
- `KERNEL32!EnterCriticalSection` at `0x180009461`
- `KERNEL32!GetModuleFileNameW` at `0x1800092af`
- `KERNEL32!GetModuleFileNameW` at `0x1800092af`
- `KERNEL32!LeaveCriticalSection` at `0x180009265`
- `KERNEL32!LeaveCriticalSection` at `0x180009360`
- `KERNEL32!LeaveCriticalSection` at `0x18000942e`
- `KERNEL32!LeaveCriticalSection` at `0x18000948b`
- `KERNEL32!LeaveCriticalSection` at `0x180009265`
- `KERNEL32!LeaveCriticalSection` at `0x180009360`
- `KERNEL32!LeaveCriticalSection` at `0x18000942e`
- `KERNEL32!LeaveCriticalSection` at `0x18000948b`
- `KERNEL32!InitializeCriticalSectionEx` at `0x180009207`
- `KERNEL32!InitializeCriticalSectionEx` at `0x180009207`
- `KERNEL32!GetLastError` at `0x180009211`
- `KERNEL32!GetLastError` at `0x180009211`
- `KERNEL32!GetModuleHandleW` at `0x180009326`
- `KERNEL32!GetModuleHandleW` at `0x180009326`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180009447`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180009447`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18000944f`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18000944f`

## string_xrefs

- `0x1800094ee`: `REGISTRY`
- `0x180009519`: `REGISTRY`

## pseudocode

```c

```
