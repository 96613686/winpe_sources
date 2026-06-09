# Igx::CNativeOATextPasteHandler::DoDrop(Art::Selection &,Igx::ICommandTranslator &,Igx::ClipboardData *,ulong,ulong *,Igx::CPasteInfo &)

- ea: `0x1801a5c70`
- end: `0x1801a601a`
- name: `?DoDrop@CNativeOATextPasteHandler@Igx@@UEBAXAEAVSelection@Art@@AEAVICommandTranslator@2@PEAVClipboardData@2@KPEAKAEAVCPasteInfo@2@@Z`
- size: `938`
- prototype: `void __usercall(Igx::CNativeOATextPasteHandler *__hidden this@<rcx>, struct Art::Selection *@<rdx>, struct Igx::ICommandTranslator *@<r8>, struct Igx::ClipboardData *@<r9>, unsigned int, unsigned int *, struct Igx::CPasteInfo *)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180024330`
- `0x180024380`
- `0x180024bd0`
- `0x1800290f0`
- `0x180029590`
- `0x1801912d4`
- `0x180191990`
- `0x180192024`
- `0x18019a7a0`
- `0x18019a8a0`
- `0x1801a5c70`
- `0x1801c32ac`

## import_xrefs

- `KERNEL32!EncodePointer` at `0x1801a5d62`
- `KERNEL32!EncodePointer` at `0x1801a5d62`
- `oart!__imp_??1TextAutofit@Art@@QEAA@XZ` at `0x1801a5fad`
- `oart!__imp_??1TextAutofit@Art@@QEAA@XZ` at `0x1801a5fad`
- `oart!__imp_?FGetTextFromDataObject@Art@@YA_NPEAUIDataObject@@GAEBV?$TWeakPtr@VDocumentContext@Art@@@Ofc@@AEAV?$TOwningPtr@VTextBody@Art@@@4@AEAVTextAutofit@1@AEAV?$TOwningPtr@VClipboardTextResolver@Art@@@4@AEAVCVarStr@4@PEA_N@Z` at `0x1801a5e01`
- `oart!__imp_?FGetTextFromDataObject@Art@@YA_NPEAUIDataObject@@GAEBV?$TWeakPtr@VDocumentContext@Art@@@Ofc@@AEAV?$TOwningPtr@VTextBody@Art@@@4@AEAVTextAutofit@1@AEAV?$TOwningPtr@VClipboardTextResolver@Art@@@4@AEAVCVarStr@4@PEA_N@Z` at `0x1801a5e01`
- `oart!__imp_??0TextAutofit@Art@@QEAA@XZ` at `0x1801a5db3`
- `oart!__imp_??0TextAutofit@Art@@QEAA@XZ` at `0x1801a5db3`
- `oart!__imp_??0TextBody@Art@@QEAA@XZ` at `0x1801a5d36`
- `oart!__imp_??0TextBody@Art@@QEAA@XZ` at `0x1801a5d36`
- `ole32!ReleaseStgMedium` at `0x1801a5fd7`
- `ole32!ReleaseStgMedium` at `0x1801a5fd7`
- `mso40uiWin32Client!__imp_?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z` at `0x1801a5d99`
- `mso40uiWin32Client!__imp_?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z` at `0x1801a5ea5`
- `mso40uiWin32Client!__imp_?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z` at `0x1801a5d99`
- `mso40uiWin32Client!__imp_?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z` at `0x1801a5ea5`
- `mso40uiWin32Client!__imp_?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1801a5da9`
- `mso40uiWin32Client!__imp_?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1801a5da9`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x1801a5dca`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x1801a5e6a`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x1801a5e89`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x1801a5dca`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x1801a5e6a`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x1801a5e89`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1801a5ece`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1801a5f95`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1801a5fb8`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1801a5fc3`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1801a5fcd`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1801a5ece`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1801a5f95`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1801a5fb8`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1801a5fc3`
- `mso40uiWin32Client!__imp_?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z` at `0x1801a5fcd`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x1801a5f31`
- `Mso20Win32Client!__imp_?MsoShouldTrace@Logging@Mso@@YA_NKW4Category@12@W4Severity@12@W4DataCategories@12@@Z` at `0x1801a5f31`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x1801a5e48`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x1801a5e48`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEB_WAEBUIStructuredTrace@12@@Z` at `0x1801a5f86`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEB_WAEBUIStructuredTrace@12@@Z` at `0x1801a5f86`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1801a5e35`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1801a5e35`

## pseudocode

```c

```
