# RegistryStore::GetAllRegistryValues(HKEY__ *,ushort const *,ushort const *,std::vector<std::unique_ptr<RegistryDataEntry,void * (*)(void *)>,std::allocator<std::unique_ptr<RegistryDataEntry,void * (*)(void *)>>> &,std::set<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> *)

- ea: `0x180080e3c`
- end: `0x18008103a`
- name: `?GetAllRegistryValues@RegistryStore@@AEAAJPEAUHKEY__@@PEBG1AEAV?$vector@V?$unique_ptr@URegistryDataEntry@@P6APEAXPEAX@Z@std@@V?$allocator@V?$unique_ptr@URegistryDataEntry@@P6APEAXPEAX@Z@std@@@2@@std@@PEAV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@4@@Z`
- size: `510`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18002b618`
- `0x180081040`

## callees

- `0x180015fa0`
- `0x180016440`
- `0x18002edcc`
- `0x180037780`
- `0x18006ee7c`
- `0x18007e93c`
- `0x18007f2f0`
- `0x180080114`
- `0x1800806dc`
- `0x180080e3c`
- `0x1800812ac`
- `0x180083334`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180080ee9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180080f4b`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180080eb7`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180080eb7`

## string_xrefs

- `0x180080fd8`: `onecore\windows\hvsi\settings\src\registryutils\registrystore.cpp`
- `0x180081002`: `onecore\windows\hvsi\settings\src\registryutils\registrystore.cpp`
- `0x180080fc9`: `Path = %ws Name = %ws`

## pseudocode

```c

```
