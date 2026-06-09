# CManifest::MecInstallFile(HKEY__ *,wchar_t const *,MnfstF *,int)

- ea: `0x18165e3ac`
- end: `0x18165f36c`
- name: `?MecInstallFile@CManifest@@IEAAHPEAUHKEY__@@PEB_WPEAVMnfstF@@H@Z`
- size: `4032`
- prototype: `__int64 __fastcall(CManifest *__hidden this, HKEY, const wchar_t *, struct MnfstF *, int)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18165f36c`

## callees

- `0x18001aeb0`
- `0x18001d310`
- `0x18001d460`
- `0x18003a2b0`
- `0x1801cd240`
- `0x180485240`
- `0x180485dd0`
- `0x18095568c`
- `0x181659ea4`
- `0x18165a034`
- `0x18165a558`
- `0x18165ac48`
- `0x18165ac6c`
- `0x18165ae40`
- `0x18165b350`
- `0x18165c088`
- `0x18165ca30`
- `0x18165cb8c`
- `0x18165d634`
- `0x18165e3ac`
- `0x181660598`
- `0x181660878`
- `0x1816613f0`
- `0x1816614a0`
- `0x181661e5c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18165ec6d`
- `KERNEL32!GetLastError` at `0x18165ec6d`
- `KERNEL32!DeleteFileW` at `0x18165ec5f`
- `KERNEL32!DeleteFileW` at `0x18165ec5f`
- `KERNEL32!GetFileAttributesW` at `0x18165ec9a`
- `KERNEL32!GetFileAttributesW` at `0x18165ec9a`
- `KERNEL32!SetFileAttributesW` at `0x18165ec52`
- `KERNEL32!SetFileAttributesW` at `0x18165ec52`
- `KERNEL32!FindFirstFileW` at `0x18165e959`
- `KERNEL32!FindFirstFileW` at `0x18165e959`
- `KERNEL32!FindNextFileW` at `0x18165e9ef`
- `KERNEL32!FindNextFileW` at `0x18165e9ef`
- `KERNEL32!LocalFree` at `0x18165ed51`
- `KERNEL32!LocalFree` at `0x18165ed94`
- `KERNEL32!LocalFree` at `0x18165ed51`
- `KERNEL32!LocalFree` at `0x18165ed94`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x18165e556`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x18165e59e`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x18165e556`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x18165e59e`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18165ec05`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18165ed2b`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18165ed3d`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18165ede6`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18165ec05`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18165ed2b`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18165ed3d`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18165ede6`
- `Mso20Win32Client!__imp_?MsoFEnsureDirectory@@YAHPEB_W@Z` at `0x18165ebf6`
- `Mso20Win32Client!__imp_?MsoFEnsureDirectory@@YAHPEB_W@Z` at `0x18165ebf6`
- `Mso20Win32Client!__imp_MsoWzDecodeInt` at `0x18165ea52`
- `Mso20Win32Client!__imp_MsoWzDecodeInt` at `0x18165ea52`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18165e73e`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18165ea7d`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18165eb1b`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18165eb24`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18165ebc3`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18165efab`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18165f238`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18165f33a`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18165e73e`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18165ea7d`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18165eb1b`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18165eb24`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18165ebc3`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18165efab`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18165f238`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18165f33a`
- `Mso20Win32Client!__imp_?TryRegisterComServer@ComUtil@Mso@@YA_NPEB_W@Z` at `0x18165edd7`
- `Mso20Win32Client!__imp_?TryRegisterComServer@ComUtil@Mso@@YA_NPEB_W@Z` at `0x18165edd7`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165e6b2`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165e701`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165e735`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165e7bb`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165e869`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165e92e`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165e948`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165eac5`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165eae1`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165eb8a`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165ebba`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165ef1f`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165ef3d`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165f09b`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165f0bb`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165f0d8`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165f1c3`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165e6b2`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165e701`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165e735`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165e7bb`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165e869`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165e92e`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165e948`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165eac5`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165eae1`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165eb8a`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165ebba`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165ef1f`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165ef3d`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165f09b`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165f0bb`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165f0d8`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x18165f1c3`
- `Mso20Win32Client!__imp_??2@YAPEAX_KAEBUMarkingLeak_t@NoThrow@Memory@Mso@@@Z` at `0x18165ecdd`
- `Mso20Win32Client!__imp_??2@YAPEAX_KAEBUMarkingLeak_t@NoThrow@Memory@Mso@@@Z` at `0x18165ecdd`
- `Mso20Win32Client!__imp_MsoParseIntWz` at `0x18165e99b`
- `Mso20Win32Client!__imp_MsoParseIntWz` at `0x18165e9d4`
- `Mso20Win32Client!__imp_MsoParseIntWz` at `0x18165e99b`
- `Mso20Win32Client!__imp_MsoParseIntWz` at `0x18165e9d4`
- `ole32!StringFromIID` at `0x18165eeb3`
- `ole32!StringFromIID` at `0x18165eeb3`
- `ole32!CoTaskMemFree` at `0x18165ef48`
- `ole32!CoTaskMemFree` at `0x18165ef48`
- `ADVAPI32!RegCloseKey` at `0x18165efb4`
- `ADVAPI32!RegCloseKey` at `0x18165f109`
- `ADVAPI32!RegCloseKey` at `0x18165f28f`
- `ADVAPI32!RegCloseKey` at `0x18165efb4`
- `ADVAPI32!RegCloseKey` at `0x18165f109`
- `ADVAPI32!RegCloseKey` at `0x18165f28f`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x18165ec40`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x18165ec40`
- `msi!__imp_MsiInstallProductW` at `0x18165e569`
- `msi!__imp_MsiInstallProductW` at `0x18165e569`

## string_xrefs

- `0x18165efde`: `Software\Microsoft\Office\Common\Smart Tag\Recognizers`
- `0x18165eee2`: `Software\Microsoft\Office\Common\Smart Tag\Actions`
- `0x18165f148`: `Software\Microsoft\Office\Common\Smart Tag\Actions`
- `0x18165f155`: `Software\Microsoft\Office\Common\Smart Tag\Actions`

## pseudocode

```c

```
