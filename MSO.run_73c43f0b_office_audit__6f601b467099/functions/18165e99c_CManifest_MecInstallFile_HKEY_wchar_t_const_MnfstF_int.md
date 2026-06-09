# CManifest::MecInstallFile(HKEY__ *,wchar_t const *,MnfstF *,int)

- ea: `0x18165e99c`
- end: `0x18165f95c`
- name: `?MecInstallFile@CManifest@@IEAAHPEAUHKEY__@@PEB_WPEAVMnfstF@@H@Z`
- size: `4032`
- prototype: `__int64 __fastcall(CManifest *__hidden this, HKEY, const wchar_t *, struct MnfstF *, int)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18165f95c`

## callees

- `0x18001aea0`
- `0x18001d310`
- `0x18001d460`
- `0x18003a2f0`
- `0x18016eca0`
- `0x1801d44e0`
- `0x1804860a0`
- `0x18095bc5c`
- `0x18165a494`
- `0x18165a624`
- `0x18165ab48`
- `0x18165b238`
- `0x18165b25c`
- `0x18165b430`
- `0x18165b940`
- `0x18165c678`
- `0x18165d020`
- `0x18165d17c`
- `0x18165dc24`
- `0x18165e99c`
- `0x181660b88`
- `0x181660e68`
- `0x1816619e0`
- `0x181661a90`
- `0x18166244c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18165f25d`
- `KERNEL32!GetLastError` at `0x18165f25d`
- `KERNEL32!DeleteFileW` at `0x18165f24f`
- `KERNEL32!DeleteFileW` at `0x18165f24f`
- `KERNEL32!GetFileAttributesW` at `0x18165f28a`
- `KERNEL32!GetFileAttributesW` at `0x18165f28a`
- `KERNEL32!SetFileAttributesW` at `0x18165f242`
- `KERNEL32!SetFileAttributesW` at `0x18165f242`
- `KERNEL32!FindFirstFileW` at `0x18165ef49`
- `KERNEL32!FindFirstFileW` at `0x18165ef49`
- `KERNEL32!FindNextFileW` at `0x18165efdf`
- `KERNEL32!FindNextFileW` at `0x18165efdf`
- `KERNEL32!LocalFree` at `0x18165f341`
- `KERNEL32!LocalFree` at `0x18165f384`
- `KERNEL32!LocalFree` at `0x18165f341`
- `KERNEL32!LocalFree` at `0x18165f384`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x18165eb46`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x18165eb8e`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x18165eb46`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x18165eb8e`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18165f1f5`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18165f31b`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18165f32d`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18165f3d6`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18165f1f5`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18165f31b`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18165f32d`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18165f3d6`
- `Mso20Win32Client!__imp_?MsoFEnsureDirectory@@YAHPEB_W@Z` at `0x18165f1e6`
- `Mso20Win32Client!__imp_?MsoFEnsureDirectory@@YAHPEB_W@Z` at `0x18165f1e6`
- `Mso20Win32Client!__imp_MsoWzDecodeInt` at `0x18165f042`
- `Mso20Win32Client!__imp_MsoWzDecodeInt` at `0x18165f042`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18165ed2e`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18165f06d`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18165f10b`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18165f114`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18165f1b3`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18165f59b`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18165f828`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18165f92a`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18165ed2e`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18165f06d`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18165f10b`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18165f114`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18165f1b3`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18165f59b`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18165f828`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18165f92a`
- `Mso20Win32Client!__imp_?TryRegisterComServer@ComUtil@Mso@@YA_NPEB_W@Z` at `0x18165f3c7`
- `Mso20Win32Client!__imp_?TryRegisterComServer@ComUtil@Mso@@YA_NPEB_W@Z` at `0x18165f3c7`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165eca2`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165ecf1`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165ed25`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165edab`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165ee59`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165ef1e`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165ef38`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165f0b5`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165f0d1`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165f17a`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165f1aa`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165f50f`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165f52d`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165f68b`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165f6ab`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165f6c8`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165f7b3`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165eca2`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165ecf1`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165ed25`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165edab`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165ee59`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165ef1e`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165ef38`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165f0b5`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165f0d1`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165f17a`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165f1aa`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165f50f`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165f52d`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165f68b`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165f6ab`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165f6c8`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165f7b3`
- `Mso20Win32Client!__imp_??2@YAPEAX_KAEBUMarkingLeak_t@NoThrow@Memory@Mso@@@Z` at `0x18165f2cd`
- `Mso20Win32Client!__imp_??2@YAPEAX_KAEBUMarkingLeak_t@NoThrow@Memory@Mso@@@Z` at `0x18165f2cd`
- `Mso20Win32Client!__imp_MsoParseIntWz` at `0x18165ef8b`
- `Mso20Win32Client!__imp_MsoParseIntWz` at `0x18165efc4`
- `Mso20Win32Client!__imp_MsoParseIntWz` at `0x18165ef8b`
- `Mso20Win32Client!__imp_MsoParseIntWz` at `0x18165efc4`
- `ole32!StringFromIID` at `0x18165f4a3`
- `ole32!StringFromIID` at `0x18165f4a3`
- `ole32!CoTaskMemFree` at `0x18165f538`
- `ole32!CoTaskMemFree` at `0x18165f538`
- `ADVAPI32!RegCloseKey` at `0x18165f5a4`
- `ADVAPI32!RegCloseKey` at `0x18165f6f9`
- `ADVAPI32!RegCloseKey` at `0x18165f87f`
- `ADVAPI32!RegCloseKey` at `0x18165f5a4`
- `ADVAPI32!RegCloseKey` at `0x18165f6f9`
- `ADVAPI32!RegCloseKey` at `0x18165f87f`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x18165f230`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x18165f230`
- `msi!__imp_MsiInstallProductW` at `0x18165eb59`
- `msi!__imp_MsiInstallProductW` at `0x18165eb59`

## string_xrefs

- `0x18165f4d2`: `Software\Microsoft\Office\Common\Smart Tag\Actions`
- `0x18165f738`: `Software\Microsoft\Office\Common\Smart Tag\Actions`
- `0x18165f745`: `Software\Microsoft\Office\Common\Smart Tag\Actions`
- `0x18165f5ce`: `Software\Microsoft\Office\Common\Smart Tag\Recognizers`

## pseudocode

```c

```
