# NetSetupPluginManager::LoadDllPlugin(RegistryKey &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,NetSetupPluginType,INetSetupLibraryLoader *)

- ea: `0x18002aac0`
- end: `0x18002abf8`
- name: `?LoadDllPlugin@NetSetupPluginManager@@AEAAXAEAVRegistryKey@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4NetSetupPluginType@@PEAUINetSetupLibraryLoader@@@Z`
- size: `312`
- prototype: `int __fastcall(__int64, __int64, _QWORD *, int, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180048af8`

## callees

- `0x18002aac0`
- `0x18002ac00`
- `0x18002b624`
- `0x18003292c`
- `0x1800646b8`
- `0x1800810d0`

## import_xrefs

- `msvcrt!swscanf_s` at `0x18002ab0f`
- `msvcrt!swscanf_s` at `0x18002ab0f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002abc2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002abc2`

## pseudocode

```c

```
