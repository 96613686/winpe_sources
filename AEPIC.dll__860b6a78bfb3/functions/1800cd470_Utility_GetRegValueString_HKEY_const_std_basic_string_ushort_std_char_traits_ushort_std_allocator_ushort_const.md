# Utility::GetRegValueString(HKEY__ * const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool)

- ea: `0x1800cd470`
- end: `0x1800cd65f`
- name: `?GetRegValueString@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAUHKEY__@@AEBV23@1_N@Z`
- size: `495`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800cca78`
- `0x1800cd894`

## callees

- `0x180005890`
- `0x18000faf0`
- `0x18001c5f0`
- `0x1800c31ac`
- `0x1800c9810`
- `0x1800c9a04`
- `0x1800cd470`
- `0x1800cfc40`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800cd51b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800cd51b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800cd4fb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800cd586`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800cd4fb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800cd586`

## string_xrefs

- `0x1800cd53a`: `onecore\base\appcompat\inventory\software\inv\lib\utility.cpp`
- `0x1800cd597`: `onecore\base\appcompat\inventory\software\inv\lib\utility.cpp`

## pseudocode

```c

```
