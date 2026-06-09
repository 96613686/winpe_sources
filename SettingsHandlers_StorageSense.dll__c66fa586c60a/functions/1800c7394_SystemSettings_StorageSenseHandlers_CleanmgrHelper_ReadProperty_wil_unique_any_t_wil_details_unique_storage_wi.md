# SystemSettings::StorageSenseHandlers::CleanmgrHelper::_ReadProperty(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Microsoft::WRL::ComPtr<IPropertyBag> const &,ushort const *,ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800c7394`
- end: `0x1800c7545`
- name: `?_ReadProperty@CleanmgrHelper@StorageSenseHandlers@SystemSettings@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$ComPtr@UIPropertyBag@@@WRL@Microsoft@@PEBGKAEAV67@@Z`
- size: `433`
- prototype: `__int64 __fastcall(int, int, int, int, LPCWSTR lpValueName, int, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800c71e8`

## callees

- `0x180029a74`
- `0x1800352b4`
- `0x1800352d8`
- `0x1800af0a0`
- `0x1800c3e2c`
- `0x1800c7394`
- `0x1800e3010`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x1800c742e`
- `OLEAUT32!__imp_SysStringLen` at `0x1800c742e`
- `OLEAUT32!__imp_VariantInit` at `0x1800c73d5`
- `OLEAUT32!__imp_VariantInit` at `0x1800c73d5`
- `OLEAUT32!__imp_VariantClear` at `0x1800c7447`
- `OLEAUT32!__imp_VariantClear` at `0x1800c7447`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c7485`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c74c9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c7485`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c74c9`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x1800c74fa`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x1800c74fa`

## pseudocode

```c

```
