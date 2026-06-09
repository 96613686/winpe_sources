# Microsoft::Windows::Autopilot::AutoPilotStringFile::ConvertRawBytesToString(uint,char const *,int,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)

- ea: `0x18017f68c`
- end: `0x18017f7e1`
- name: `?ConvertRawBytesToString@AutoPilotStringFile@Autopilot@Windows@Microsoft@@SAJIPEBDHAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `341`
- prototype: `__int64 __fastcall(UINT CodePage, LPCCH lpMultiByteStr, int cbMultiByte)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18017ff48`
- `0x180199ddc`
- `0x18019b890`

## callees

- `0x1800658d8`
- `0x180065d10`
- `0x180067a34`
- `0x180067a54`
- `0x18008f6a8`
- `0x18017f614`
- `0x18017f68c`
- `0x180180378`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x18017f722`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x18017f722`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18017f6fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x18017f6fd`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18017f6c7`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18017f765`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18017f6c7`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18017f765`

## string_xrefs

- `0x18017f73e`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotconfigurationfile.cpp`
- `0x18017f77c`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotconfigurationfile.cpp`

## pseudocode

```c

```
