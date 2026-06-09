# CtapHybridInternal::GetLinkedDevicesNamesFromRegistry(HKEY__ *,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x1801229d0`
- end: `0x180122c51`
- name: `?GetLinkedDevicesNamesFromRegistry@CtapHybridInternal@@YAJPEAUHKEY__@@AEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `641`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180122920`
- `0x1801239cc`

## callees

- `0x18001d5e4`
- `0x180021878`
- `0x1800328b8`
- `0x180037f6c`
- `0x18003a3c0`
- `0x18003a9e8`
- `0x180042df8`
- `0x18004349c`
- `0x180098060`
- `0x1800ae560`
- `0x18010bfa8`
- `0x18010c4b8`
- `0x1801229d0`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180122a3f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180122a3f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180122b1b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180122b6e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180122b1b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180122b6e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180122ae0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180122ae0`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x180122aaa`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x180122aaa`

## string_xrefs

- `0x180122a54`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybridlinkeddevice.cpp`

## pseudocode

```c

```
