# CtapHybridInternal::GetLinkedDeviceRegKey(HKEY__ *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &)

- ea: `0x180122680`
- end: `0x18012291a`
- name: `?GetLinkedDeviceRegKey@CtapHybridInternal@@YAJPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `666`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801235dc`

## callees

- `0x180021878`
- `0x1800328b8`
- `0x180037f6c`
- `0x18003a9e8`
- `0x180042df8`
- `0x18004349c`
- `0x1800510e8`
- `0x18010bfa8`
- `0x1801223c4`
- `0x180122680`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1801226f1`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1801226f1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801227c6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180122813`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801227c6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180122813`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012278b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012278b`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x180122755`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x180122755`

## string_xrefs

- `0x180122706`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybridlinkeddevice.cpp`

## pseudocode

```c

```
