# Utility::GetRegValueString(HKEY__ * const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool)

- ea: `0x180039b70`
- end: `0x180039d6e`
- name: `?GetRegValueString@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAUHKEY__@@AEBV23@1_N@Z`
- size: `510`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180039288`

## callees

- `0x180004ea0`
- `0x18000fb60`
- `0x1800134b8`
- `0x180039b70`
- `0x180044364`
- `0x180044388`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180039bf1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180039c61`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180039bf1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180039c61`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180039c11`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180039c11`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039d20`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039d20`

## string_xrefs

- `0x180039d4a`: `onecore\internal\base\inc\appcompat\inventory\utility.cpp`
- `0x180039d5c`: `onecore\internal\base\inc\appcompat\inventory\utility.cpp`

## pseudocode

```c

```
