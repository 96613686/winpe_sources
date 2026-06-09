# WaasMedic::CDeferManager::GetPluginDeferredTime(ushort const *,bool &,bool &,_FILETIME &)

- ea: `0x18002094c`
- end: `0x180020b42`
- name: `?GetPluginDeferredTime@CDeferManager@WaasMedic@@AEAAJPEBGAEA_N1AEAU_FILETIME@@@Z`
- size: `502`
- prototype: `__int64 __fastcall(WaasMedic::CDeferManager *__hidden this, const unsigned __int16 *, bool *, bool *, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x1800202d8`

## callees

- `0x1800050a0`
- `0x18000bbd4`
- `0x18002094c`
- `0x180029a30`
- `0x180029d0c`
- `0x18002a2b8`
- `0x18002e81c`
- `0x1800639bc`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180020a05`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180020a05`
- `OLEAUT32!__imp_VariantInit` at `0x180020983`
- `OLEAUT32!__imp_VariantInit` at `0x180020983`
- `OLEAUT32!__imp_VariantClear` at `0x1800209d5`
- `OLEAUT32!__imp_VariantClear` at `0x180020a3b`
- `OLEAUT32!__imp_VariantClear` at `0x180020aa4`
- `OLEAUT32!__imp_VariantClear` at `0x180020afa`
- `OLEAUT32!__imp_VariantClear` at `0x1800209d5`
- `OLEAUT32!__imp_VariantClear` at `0x180020a3b`
- `OLEAUT32!__imp_VariantClear` at `0x180020aa4`
- `OLEAUT32!__imp_VariantClear` at `0x180020afa`

## string_xrefs

- `0x180020a64`: `Time plugin scheduled: %s`
- `0x180020ae4`: `GetPluginDeferredTime for plugin %s: Deferred: %d Expired: %d.`

## pseudocode

```c

```
