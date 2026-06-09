# ModernDeployment::Autopilot::Core::CryptoWrappers::ExportTpmKeyBlobFromSrkBasedKey(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::vector<uchar,std::allocator<uchar>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,ulong &)

- ea: `0x18015e760`
- end: `0x18015eae3`
- name: `?ExportTpmKeyBlobFromSrkBasedKey@CryptoWrappers@Core@Autopilot@ModernDeployment@@SAJAEBV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV78@AEAV?$vector@EV?$allocator@E@std@@@8@2AEAK@Z`
- size: `899`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, service_task`

## callers

- `0x180139148`
- `0x18013aff8`

## callees

- `0x18000b820`
- `0x180067a54`
- `0x18007755c`
- `0x18008019c`
- `0x1800801fc`
- `0x1800814a8`
- `0x18008a0a8`
- `0x18008c244`
- `0x180131cb0`
- `0x1801320e0`
- `0x18013c3c8`
- `0x180144120`
- `0x18015d794`
- `0x18015e760`

## import_xrefs

- `TpmCoreProvisioning!TpmGetPssSalt` at `0x18015ea66`
- `TpmCoreProvisioning!TpmGetPssSalt` at `0x18015ea66`
- `ncrypt!NCryptGetProperty` at `0x18015e98b`
- `ncrypt!NCryptGetProperty` at `0x18015e9ee`
- `ncrypt!NCryptGetProperty` at `0x18015e98b`
- `ncrypt!NCryptGetProperty` at `0x18015e9ee`
- `ncrypt!NCryptExportKey` at `0x18015e89a`
- `ncrypt!NCryptExportKey` at `0x18015e924`
- `ncrypt!NCryptExportKey` at `0x18015e89a`
- `ncrypt!NCryptExportKey` at `0x18015e924`

## string_xrefs

- `0x18015e7ba`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\cryptowrappers.cpp`
- `0x18015e8b2`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\cryptowrappers.cpp`
- `0x18015ea1d`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\cryptowrappers.cpp`

## pseudocode

```c

```
