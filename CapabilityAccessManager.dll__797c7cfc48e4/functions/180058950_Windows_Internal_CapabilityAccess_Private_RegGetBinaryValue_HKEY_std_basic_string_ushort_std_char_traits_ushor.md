# Windows::Internal::CapabilityAccess::Private::RegGetBinaryValue(HKEY__ *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::vector<uchar,std::allocator<uchar>> &,bool &)

- ea: `0x180058950`
- end: `0x180058abb`
- name: `?RegGetBinaryValue@Private@CapabilityAccess@Internal@Windows@@YAXPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@EV?$allocator@E@std@@@7@AEA_N@Z`
- size: `363`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18004a788`

## callees

- `0x18000a0bc`
- `0x180029408`
- `0x1800299c4`
- `0x18003ee08`
- `0x180058950`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800589a6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180058a5b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800589a6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180058a5b`

## string_xrefs

- `0x180058a6f`: `onecore\base\devices\cam\core\registryhelpers.cpp`
- `0x180058a8c`: `onecore\base\devices\cam\core\registryhelpers.cpp`
- `0x180058aa6`: `onecore\base\devices\cam\core\registryhelpers.cpp`

## pseudocode

```c

```
