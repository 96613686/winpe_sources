# GetKeyValueStringsWithKeyNamePattern(HKEY__ *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,int,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x18008ed80`
- end: `0x18008f069`
- name: `?GetKeyValueStringsWithKeyNamePattern@@YAJPEAUHKEY__@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@3@@Z`
- size: `745`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x180075ef0`

## callees

- `0x18000b9e0`
- `0x1800117dc`
- `0x180013ef0`
- `0x180014348`
- `0x18001438c`
- `0x180018ac0`
- `0x18001bdd0`
- `0x18001dea8`
- `0x18004dc70`
- `0x1800550dc`
- `0x18008ed80`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008eec7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008eec7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008efc3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008f022`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008efc3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008f022`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18008ee00`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18008ef31`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18008ee00`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18008ef31`

## string_xrefs

- `0x18008effa`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`

## pseudocode

```c

```
