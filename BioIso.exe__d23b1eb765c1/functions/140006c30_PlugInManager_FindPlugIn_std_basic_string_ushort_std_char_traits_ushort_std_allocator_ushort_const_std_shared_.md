# PlugInManager::FindPlugIn(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::shared_ptr<PlugIn> *)

- ea: `0x140006c30`
- end: `0x140006d4b`
- name: `?FindPlugIn@PlugInManager@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV?$shared_ptr@VPlugIn@@@3@@Z`
- size: `283`
- prototype: `__int64 __fastcall(_QWORD *, __int64 *)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140008380`
- `0x14000a040`

## callees

- `0x140006c30`
- `0x140007b30`
- `0x140008968`
- `0x14000a420`
- `0x14000c8f0`
- `0x14000e680`
- `0x1400139ac`
- `0x14001bd40`
- `0x14005a960`
- `0x14005b5d0`
- `0x14005b678`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140006ca0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140006ca0`

## string_xrefs

- `0x140006c7f`: `onecore\ds\security\biometrics\service\trustlet\exe\pluginmanager.cpp`

## pseudocode

```c

```
