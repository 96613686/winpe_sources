# Windows::Internal::CapabilityAccess::Private::RegGetStringValue(HKEY__ *,ushort const *,ushort const *,bool *)

- ea: `0x180058c8c`
- end: `0x180058df5`
- name: `?RegGetStringValue@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@PEBG1PEA_N@Z`
- size: `361`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `12`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800330f8`
- `0x18004a788`
- `0x18004ac88`
- `0x18004aff8`
- `0x18004b3fc`
- `0x180054fd0`
- `0x1800553e8`
- `0x180056c20`
- `0x18006eda4`
- `0x180074db8`
- `0x180075070`
- `0x180086024`

## callees

- `0x1800094c0`
- `0x18001c3b4`
- `0x18002576c`
- `0x1800257ec`
- `0x180029408`
- `0x1800299c4`
- `0x18003cf4c`
- `0x18003f2d8`
- `0x180058c8c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180058cfc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180058d77`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180058cfc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180058d77`

## string_xrefs

- `0x180058d1f`: `onecore\base\devices\cam\core\registryhelpers.cpp`
- `0x180058d88`: `onecore\base\devices\cam\core\registryhelpers.cpp`

## pseudocode

```c

```
