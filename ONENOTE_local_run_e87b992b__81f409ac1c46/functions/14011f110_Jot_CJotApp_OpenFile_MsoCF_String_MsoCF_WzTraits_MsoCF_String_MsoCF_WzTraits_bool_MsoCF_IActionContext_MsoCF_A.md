# Jot::CJotApp::OpenFile(MsoCF::String<MsoCF::WzTraits>,MsoCF::String<MsoCF::WzTraits>,bool,MsoCF::IActionContext *,MsoCF::AFrame *,bool,bool,bool,bool,bool)

- ea: `0x14011f110`
- end: `0x1401205eb`
- name: `?OpenFile@CJotApp@Jot@@SA_NV?$String@UWzTraits@MsoCF@@@MsoCF@@0_NPEAUIActionContext@4@PEAUAFrame@4@11111@Z`
- size: `5339`
- prototype: `char __fastcall(_WORD *, const wchar_t *, char, struct MsoCF::IActionContext *, __int64, char, char, char, char, char)`
- caller_count: `4`
- callee_count: `19`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14001446c`
- `0x1400eaa04`
- `0x1400eb020`
- `0x1400ec1c4`

## callees

- `0x1400209a0`
- `0x14003f250`
- `0x140040888`
- `0x1400488d0`
- `0x140048a58`
- `0x140048fb0`
- `0x140052c10`
- `0x140056ac0`
- `0x140057580`
- `0x140064e70`
- `0x140095a60`
- `0x1400bc868`
- `0x1400e8a74`
- `0x1400e926c`
- `0x1400ea380`
- `0x1400ea420`
- `0x14011f110`
- `0x1401221d4`
- `0x1401a91a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14011f4ce`
- `KERNEL32!GetLastError` at `0x14011f4ce`
- `onmain!?GetFolderProxyFromPath_Exported@Jot@@YAXV?$String@UWzTraits@MsoCF@@@MsoCF@@PEAPEAUIFolderProxy@1@_NPEA_N2@Z` at `0x14011f567`
- `onmain!?GetFolderProxyFromPath_Exported@Jot@@YAXV?$String@UWzTraits@MsoCF@@@MsoCF@@PEAPEAUIFolderProxy@1@_NPEA_N2@Z` at `0x14011f567`
- `onmain!?priOpenReadOnly@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B` at `0x140120497`
- `onmain!?priWarnAgainstIncorrectExtension@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B` at `0x1401204f2`
- `onmain!??0CProgressLock@ProgressUI@OneNote@@QEAA@PEAUIProgress@12@I@Z` at `0x14011f33d`
- `onmain!??0CProgressLock@ProgressUI@OneNote@@QEAA@PEAUIProgress@12@I@Z` at `0x14011f33d`
- `onmain!?c_wzTableOfContentsFileExtensionV2@Jot@@3PEB_WEB` at `0x14011f3f0`
- `onmain!?GetFileProxyFromPath_Async_MayShowAuthUI_Exported@Jot@@YAXV?$String@UWzTraits@MsoCF@@@MsoCF@@PEAPEAUIAsyncResult_IFileProxy@1@PEAUHWND__@@PEAUIProgress@ProgressUI@OneNote@@H@Z` at `0x14011f45e`
- `onmain!?GetFileProxyFromPath_Async_MayShowAuthUI_Exported@Jot@@YAXV?$String@UWzTraits@MsoCF@@@MsoCF@@PEAPEAUIAsyncResult_IFileProxy@1@PEAUHWND__@@PEAUIProgress@ProgressUI@OneNote@@H@Z` at `0x14011f45e`
- `onmain!?WaitToComplete_Throws@Jot@@YAXPEAUIAsyncResult@1@PEAUIProgress@ProgressUI@OneNote@@@Z` at `0x14011f48e`
- `onmain!?WaitToComplete_Throws@Jot@@YAXPEAUIAsyncResult@1@PEAUIProgress@ProgressUI@OneNote@@@Z` at `0x14011f48e`
- `onmain!?IsTaskLinkFile@Jot@@YA_NPEAUIFileProxy@1@AEAVCWzInBuffer@1@PEAUIProgress@ProgressUI@OneNote@@@Z` at `0x14011f66a`
- `onmain!?IsTaskLinkFile@Jot@@YA_NPEAUIFileProxy@1@AEAVCWzInBuffer@1@PEAUIProgress@ProgressUI@OneNote@@@Z` at `0x14011f66a`
- `onmain!?IsFileInAnyKnownTempFolder@Jot@@YA_NPEAUIFileProxy@1@@Z` at `0x14011fa65`
- `onmain!?IsFileInAnyKnownTempFolder@Jot@@YA_NPEAUIFileProxy@1@@Z` at `0x14011fa65`
- `onmain!?GetInternetCacheFolder@Jot@@YAXPEAPEAUIFolderProxy@1@@Z` at `0x14012034d`
- `onmain!?GetInternetCacheFolder@Jot@@YAXPEAPEAUIFolderProxy@1@@Z` at `0x14012034d`
- `onmain!??BCWzInBuffer@Jot@@QEBAPEB_WXZ` at `0x14011f3c3`
- `onmain!??BCWzInBuffer@Jot@@QEBAPEB_WXZ` at `0x14011f3c3`
- `onmain!?FIsRestrictedLocation@Jot@@YA_NPEAUIFolderProxy@1@@Z` at `0x14011fe9f`
- `onmain!?FIsRestrictedLocation@Jot@@YA_NPEAUIFolderProxy@1@@Z` at `0x14011fe9f`
- `onmain!?IsServerAuthenticationError@Jot@@YA_NAEBVexception_ptr@std@@@Z` at `0x14011fb01`
- `onmain!?IsServerAuthenticationError@Jot@@YA_NAEBVexception_ptr@std@@@Z` at `0x14011fb01`
- `onmain!?FGetNotebookRoot@Jot@@YA_NPEAUIFileProxy@1@PEAPEAUIFolderProxy@1@PEAPEAU21@_NPEAUHWND__@@PEAVexception_ptr@std@@PEAUIProgress@ProgressUI@OneNote@@PEA_N7@Z` at `0x14011faf0`
- `onmain!?FGetNotebookRoot@Jot@@YA_NPEAUIFileProxy@1@PEAPEAUIFolderProxy@1@PEAPEAU21@_NPEAUHWND__@@PEAVexception_ptr@std@@PEAUIProgress@ProgressUI@OneNote@@PEA_N7@Z` at `0x14011faf0`
- `onmain!?UseProgress@CProgressLock@ProgressUI@OneNote@@UEBAPEAUIProgress@23@XZ` at `0x14011f680`
- `onmain!?UseProgress@CProgressLock@ProgressUI@OneNote@@UEBAPEAUIProgress@23@XZ` at `0x14011fc72`
- `onmain!?UseProgress@CProgressLock@ProgressUI@OneNote@@UEBAPEAUIProgress@23@XZ` at `0x14011feb5`
- `onmain!?UseProgress@CProgressLock@ProgressUI@OneNote@@UEBAPEAUIProgress@23@XZ` at `0x140120163`
- `onmain!?UseProgress@CProgressLock@ProgressUI@OneNote@@UEBAPEAUIProgress@23@XZ` at `0x14011f680`
- `onmain!?UseProgress@CProgressLock@ProgressUI@OneNote@@UEBAPEAUIProgress@23@XZ` at `0x14011fc72`
- `onmain!?UseProgress@CProgressLock@ProgressUI@OneNote@@UEBAPEAUIProgress@23@XZ` at `0x14011feb5`
- `onmain!?UseProgress@CProgressLock@ProgressUI@OneNote@@UEBAPEAUIProgress@23@XZ` at `0x140120163`
- `onmain!?CreateChildProgress@CProgressLock@ProgressUI@OneNote@@UEAA?AV?$CIPtr@UIProgress@ProgressUI@OneNote@@U123@@MsoCF@@I@Z` at `0x14011f321`
- `onmain!?CreateChildProgress@CProgressLock@ProgressUI@OneNote@@UEAA?AV?$CIPtr@UIProgress@ProgressUI@OneNote@@U123@@MsoCF@@I@Z` at `0x14011f35b`
- `onmain!?CreateChildProgress@CProgressLock@ProgressUI@OneNote@@UEAA?AV?$CIPtr@UIProgress@ProgressUI@OneNote@@U123@@MsoCF@@I@Z` at `0x14011f477`
- `onmain!?CreateChildProgress@CProgressLock@ProgressUI@OneNote@@UEAA?AV?$CIPtr@UIProgress@ProgressUI@OneNote@@U123@@MsoCF@@I@Z` at `0x14011f635`
- `onmain!?CreateChildProgress@CProgressLock@ProgressUI@OneNote@@UEAA?AV?$CIPtr@UIProgress@ProgressUI@OneNote@@U123@@MsoCF@@I@Z` at `0x14011f866`
- `onmain!?CreateChildProgress@CProgressLock@ProgressUI@OneNote@@UEAA?AV?$CIPtr@UIProgress@ProgressUI@OneNote@@U123@@MsoCF@@I@Z` at `0x14011f321`
- `onmain!?CreateChildProgress@CProgressLock@ProgressUI@OneNote@@UEAA?AV?$CIPtr@UIProgress@ProgressUI@OneNote@@U123@@MsoCF@@I@Z` at `0x14011f35b`
- `onmain!?CreateChildProgress@CProgressLock@ProgressUI@OneNote@@UEAA?AV?$CIPtr@UIProgress@ProgressUI@OneNote@@U123@@MsoCF@@I@Z` at `0x14011f477`
- `onmain!?CreateChildProgress@CProgressLock@ProgressUI@OneNote@@UEAA?AV?$CIPtr@UIProgress@ProgressUI@OneNote@@U123@@MsoCF@@I@Z` at `0x14011f635`
- `onmain!?CreateChildProgress@CProgressLock@ProgressUI@OneNote@@UEAA?AV?$CIPtr@UIProgress@ProgressUI@OneNote@@U123@@MsoCF@@I@Z` at `0x14011f866`
- `onmain!??0CProgressLock@ProgressUI@OneNote@@QEAA@PEAUIProgress@12@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z` at `0x14011f2f9`
- `onmain!??0CProgressLock@ProgressUI@OneNote@@QEAA@PEAUIProgress@12@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z` at `0x14011f2f9`
- `onmain!?CreateProgressDialog@ProgressUI@OneNote@@YA?AV?$CIRef@UIProgress@ProgressUI@OneNote@@@MsoCF@@PEBVCWindow@4@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1_N@Z` at `0x14011f2a4`
- `onmain!?CreateProgressDialog@ProgressUI@OneNote@@YA?AV?$CIRef@UIProgress@ProgressUI@OneNote@@@MsoCF@@PEBVCWindow@4@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1_N@Z` at `0x14011f2a4`
- `onmain!?GetQuickNotesSection@Jot@@YAXPEAPEAUIFileProxy@1@_N@Z` at `0x14011f997`
- `onmain!?GetQuickNotesSection@Jot@@YAXPEAPEAUIFileProxy@1@_N@Z` at `0x14011f997`
- `onmain!?AreEqualFilenames@Jot@@YA_NPEB_W0@Z` at `0x14011f1f8`
- `onmain!?AreEqualFilenames@Jot@@YA_NPEB_W0@Z` at `0x14011f3cf`
- `onmain!?AreEqualFilenames@Jot@@YA_NPEB_W0@Z` at `0x14011f3e6`
- `onmain!?AreEqualFilenames@Jot@@YA_NPEB_W0@Z` at `0x14011f3fd`
- `onmain!?AreEqualFilenames@Jot@@YA_NPEB_W0@Z` at `0x14011f1f8`
- `onmain!?AreEqualFilenames@Jot@@YA_NPEB_W0@Z` at `0x14011f3cf`
- `onmain!?AreEqualFilenames@Jot@@YA_NPEB_W0@Z` at `0x14011f3e6`
- `onmain!?AreEqualFilenames@Jot@@YA_NPEB_W0@Z` at `0x14011f3fd`
- `onmain!??BCWzInBuffer@Jot@@QEBA?AV?$String@UWzTraits@MsoCF@@@MsoCF@@XZ` at `0x14011f6da`
- `onmain!??BCWzInBuffer@Jot@@QEBA?AV?$String@UWzTraits@MsoCF@@@MsoCF@@XZ` at `0x14011f6da`
- `onmain!?LoadStringFromTheResourceDll@Jot@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z` at `0x14011f24b`
- `onmain!?LoadStringFromTheResourceDll@Jot@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z` at `0x14011f271`
- `onmain!?LoadStringFromTheResourceDll@Jot@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z` at `0x14011f2df`
- `onmain!?LoadStringFromTheResourceDll@Jot@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z` at `0x14011f24b`
- `onmain!?LoadStringFromTheResourceDll@Jot@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z` at `0x14011f271`
- `onmain!?LoadStringFromTheResourceDll@Jot@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z` at `0x14011f2df`
- `onmain!?c_wzNotesMIPFileExtension@Jot@@3PEB_WEB` at `0x14011f3d9`
- `onmain!?SetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@AEBVCPropertyValue@2@@Z` at `0x14011f73e`
- `onmain!?SetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@AEBVCPropertyValue@2@@Z` at `0x14012044c`
- `onmain!?SetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@AEBVCPropertyValue@2@@Z` at `0x1401204a6`
- `onmain!?SetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@AEBVCPropertyValue@2@@Z` at `0x140120501`
- `onmain!?SetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@AEBVCPropertyValue@2@@Z` at `0x14011f73e`
- `onmain!?SetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@AEBVCPropertyValue@2@@Z` at `0x14012044c`
- `onmain!?SetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@AEBVCPropertyValue@2@@Z` at `0x1401204a6`
- `onmain!?SetProperty@IPropertySet@MsoCF@@QEAAXAEBUPropertyInfo@2@AEBVCPropertyValue@2@@Z` at `0x140120501`
- `onmain!?priAuthAndExistenceCheckCompleted@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B` at `0x14012014a`
- `onmain!?priProgIDStampFound@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B` at `0x140120124`
- `onmain!?priOpenNotebookEvenIfTOCMissing@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B` at `0x1401200fb`
- `onmain!?priWzLink@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B` at `0x14011f72f`
- `onmain!?priOpenInCurrentFolder@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B` at `0x140120526`
- `onmain!?priFilepath@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B` at `0x14012043d`
- `onmain!??1CProgressLock@ProgressUI@OneNote@@UEAA@XZ` at `0x14011f602`
- `onmain!??1CProgressLock@ProgressUI@OneNote@@UEAA@XZ` at `0x14011f7e6`
- `onmain!??1CProgressLock@ProgressUI@OneNote@@UEAA@XZ` at `0x14011fd9b`
- `onmain!??1CProgressLock@ProgressUI@OneNote@@UEAA@XZ` at `0x140120293`
- `onmain!??1CProgressLock@ProgressUI@OneNote@@UEAA@XZ` at `0x1401203b3`
- `onmain!??1CProgressLock@ProgressUI@OneNote@@UEAA@XZ` at `0x14011f602`
- `onmain!??1CProgressLock@ProgressUI@OneNote@@UEAA@XZ` at `0x14011f7e6`
- `onmain!??1CProgressLock@ProgressUI@OneNote@@UEAA@XZ` at `0x14011fd9b`
- `onmain!??1CProgressLock@ProgressUI@OneNote@@UEAA@XZ` at `0x140120293`
- `onmain!??1CProgressLock@ProgressUI@OneNote@@UEAA@XZ` at `0x1401203b3`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x14011f6fc`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x14011f76e`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x14012046b`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x1401204c5`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x140120562`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x14011f6fc`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x14011f76e`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x14012046b`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x1401204c5`
- `onmain!?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z` at `0x140120562`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x14011f1c9`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x14011f1c9`
- `onmain!?CreatePropertySet@MsoCF@@YAXPEAPEAUIPropertySet@1@PEAU21@@Z` at `0x14011f6b4`
- `onmain!?CreatePropertySet@MsoCF@@YAXPEAPEAUIPropertySet@1@PEAU21@@Z` at `0x140120069`
- `onmain!?CreatePropertySet@MsoCF@@YAXPEAPEAUIPropertySet@1@PEAU21@@Z` at `0x1401203ed`
- `onmain!?CreatePropertySet@MsoCF@@YAXPEAPEAUIPropertySet@1@PEAU21@@Z` at `0x14011f6b4`
- `onmain!?CreatePropertySet@MsoCF@@YAXPEAPEAUIPropertySet@1@PEAU21@@Z` at `0x140120069`
- `onmain!?CreatePropertySet@MsoCF@@YAXPEAPEAUIPropertySet@1@PEAU21@@Z` at `0x1401203ed`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x14011fb27`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x14011fb27`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x14011fbe7`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x14011fce9`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x14011ff68`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x14011ffec`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x14011fbe7`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x14011fce9`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x14011ff68`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x14011ffec`
- `MSVCP140!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x14011fb45`
- `MSVCP140!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x14011fb45`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x14011fa9c`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x14011fa9c`
- `SHLWAPI!PathFindExtensionW` at `0x14011f1ec`
- `SHLWAPI!PathFindExtensionW` at `0x14011f1ec`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x14011f95e`
- `Mso20Win32Client!__imp_?MsoDwRegGetDw@@YAKPEBU_msoreg@@@Z` at `0x14011f95e`
- `Mso20Win32Client!__imp_?MsoPathFindExtension@Path@Mso@@YAPEA_WPEB_W@Z` at `0x14011f39f`
- `Mso20Win32Client!__imp_?MsoPathFindExtension@Path@Mso@@YAPEA_WPEB_W@Z` at `0x14011f39f`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
char __fastcall Jot::CJotApp::OpenFile(
        _WORD *a1,
        const wchar_t *a2,
        char a3,
        struct MsoCF::IActionContext *a4,
        __int64 a5,
        char a6,
        char a7,
        char a8,
        char a9,
        char a10)
{
  int v10; // r14d
  struct MsoCF::IActionContext *v11; // r15
  const wchar_t *v14; // rbx
  const WCHAR *v15; // rcx
  Jot *ExtensionW; // rax
  const wchar_t *v17; // r8
  const wchar_t *v18; // rdx
  bool v19; // bl
  __int64 StringFromTheResourceDll; // rdi
  __int64 v21; // rbx
  __int64 v22; // rax
  __int64 *v23; // rax
  __int64 v24; // r12
  __int64 v25; // rax
  Jot *v26; // rbx
  const wchar_t *v27; // rdx
  LPCWSTR *v28; // rcx
  wchar_t *Extension; // rax
  Jot *v30; // rdi
  const wchar_t *v31; // rax
  const wchar_t *v32; // r8
  const wchar_t *v33; // r8
  const wchar_t *v34; // r8
  __int64 v35; // rcx
  __int64 v36; // r8
  LPCWSTR *v37; // rcx
  struct OneNote::ProgressUI::IProgress *v38; // r8
  __int64 v39; // rax
  DWORD LastError; // eax
  LPCWSTR *v41; // rdx
  const struct Ofc::CException *v42; // rax
  Jot *v43; // rcx
  LPCWSTR *v44; // rcx
  __int64 v45; // rax
  struct OneNote::ProgressUI::IProgress *v46; // r9
  struct OneNote::ProgressUI::IProgress *v47; // rax
  struct MsoCF::IPropertySet *v48; // r8
  __int64 v49; // rdi
  struct Jot::IFolderProxy **v51; // rdx
  char v52; // si
  char v53; // r15
  char v54; // r14
  Jot *v55; // rdi
  void (__fastcall ***v56)(_QWORD, GUID *, Jot **); // rcx
  bool v57; // r8
  unsigned int Dw; // r13d
  Jot *v59; // rcx
  struct MsoCF::IPropertySet *v60; // r8
  struct Jot::IFileProxy *v61; // rdx
  struct Jot::IFileProxy **v62; // r9
  bool v63; // r14
  const struct std::exception_ptr *v64; // rdx
  __int64 v65; // rax
  struct Jot::IFolderProxy *v66; // rsi
  Jot *v67; // rcx
  struct OneNote::ProgressUI::IProgress *v68; // rax
  Jot::CJotApp *v69; // rsi
  __int64 v70; // rax
  int v71; // r9d
  __int64 v72; // rax
  struct Jot::IFolderProxy *v73; // rdx
  struct OneNote::ProgressUI::IProgress *v74; // rax
  const wchar_t *v75; // rdx
  const wchar_t *v76; // rcx
  Jot *v77; // rcx
  Jot *v78; // rcx
  Jot *v79; // rcx
  __int64 v80; // rax
  _QWORD *v81; // rax
  _QWORD *v82; // rdx
  struct OneNote::ProgressUI::IProgress *v83; // rax
  bool v84; // si
  struct MsoCF::IActionContext *v85; // rcx
  struct MsoCF::IPropertySet *v86; // r8
  LPCWSTR *v87; // rdx
  int v88; // [rsp+20h] [rbp-758h]
  bool *v89; // [rsp+48h] [rbp-730h]
  char v90[8]; // [rsp+50h] [rbp-728h] BYREF
  char v91[8]; // [rsp+58h] [rbp-720h] BYREF
  char v92[8]; // [rsp+60h] [rbp-718h] BYREF
  bool v93; // [rsp+68h] [rbp-710h] BYREF
  bool v94[8]; // [rsp+70h] [rbp-708h] BYREF
  Jot *v95; // [rsp+78h] [rbp-700h] BYREF
  struct MsoCF::IActionContext *v96; // [rsp+80h] [rbp-6F8h] BYREF
  Jot *v97; // [rsp+88h] [rbp-6F0h] BYREF
  __int64 v98; // [rsp+90h] [rbp-6E8h] BYREF
  int v99; // [rsp+98h] [rbp-6E0h]
  struct Jot::IFolderProxy *v100; // [rsp+A0h] [rbp-6D8h] BYREF
  __m128i si128; // [rsp+A8h] [rbp-6D0h] BYREF
  __int128 *v102; // [rsp+B8h] [rbp-6C0h] BYREF
  Jot *v103; // [rsp+C0h] [rbp-6B8h] BYREF
  int v104; // [rsp+C8h] [rbp-6B0h] BYREF
  __int128 *v105; // [rsp+D0h] [rbp-6A8h] BYREF
  _BYTE v106[16]; // [rsp+D8h] [rbp-6A0h] BYREF
  int v107; // [rsp+E8h] [rbp-690h] BYREF
  Jot *v108; // [rsp+F0h] [rbp-688h] BYREF
  struct std::exception_ptr *v109; // [rsp+F8h] [rbp-680h] BYREF
  __int64 v110; // [rsp+100h] [rbp-678h] BYREF
  int v111; // [rsp+108h] [rbp-670h]
  Jot *v112; // [rsp+110h] [rbp-668h] BYREF
  __int64 v113; // [rsp+118h] [rbp-660h] BYREF
  int v114; // [rsp+120h] [rbp-658h] BYREF
  MsoCF::IPropertySet *v115; // [rsp+128h] [rbp-650h] BYREF
  Jot *v116; // [rsp+130h] [rbp-648h] BYREF
  Jot *v117; // [rsp+138h] [rbp-640h]
  int v118; // [rsp+140h] [rbp-638h] BYREF
  MsoCF::IPropertySet *v119; // [rsp+148h] [rbp-630h] BYREF
  struct Jot::IAsyncResult *v120; // [rsp+150h] [rbp-628h] BYREF
  __int64 v121; // [rsp+158h] [rbp-620h] BYREF
  _BYTE *v122; // [rsp+160h] [rbp-618h] BYREF
  struct OneNote::ProgressUI::IProgress *v123; // [rsp+168h] [rbp-610h] BYREF
  __int64 v124; // [rsp+170h] [rbp-608h] BYREF
  __int128 v125; // [rsp+178h] [rbp-600h] BYREF
  __int64 v126; // [rsp+188h] [rbp-5F0h] BYREF
  __int64 v127; // [rsp+190h] [rbp-5E8h] BYREF
  _BYTE v128[16]; // [rsp+198h] [rbp-5E0h] BYREF
  __int64 v129; // [rsp+1A8h] [rbp-5D0h]
  _BYTE v130[32]; // [rsp+1B0h] [rbp-5C8h] BYREF
  _BYTE v131[32]; // [rsp+1D0h] [rbp-5A8h] BYREF
  char v132[32]; // [rsp+1F0h] [rbp-588h] BYREF
  char v133[32]; // [rsp+210h] [rbp-568h] BYREF
  LPCWSTR pszPath[3]; // [rsp+230h] [rbp-548h] BYREF
  unsigned __int64 v135; // [rsp+248h] [rbp-530h]
  wchar_t *v136[4]; // [rsp+250h] [rbp-528h] BYREF
  wchar_t *v137[4]; // [rsp+270h] [rbp-508h] BYREF
  _BYTE v138[32]; // [rsp+290h] [rbp-4E8h] BYREF
  _BYTE v139[32]; // [rsp+2B0h] [rbp-4C8h] BYREF
  _BYTE v140[32]; // [rsp+2D0h] [rbp-4A8h] BYREF
  _BYTE v141[368]; // [rsp+2F0h] [rbp-488h] BYREF
  _BYTE v142[368]; // [rsp+460h] [rbp-318h] BYREF
  _BYTE v143[368]; // [rsp+5D0h] [rbp-1A8h] BYREF

  v11 = a4;
  v96 = a4;
  LOBYTE(v10) = a3;
  v107 = v10;
  v113 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a5 + 120LL))(a5);
  if ( !a1 || !*a1 )
    return 0;
  std::wstring::wstring(pszPath, a1);
  Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(
    v141,
    *((_QWORD *)Jot::CJotApp::s_pSingletonJotApp + 62),
    3288324948LL);
  v14 = (const wchar_t *)Jot::CWzInBuffer::operator wchar_t *(v141);
  v15 = (const WCHAR *)pszPath;
  if ( v135 > 7 )
    v15 = pszPath[0];
  ExtensionW = (Jot *)PathFindExtensionW(v15);
  if ( Jot::AreEqualFilenames(ExtensionW, v14, v17) )
  {
    v18 = (const wchar_t *)pszPath;
    if ( v135 > 7 )
      v18 = pszPath[0];
    v19 = Jot::CBasicUIActor::FOpenArchive(v11, v18, a2);
LABEL_197:
    Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>::~CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>(v141);
    std::wstring::~wstring(pszPath);
    return v19;
  }
  v102 = (__int128 *)v130;
  StringFromTheResourceDll = Jot::LoadStringFromTheResourceDll(v130, 3004109778LL);
  v122 = v131;
  v21 = Jot::LoadStringFromTheResourceDll(v131, 645739117);
  v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a5 + 128LL))(a5);
  v23 = (__int64 *)OneNote::ProgressUI::CreateProgressDialog(&v127, v22, v21, StringFromTheResourceDll, 0);
  v24 = *v23;
  *v23 = 0;
  v129 = v24;
  if ( v127 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v127 + 16LL))(v127);
  v25 = Jot::LoadStringFromTheResourceDll(v132, 872696638);
  OneNote::ProgressUI::CProgressLock::CProgressLock(v106, v24, v25, 16);
  v26 = 0;
  v117 = 0;
  OneNote::ProgressUI::CProgressLock::CreateChildProgress(v106, &v123, 5);
  OneNote::ProgressUI::CProgressLock::CProgressLock((OneNote::ProgressUI::CProgressLock *)v128, v123, 2u);
  OneNote::ProgressUI::CProgressLock::CreateChildProgress(v128, &v121, 1);
  Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(
    v143,
    *((_QWORD *)Jot::CJotApp::s_pSingletonJotApp + 62),
    965895237);
  v28 = pszPath;
  if ( v135 > 7 )
    v28 = (LPCWSTR *)pszPath[0];
  Extension = Mso::Path::MsoPathFindExtension((Mso::Path *)v28, v27);
  v30 = (Jot *)Extension;
  if ( Extension
    && *Extension
    && ((v31 = (const wchar_t *)Jot::CWzInBuffer::operator wchar_t const *(v143), Jot::AreEqualFilenames(v30, v31, v32))
     || Jot::AreEqualFilenames(v30, Jot::c_wzNotesMIPFileExtension, v33)
     || Jot::AreEqualFilenames(v30, Jot::c_wzTableOfContentsFileExtensionV2, v34)) )
  {
    v108 = 0;
    v35 = *((_QWORD *)Jot::CJotApp::s_pSingletonJotApp + 58);
    if ( v35 )
      v36 = *(_QWORD *)(v35 + 8);
    else
      v36 = 0;
    v37 = pszPath;
    if ( v135 > 7 )
      v37 = (LPCWSTR *)pszPath[0];
    Jot::GetFileProxyFromPath_Async_MayShowAuthUI_Exported(v37, &v108, v36, v121, 0);
    OneNote::ProgressUI::CProgressLock::CreateChildProgress(v128, &v120, 1);
    Jot::WaitToComplete_Throws(v108, v120, v38);
    v39 = (*(__int64 (__fastcall **)(Jot *))(*(_QWORD *)v108 + 96LL))(v108);
    v26 = (Jot *)v39;
    if ( v39 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 8LL))(v39);
    v117 = v26;
    if ( !v26 )
    {
      LastError = GetLastError();
      v41 = pszPath;
      if ( v135 > 7 )
        v41 = (LPCWSTR *)pszPath[0];
      v42 = (const struct Ofc::CException *)Ofc::CFileException::CFileException(v133, v41, LastError);
      Ofc::CException::Throw(v42);
    }
    if ( v120 )
      (*(void (__fastcall **)(struct Jot::IAsyncResult *))(*(_QWORD *)v120 + 16LL))(v120);
    v43 = v108;
  }
  else
  {
    v116 = 0;
    v44 = pszPath;
    if ( v135 > 7 )
      v44 = (LPCWSTR *)pszPath[0];
    LOBYTE(v88) = 0;
    Jot::GetFolderProxyFromPath_Exported(v44, &v116, 0, 0, v88);
    v43 = v116;
    if ( v116 )
    {
      v45 = (*(__int64 (__fastcall **)(Jot *))(*(_QWORD *)v116 + 24LL))(v116);
      v26 = (Jot *)v45;
      if ( v45 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 8LL))(v45);
      v117 = v26;
      v43 = v116;
    }
  }
  if ( v43 )
    (*(void (__fastcall **)(Jot *))(*(_QWORD *)v43 + 16LL))(v43);
  (*(void (__fastcall **)(Jot *))(*(_QWORD *)v26 + 72LL))(v26);
  Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>::~CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>(v143);
  if ( v121 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v121 + 16LL))(v121);
  OneNote::ProgressUI::CProgressLock::~CProgressLock((OneNote::ProgressUI::CProgressLock *)v128);
  if ( v123 )
    (*(void (__fastcall **)(struct OneNote::ProgressUI::IProgress *))(*(_QWORD *)v123 + 16LL))(v123);
  OneNote::ProgressUI::CProgressLock::CreateChildProgress(v106, &v124, 1);
  if ( *((_QWORD *)Jot::CJotApp::s_pSingletonJotApp + 54) )
  {
    Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(v142);
    if ( Jot::IsTaskLinkFile(v26, (struct Jot::IFileProxy *)v142, 0, v46) )
    {
      v47 = OneNote::ProgressUI::CProgressLock::UseProgress((OneNote::ProgressUI::CProgressLock *)v106);
      OneNote::ProgressUI::CProgressPauseLock::CProgressPauseLock((OneNote::ProgressUI::CProgressPauseLock *)&v112, v47);
      v119 = 0;
      v118 = 132173;
      MsoCF::CreatePropertySet((MsoCF *)&v119, 0, v48);
      v110 = 0;
      v111 = 0;
      v49 = *(_QWORD *)Jot::CWzInBuffer::operator MsoCF::String<MsoCF::WzTraits>(v142, &v102);
      if ( (v111 & 0x2000000) != 0 )
        MsoCF::CPropertyData::FreeAndZero_ComplexType(&v110);
      else
        v110 = 0;
      MsoCF::ProduceAtomFromString<MsoCF::String<MsoCF::WzTraits>>(&v110, v49);
      v111 = 117899322;
      MsoCF::IPropertySet::SetProperty(
        v119,
        Jot::PropertySpace_JotMain::priWzLink,
        (const struct MsoCF::CPropertyValue *)&v110);
      MsoCF::CActionPropertySet::Execute((MsoCF::CActionPropertySet *)&v118, v11);
      if ( (v111 & 0x2000000) != 0 )
        MsoCF::CPropertyData::FreeAndZero_ComplexType(&v110);
      if ( v119 )
        (*(void (__fastcall **)(MsoCF::IPropertySet *))(*(_QWORD *)v119 + 16LL))(v119);
      v119 = 0;
      OneNote::ProgressUI::CProgressPauseLock::~CProgressPauseLock((OneNote::ProgressUI::CProgressPauseLock *)&v112);
      Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>::~CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>(v142);
      if ( v124 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v124 + 16LL))(v124);
      (*(void (__fastcall **)(Jot *))(*(_QWORD *)v26 + 16LL))(v26);
      OneNote::ProgressUI::CProgressLock::~CProgressLock((OneNote::ProgressUI::CProgressLock *)v106);
      if ( v24 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>::~CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>(v141);
      std::wstring::~wstring(pszPath);
      return 1;
    }
    Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>::~CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>(v142);
  }
  if ( v124 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v124 + 16LL))(v124);
  OneNote::ProgressUI::CProgressLock::CreateChildProgress(v106, &v109, 10);
  if ( !a9 )
  {
LABEL_172:
    if ( v109 )
      (*(void (__fastcall **)(struct std::exception_ptr *))(*(_QWORD *)v109 + 16LL))(v109);
    if ( a7 )
    {
      v96 = 0;
      Jot::GetInternetCacheFolder((Jot *)&v96, v51);
      v85 = v96;
      if ( v96 )
      {
        if ( (*(unsigned __int8 (__fastcall **)(Jot *, struct MsoCF::IActionContext *))(*(_QWORD *)v26 + 248LL))(
               v26,
               v96) )
        {
          LOBYTE(v10) = 1;
        }
        v85 = v96;
      }
      if ( v85 )
        (*(void (__fastcall **)(struct MsoCF::IActionContext *))(*(_QWORD *)v85 + 16LL))(v85);
    }
    (*(void (__fastcall **)(Jot *))(*(_QWORD *)v26 + 16LL))(v26);
    OneNote::ProgressUI::CProgressLock::~CProgressLock((OneNote::ProgressUI::CProgressLock *)v106);
    if ( v24 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    v115 = 0;
    v114 = 131326;
    MsoCF::CreatePropertySet((MsoCF *)&v115, 0, v86);
    v99 = 0;
    v87 = pszPath;
    if ( v135 > 7 )
      v87 = (LPCWSTR *)pszPath[0];
    v98 = 0;
    MsoCF::ProduceAtomFromString<MsoCF::String<MsoCF::WzTraits>>(&v98, v87);
    v99 = 117899322;
    MsoCF::IPropertySet::SetProperty(
      v115,
      Jot::PropertySpace_JotMain::priFilepath,
      (const struct MsoCF::CPropertyValue *)&v98);
    if ( (v99 & 0x2000000) != 0 )
      MsoCF::CPropertyData::FreeAndZero_ComplexType(&v98);
    else
      v98 = 0;
    LOBYTE(v98) = v10;
    v99 = 2228226;
    MsoCF::IPropertySet::SetProperty(
      v115,
      Jot::PropertySpace_JotMain::priOpenReadOnly,
      (const struct MsoCF::CPropertyValue *)&v98);
    if ( (v99 & 0x2000000) != 0 )
      MsoCF::CPropertyData::FreeAndZero_ComplexType(&v98);
    else
      v98 = 0;
    LOBYTE(v98) = a6;
    v99 = 2228226;
    MsoCF::IPropertySet::SetProperty(
      v115,
      Jot::PropertySpace_JotMain::priWarnAgainstIncorrectExtension,
      (const struct MsoCF::CPropertyValue *)&v98);
    if ( a8 )
    {
      v92[0] = 1;
      (*(void (__fastcall **)(MsoCF::IPropertySet *, _QWORD, char *))(*(_QWORD *)v115 + 56LL))(
        v115,
        Jot::PropertySpace_JotMain::priOpenInCurrentFolder,
        v92);
    }
    v19 = MsoCF::CActionPropertySet::Execute((MsoCF::CActionPropertySet *)&v114, v11);
    if ( (v99 & 0x2000000) != 0 )
      MsoCF::CPropertyData::FreeAndZero_ComplexType(&v98);
    if ( v115 )
      (*(void (__fastcall **)(MsoCF::IPropertySet *))(*(_QWORD *)v115 + 16LL))(v115);
    goto LABEL_197;
  }
  v52 = (*(__int64 (__fastcall **)(Jot *))(*(_QWORD *)v26 + 176LL))(v26);
  v53 = 0;
  v95 = 0;
  v54 = 0;
  v112 = 0;
  if ( v52 )
  {
    v103 = 0;
    (**(void (__fastcall ***)(Jot *, GUID *, Jot **))v26)(v26, &GUID_4735b3bf_db6a_44c3_942e_6c16a8b935ce, &v103);
    v55 = v103;
    v112 = v103;
  }
  else
  {
    v56 = *(void (__fastcall ****)(_QWORD, GUID *, Jot **))(*(__int64 (__fastcall **)(Jot *, __int64 *))(*(_QWORD *)v26 + 232LL))(
                                                             v26,
                                                             &v126);
    v55 = 0;
    v103 = 0;
    if ( v56 )
    {
      (**v56)(v56, &GUID_4735b3bf_db6a_44c3_942e_6c16a8b935ce, &v103);
      v55 = v103;
    }
    v103 = 0;
    v112 = v55;
    if ( v126 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v126 + 16LL))(v126);
  }
  Dw = MsoDwRegGetDw((const struct _msoreg *)&vmsoridEnableOpenFolderAsNotebook);
  v93 = 0;
  if ( !*((_QWORD *)Jot::CJotApp::s_pSingletonJotApp + 54) )
    goto LABEL_166;
  v91[0] = 0;
  v97 = 0;
  Jot::GetQuickNotesSection((Jot *)&v97, 0, v57);
  v59 = v97;
  if ( v26 == v97 )
    goto LABEL_70;
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD, Jot *))(**((_QWORD **)Jot::CJotApp::s_pSingletonJotApp + 54) + 96LL))(
         *((_QWORD *)Jot::CJotApp::s_pSingletonJotApp + 54),
         v26) )
  {
    if ( v55 )
      (*(void (__fastcall **)(Jot *))(*(_QWORD *)v55 + 8LL))(v55);
    v95 = v55;
    if ( v97 )
      (*(void (__fastcall **)(Jot *))(*(_QWORD *)v97 + 16LL))(v97);
    goto LABEL_145;
  }
  if ( !v52
    && (*(unsigned __int8 (__fastcall **)(Jot *, const wchar_t *))(*(_QWORD *)v26 + 280LL))(v26, L".one")
    && Jot::IsFileInAnyKnownTempFolder(v26, v61) )
  {
    v59 = v97;
LABEL_70:
    if ( v59 )
      (*(void (__fastcall **)(Jot *))(*(_QWORD *)v59 + 16LL))(v59);
    goto LABEL_166;
  }
  v100 = 0;
  si128 = 0;
  __ExceptionPtrCreate(&si128);
  LOBYTE(v62) = 1;
  v63 = Jot::FGetNotebookRoot(
          v26,
          (struct Jot::IFileProxy *)&v95,
          &v100,
          v62,
          v113,
          (HWND)&si128,
          v109,
          (struct OneNote::ProgressUI::IProgress *)v91,
          &v93,
          v89);
  if ( Jot::IsServerAuthenticationError((Jot *)&si128, v64) )
  {
    v125 = 0;
    __ExceptionPtrCopy(&v125, &si128);
    v102 = &v125;
    __ExceptionPtrRethrow(&v125);
  }
  v90[0] = 1;
  if ( !v63 )
  {
    if ( v52 )
    {
      if ( v91[0] && !Dw && !a10 )
      {
        v68 = OneNote::ProgressUI::CProgressLock::UseProgress((OneNote::ProgressUI::CProgressLock *)v106);
        OneNote::ProgressUI::CProgressPauseLock::CProgressPauseLock(
          (OneNote::ProgressUI::CProgressPauseLock *)&v107,
          v68);
        v69 = Jot::CJotApp::s_pSingletonJotApp;
        v70 = (*(__int64 (__fastcall **)(Jot *, _BYTE *, _QWORD))(*(_QWORD *)v26 + 112LL))(v26, v139, 0);
        if ( *(_QWORD *)(v70 + 24) > 7u )
          v70 = *(_QWORD *)v70;
        Jot::CJotApp::ShowAlertIdsWz1(v69, -1122079099, (const wchar_t *)v70, v71);
        std::wstring::~wstring(v139);
        OneNote::ProgressUI::CProgressPauseLock::~CProgressPauseLock((OneNote::ProgressUI::CProgressPauseLock *)&v107);
        __ExceptionPtrDestroy(&si128);
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        if ( v100 )
          (*(void (__fastcall **)(struct Jot::IFolderProxy *))(*(_QWORD *)v100 + 16LL))(v100);
        if ( v97 )
          (*(void (__fastcall **)(Jot *))(*(_QWORD *)v97 + 16LL))(v97);
        if ( v55 )
          (*(void (__fastcall **)(Jot *))(*(_QWORD *)v55 + 16LL))(v55);
        if ( v95 )
          (*(void (__fastcall **)(Jot *))(*(_QWORD *)v95 + 16LL))(v95);
        if ( v109 )
          (*(void (__fastcall **)(struct std::exception_ptr *))(*(_QWORD *)v109 + 16LL))(v109);
        (*(void (__fastcall **)(Jot *))(*(_QWORD *)v26 + 16LL))(v26);
        OneNote::ProgressUI::CProgressLock::~CProgressLock((OneNote::ProgressUI::CProgressLock *)v106);
        if ( v24 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
        Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>::~CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>(v141);
        std::wstring::~wstring(pszPath);
        return 0;
      }
      if ( v55 )
        (*(void (__fastcall **)(Jot *))(*(_QWORD *)v55 + 8LL))(v55);
      v67 = v95;
      v95 = v55;
      goto LABEL_89;
    }
    if ( (*(unsigned __int8 (__fastcall **)(Jot *, const wchar_t *))(*(_QWORD *)v26 + 280LL))(v26, L".onetoc")
      || (*(unsigned __int8 (__fastcall **)(Jot *, const wchar_t *))(*(_QWORD *)v26 + 280LL))(v26, L".onetoc2") )
    {
      if ( v55 )
        (*(void (__fastcall **)(Jot *))(*(_QWORD *)v55 + 8LL))(v55);
      v79 = v95;
      v95 = v55;
      if ( v79 )
        (*(void (__fastcall **)(Jot *))(*(_QWORD *)v79 + 16LL))(v79);
      v53 = 1;
      __ExceptionPtrDestroy(&si128);
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      if ( v100 )
        (*(void (__fastcall **)(struct Jot::IFolderProxy *))(*(_QWORD *)v100 + 16LL))(v100);
      v78 = v97;
      if ( !v97 )
        goto LABEL_144;
    }
    else
    {
      v72 = (*(__int64 (__fastcall **)(Jot *))(*(_QWORD *)v55 + 24LL))(v55);
      (*(void (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v72 + 144LL))(v72, v137);
      (*(void (__fastcall **)(Jot *, wchar_t **))(*(_QWORD *)v26 + 144LL))(v26, v136);
      if ( (!v91[0] || Dw) && !Jot::FIsRestrictedLocation(v55, v73) )
      {
        v74 = OneNote::ProgressUI::CProgressLock::UseProgress((OneNote::ProgressUI::CProgressLock *)v106);
        OneNote::ProgressUI::CProgressPauseLock::CProgressPauseLock(
          (OneNote::ProgressUI::CProgressPauseLock *)&v122,
          v74);
        v75 = (const wchar_t *)v136;
        if ( v136[3] > (wchar_t *)7 )
          v75 = v136[0];
        v76 = (const wchar_t *)v137;
        if ( v137[3] > (wchar_t *)7 )
          v76 = v137[0];
        if ( Jot::CBasicUIActor::FOpenFolderPrompt(v76, v75) )
        {
          (*(void (__fastcall **)(Jot *))(*(_QWORD *)v55 + 8LL))(v55);
          v77 = v95;
          v95 = v55;
          if ( v77 )
            (*(void (__fastcall **)(Jot *))(*(_QWORD *)v77 + 16LL))(v77);
          v53 = 1;
        }
        OneNote::ProgressUI::CProgressPauseLock::~CProgressPauseLock((OneNote::ProgressUI::CProgressPauseLock *)&v122);
      }
      std::wstring::~wstring(v136);
      std::wstring::~wstring(v137);
      __ExceptionPtrDestroy(&si128);
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      if ( v100 )
        (*(void (__fastcall **)(struct Jot::IFolderProxy *))(*(_QWORD *)v100 + 16LL))(v100);
      v78 = v97;
      if ( !v97 )
      {
LABEL_143:
        if ( !v53 )
        {
LABEL_166:
          v11 = v96;
LABEL_167:
          if ( v55 )
            (*(void (__fastcall **)(Jot *))(*(_QWORD *)v55 + 16LL))(v55);
          if ( v95 )
            (*(void (__fastcall **)(Jot *))(*(_QWORD *)v95 + 16LL))(v95);
          LOBYTE(v10) = v107;
          goto LABEL_172;
        }
        goto LABEL_144;
      }
    }
    (*(void (__fastcall **)(Jot *))(*(_QWORD *)v78 + 16LL))(v78);
    goto LABEL_143;
  }
  if ( v100 && v100 != v26 )
  {
    v65 = (*(__int64 (__fastcall **)(struct Jot::IFolderProxy *, _BYTE *, _QWORD))(*(_QWORD *)v100 + 112LL))(
            v100,
            v138,
            0);
    std::wstring::operator=(pszPath, v65);
    std::wstring::~wstring(v138);
    v66 = v100;
    if ( v100 )
      (*(void (__fastcall **)(struct Jot::IFolderProxy *))(*(_QWORD *)v100 + 8LL))(v100);
    v67 = v26;
    v26 = v66;
    v117 = v66;
LABEL_89:
    if ( v67 )
      (*(void (__fastcall **)(Jot *))(*(_QWORD *)v67 + 16LL))(v67);
  }
  __ExceptionPtrDestroy(&si128);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  if ( v100 )
    (*(void (__fastcall **)(struct Jot::IFolderProxy *))(*(_QWORD *)v100 + 16LL))(v100);
  if ( v97 )
    (*(void (__fastcall **)(Jot *))(*(_QWORD *)v97 + 16LL))(v97);
LABEL_144:
  v54 = v90[0];
LABEL_145:
  v105 = 0;
  v104 = 132051;
  MsoCF::CreatePropertySet((MsoCF *)&v105, 0, v60);
  v80 = (*(__int64 (__fastcall **)(Jot *))(*(_QWORD *)v95 + 24LL))(v95);
  v81 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *, _QWORD))(*(_QWORD *)v80 + 112LL))(v80, v140, 0);
  v82 = v81;
  if ( v81[3] > 7u )
    v82 = (_QWORD *)*v81;
  v102 = v105;
  MsoCF::IPropertySet::CEntry<Jot::PropertySpace_JotMain::prtidFilepath,MsoCF::CIPtr<MsoCF::IStringInAtom<MsoCF::String<MsoCF::WzTraits>>,MsoCF::IStringInAtom<MsoCF::String<MsoCF::WzTraits>>>>::operator=(
    &v102,
    v82);
  std::wstring::~wstring(v140);
  if ( a10 || Dw )
  {
    v90[0] = 1;
    (*(void (__fastcall **)(__int128 *, _QWORD, char *))(*(_QWORD *)v105 + 56LL))(
      v105,
      Jot::PropertySpace_JotMain::priOpenNotebookEvenIfTOCMissing,
      v90);
  }
  v94[0] = v93;
  (*(void (__fastcall **)(__int128 *, _QWORD, bool *))(*(_QWORD *)v105 + 56LL))(
    v105,
    Jot::PropertySpace_JotMain::priProgIDStampFound,
    v94);
  v92[0] = v54;
  (*(void (__fastcall **)(__int128 *, _QWORD, char *))(*(_QWORD *)v105 + 56LL))(
    v105,
    Jot::PropertySpace_JotMain::priAuthAndExistenceCheckCompleted,
    v92);
  v83 = OneNote::ProgressUI::CProgressLock::UseProgress((OneNote::ProgressUI::CProgressLock *)v106);
  OneNote::ProgressUI::CProgressPauseLock::CProgressPauseLock((OneNote::ProgressUI::CProgressPauseLock *)&v113, v83);
  v11 = v96;
  v84 = MsoCF::CActionPropertySet::Execute((MsoCF::CActionPropertySet *)&v104, v96);
  if ( !(*(unsigned __int8 (__fastcall **)(Jot *))(*(_QWORD *)v26 + 176LL))(v26)
    && (*(unsigned __int8 (__fastcall **)(Jot *, const wchar_t *))(*(_QWORD *)v26 + 280LL))(v26, L".one") )
  {
    OneNote::ProgressUI::CProgressPauseLock::~CProgressPauseLock((OneNote::ProgressUI::CProgressPauseLock *)&v113);
    if ( v105 )
      (*(void (__fastcall **)(__int128 *))(*(_QWORD *)v105 + 16LL))(v105);
    v105 = 0;
    goto LABEL_167;
  }
  OneNote::ProgressUI::CProgressPauseLock::~CProgressPauseLock((OneNote::ProgressUI::CProgressPauseLock *)&v113);
  if ( v105 )
    (*(void (__fastcall **)(__int128 *))(*(_QWORD *)v105 + 16LL))(v105);
  v105 = 0;
  if ( v55 )
    (*(void (__fastcall **)(Jot *))(*(_QWORD *)v55 + 16LL))(v55);
  if ( v95 )
    (*(void (__fastcall **)(Jot *))(*(_QWORD *)v95 + 16LL))(v95);
  if ( v109 )
    (*(void (__fastcall **)(struct std::exception_ptr *))(*(_QWORD *)v109 + 16LL))(v109);
  (*(void (__fastcall **)(Jot *))(*(_QWORD *)v26 + 16LL))(v26);
  OneNote::ProgressUI::CProgressLock::~CProgressLock((OneNote::ProgressUI::CProgressLock *)v106);
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>::~CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>(v141);
  std::wstring::~wstring(pszPath);
  return v84;
}

```

## disassembly

```asm
0x14011f110  mov     [rsp+arg_0], rbx
0x14011f115  mov     [rsp+arg_8], rsi
0x14011f11a  push    rdi
0x14011f11b  push    r12
0x14011f11d  push    r13
0x14011f11f  push    r14
0x14011f121  push    r15
0x14011f123  sub     rsp, 750h
0x14011f12a  mov     rax, cs:__security_cookie
0x14011f131  xor     rax, rsp
0x14011f134  mov     [rsp+778h+var_38], rax
0x14011f13c  mov     r15, r9
0x14011f13f  mov     [rsp+778h+var_6F8], r9
0x14011f147  mov     r14b, r8b
0x14011f14a  mov     [rsp+778h+var_690], r14d
0x14011f152  mov     rdi, rdx
0x14011f155  mov     rbx, rcx
0x14011f158  mov     rsi, [rsp+778h+arg_20]
0x14011f160  mov     rax, [rsi]
0x14011f163  mov     rcx, rsi
0x14011f166  mov     rax, [rax+78h]
0x14011f16a  call    cs:__guard_dispatch_icall_fptr
0x14011f170  mov     [rsp+778h+var_660], rax
0x14011f178  xor     r13d, r13d
0x14011f17b  test    rbx, rbx
0x14011f17e  jz      loc_1401205BC
0x14011f184  cmp     [rbx], r13w
0x14011f188  jz      loc_1401205BC
0x14011f18e  mov     rdx, rbx
0x14011f191  lea     rcx, [rsp+778h+pszPath]
0x14011f199  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14011f19e  nop
0x14011f19f  mov     r8d, 0C3FFDB54h
0x14011f1a5  mov     rdx, cs:?s_pSingletonJotApp@CJotApp@Jot@@0PEAV12@EA; Jot::CJotApp * Jot::CJotApp::s_pSingletonJotApp
0x14011f1ac  mov     rdx, [rdx+1F0h]
0x14011f1b3  lea     rcx, [rsp+778h+var_488]
0x14011f1bb  call    ??0?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0IB@@2@@MsoCF@@$0IA@@Jot@@QEAA@PEAUHINSTANCE__@@I@Z; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(HINSTANCE__ *,uint)
0x14011f1c0  nop
0x14011f1c1  lea     rcx, [rsp+778h+var_488]
0x14011f1c9  call    cs:__imp_??BCWzInBuffer@Jot@@QEAAPEA_WXZ; Jot::CWzInBuffer::operator wchar_t *(void)
0x14011f1cf  mov     rbx, rax
0x14011f1d2  lea     rcx, [rsp+778h+pszPath]
0x14011f1da  cmp     [rsp+778h+var_530], 7
0x14011f1e3  cmova   rcx, [rsp+778h+pszPath]; pszPath
0x14011f1ec  call    cs:__imp_PathFindExtensionW
0x14011f1f2  mov     rdx, rbx
0x14011f1f5  mov     rcx, rax
0x14011f1f8  call    cs:__imp_?AreEqualFilenames@Jot@@YA_NPEB_W0@Z; Jot::AreEqualFilenames(wchar_t const *,wchar_t const *)
0x14011f1fe  test    al, al
0x14011f200  jz      short loc_14011F22E
0x14011f202  lea     rdx, [rsp+778h+pszPath]
0x14011f20a  cmp     [rsp+778h+var_530], 7
0x14011f213  cmova   rdx, [rsp+778h+pszPath]; wchar_t *
0x14011f21c  mov     r8, rdi; wchar_t *
0x14011f21f  mov     rcx, r15; struct MsoCF::IActionContext *
0x14011f222  call    ?FOpenArchive@CBasicUIActor@Jot@@SA_NPEAUIActionContext@MsoCF@@PEB_W1@Z; Jot::CBasicUIActor::FOpenArchive(MsoCF::IActionContext *,wchar_t const *,wchar_t const *)
0x14011f227  mov     bl, al
0x14011f229  jmp     loc_140120584
0x14011f22e  lea     rax, [rsp+778h+var_5C8]
0x14011f236  mov     [rsp+778h+var_6C0], rax
0x14011f23e  mov     edx, 0B30F13D2h
0x14011f243  lea     rcx, [rsp+778h+var_5C8]
0x14011f24b  call    cs:__imp_?LoadStringFromTheResourceDll@Jot@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z; Jot::LoadStringFromTheResourceDll(uint)
0x14011f251  mov     rdi, rax
0x14011f254  lea     rax, [rsp+778h+var_5A8]
0x14011f25c  mov     [rsp+778h+var_618], rax
0x14011f264  mov     edx, 267D326Dh
0x14011f269  lea     rcx, [rsp+778h+var_5A8]
0x14011f271  call    cs:__imp_?LoadStringFromTheResourceDll@Jot@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z; Jot::LoadStringFromTheResourceDll(uint)
0x14011f277  mov     rbx, rax
0x14011f27a  mov     rdx, [rsi]
0x14011f27d  mov     rcx, rsi
0x14011f280  mov     rax, [rdx+80h]
0x14011f287  call    cs:__guard_dispatch_icall_fptr
0x14011f28d  nop
0x14011f28e  mov     byte ptr [rsp+778h+var_758], r13b
0x14011f293  mov     r9, rdi
0x14011f296  mov     r8, rbx
0x14011f299  mov     rdx, rax
0x14011f29c  lea     rcx, [rsp+778h+var_5E8]
0x14011f2a4  call    cs:__imp_?CreateProgressDialog@ProgressUI@OneNote@@YA?AV?$CIRef@UIProgress@ProgressUI@OneNote@@@MsoCF@@PEBVCWindow@4@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1_N@Z; OneNote::ProgressUI::CreateProgressDialog(MsoCF::CWindow const *,std::wstring,std::wstring,bool)
0x14011f2aa  mov     r12, [rax]
0x14011f2ad  mov     [rax], r13
0x14011f2b0  mov     [rsp+778h+var_5D0], r12
0x14011f2b8  mov     rcx, [rsp+778h+var_5E8]
0x14011f2c0  test    rcx, rcx
0x14011f2c3  jz      short loc_14011F2D2
0x14011f2c5  mov     rax, [rcx]
0x14011f2c8  mov     rax, [rax+10h]
0x14011f2cc  call    cs:__guard_dispatch_icall_fptr
0x14011f2d2  mov     edx, 34044B3Eh
0x14011f2d7  lea     rcx, [rsp+778h+var_588]
0x14011f2df  call    cs:__imp_?LoadStringFromTheResourceDll@Jot@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z; Jot::LoadStringFromTheResourceDll(uint)
0x14011f2e5  mov     r9d, 10h
0x14011f2eb  mov     r8, rax
0x14011f2ee  mov     rdx, r12
0x14011f2f1  lea     rcx, [rsp+778h+var_6A0]
0x14011f2f9  call    cs:__imp_??0CProgressLock@ProgressUI@OneNote@@QEAA@PEAUIProgress@12@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z; OneNote::ProgressUI::CProgressLock::CProgressLock(OneNote::ProgressUI::IProgress *,std::wstring,uint)
0x14011f2ff  nop
0x14011f300  mov     rbx, r13
0x14011f303  mov     [rsp+778h+var_640], rbx
0x14011f30b  mov     r8d, 5
0x14011f311  lea     rdx, [rsp+778h+var_610]
0x14011f319  lea     rcx, [rsp+778h+var_6A0]
0x14011f321  call    cs:__imp_?CreateChildProgress@CProgressLock@ProgressUI@OneNote@@UEAA?AV?$CIPtr@UIProgress@ProgressUI@OneNote@@U123@@MsoCF@@I@Z; OneNote::ProgressUI::CProgressLock::CreateChildProgress(uint)
0x14011f327  mov     r8d, 2
0x14011f32d  mov     rdx, [rsp+778h+var_610]
0x14011f335  lea     rcx, [rsp+778h+var_5E0]
0x14011f33d  call    cs:__imp_??0CProgressLock@ProgressUI@OneNote@@QEAA@PEAUIProgress@12@I@Z; OneNote::ProgressUI::CProgressLock::CProgressLock(OneNote::ProgressUI::IProgress *,uint)
0x14011f343  mov     esi, 1
0x14011f348  mov     r8d, esi
0x14011f34b  lea     rdx, [rsp+778h+var_620]
0x14011f353  lea     rcx, [rsp+778h+var_5E0]
0x14011f35b  call    cs:__imp_?CreateChildProgress@CProgressLock@ProgressUI@OneNote@@UEAA?AV?$CIPtr@UIProgress@ProgressUI@OneNote@@U123@@MsoCF@@I@Z; OneNote::ProgressUI::CProgressLock::CreateChildProgress(uint)
0x14011f361  mov     r8d, 39926445h
0x14011f367  mov     rdx, cs:?s_pSingletonJotApp@CJotApp@Jot@@0PEAV12@EA; Jot::CJotApp * Jot::CJotApp::s_pSingletonJotApp
0x14011f36e  mov     rdx, [rdx+1F0h]
0x14011f375  lea     rcx, [rsp+778h+var_1A8]
0x14011f37d  nop     dword ptr [rax]
0x14011f380  call    ??0?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0IB@@2@@MsoCF@@$0IA@@Jot@@QEAA@PEAUHINSTANCE__@@I@Z; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(HINSTANCE__ *,uint)
0x14011f385  lea     rcx, [rsp+778h+pszPath]
0x14011f38d  cmp     [rsp+778h+var_530], 7
0x14011f396  cmova   rcx, [rsp+778h+pszPath]
0x14011f39f  call    cs:__imp_?MsoPathFindExtension@Path@Mso@@YAPEA_WPEB_W@Z; Mso::Path::MsoPathFindExtension(wchar_t const *)
0x14011f3a5  mov     rdi, rax
0x14011f3a8  test    rax, rax
0x14011f3ab  jz      loc_14011F532
0x14011f3b1  cmp     [rax], r13w
0x14011f3b5  jz      loc_14011F532
0x14011f3bb  lea     rcx, [rsp+778h+var_1A8]
0x14011f3c3  call    cs:__imp_??BCWzInBuffer@Jot@@QEBAPEB_WXZ; Jot::CWzInBuffer::operator wchar_t const *(void)
0x14011f3c9  mov     rdx, rax
0x14011f3cc  mov     rcx, rdi
0x14011f3cf  call    cs:__imp_?AreEqualFilenames@Jot@@YA_NPEB_W0@Z; Jot::AreEqualFilenames(wchar_t const *,wchar_t const *)
0x14011f3d5  test    al, al
0x14011f3d7  jnz     short loc_14011F40B
0x14011f3d9  mov     rdx, cs:__imp_?c_wzNotesMIPFileExtension@Jot@@3PEB_WEB; wchar_t const * const Jot::c_wzNotesMIPFileExtension
0x14011f3e0  mov     rdx, [rdx]
0x14011f3e3  mov     rcx, rdi
0x14011f3e6  call    cs:__imp_?AreEqualFilenames@Jot@@YA_NPEB_W0@Z; Jot::AreEqualFilenames(wchar_t const *,wchar_t const *)
0x14011f3ec  test    al, al
0x14011f3ee  jnz     short loc_14011F40B
0x14011f3f0  mov     rdx, cs:__imp_?c_wzTableOfContentsFileExtensionV2@Jot@@3PEB_WEB; wchar_t const * const Jot::c_wzTableOfContentsFileExtensionV2
0x14011f3f7  mov     rdx, [rdx]
0x14011f3fa  mov     rcx, rdi
0x14011f3fd  call    cs:__imp_?AreEqualFilenames@Jot@@YA_NPEB_W0@Z; Jot::AreEqualFilenames(wchar_t const *,wchar_t const *)
0x14011f403  test    al, al
0x14011f405  jz      loc_14011F532
0x14011f40b  mov     [rsp+778h+var_688], r13
0x14011f413  mov     rax, cs:?s_pSingletonJotApp@CJotApp@Jot@@0PEAV12@EA; Jot::CJotApp * Jot::CJotApp::s_pSingletonJotApp
0x14011f41a  mov     rcx, [rax+1D0h]
0x14011f421  test    rcx, rcx
0x14011f424  jz      short loc_14011F42C
0x14011f426  mov     r8, [rcx+8]
0x14011f42a  jmp     short loc_14011F42F
0x14011f42c  mov     r8, r13
0x14011f42f  lea     rcx, [rsp+778h+pszPath]
0x14011f437  cmp     [rsp+778h+var_530], 7
0x14011f440  cmova   rcx, [rsp+778h+pszPath]
0x14011f449  mov     dword ptr [rsp+778h+var_758], r13d
0x14011f44e  mov     r9, [rsp+778h+var_620]
0x14011f456  lea     rdx, [rsp+778h+var_688]
0x14011f45e  call    cs:__imp_?GetFileProxyFromPath_Async_MayShowAuthUI_Exported@Jot@@YAXV?$String@UWzTraits@MsoCF@@@MsoCF@@PEAPEAUIAsyncResult_IFileProxy@1@PEAUHWND__@@PEAUIProgress@ProgressUI@OneNote@@H@Z; Jot::GetFileProxyFromPath_Async_MayShowAuthUI_Exported(MsoCF::String<MsoCF::WzTraits>,Jot::IAsyncResult_IFileProxy * *,HWND__ *,OneNote::ProgressUI::IProgress *,int)
0x14011f464  mov     r8d, esi
0x14011f467  lea     rdx, [rsp+778h+var_628]
0x14011f46f  lea     rcx, [rsp+778h+var_5E0]
0x14011f477  call    cs:__imp_?CreateChildProgress@CProgressLock@ProgressUI@OneNote@@UEAA?AV?$CIPtr@UIProgress@ProgressUI@OneNote@@U123@@MsoCF@@I@Z; OneNote::ProgressUI::CProgressLock::CreateChildProgress(uint)
0x14011f47d  nop
0x14011f47e  mov     rdx, [rsp+778h+var_628]
0x14011f486  mov     rcx, [rsp+778h+var_688]
0x14011f48e  call    cs:__imp_?WaitToComplete_Throws@Jot@@YAXPEAUIAsyncResult@1@PEAUIProgress@ProgressUI@OneNote@@@Z; Jot::WaitToComplete_Throws(Jot::IAsyncResult *,OneNote::ProgressUI::IProgress *)
0x14011f494  mov     rcx, [rsp+778h+var_688]
0x14011f49c  mov     rax, [rcx]
0x14011f49f  mov     rax, [rax+60h]
0x14011f4a3  call    cs:__guard_dispatch_icall_fptr
0x14011f4a9  mov     rbx, rax
0x14011f4ac  test    rax, rax
0x14011f4af  jz      short loc_14011F4C1
0x14011f4b1  mov     rax, [rax]
0x14011f4b4  mov     rcx, rbx
0x14011f4b7  mov     rax, [rax+8]
0x14011f4bb  call    cs:__guard_dispatch_icall_fptr
0x14011f4c1  mov     [rsp+778h+var_640], rbx
0x14011f4c9  test    rbx, rbx
0x14011f4cc  jnz     short loc_14011F50D
0x14011f4ce  call    cs:__imp_GetLastError
0x14011f4d4  lea     rdx, [rsp+778h+pszPath]
0x14011f4dc  cmp     [rsp+778h+var_530], 7
0x14011f4e5  cmova   rdx, [rsp+778h+pszPath]
0x14011f4ee  mov     r8d, eax
0x14011f4f1  lea     rcx, [rsp+778h+var_568]
0x14011f4f9  call    ??0CFileException@Ofc@@AEAA@PEB_WIKW4ExcSeverityLevel@1@@Z; Ofc::CFileException::CFileException(wchar_t const *,uint,ulong,Ofc::ExcSeverityLevel)
0x14011f4fe  nop
0x14011f4ff  nop
0x14011f500  mov     rcx, rax; struct Ofc::CException *
0x14011f503  call    ?Throw@CException@Ofc@@KAXAEBV12@@Z; Ofc::CException::Throw(Ofc::CException const &)
0x14011f508  nop
0x14011f509  jmp     short loc_14011F50C
0x14011f50c  nop
0x14011f50d  mov     rcx, [rsp+778h+var_628]
0x14011f515  test    rcx, rcx
0x14011f518  jz      short loc_14011F528
0x14011f51a  mov     rax, [rcx]
0x14011f51d  mov     rax, [rax+10h]
0x14011f521  call    cs:__guard_dispatch_icall_fptr
0x14011f527  nop
0x14011f528  mov     rcx, [rsp+778h+var_688]
0x14011f530  jmp     short loc_14011F5AF
0x14011f532  mov     [rsp+778h+var_648], r13
0x14011f53a  lea     rcx, [rsp+778h+pszPath]
0x14011f542  cmp     [rsp+778h+var_530], 7
0x14011f54b  cmova   rcx, [rsp+778h+pszPath]
0x14011f554  mov     byte ptr [rsp+778h+var_758], r13b
0x14011f559  xor     r9d, r9d
0x14011f55c  xor     r8d, r8d
0x14011f55f  lea     rdx, [rsp+778h+var_648]
0x14011f567  call    cs:__imp_?GetFolderProxyFromPath_Exported@Jot@@YAXV?$String@UWzTraits@MsoCF@@@MsoCF@@PEAPEAUIFolderProxy@1@_NPEA_N2@Z; Jot::GetFolderProxyFromPath_Exported(MsoCF::String<MsoCF::WzTraits>,Jot::IFolderProxy * *,bool,bool *,bool)
0x14011f56d  mov     rcx, [rsp+778h+var_648]
0x14011f575  test    rcx, rcx
0x14011f578  jz      short loc_14011F5AF
0x14011f57a  mov     rax, [rcx]
0x14011f57d  mov     rax, [rax+18h]
0x14011f581  call    cs:__guard_dispatch_icall_fptr
0x14011f587  mov     rbx, rax
0x14011f58a  test    rax, rax
0x14011f58d  jz      short loc_14011F59F
0x14011f58f  mov     rax, [rax]
0x14011f592  mov     rcx, rbx
0x14011f595  mov     rax, [rax+8]
0x14011f599  call    cs:__guard_dispatch_icall_fptr
0x14011f59f  mov     [rsp+778h+var_640], rbx
0x14011f5a7  mov     rcx, [rsp+778h+var_648]
0x14011f5af  test    rcx, rcx
0x14011f5b2  jz      short loc_14011F5C1
0x14011f5b4  mov     rax, [rcx]
0x14011f5b7  mov     rax, [rax+10h]
0x14011f5bb  call    cs:__guard_dispatch_icall_fptr
0x14011f5c1  mov     rax, [rbx]
0x14011f5c4  mov     rcx, rbx
0x14011f5c7  mov     rax, [rax+48h]
0x14011f5cb  call    cs:__guard_dispatch_icall_fptr
0x14011f5d1  nop
0x14011f5d2  lea     rcx, [rsp+778h+var_1A8]
0x14011f5da  call    ??1?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0ICF@@2@@MsoCF@@$0ICE@@Jot@@QEAA@XZ; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>::~CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>(void)
0x14011f5df  mov     rcx, [rsp+778h+var_620]
0x14011f5e7  test    rcx, rcx
0x14011f5ea  jz      short loc_14011F5FA
0x14011f5ec  mov     rax, [rcx]
0x14011f5ef  mov     rax, [rax+10h]
0x14011f5f3  call    cs:__guard_dispatch_icall_fptr
0x14011f5f9  nop
0x14011f5fa  lea     rcx, [rsp+778h+var_5E0]
0x14011f602  call    cs:__imp_??1CProgressLock@ProgressUI@OneNote@@UEAA@XZ; OneNote::ProgressUI::CProgressLock::~CProgressLock(void)
0x14011f608  mov     rcx, [rsp+778h+var_610]
0x14011f610  test    rcx, rcx
0x14011f613  jz      short loc_14011F622
0x14011f615  mov     rax, [rcx]
0x14011f618  mov     rax, [rax+10h]
0x14011f61c  call    cs:__guard_dispatch_icall_fptr
0x14011f622  mov     r8d, esi
0x14011f625  lea     rdx, [rsp+778h+var_608]
0x14011f62d  lea     rcx, [rsp+778h+var_6A0]
0x14011f635  call    cs:__imp_?CreateChildProgress@CProgressLock@ProgressUI@OneNote@@UEAA?AV?$CIPtr@UIProgress@ProgressUI@OneNote@@U123@@MsoCF@@I@Z; OneNote::ProgressUI::CProgressLock::CreateChildProgress(uint)
0x14011f63b  mov     rax, cs:?s_pSingletonJotApp@CJotApp@Jot@@0PEAV12@EA; Jot::CJotApp * Jot::CJotApp::s_pSingletonJotApp
0x14011f642  cmp     [rax+1B0h], r13
0x14011f649  jz      loc_14011F836
0x14011f64f  lea     rcx, [rsp+778h+var_318]
0x14011f657  call    ??0?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0IB@@2@@MsoCF@@$0IA@@Jot@@QEAA@XZ; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(void)
0x14011f65c  xor     r8d, r8d
0x14011f65f  lea     rdx, [rsp+778h+var_318]
0x14011f667  mov     rcx, rbx
0x14011f66a  call    cs:__imp_?IsTaskLinkFile@Jot@@YA_NPEAUIFileProxy@1@AEAVCWzInBuffer@1@PEAUIProgress@ProgressUI@OneNote@@@Z; Jot::IsTaskLinkFile(Jot::IFileProxy *,Jot::CWzInBuffer &,OneNote::ProgressUI::IProgress *)
0x14011f670  test    al, al
0x14011f672  jz      loc_14011F828
0x14011f678  lea     rcx, [rsp+778h+var_6A0]
0x14011f680  call    cs:__imp_?UseProgress@CProgressLock@ProgressUI@OneNote@@UEBAPEAUIProgress@23@XZ; OneNote::ProgressUI::CProgressLock::UseProgress(void)
0x14011f686  mov     rdx, rax; struct OneNote::ProgressUI::IProgress *
0x14011f689  lea     rcx, [rsp+778h+var_668]; this
0x14011f691  call    ??0CProgressPauseLock@ProgressUI@OneNote@@QEAA@PEAUIProgress@12@@Z; OneNote::ProgressUI::CProgressPauseLock::CProgressPauseLock(OneNote::ProgressUI::IProgress *)
0x14011f696  nop
0x14011f697  mov     [rsp+778h+var_630], r13
0x14011f69f  mov     [rsp+778h+var_638], 2044Dh
0x14011f6aa  xor     edx, edx
0x14011f6ac  lea     rcx, [rsp+778h+var_630]
0x14011f6b4  call    cs:__imp_?CreatePropertySet@MsoCF@@YAXPEAPEAUIPropertySet@1@PEAU21@@Z; MsoCF::CreatePropertySet(MsoCF::IPropertySet * *,MsoCF::IPropertySet *)
0x14011f6ba  mov     [rsp+778h+var_678], r13
0x14011f6c2  mov     [rsp+778h+var_670], r13d
0x14011f6ca  lea     rdx, [rsp+778h+var_6C0]
0x14011f6d2  lea     rcx, [rsp+778h+var_318]
0x14011f6da  call    cs:__imp_??BCWzInBuffer@Jot@@QEBA?AV?$String@UWzTraits@MsoCF@@@MsoCF@@XZ; Jot::CWzInBuffer::operator MsoCF::String<MsoCF::WzTraits>(void)
0x14011f6e0  mov     rdi, [rax]
0x14011f6e3  mov     edx, [rsp+778h+var_670]
0x14011f6ea  mov     eax, edx
0x14011f6ec  shr     eax, 19h
0x14011f6ef  test    sil, al
0x14011f6f2  jz      short loc_14011F704
0x14011f6f4  lea     rcx, [rsp+778h+var_678]
0x14011f6fc  call    cs:__imp_?FreeAndZero_ComplexType@CPropertyData@MsoCF@@SAXPEAXW4PropertyType@2@@Z; MsoCF::CPropertyData::FreeAndZero_ComplexType(void *,MsoCF::PropertyType)
0x14011f702  jmp     short loc_14011F70C
0x14011f704  mov     [rsp+778h+var_678], r13
  ... truncated ...
```
