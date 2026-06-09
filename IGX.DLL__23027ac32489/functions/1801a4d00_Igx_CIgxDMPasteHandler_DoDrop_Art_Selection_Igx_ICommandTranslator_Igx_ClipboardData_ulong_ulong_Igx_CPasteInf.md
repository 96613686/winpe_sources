# Igx::CIgxDMPasteHandler::DoDrop(Art::Selection &,Igx::ICommandTranslator &,Igx::ClipboardData *,ulong,ulong *,Igx::CPasteInfo &)

- ea: `0x1801a4d00`
- end: `0x1801a5258`
- name: `?DoDrop@CIgxDMPasteHandler@Igx@@UEBAXAEAVSelection@Art@@AEAVICommandTranslator@2@PEAVClipboardData@2@KPEAKAEAVCPasteInfo@2@@Z`
- size: `1368`
- prototype: `void __usercall(Igx::CIgxDMPasteHandler *__hidden this@<rcx>, struct Art::Selection *@<rdx>, struct Igx::ICommandTranslator *@<r8>, struct Igx::ClipboardData *@<r9>, unsigned int, unsigned int *, struct Igx::CPasteInfo *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180024bd0`
- `0x180029590`
- `0x18004d240`
- `0x1800b33fc`
- `0x18011bd68`
- `0x180198fb0`
- `0x1801a4d00`
- `0x1801c32ac`

## import_xrefs

- `USER32!RegisterClipboardFormatW` at `0x1801a4f8f`
- `USER32!RegisterClipboardFormatW` at `0x1801a4f8f`
- `ole32!OleIsCurrentClipboard` at `0x1801a4dd9`
- `ole32!OleIsCurrentClipboard` at `0x1801a4dd9`
- `ole32!CreateStreamOnHGlobal` at `0x1801a500f`
- `ole32!CreateStreamOnHGlobal` at `0x1801a500f`
- `ole32!ReleaseStgMedium` at `0x1801a5203`
- `ole32!ReleaseStgMedium` at `0x1801a5203`
- `mso40uiWin32Client!__imp_?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z` at `0x1801a4e35`
- `mso40uiWin32Client!__imp_?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z` at `0x1801a4e5b`
- `mso40uiWin32Client!__imp_?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z` at `0x1801a50c2`
- `mso40uiWin32Client!__imp_?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z` at `0x1801a4e35`
- `mso40uiWin32Client!__imp_?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z` at `0x1801a4e5b`
- `mso40uiWin32Client!__imp_?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z` at `0x1801a50c2`
- `mso40uiWin32Client!__imp_?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1801a4f5f`
- `mso40uiWin32Client!__imp_?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1801a50a9`
- `mso40uiWin32Client!__imp_?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1801a4f5f`
- `mso40uiWin32Client!__imp_?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1801a50a9`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x1801a4e43`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x1801a5065`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x1801a50cf`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x1801a4e43`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x1801a5065`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x1801a50cf`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1801a4e86`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1801a4f54`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1801a5115`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1801a51d2`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1801a51dd`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1801a4e86`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1801a4f54`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1801a5115`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1801a51d2`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1801a51dd`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1801a501c`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1801a501c`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x1801a4eed`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x1801a5171`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x1801a4eed`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x1801a5171`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEB_WAEBUIStructuredTrace@12@@Z` at `0x1801a4f48`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEB_WAEBUIStructuredTrace@12@@Z` at `0x1801a51c7`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEB_WAEBUIStructuredTrace@12@@Z` at `0x1801a4f48`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEB_WAEBUIStructuredTrace@12@@Z` at `0x1801a51c7`

## pseudocode

```c

```
