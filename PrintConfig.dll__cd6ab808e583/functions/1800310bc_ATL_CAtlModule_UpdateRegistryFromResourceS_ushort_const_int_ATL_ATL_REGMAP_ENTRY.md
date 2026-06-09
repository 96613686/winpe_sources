# ATL::CAtlModule::UpdateRegistryFromResourceS(ushort const *,int,ATL::_ATL_REGMAP_ENTRY *)

- ea: `0x1800310bc`
- end: `0x1800313db`
- name: `?UpdateRegistryFromResourceS@CAtlModule@ATL@@QEAAJPEBGHPEAU_ATL_REGMAP_ENTRY@2@@Z`
- size: `799`
- prototype: `int(ATL::CAtlModule *__hidden this, const unsigned __int16 *, int, struct ATL::_ATL_REGMAP_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update`

## callers

- `0x180031400`

## callees

- `0x1800032e0`
- `0x180003af0`
- `0x18000425e`
- `0x180010458`
- `0x180026b8c`
- `0x1800272c8`
- `0x1800275e0`
- `0x180029f60`
- `0x18002b888`
- `0x1800310bc`
- `0x1801adb4c`
- `0x1801c3010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180031355`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180031355`
- `KERNEL32!GetModuleHandleW` at `0x18003121c`
- `KERNEL32!GetModuleHandleW` at `0x18003121c`
- `KERNEL32!LeaveCriticalSection` at `0x1800312f0`
- `KERNEL32!LeaveCriticalSection` at `0x180031331`
- `KERNEL32!LeaveCriticalSection` at `0x1800312f0`
- `KERNEL32!LeaveCriticalSection` at `0x180031331`
- `KERNEL32!EnterCriticalSection` at `0x18003122c`
- `KERNEL32!EnterCriticalSection` at `0x1800312cb`
- `KERNEL32!EnterCriticalSection` at `0x18003130c`
- `KERNEL32!EnterCriticalSection` at `0x18003122c`
- `KERNEL32!EnterCriticalSection` at `0x1800312cb`
- `KERNEL32!EnterCriticalSection` at `0x18003130c`
- `KERNEL32!GetModuleFileNameW` at `0x1800311a3`
- `KERNEL32!GetModuleFileNameW` at `0x1800311a3`

## string_xrefs

- `0x180031387`: `REGISTRY`

## pseudocode

```c

```
