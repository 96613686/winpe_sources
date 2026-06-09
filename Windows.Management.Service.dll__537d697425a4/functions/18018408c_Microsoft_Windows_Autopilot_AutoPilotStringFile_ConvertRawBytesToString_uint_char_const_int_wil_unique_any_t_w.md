# Microsoft::Windows::Autopilot::AutoPilotStringFile::ConvertRawBytesToString(uint,char const *,int,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &)

- ea: `0x18018408c`
- end: `0x1801841fd`
- name: `?ConvertRawBytesToString@AutoPilotStringFile@Autopilot@Windows@Microsoft@@SAJIPEBDHAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `369`
- prototype: `__int64 __fastcall(UINT CodePage, LPCCH lpMultiByteStr, int cbMultiByte)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801849dc`
- `0x18019f170`
- `0x1801a0c8c`

## callees

- `0x180065b14`
- `0x180065f10`
- `0x180067e34`
- `0x180067e54`
- `0x180090810`
- `0x180184004`
- `0x18018408c`
- `0x180184e54`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x18018412e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x18018412e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x180184103`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteStringBuffer` at `0x180184103`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1801840c7`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18018417a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1801840c7`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18018417a`

## string_xrefs

- `0x180184150`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotconfigurationfile.cpp`
- `0x180184197`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotconfigurationfile.cpp`

## pseudocode

```c

```
