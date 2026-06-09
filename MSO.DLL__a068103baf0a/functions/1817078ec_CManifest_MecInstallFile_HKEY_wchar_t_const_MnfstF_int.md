# CManifest::MecInstallFile(HKEY__ *,wchar_t const *,MnfstF *,int)

- ea: `0x1817078ec`
- end: `0x1817088a5`
- name: `?MecInstallFile@CManifest@@IEAAHPEAUHKEY__@@PEB_WPEAVMnfstF@@H@Z`
- size: `4025`
- prototype: `__int64 __fastcall(CManifest *__hidden this, HKEY, const wchar_t *, struct MnfstF *, int)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1817088a8`

## callees

- `0x1800e8d70`
- `0x1801255bc`
- `0x180239aa0`
- `0x18023c2e0`
- `0x18023e8d0`
- `0x180744730`
- `0x1807b2b54`
- `0x1808bdc9c`
- `0x181703404`
- `0x181703584`
- `0x181703aa8`
- `0x181704198`
- `0x1817041bc`
- `0x181704390`
- `0x18170489c`
- `0x1817055c8`
- `0x181705f70`
- `0x1817060cc`
- `0x181706b74`
- `0x1817078ec`
- `0x181709ad4`
- `0x181709db8`
- `0x18170a920`
- `0x18170a9d0`
- `0x18170b378`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1817081ad`
- `KERNEL32!GetLastError` at `0x1817081ad`
- `KERNEL32!DeleteFileW` at `0x18170819f`
- `KERNEL32!DeleteFileW` at `0x18170819f`
- `KERNEL32!GetFileAttributesW` at `0x1817081da`
- `KERNEL32!GetFileAttributesW` at `0x1817081da`
- `KERNEL32!SetFileAttributesW` at `0x181708192`
- `KERNEL32!SetFileAttributesW` at `0x181708192`
- `KERNEL32!FindFirstFileW` at `0x181707e99`
- `KERNEL32!FindFirstFileW` at `0x181707e99`
- `KERNEL32!FindNextFileW` at `0x181707f2f`
- `KERNEL32!FindNextFileW` at `0x181707f2f`
- `KERNEL32!LocalFree` at `0x18170828a`
- `KERNEL32!LocalFree` at `0x1817082cd`
- `KERNEL32!LocalFree` at `0x18170828a`
- `KERNEL32!LocalFree` at `0x1817082cd`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x181707a96`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x181707ade`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x181707a96`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x181707ade`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x181708145`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x181708264`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x181708276`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18170831f`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x181708145`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x181708264`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x181708276`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18170831f`
- `Mso20Win32Client!__imp_?MsoFEnsureDirectory@@YAHPEB_W@Z` at `0x181708136`
- `Mso20Win32Client!__imp_?MsoFEnsureDirectory@@YAHPEB_W@Z` at `0x181708136`
- `Mso20Win32Client!__imp_MsoWzDecodeInt` at `0x181707f92`
- `Mso20Win32Client!__imp_MsoWzDecodeInt` at `0x181707f92`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x181708216`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x181708216`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x181707c7e`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x181707fbd`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18170805b`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x181708064`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x181708103`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1817084e4`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x181708771`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x181708873`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x181707c7e`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x181707fbd`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18170805b`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x181708064`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x181708103`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1817084e4`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x181708771`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x181708873`
- `Mso20Win32Client!__imp_?TryRegisterComServer@ComUtil@Mso@@YA_NPEB_W@Z` at `0x181708310`
- `Mso20Win32Client!__imp_?TryRegisterComServer@ComUtil@Mso@@YA_NPEB_W@Z` at `0x181708310`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x181707bf2`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x181707c41`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x181707c75`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x181707cfb`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x181707da9`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x181707e6e`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x181707e88`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x181708005`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x181708021`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x1817080ca`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x1817080fa`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x181708458`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x181708476`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x1817085d4`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x1817085f4`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x181708611`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x1817086fc`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x181707bf2`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x181707c41`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x181707c75`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x181707cfb`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x181707da9`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x181707e6e`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x181707e88`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x181708005`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x181708021`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x1817080ca`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x1817080fa`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x181708458`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x181708476`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x1817085d4`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x1817085f4`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x181708611`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x1817086fc`
- `Mso20Win32Client!__imp_MsoParseIntWz` at `0x181707edb`
- `Mso20Win32Client!__imp_MsoParseIntWz` at `0x181707f14`
- `Mso20Win32Client!__imp_MsoParseIntWz` at `0x181707edb`
- `Mso20Win32Client!__imp_MsoParseIntWz` at `0x181707f14`
- `ole32!StringFromIID` at `0x1817083ec`
- `ole32!StringFromIID` at `0x1817083ec`
- `ole32!CoTaskMemFree` at `0x181708481`
- `ole32!CoTaskMemFree` at `0x181708481`
- `ADVAPI32!RegCloseKey` at `0x1817084ed`
- `ADVAPI32!RegCloseKey` at `0x181708642`
- `ADVAPI32!RegCloseKey` at `0x1817087c8`
- `ADVAPI32!RegCloseKey` at `0x1817084ed`
- `ADVAPI32!RegCloseKey` at `0x181708642`
- `ADVAPI32!RegCloseKey` at `0x1817087c8`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x181708180`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x181708180`
- `msi!__imp_MsiInstallProductW` at `0x181707aa9`
- `msi!__imp_MsiInstallProductW` at `0x181707aa9`

## string_xrefs

- `0x18170841b`: `Software\Microsoft\Office\Common\Smart Tag\Actions`
- `0x181708681`: `Software\Microsoft\Office\Common\Smart Tag\Actions`
- `0x18170868e`: `Software\Microsoft\Office\Common\Smart Tag\Actions`
- `0x181708517`: `Software\Microsoft\Office\Common\Smart Tag\Recognizers`

## pseudocode

```c

```
