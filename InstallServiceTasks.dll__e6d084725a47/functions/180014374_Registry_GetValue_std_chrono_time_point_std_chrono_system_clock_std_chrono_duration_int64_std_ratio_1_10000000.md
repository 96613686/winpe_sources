# Registry::GetValue<std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(HKEY__ *,ushort const *,ushort const *)

- ea: `0x180014374`
- end: `0x180014420`
- name: `??$GetValue@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Registry@@YA?AV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@PEAUHKEY__@@PEBG1@Z`
- size: `172`
- prototype: `_QWORD *__fastcall(_QWORD *, HKEY, const WCHAR *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x1800190e0`
- `0x18001913c`

## callees

- `0x180003450`
- `0x180011544`
- `0x180014374`
- `0x180019640`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800143cd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800143cd`

## string_xrefs

- `0x1800143a7`: `AutoUpdateLastSuccessTime`

## pseudocode

```c

```
