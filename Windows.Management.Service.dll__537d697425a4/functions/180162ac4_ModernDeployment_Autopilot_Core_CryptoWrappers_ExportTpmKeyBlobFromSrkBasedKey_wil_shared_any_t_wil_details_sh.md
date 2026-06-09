# ModernDeployment::Autopilot::Core::CryptoWrappers::ExportTpmKeyBlobFromSrkBasedKey(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::vector<uchar,std::allocator<uchar>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,ulong &)

- ea: `0x180162ac4`
- end: `0x180162e66`
- name: `?ExportTpmKeyBlobFromSrkBasedKey@CryptoWrappers@Core@Autopilot@ModernDeployment@@SAJAEBV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV78@AEAV?$vector@EV?$allocator@E@std@@@8@2AEAK@Z`
- size: `930`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, service_task`

## callers

- `0x18013d140`
- `0x18013f04c`

## callees

- `0x18000b8f0`
- `0x180067e54`
- `0x180077de0`
- `0x180080bac`
- `0x180080c10`
- `0x180081f38`
- `0x18008af70`
- `0x18008d290`
- `0x180135a64`
- `0x180135ea0`
- `0x180140448`
- `0x1801481a0`
- `0x180161ac4`
- `0x180162ac4`

## import_xrefs

- `TpmCoreProvisioning!TpmGetPssSalt` at `0x180162de2`
- `TpmCoreProvisioning!TpmGetPssSalt` at `0x180162de2`
- `ncrypt!NCryptGetProperty` at `0x180162cfb`
- `ncrypt!NCryptGetProperty` at `0x180162d64`
- `ncrypt!NCryptGetProperty` at `0x180162cfb`
- `ncrypt!NCryptGetProperty` at `0x180162d64`
- `ncrypt!NCryptExportKey` at `0x180162bfe`
- `ncrypt!NCryptExportKey` at `0x180162c8e`
- `ncrypt!NCryptExportKey` at `0x180162bfe`
- `ncrypt!NCryptExportKey` at `0x180162c8e`

## string_xrefs

- `0x180162b1e`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\cryptowrappers.cpp`
- `0x180162c1c`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\cryptowrappers.cpp`
- `0x180162d99`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\cryptowrappers.cpp`

## pseudocode

```c

```
