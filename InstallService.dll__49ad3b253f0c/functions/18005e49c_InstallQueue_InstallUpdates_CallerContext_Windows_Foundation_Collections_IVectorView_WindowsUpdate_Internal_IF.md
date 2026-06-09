# InstallQueue::_InstallUpdates(CallerContext &,Windows::Foundation::Collections::IVectorView<WindowsUpdate::Internal::IFulfillmentDataInfo *> *,ulong,int,HSTRING__ *,char const *,Windows::Foundation::Collections::IVectorView<WindowsUpdate::Internal::IInstallItem *> * *)

- ea: `0x18005e49c`
- end: `0x18005f68b`
- name: `?_InstallUpdates@InstallQueue@@AEAAJAEAVCallerContext@@PEAU?$IVectorView@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@Collections@Foundation@Windows@@KHPEAUHSTRING__@@PEBDPEAPEAU?$IVectorView@PEAUIInstallItem@Internal@WindowsUpdate@@@456@@Z`
- size: `4591`
- prototype: `__int64 __usercall@<rax>(InstallQueue *this@<rcx>, int, __int64, char *, __int64)`
- caller_count: `1`
- callee_count: `55`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180028be0`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x18001af10`
- `0x18001bf24`
- `0x18001c414`
- `0x18001c844`
- `0x18001f784`
- `0x180020274`
- `0x180020960`
- `0x1800222d8`
- `0x180022374`
- `0x1800252e8`
- `0x18002548c`
- `0x1800265e0`
- `0x180028cd4`
- `0x18002ec2c`
- `0x18002ec4c`
- `0x18002f214`
- `0x1800343cc`
- `0x1800345d0`
- `0x180037510`
- `0x180038580`
- `0x18003f884`
- `0x180043320`
- `0x18004c5d8`
- `0x18004cba0`
- `0x18004e364`
- `0x18004e938`
- `0x18004fd94`
- `0x1800509c8`
- `0x180051478`
- `0x1800514a8`
- `0x180051d18`
- `0x180051fc4`
- `0x180052268`
- `0x1800578cc`
- `0x180057fbc`
- `0x18005bdd8`
- `0x18005bfcc`
- `0x18005c078`
- `0x18005c338`
- `0x18005d640`
- `0x18005e49c`
- `0x180061fb0`
- `0x180063178`
- `0x1800636d8`
- `0x180064ffc`
- `0x180073110`
- `0x180076628`
- `0x180076e48`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs` at `0x18005f167`
- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs` at `0x18005f167`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18005e555`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18005e583`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18005e555`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18005e583`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ed08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ef35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ef98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f091`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f0da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f106`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ed08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ef35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ef98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f091`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f0da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f106`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005e75c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005ea89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005ebdb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005ec53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005ed97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005edaf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005e75c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005ea89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005ebdb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005ec53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005ed97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005edaf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x18005ed55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x18005ed55`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005eb2f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005eccc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005eb2f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005eccc`

## string_xrefs

- `0x18005f42b`: `SOFTWARE\Microsoft\Windows\CurrentVersion\InstallService\State`
- `0x18005f460`: `HasFrameworkUpdates`
- `0x18005e5e1`: `onecoreuap\enduser\winstore\installservice\lib\installqueue.cpp`
- `0x18005e623`: `onecoreuap\enduser\winstore\installservice\lib\installqueue.cpp`
- `0x18005e79f`: `onecoreuap\enduser\winstore\installservice\lib\installqueue.cpp`
- `0x18005f4cf`: `onecoreuap\enduser\winstore\installservice\lib\installqueue.cpp`
- `0x18005e77e`: `Intiating Scan as UserSid = %s, cv = %hs`
- `0x18005e792`: `InstallQueue::_InstallUpdates`
- `0x18005e88f`: `InstallQueue::_InstallUpdates`
- `0x18005eabf`: `InstallQueue::_InstallUpdates`
- `0x18005ec11`: `InstallQueue::_InstallUpdates`
- `0x18005ec89`: `InstallQueue::_InstallUpdates`
- `0x18005f403`: `InstallQueue::_InstallUpdates`
- `0x18005e87b`: `No Updates Found. Checked %d categoryIds`
- `0x18005eaab`: `Found framework update, categoryId = %s, cv = %hs`
- `0x18005ebfd`: `Update search returned unrecognized categoryId = %s, cv = %hs`
- `0x18005ec75`: `Doing per app offline scan to get app specific update collection. categoryId = %s, cv = %hs`
- `0x18005ed28`: `Update;`
- `0x18005f3fc`: `::UpdateFrameworks(callerContext, spFrameworkUpdates.Get(), szCV)`

## pseudocode

```c
// Hidden C++ exception states: #wind=37 #try_helpers=1
__int64 __fastcall InstallQueue::_InstallUpdates(
        InstallQueue *this,
        CallerContext *a2,
        HKEY a3,
        int a4,
        int a5,
        HSTRING a6,
        char *a7,
        void **a8)
{
  char *v10; // rcx
  const char *v11; // r9
  TraceLoggingCorrelationVector *v12; // rsi
  __int64 v13; // rcx
  int v14; // eax
  int i; // eax
  HKEY v16; // rbx
  __int16 v17; // bx
  int v18; // edi
  PCWSTR StringRawBuffer; // rax
  unsigned int v20; // ebx
  void *ClientHandleOrNullIfLocalSystem; // rax
  __int64 v22; // rax
  __int64 v23; // rdi
  unsigned int v24; // ebx
  int v26; // eax
  int v27; // r14d
  int (__fastcall *v28)(__int64, _QWORD, struct IUpdate **); // rbx
  struct IUpdateCollection *v29; // rcx
  HRESULT Instance; // eax
  int v31; // eax
  __int64 v32; // rbx
  HSTRING v33; // rcx
  HRESULT v34; // eax
  HRESULT v35; // eax
  int v36; // r14d
  void *v37; // rax
  int updated; // eax
  __int64 v39; // rbx
  __int64 (__fastcall *v40)(__int64, HKEY *); // r14
  HKEY v41; // rcx
  int v42; // eax
  int v43; // eax
  HKEY v44; // rbx
  int (__fastcall *v45)(HKEY, HSTRING *); // r14
  HSTRING v46; // rcx
  __int64 v47; // rbx
  HKEY v48; // rax
  __int64 v49; // rcx
  __int64 v50; // rax
  __int64 v51; // rcx
  __int64 v52; // rdx
  __int64 v53; // rdx
  __int64 v54; // rdx
  char v55; // r14
  __int64 *v56; // rbx
  __int64 v57; // rdi
  __int64 v58; // rcx
  HSTRING *v59; // rdi
  __int64 v60; // rdx
  HSTRING *v61; // rax
  __int64 inserted; // rax
  WindowsUpdate::Internal::InstallItem **v63; // rax
  WindowsUpdate::Internal::InstallItem *v64; // r14
  int v65; // eax
  int v66; // eax
  __int64 **v67; // rcx
  __int64 *j; // rax
  __int64 *k; // rcx
  struct IUpdateCollection *v70; // rax
  int v71; // eax
  const WCHAR *RegistryLocation; // rax
  const char *v73; // r9
  InstallQueue *v74; // rdi
  void **v75; // rbx
  int v76; // eax
  struct WindowsUpdate::Internal::InstallItem *v77; // rbx
  int v78; // eax
  const char *v79; // r9
  int ppv; // [rsp+20h] [rbp-398h]
  int ppva; // [rsp+20h] [rbp-398h]
  int ppvb; // [rsp+20h] [rbp-398h]
  unsigned __int16 *v83; // [rsp+28h] [rbp-390h]
  PCWSTR v84; // [rsp+40h] [rbp-378h]
  __int64 v85; // [rsp+48h] [rbp-370h]
  int v86; // [rsp+58h] [rbp-360h]
  int v87; // [rsp+70h] [rbp-348h] BYREF
  char v88; // [rsp+78h] [rbp-340h]
  HKEY phkResult; // [rsp+80h] [rbp-338h] BYREF
  char v90; // [rsp+88h] [rbp-330h]
  HSTRING string; // [rsp+90h] [rbp-328h] BYREF
  int v92; // [rsp+98h] [rbp-320h]
  HSTRING newString; // [rsp+A0h] [rbp-318h] BYREF
  struct IUpdateCollection *v94; // [rsp+A8h] [rbp-310h] BYREF
  HSTRING v95; // [rsp+B0h] [rbp-308h] BYREF
  HKEY v96; // [rsp+B8h] [rbp-300h] BYREF
  HSTRING *v97; // [rsp+C0h] [rbp-2F8h]
  __int64 v98; // [rsp+C8h] [rbp-2F0h] BYREF
  struct IUpdate *v99; // [rsp+D0h] [rbp-2E8h] BYREF
  InstallQueue *v100; // [rsp+D8h] [rbp-2E0h]
  __int64 v101; // [rsp+E0h] [rbp-2D8h] BYREF
  HKEY v102; // [rsp+E8h] [rbp-2D0h] BYREF
  int v103; // [rsp+F0h] [rbp-2C8h] BYREF
  int v104; // [rsp+F4h] [rbp-2C4h]
  CallerContext *v105; // [rsp+F8h] [rbp-2C0h]
  LPVOID v106; // [rsp+100h] [rbp-2B8h] BYREF
  Microsoft::WRL::Wrappers::HString *v107[2]; // [rsp+108h] [rbp-2B0h] BYREF
  __int64 v108; // [rsp+118h] [rbp-2A0h]
  __int64 v109; // [rsp+120h] [rbp-298h] BYREF
  __int64 v110; // [rsp+128h] [rbp-290h] BYREF
  void **v111; // [rsp+130h] [rbp-288h]
  HSTRING string2; // [rsp+138h] [rbp-280h]
  __int64 v113; // [rsp+140h] [rbp-278h] BYREF
  struct TraceLoggingCorrelationVector *v114; // [rsp+148h] [rbp-270h] BYREF
  __int64 v115; // [rsp+150h] [rbp-268h] BYREF
  void **v116; // [rsp+158h] [rbp-260h] BYREF
  HKEY v117; // [rsp+160h] [rbp-258h] BYREF
  __int64 v118; // [rsp+168h] [rbp-250h] BYREF
  _QWORD v119[2]; // [rsp+170h] [rbp-248h] BYREF
  HKEY v120; // [rsp+180h] [rbp-238h] BYREF
  int v121; // [rsp+188h] [rbp-230h]
  __int64 v122; // [rsp+190h] [rbp-228h] BYREF
  __int128 v123; // [rsp+198h] [rbp-220h] BYREF
  InstallQueue *v124; // [rsp+1A8h] [rbp-210h]
  const ScanException *v125; // [rsp+1B0h] [rbp-208h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+1B8h] [rbp-200h] BYREF
  HSTRING string1; // [rsp+1D0h] [rbp-1E8h]
  char v128[144]; // [rsp+1E0h] [rbp-1D8h] BYREF
  WCHAR sourceString[136]; // [rsp+270h] [rbp-148h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3B8h] [rbp+0h]

  v92 = a4;
  v105 = a2;
  v100 = this;
  v124 = this;
  string2 = a6;
  v111 = a8;
  v116 = a8;
  *a8 = 0;
  v104 = a4 & 1;
  if ( (a4 & 1) != 0 )
    goto LABEL_7;
  InitOnceExecuteOnce(&InitOnce, InitializeInstallServiceConfiguration, 0, 0);
  if ( dword_1802E4F6C )
  {
    if ( !byte_1802E4F68 )
      goto LABEL_7;
  }
  else
  {
    InitOnceExecuteOnce(&stru_1802E5520, SlsInit, 0, 0);
  }
  InstallQueue::_BackgroundRetry(this);
LABEL_7:
  if ( a7 && TraceLoggingCorrelationVector::Validate(a7) )
  {
    v10 = a7;
  }
  else
  {
    TraceLoggingCorrelationVector::Increment((InstallQueue *)((char *)this + 48), v128);
    v10 = v128;
  }
  v114 = TraceLoggingCorrelationVector::Extend(v10, 0);
  v12 = v114;
  if ( !v114 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x87E,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
      v11);
  v101 = 0;
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v101);
  v14 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<WindowsUpdate::Internal::IInstallItem,Windows::Foundation::Collections::Internal::Vector<WindowsUpdate::Internal::IInstallItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IInstallItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IInstallItem *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<WindowsUpdate::Internal::IInstallItem *>>>(
          v13,
          &v101);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x881,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
      (const char *)(unsigned int)v14,
      ppv);
  std::vector<ChainedInstallServiceWork::SubTaskCheckpointData>::vector<ChainedInstallServiceWork::SubTaskCheckpointData>(v107);
  std::map<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::Wrappers::HString>::map<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::Wrappers::HString>(v119);
  phkResult = a3;
  v120 = a3;
  v121 = 0;
  v122 = 0;
  wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::UI::Notifications::ToastNotification *>,wil::err_exception_policy>::end(
    &phkResult,
    &v96);
  for ( i = v121; i != (_DWORD)v97; i = ++v121 )
  {
    v16 = *(HKEY *)wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::Application *>,wil::err_exception_policy>::vector_iterator::operator*(&v120);
    phkResult = v16;
    if ( v16 )
      (*(void (__fastcall **)(HKEY))(*(_QWORD *)v16 + 8LL))(v16);
    InstallQueue::_AppendWuCategoryIdIfNotRunning(this, (__int64)v107);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&phkResult);
  }
  v17 = v92;
  v18 = v92 & 0x400;
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v98);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v122);
  TraceLoggingCorrelationVector::Increment(v12, v128);
  v90 = *((_BYTE *)v105 + 24);
  StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)v105, 0);
  LogMessage(
    3u,
    "onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
    0x88Cu,
    "InstallQueue::_InstallUpdates",
    -1,
    L"Intiating Scan as UserSid = %s, cv = %hs",
    0,
    0,
    StringRawBuffer,
    v128);
  try
  {
    v20 = (16 * v104) | (a5 != 0 ? 0x100 : 0) | (v18 != 0 ? 0x800 : 0) | v17 & 0x200 | 2;
    v110 = 0;
    ClientHandleOrNullIfLocalSystem = CallerContext::GetClientHandleOrNullIfLocalSystem(v105);
    v83 = (unsigned __int16 *)v128;
    ppva = (int)string2;
    v22 = ScanForUpdates((__int64)&phkResult, (__int64)ClientHandleOrNullIfLocalSystem, (__int64)v107, v20);
    Microsoft::WRL::ComPtr<IUpdateCollection>::operator=(&v110, v22);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&phkResult);
  }
  catch ( const ScanException *v125 )
  {
    SetRetryIntervalTriggersOnBackgroundUpdateTask(*((_DWORD *)v125 + 52));
    throw;
  }
  v23 = v110;
  if ( !v110 )
  {
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
      0x89Eu,
      "InstallQueue::_InstallUpdates",
      -1,
      L"No Updates Found. Checked %d categoryIds",
      0,
      0,
      (v107[1] - v107[0]) >> 3);
    v24 = (*(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v101 + 64LL))(v101, v111);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v110);
    std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IFulfillmentDataInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IFulfillmentDataInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IFulfillmentDataInfo *>,0>>,std::less<Microsoft::WRL::Wrappers::HString>,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IFulfillmentDataInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IFulfillmentDataInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IFulfillmentDataInfo *>,0>>>>,0>>::~_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IFulfillmentDataInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IFulfillmentDataInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IFulfillmentDataInfo *>,0>>,std::less<Microsoft::WRL::Wrappers::HString>,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IFulfillmentDataInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IFulfillmentDataInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IFulfillmentDataInfo *>,0>>>>,0>>(v119);
    if ( v107[0] )
    {
      std::_Destroy_range<std::allocator<Microsoft::WRL::Wrappers::HString>>(v107[0]);
      std::_Deallocate<16>(
        v107[0],
        (struct std::nothrow_t *)((v108 - (unsigned __int64)v107[0]) & 0xFFFFFFFFFFFFFFF8uLL));
      *(_OWORD *)v107 = 0;
      v108 = 0;
    }
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v101);
    std::_Temporary_owner<TraceLoggingCorrelationVector>::~_Temporary_owner<TraceLoggingCorrelationVector>(&v114);
    return v24;
  }
  v103 = 0;
  v26 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v110 + 80LL))(v110, &v103);
  if ( v26 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8A4,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
      (const char *)(unsigned int)v26,
      ppva);
  v94 = 0;
  v113 = 0;
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v113);
  v87 = 300000;
  phkResult = (HKEY)v100;
  Microsoft::WRL::Details::MakeAndInitialize<InstallQueue::SuspendScope,IInspectable,unsigned int &,InstallQueue *>(
    &v113,
    &v87,
    &phkResult);
  v88 = 0;
  v123 = 0;
  std::_Tree_std::_Tmap_traits_Microsoft::WRL::Wrappers::HString__InstallQueue::_InstallUpdates_::_3_::UpdateData_std::less_Microsoft::WRL::Wrappers::HString__std::allocator_std::pair_Microsoft::WRL::Wrappers::HString_const___InstallQueue::_InstallUpdates_::_3_::UpdateData____0___::_Alloc_sentinel_and_proxy(&v123);
  v27 = 0;
LABEL_28:
  v87 = v27;
  if ( v27 < v103 )
  {
    v99 = 0;
    v28 = *(int (__fastcall **)(__int64, _QWORD, struct IUpdate **))(*(_QWORD *)v23 + 56LL);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v99);
    if ( v28(v23, (unsigned int)v27, &v99) < 0 )
      goto LABEL_73;
    AppIdFromUpdateOrEmpty(&string, v99);
    if ( !string )
    {
      v33 = 0;
      goto LABEL_72;
    }
    if ( UpdateIsFramework(v99) )
    {
      WindowsGetStringRawBuffer(string, 0);
      LogMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
        0x8C2u,
        "InstallQueue::_InstallUpdates",
        -1,
        L"Found framework update, categoryId = %s, cv = %hs",
        0,
        0);
      if ( !(_BYTE)v104 && !v90 )
      {
        v29 = v94;
        if ( v94 )
          goto LABEL_38;
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v94);
        Instance = CoCreateInstance(
                     &GUID_13639463_00db_4646_803d_528026140d88,
                     0,
                     1u,
                     &GUID_07f7438c_7709_4ca5_b518_91279288134e,
                     (LPVOID *)&v94);
        if ( Instance < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x8CA,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
            (const char *)(unsigned int)Instance,
            ppva);
        v29 = v94;
        if ( v94 )
        {
LABEL_38:
          v87 = 0;
          v31 = ((__int64 (__fastcall *)(struct IUpdateCollection *, struct IUpdate *, int *))v29->lpVtbl->Add)(
                  v29,
                  v99,
                  &v87);
          if ( v31 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x8CF,
              (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
              (const char *)(unsigned int)v31,
              ppva);
        }
      }
      v88 = 1;
      goto LABEL_43;
    }
    std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IFulfillmentDataInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IFulfillmentDataInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IFulfillmentDataInfo *>,0>>,std::less<Microsoft::WRL::Wrappers::HString>,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IFulfillmentDataInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IFulfillmentDataInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IFulfillmentDataInfo *>,0>>>>,0>>::find(
      v119,
      &v115,
      &string);
    v32 = v115;
    if ( v115 == v119[0] )
    {
      WindowsGetStringRawBuffer(string, 0);
      LogMessage(
        2u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
        0x8D8u,
        "InstallQueue::_InstallUpdates",
        -1,
        L"Update search returned unrecognized categoryId = %s, cv = %hs",
        0,
        0);
      goto LABEL_43;
    }
    TraceLoggingCorrelationVector::Increment(v12, v128);
    v84 = WindowsGetStringRawBuffer(string, 0);
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
      0x8DEu,
      "InstallQueue::_InstallUpdates",
      -1,
      L"Doing per app offline scan to get app specific update collection. categoryId = %s, cv = %hs",
      0,
      0,
      v84,
      v128);
    v106 = 0;
    v34 = CoCreateInstance(
            &GUID_4cb43d7f_7eee_4906_8698_60da1c38f2fe,
            0,
            1u,
            &GUID_816858a4_260d_4260_933a_2585f1abc76b,
            &v106);
    if ( v34 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8E3,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
        (const char *)(unsigned int)v34,
        ppvb);
    v109 = 0;
    v102 = 0;
    newString = 0;
    WindowsDeleteString(0);
    newString = 0;
    string1 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Update;", 8u, 7u);
    v35 = WindowsConcatString(string1, string2, &newString);
    if ( v35 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8E8,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
        (const char *)(unsigned int)v35,
        ppvb);
    wil::com_ptr_t<IUpdateCollection,wil::err_exception_policy>::reset(&v109);
    v36 = (int)v106;
    phkResult = (HKEY)WindowsGetStringRawBuffer(newString, 0);
    v95 = (HSTRING)WindowsGetStringRawBuffer(string, 0);
    v37 = CallerContext::GetClientHandleOrNullIfLocalSystem(v105);
    v86 = v36;
    LOBYTE(v83) = 0;
    ppva = 0;
    updated = SearchUpdatePackages(v37, v95, 0, 0);
    if ( updated < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8F7,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
        (const char *)(unsigned int)updated,
        0);
    v39 = *(_QWORD *)(v32 + 40);
    v40 = *(__int64 (__fastcall **)(__int64, HKEY *))(*(_QWORD *)v39 + 64LL);
    v41 = v102;
    v102 = 0;
    if ( v41 )
      (*(void (__fastcall **)(HKEY))(*(_QWORD *)v41 + 16LL))(v41);
    v42 = v40(v39, &v102);
    if ( v42 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8F8,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
        (const char *)(unsigned int)v42,
        0);
    phkResult = v102;
    v96 = v102;
    LODWORD(v97) = 0;
    v98 = 0;
    wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::UI::Notifications::ToastNotification *>,wil::err_exception_policy>::end(
      &phkResult,
      &hstringHeader);
    v43 = (int)v97;
    while ( 1 )
    {
      if ( v43 == *(_DWORD *)&hstringHeader.Reserved.Reserved2[8] )
      {
LABEL_62:
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&hstringHeader.Reserved.Reserved2[16]);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v98);
        v117 = v102;
        if ( v102 )
          (*(void (__fastcall **)(HKEY))(*(_QWORD *)v102 + 8LL))(v102);
        UWAInstallWork::CreateCheckpointData(&v118, v109);
        v47 = *(_QWORD *)std::map_Microsoft::WRL::Wrappers::HString__InstallQueue::_InstallUpdates_::_3_::UpdateData_std::less_Microsoft::WRL::Wrappers::HString__std::allocator_std::pair_Microsoft::WRL::Wrappers::HString_const___InstallQueue::_InstallUpdates_::_3_::UpdateData_____::_Try_emplace_Microsoft::WRL::Wrappers::HString_(
                           &v123,
                           &v120,
                           &string);
        v48 = v117;
        v117 = 0;
        v49 = *(_QWORD *)(v47 + 40);
        *(_QWORD *)(v47 + 40) = v48;
        if ( v49 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
        v50 = v118;
        v118 = 0;
        v51 = *(_QWORD *)(v47 + 48);
        *(_QWORD *)(v47 + 48) = v50;
        if ( v51 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
        InstallQueue::_InstallUpdates_::_3_::UpdateData::_UpdateData(&v117);
        WindowsDeleteString(newString);
        newString = 0;
        wil::com_ptr_t<InstallQueue,wil::err_exception_policy>::~com_ptr_t<InstallQueue,wil::err_exception_policy>(
          &v102,
          v52);
        wil::com_ptr_t<InstallQueue,wil::err_exception_policy>::~com_ptr_t<InstallQueue,wil::err_exception_policy>(
          &v109,
          v53);
        wil::com_ptr_t<InstallQueue,wil::err_exception_policy>::~com_ptr_t<InstallQueue,wil::err_exception_policy>(
          &v106,
          v54);
        v27 = v87;
LABEL_43:
        v33 = string;
LABEL_72:
        WindowsDeleteString(v33);
        string = 0;
LABEL_73:
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v99);
        ++v27;
        goto LABEL_28;
      }
      v44 = *(HKEY *)wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::Application *>,wil::err_exception_policy>::vector_iterator::operator*(&v96);
      phkResult = v44;
      if ( v44 )
        (*(void (__fastcall **)(HKEY))(*(_QWORD *)v44 + 8LL))(v44);
      v95 = 0;
      v45 = *(int (__fastcall **)(HKEY, HSTRING *))(*(_QWORD *)v44 + 200LL);
      WindowsDeleteString(0);
      v95 = 0;
      if ( v45(v44, &v95) >= 0 )
      {
        v46 = v95;
        if ( !v95 )
          goto LABEL_70;
        if ( UpdateIsMandatory(v99, v95) )
        {
          v92 |= 0x80u;
          WindowsDeleteString(v95);
          v95 = 0;
          Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&phkResult);
          goto LABEL_62;
        }
      }
      v46 = v95;
LABEL_70:
      WindowsDeleteString(v46);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&phkResult);
      v43 = (_DWORD)v97 + 1;
      LODWORD(v97) = (_DWORD)v97 + 1;
    }
  }
  v55 = 0;
  v56 = *(__int64 **)v123;
  while ( !*((_BYTE *)v56 + 25) )
  {
    TraceLoggingCorrelationVector::Increment(v12, v128);
    _o_mbstowcs(sourceString, v128, 129);
    v57 = v56[6];
    v85 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, sourceString) + 24);
    WindowsUpdate::Internal::InstallItem::Create(
      (unsigned int)&v96,
      (_DWORD)v100,
      (_DWORD)v105,
      v56[5],
      1,
      v92,
      0,
      0,
      (__int64)string2,
      v85,
      v57,
      v86,
      0);
    v58 = (__int64)v96;
    v59 = (HSTRING *)v96;
    v60 = (__int64)v97;
    v61 = v97;
    v106 = v97;
    while ( v59 != v61 )
    {
      newString = *v59;
      Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(&newString);
      inserted = InstallQueue::_FindOrInsertInstallItem(v100);
      v63 = (WindowsUpdate::Internal::InstallItem **)Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl>::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManagerImpl>(
                                                       &v115,
                                                       inserted);
      v64 = *v63;
      *v63 = (WindowsUpdate::Internal::InstallItem *)newString;
      newString = (HSTRING)v64;
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v115);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&phkResult);
      if ( (v92 & 0x20) != 0 )
      {
        v65 = WindowsUpdate::Internal::InstallItem::Pause(v64, 0, 0);
        if ( v65 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x926,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
            (const char *)(unsigned int)v65,
            ppva);
        InstallQueue::RaiseProgressEvent(v100, v64);
      }
      v66 = (*(__int64 (__fastcall **)(__int64, WindowsUpdate::Internal::InstallItem *))(*(_QWORD *)v101 + 104LL))(
              v101,
              v64);
      if ( v66 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x92A,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
          (const char *)(unsigned int)v66,
          ppva);
      v55 = 1;
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&newString);
      ++v59;
      v60 = (__int64)v97;
      v58 = (__int64)v96;
      v61 = (HSTRING *)v106;
    }
    if ( v58 )
    {
      std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<WindowsUpdate::Internal::IFulfillmentDataInfo>>>(
        v58,
        v60);
      std::_Deallocate<16>(v96, (struct std::nothrow_t *)((v98 - (_QWORD)v96) & 0xFFFFFFFFFFFFFFF8uLL));
    }
    v67 = (__int64 **)v56[2];
    if ( *((_BYTE *)v67 + 25) )
    {
      for ( j = (__int64 *)v56[1]; !*((_BYTE *)j + 25) && v56 == (__int64 *)j[2]; j = (__int64 *)j[1] )
        v56 = j;
      v56 = j;
    }
    else
    {
      v56 = (__int64 *)v56[2];
      for ( k = *v67; !*((_BYTE *)k + 25); k = (__int64 *)*k )
        v56 = k;
    }
  }
  v70 = v94;
  if ( v94 )
  {
    v87 = 1;
    GetAutoUpdateState((enum WindowsUpdate::Internal::AutoUpdateState *)&v87);
    if ( ((v87 - 1) & 0xFFFFFFFD) == 0 && !v55 )
    {
      TraceLoggingCorrelationVector::Increment(v12, v128);
      v71 = UpdateFrameworks(v105, v94, v128);
      TraceHR(
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
        0x939u,
        "InstallQueue::_InstallUpdates",
        "::UpdateFrameworks(callerContext, spFrameworkUpdates.Get(), szCV)",
        v71,
        (int)v83);
    }
    v70 = v94;
  }
  if ( v88 && !v70 )
  {
    try
    {
      RegistryLocation = (const WCHAR *)_InitOnceAndGetRegistryLocation(
                                          (__int64)&qword_1802CAE80,
                                          (__int64)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\InstallService\\State");
      Registry::OpenKeyForWrite<Registry::NotFoundPolicy::CreateNew>(&phkResult, HKEY_LOCAL_MACHINE, RegistryLocation);
      v87 = 1;
      Registry::SetValue<unsigned long>(phkResult, 0, L"HasFrameworkUpdates", &v87);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x941,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
        v73);
      v74 = v124;
      v75 = v116;
      goto LABEL_104;
    }
  }
  v74 = v100;
  v75 = v111;
LABEL_104:
  v76 = (*(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v101 + 64LL))(v101, v75);
  if ( v76 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x943,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
      (const char *)(unsigned int)v76,
      ppva);
  try
  {
    v116 = (void **)*v75;
    v96 = (HKEY)v116;
    LODWORD(v97) = 0;
    v98 = 0;
    wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::UI::Notifications::ToastNotification *>,wil::err_exception_policy>::end(
      &v116,
      &hstringHeader);
    v78 = (int)v97;
    while ( v78 != *(_DWORD *)&hstringHeader.Reserved.Reserved2[8] )
    {
      v77 = *(struct WindowsUpdate::Internal::InstallItem **)wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::Application *>,wil::err_exception_policy>::vector_iterator::operator*(&v96);
      phkResult = (HKEY)v77;
      Microsoft::WRL::ComPtr<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::InternalAddRef(&phkResult);
      InstallQueue::_ScheduleInstallItem(v74, v77, 0, 1);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&phkResult);
      v78 = (_DWORD)v97 + 1;
      LODWORD(v97) = (_DWORD)v97 + 1;
    }
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&hstringHeader.Reserved.Reserved2[16]);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v98);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x94B,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\installqueue.cpp",
      v79);
  }
  std::_Tree_std::_Tmap_traits_Microsoft::WRL::Wrappers::HString__InstallQueue::_InstallUpdates_::_3_::UpdateData_std::less_Microsoft::WRL::Wrappers::HString__std::allocator_std::pair_Microsoft::WRL::Wrappers::HString_const___InstallQueue::_InstallUpdates_::_3_::UpdateData____0___::__Tree_std::_Tmap_traits_Microsoft::WRL::Wrappers::HString__InstallQueue::_InstallUpdates_::_3_::UpdateData_std::less_Microsoft::WRL::Wrappers::HString__std::allocator_std::pair_Microsoft::WRL::Wrappers::HString_const___InstallQueue::_InstallUpdates_::_3_::UpdateData____0___(&v123);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v113);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v94);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v110);
  std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IFulfillmentDataInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IFulfillmentDataInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IFulfillmentDataInfo *>,0>>,std::less<Microsoft::WRL::Wrappers::HString>,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IFulfillmentDataInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IFulfillmentDataInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IFulfillmentDataInfo *>,0>>>>,0>>::~_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IFulfillmentDataInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IFulfillmentDataInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IFulfillmentDataInfo *>,0>>,std::less<Microsoft::WRL::Wrappers::HString>,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IFulfillmentDataInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IFulfillmentDataInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IFulfillmentDataInfo *>,0>>>>,0>>(v119);
  if ( v107[0] )
  {
    std::_Destroy_range<std::allocator<Microsoft::WRL::Wrappers::HString>>(v107[0]);
    std::_Deallocate<16>(v107[0], (struct std::nothrow_t *)((v108 - (unsigned __int64)v107[0]) & 0xFFFFFFFFFFFFFFF8uLL));
    *(_OWORD *)v107 = 0;
    v108 = 0;
  }
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v101);
  std::_Temporary_owner<TraceLoggingCorrelationVector>::~_Temporary_owner<TraceLoggingCorrelationVector>(&v114);
  return 0;
}

```

## disassembly

```asm
0x18005e49c  mov     [rsp+arg_10], rbx
0x18005e4a1  mov     [rsp+arg_18], rsi
0x18005e4a6  push    rdi
0x18005e4a7  push    r12
0x18005e4a9  push    r13
0x18005e4ab  push    r14
0x18005e4ad  push    r15
0x18005e4af  sub     rsp, 390h
0x18005e4b6  mov     rax, cs:__security_cookie
0x18005e4bd  xor     rax, rsp
0x18005e4c0  mov     [rsp+3B8h+var_38], rax
0x18005e4c8  mov     [rsp+3B8h+var_320], r9d
0x18005e4d0  mov     rdi, r8
0x18005e4d3  mov     [rsp+3B8h+var_2C0], rdx
0x18005e4db  mov     r12, rcx
0x18005e4de  mov     [rsp+3B8h+var_2E0], rcx
0x18005e4e6  mov     r14d, [rsp+3B8h+arg_20]
0x18005e4ee  mov     [rsp+3B8h+var_210], rcx
0x18005e4f6  mov     rax, [rsp+3B8h+arg_28]
0x18005e4fe  mov     [rsp+3B8h+string2], rax
0x18005e506  mov     rbx, [rsp+3B8h+arg_30]
0x18005e50e  mov     rax, [rsp+3B8h+arg_38]
0x18005e516  mov     [rsp+3B8h+var_288], rax
0x18005e51e  mov     [rsp+3B8h+var_260], rax
0x18005e526  xor     r15d, r15d
0x18005e529  mov     [rax], r15
0x18005e52c  mov     eax, r9d
0x18005e52f  lea     r13d, [r15+1]
0x18005e533  and     eax, r13d
0x18005e536  mov     [rsp+3B8h+var_2C4], eax
0x18005e53d  test    al, al
0x18005e53f  jnz     short loc_18005E592
0x18005e541  xor     r9d, r9d; Context
0x18005e544  xor     r8d, r8d; Parameter
0x18005e547  lea     rdx, InitializeInstallServiceConfiguration; InitFn
0x18005e54e  lea     rcx, InitOnce; InitOnce
0x18005e555  call    cs:__imp_InitOnceExecuteOnce
0x18005e55b  cmp     cs:dword_1802E4F6C, r15d
0x18005e562  jz      short loc_18005E56F
0x18005e564  cmp     cs:byte_1802E4F68, r15b
0x18005e56b  jz      short loc_18005E592
0x18005e56d  jmp     short loc_18005E589
0x18005e56f  xor     r9d, r9d; Context
0x18005e572  xor     r8d, r8d; Parameter
0x18005e575  lea     rdx, SlsInit; InitFn
0x18005e57c  lea     rcx, stru_1802E5520; InitOnce
0x18005e583  call    cs:__imp_InitOnceExecuteOnce
0x18005e589  mov     rcx, r12; this
0x18005e58c  call    ?_BackgroundRetry@InstallQueue@@AEAAXXZ; InstallQueue::_BackgroundRetry(void)
0x18005e591  nop
0x18005e592  test    rbx, rbx
0x18005e595  jz      short loc_18005E5A8
0x18005e597  mov     rcx, rbx; char *
0x18005e59a  call    ?Validate@TraceLoggingCorrelationVector@@SA_NPEBD@Z; TraceLoggingCorrelationVector::Validate(char const *)
0x18005e59f  test    al, al
0x18005e5a1  jz      short loc_18005E5A8
0x18005e5a3  mov     rcx, rbx
0x18005e5a6  jmp     short loc_18005E5C2
0x18005e5a8  lea     rcx, [r12+30h]; this
0x18005e5ad  lea     rdx, [rsp+3B8h+var_1D8]; char *
0x18005e5b5  call    ?Increment@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::Increment(char *)
0x18005e5ba  lea     rcx, [rsp+3B8h+var_1D8]; char *
0x18005e5c2  xor     edx, edx; bool
0x18005e5c4  call    ?Extend@TraceLoggingCorrelationVector@@SAPEAV1@PEBD_N@Z; TraceLoggingCorrelationVector::Extend(char const *,bool)
0x18005e5c9  mov     [rsp+3B8h+var_270], rax
0x18005e5d1  mov     rsi, rax
0x18005e5d4  mov     rcx, [rsp+3B8h]; this
0x18005e5dc  test    rax, rax
0x18005e5df  jnz     short loc_18005E5F2
0x18005e5e1  lea     r8, aOnecoreuapEndu_86; "onecoreuap\\enduser\\winstore\\installs"...
0x18005e5e8  mov     edx, 87Eh; void *
0x18005e5ed  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18005e5f2  mov     [rsp+3B8h+var_2D8], r15
0x18005e5fa  lea     rcx, [rsp+3B8h+var_2D8]
0x18005e602  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18005e607  lea     rdx, [rsp+3B8h+var_2D8]
0x18005e60f  call    ??$CreateExternalObjectVector@UIInstallItem@Internal@WindowsUpdate@@V?$Vector@PEAUIInstallItem@Internal@WindowsUpdate@@U?$DefaultEqualityPredicate@PEAUIInstallItem@Internal@WindowsUpdate@@@2Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInstallItem@Internal@WindowsUpdate@@@2567@U?$DefaultVectorOptions@PEAUIInstallItem@Internal@WindowsUpdate@@@2567@@2Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAUIInstallItem@Internal@WindowsUpdate@@U?$DefaultEqualityPredicate@PEAUIInstallItem@Internal@WindowsUpdate@@@2Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInstallItem@Internal@WindowsUpdate@@@2567@U?$DefaultVectorOptions@PEAUIInstallItem@Internal@WindowsUpdate@@@2567@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<WindowsUpdate::Internal::IInstallItem,Windows::Foundation::Collections::Internal::Vector<WindowsUpdate::Internal::IInstallItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IInstallItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IInstallItem *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<WindowsUpdate::Internal::IInstallItem *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<WindowsUpdate::Internal::IInstallItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IInstallItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IInstallItem *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<WindowsUpdate::Internal::IInstallItem *>> * *)
0x18005e614  mov     rcx, [rsp+3B8h]; this
0x18005e61c  test    eax, eax
0x18005e61e  jns     short loc_18005E634
0x18005e620  mov     r9d, eax; char *
0x18005e623  lea     r8, aOnecoreuapEndu_86; "onecoreuap\\enduser\\winstore\\installs"...
0x18005e62a  mov     edx, 881h; void *
0x18005e62f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005e634  lea     rcx, [rsp+3B8h+var_2B0]; void *
0x18005e63c  call    ??0?$vector@USubTaskCheckpointData@ChainedInstallServiceWork@@V?$allocator@USubTaskCheckpointData@ChainedInstallServiceWork@@@std@@@std@@QEAA@XZ; std::vector<ChainedInstallServiceWork::SubTaskCheckpointData>::vector<ChainedInstallServiceWork::SubTaskCheckpointData>(void)
0x18005e641  nop
0x18005e642  lea     rcx, [rsp+3B8h+var_248]
0x18005e64a  call    ??0?$map@VHString@Wrappers@WRL@Microsoft@@V1234@U?$less@VHString@Wrappers@WRL@Microsoft@@@std@@V?$allocator@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V1234@@std@@@6@@std@@QEAA@XZ; std::map<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::Wrappers::HString>::map<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::Wrappers::HString>(void)
0x18005e64f  nop
0x18005e650  mov     [rsp+3B8h+phkResult], rdi
0x18005e658  mov     [rsp+3B8h+var_238], rdi
0x18005e660  mov     [rsp+3B8h+var_230], r15d
0x18005e668  mov     [rsp+3B8h+var_228], r15
0x18005e670  lea     rdx, [rsp+3B8h+var_300]
0x18005e678  lea     rcx, [rsp+3B8h+phkResult]
0x18005e680  call    ?end@?$vector_range@U?$IVectorView@PEAVToastNotification@Notifications@UI@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA?AVvector_iterator@12@XZ; wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::UI::Notifications::ToastNotification *>,wil::err_exception_policy>::end(void)
0x18005e685  nop
0x18005e686  mov     eax, [rsp+3B8h+var_230]
0x18005e68d  cmp     eax, dword ptr [rsp+3B8h+var_2F8]
0x18005e694  jz      short loc_18005E70B
0x18005e696  lea     rcx, [rsp+3B8h+var_238]
0x18005e69e  call    ??Dvector_iterator@?$vector_range@U?$IVectorView@PEAVApplication@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEBV?$ComPtr@UIApplication@StateRepository@Internal@Windows@@@WRL@Microsoft@@XZ; wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::Application *>,wil::err_exception_policy>::vector_iterator::operator*(void)
0x18005e6a3  mov     rbx, [rax]
0x18005e6a6  mov     [rsp+3B8h+phkResult], rbx
0x18005e6ae  test    rbx, rbx
0x18005e6b1  jz      short loc_18005E6C3
0x18005e6b3  mov     rax, [rbx]
0x18005e6b6  mov     rcx, rbx
0x18005e6b9  mov     rax, [rax+8]
0x18005e6bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e6c2  nop
0x18005e6c3  test    r14d, r14d
0x18005e6c6  setnz   r8b
0x18005e6ca  lea     rax, [rsp+3B8h+var_2B0]
0x18005e6d2  mov     [rsp+3B8h+ppv], rax; __int64
0x18005e6d7  lea     r9, [rsp+3B8h+var_248]
0x18005e6df  mov     rdx, rbx
0x18005e6e2  mov     rcx, r12; this
0x18005e6e5  call    ?_AppendWuCategoryIdIfNotRunning@InstallQueue@@AEAAXPEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@_NAEAV?$map@VHString@Wrappers@WRL@Microsoft@@V?$ComPtr@V?$AgileVector@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@U?$DefaultEqualityPredicate@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@2Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@2567@$0A@@Internal@Collections@Foundation@Windows@@@34@U?$less@VHString@Wrappers@WRL@Microsoft@@@std@@V?$allocator@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$ComPtr@V?$AgileVector@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@U?$DefaultEqualityPredicate@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@2Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@2567@$0A@@Internal@Collections@Foundation@Windows@@@34@@std@@@7@@std@@AEAV?$vector@VHString@Wrappers@WRL@Microsoft@@V?$allocator@VHString@Wrappers@WRL@Microsoft@@@std@@@6@@Z; InstallQueue::_AppendWuCategoryIdIfNotRunning(WindowsUpdate::Internal::IFulfillmentDataInfo *,bool,std::map<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IFulfillmentDataInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IFulfillmentDataInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IFulfillmentDataInfo *>,0>>> &,std::vector<Microsoft::WRL::Wrappers::HString> &)
0x18005e6ea  nop
0x18005e6eb  lea     rcx, [rsp+3B8h+phkResult]
0x18005e6f3  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18005e6f8  mov     eax, [rsp+3B8h+var_230]
0x18005e6ff  add     eax, r13d
0x18005e702  mov     [rsp+3B8h+var_230], eax
0x18005e709  jmp     short loc_18005E68D
0x18005e70b  mov     ebx, [rsp+3B8h+var_320]
0x18005e712  mov     edi, ebx
0x18005e714  and     edi, 400h
0x18005e71a  lea     rcx, [rsp+3B8h+var_2F0]
0x18005e722  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18005e727  nop
0x18005e728  lea     rcx, [rsp+3B8h+var_228]
0x18005e730  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18005e735  lea     rdx, [rsp+3B8h+var_1D8]; char *
0x18005e73d  mov     rcx, rsi; this
0x18005e740  call    ?Increment@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::Increment(char *)
0x18005e745  mov     rcx, [rsp+3B8h+var_2C0]
0x18005e74d  mov     al, [rcx+18h]
0x18005e750  mov     [rsp+3B8h+var_330], al
0x18005e757  xor     edx, edx; length
0x18005e759  mov     rcx, [rcx]; string
0x18005e75c  call    cs:__imp_WindowsGetStringRawBuffer
0x18005e762  lea     rcx, [rsp+3B8h+var_1D8]
0x18005e76a  mov     [rsp+3B8h+var_370], rcx
0x18005e76f  mov     [rsp+3B8h+var_378], rax
0x18005e774  mov     [rsp+3B8h+var_380], r15; unsigned __int16 *
0x18005e779  mov     [rsp+3B8h+var_388], r15; char *
0x18005e77e  lea     rax, aIntiatingScanA; "Intiating Scan as UserSid = %s, cv = %h"...
0x18005e785  mov     [rsp+3B8h+var_390], rax; unsigned __int16 *
0x18005e78a  mov     dword ptr [rsp+3B8h+ppv], 0FFFFFFFFh; int
0x18005e792  lea     r9, aInstallqueueIn_1; "InstallQueue::_InstallUpdates"
0x18005e799  mov     r8d, 88Ch; unsigned int
0x18005e79f  lea     r12, aOnecoreuapEndu_86; "onecoreuap\\enduser\\winstore\\installs"...
0x18005e7a6  mov     rdx, r12; char *
0x18005e7a9  mov     ecx, 3; unsigned int
0x18005e7ae  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x18005e7b3  and     ebx, 200h
0x18005e7b9  or      ebx, 2
0x18005e7bc  neg     edi
0x18005e7be  sbb     eax, eax
0x18005e7c0  and     eax, 800h
0x18005e7c5  or      ebx, eax
0x18005e7c7  neg     r14d
0x18005e7ca  sbb     eax, eax
0x18005e7cc  and     eax, 100h
0x18005e7d1  or      ebx, eax
0x18005e7d3  mov     eax, [rsp+3B8h+var_2C4]
0x18005e7da  shl     eax, 4
0x18005e7dd  or      ebx, eax
0x18005e7df  mov     [rsp+3B8h+var_290], r15
0x18005e7e7  mov     rcx, [rsp+3B8h+var_2C0]; this
0x18005e7ef  call    ?GetClientHandleOrNullIfLocalSystem@CallerContext@@QEAAPEAXXZ; CallerContext::GetClientHandleOrNullIfLocalSystem(void)
0x18005e7f4  lea     rcx, [rsp+3B8h+var_1D8]
0x18005e7fc  mov     [rsp+3B8h+var_390], rcx; int
0x18005e801  mov     rcx, [rsp+3B8h+string2]
0x18005e809  mov     [rsp+3B8h+ppv], rcx; int
0x18005e80e  mov     r9d, ebx
0x18005e811  lea     r8, [rsp+3B8h+var_2B0]
0x18005e819  mov     rdx, rax
0x18005e81c  lea     rcx, [rsp+3B8h+phkResult]
0x18005e824  call    ?ScanForUpdates@@YA?AV?$ComPtr@UIUpdateCollection@@@WRL@Microsoft@@PEAXAEAV?$vector@VHString@Wrappers@WRL@Microsoft@@V?$allocator@VHString@Wrappers@WRL@Microsoft@@@std@@@std@@KPEAUHSTRING__@@PEBD@Z; ScanForUpdates(void *,std::vector<Microsoft::WRL::Wrappers::HString> &,ulong,HSTRING__ *,char const *)
0x18005e829  mov     rdx, rax
0x18005e82c  lea     rcx, [rsp+3B8h+var_290]
0x18005e834  call    ??4?$ComPtr@UIUpdateCollection@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<IUpdateCollection>::operator=(Microsoft::WRL::ComPtr<IUpdateCollection> &&)
0x18005e839  lea     rcx, [rsp+3B8h+phkResult]
0x18005e841  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18005e846  nop
0x18005e847  mov     rdi, [rsp+3B8h+var_290]
0x18005e84f  test    rdi, rdi
0x18005e852  jnz     loc_18005E94D
0x18005e858  mov     rax, [rsp+3B8h+var_2B0+8]
0x18005e860  sub     rax, [rsp+3B8h+var_2B0]
0x18005e868  sar     rax, 3
0x18005e86c  mov     [rsp+3B8h+var_378], rax
0x18005e871  mov     [rsp+3B8h+var_380], r15; unsigned __int16 *
0x18005e876  mov     [rsp+3B8h+var_388], r15; char *
0x18005e87b  lea     rax, aNoUpdatesFound_0; "No Updates Found. Checked %d categoryId"...
0x18005e882  mov     [rsp+3B8h+var_390], rax; unsigned __int16 *
0x18005e887  mov     dword ptr [rsp+3B8h+ppv], 0FFFFFFFFh; int
0x18005e88f  lea     r9, aInstallqueueIn_1; "InstallQueue::_InstallUpdates"
0x18005e896  mov     r8d, 89Eh; unsigned int
0x18005e89c  mov     rdx, r12; char *
0x18005e89f  lea     ecx, [rdi+3]; unsigned int
0x18005e8a2  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x18005e8a7  mov     rcx, [rsp+3B8h+var_2D8]
0x18005e8af  mov     rax, [rcx]
0x18005e8b2  mov     rdx, [rsp+3B8h+var_288]
0x18005e8ba  mov     rax, [rax+40h]
0x18005e8be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e8c3  mov     ebx, eax
0x18005e8c5  lea     rcx, [rsp+3B8h+var_290]
0x18005e8cd  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18005e8d2  nop
0x18005e8d3  lea     rcx, [rsp+3B8h+var_248]
0x18005e8db  call    ??1?$_Tree@V?$_Tmap_traits@VHString@Wrappers@WRL@Microsoft@@V?$ComPtr@V?$AgileVector@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@U?$DefaultEqualityPredicate@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@2Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@2567@$0A@@Internal@Collections@Foundation@Windows@@@34@U?$less@VHString@Wrappers@WRL@Microsoft@@@std@@V?$allocator@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$ComPtr@V?$AgileVector@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@U?$DefaultEqualityPredicate@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@2Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIFulfillmentDataInfo@Internal@WindowsUpdate@@@2567@$0A@@Internal@Collections@Foundation@Windows@@@34@@std@@@7@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IFulfillmentDataInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IFulfillmentDataInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IFulfillmentDataInfo *>,0>>,std::less<Microsoft::WRL::Wrappers::HString>,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IFulfillmentDataInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IFulfillmentDataInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IFulfillmentDataInfo *>,0>>>>,0>>::~_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IFulfillmentDataInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IFulfillmentDataInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IFulfillmentDataInfo *>,0>>,std::less<Microsoft::WRL::Wrappers::HString>,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<WindowsUpdate::Internal::IFulfillmentDataInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsUpdate::Internal::IFulfillmentDataInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsUpdate::Internal::IFulfillmentDataInfo *>,0>>>>,0>>(void)
0x18005e8e0  nop
0x18005e8e1  mov     rcx, [rsp+3B8h+var_2B0]; this
0x18005e8e9  test    rcx, rcx
0x18005e8ec  jz      short loc_18005E92B
0x18005e8ee  mov     rdx, [rsp+3B8h+var_2B0+8]
0x18005e8f6  call    ??$_Destroy_range@V?$allocator@VHString@Wrappers@WRL@Microsoft@@@std@@@std@@YAXPEAVHString@Wrappers@WRL@Microsoft@@QEAV1234@AEAV?$allocator@VHString@Wrappers@WRL@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::WRL::Wrappers::HString>>(Microsoft::WRL::Wrappers::HString *,Microsoft::WRL::Wrappers::HString * const,std::allocator<Microsoft::WRL::Wrappers::HString> &)
0x18005e8fb  mov     rcx, [rsp+3B8h+var_2B0]
0x18005e903  mov     rdx, [rsp+3B8h+var_2A0]
0x18005e90b  sub     rdx, rcx
0x18005e90e  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18005e912  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005e917  xorps   xmm0, xmm0
0x18005e91a  movdqu  xmmword ptr [rsp+3B8h+var_2B0], xmm0
0x18005e923  mov     [rsp+3B8h+var_2A0], r15
0x18005e92b  lea     rcx, [rsp+3B8h+var_2D8]
0x18005e933  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18005e938  nop
0x18005e939  lea     rcx, [rsp+3B8h+var_270]
0x18005e941  call    ??1?$_Temporary_owner@VTraceLoggingCorrelationVector@@@std@@QEAA@XZ; std::_Temporary_owner<TraceLoggingCorrelationVector>::~_Temporary_owner<TraceLoggingCorrelationVector>(void)
0x18005e946  mov     eax, ebx
0x18005e948  jmp     loc_18005F65D
0x18005e94d  mov     [rsp+3B8h+var_2C8], r15d
0x18005e955  mov     rax, [rdi]
0x18005e958  lea     rdx, [rsp+3B8h+var_2C8]
0x18005e960  mov     rcx, rdi
0x18005e963  mov     rax, [rax+50h]
0x18005e967  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e96c  mov     rcx, [rsp+3B8h]; this
0x18005e974  test    eax, eax
0x18005e976  jns     short loc_18005E988
0x18005e978  mov     r9d, eax; char *
0x18005e97b  mov     r8, r12; unsigned int
0x18005e97e  mov     edx, 8A4h; void *
0x18005e983  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005e988  mov     [rsp+3B8h+var_310], r15
0x18005e990  mov     [rsp+3B8h+var_278], r15
0x18005e998  lea     rcx, [rsp+3B8h+var_278]
0x18005e9a0  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18005e9a5  mov     [rsp+3B8h+var_348], 493E0h
0x18005e9ad  mov     rdx, [rsp+3B8h+var_2E0]
0x18005e9b5  mov     [rsp+3B8h+phkResult], rdx
0x18005e9bd  lea     r8, [rsp+3B8h+phkResult]
0x18005e9c5  lea     rdx, [rsp+3B8h+var_348]
0x18005e9ca  lea     rcx, [rsp+3B8h+var_278]
0x18005e9d2  call    ??$MakeAndInitialize@VSuspendScope@InstallQueue@@UIInspectable@@AEAIPEAV2@@Details@WRL@Microsoft@@YAJPEAPEAUIInspectable@@AEAI$$QEAPEAVInstallQueue@@@Z; Microsoft::WRL::Details::MakeAndInitialize<InstallQueue::SuspendScope,IInspectable,uint &,InstallQueue *>(IInspectable * *,uint &,InstallQueue * &&)
0x18005e9d7  mov     [rsp+3B8h+var_340], r15b
0x18005e9dc  xorps   xmm0, xmm0
0x18005e9df  movdqu  [rsp+3B8h+var_220], xmm0
0x18005e9e8  lea     rcx, [rsp+3B8h+var_220]
0x18005e9f0  call    std___Tree_std___Tmap_traits_Microsoft__WRL__Wrappers__HString__InstallQueue___InstallUpdates____3___UpdateData_std__less_Microsoft__WRL__Wrappers__HString__std__allocator_std__pair_Microsoft__WRL__Wrappers__HString_const___InstallQueue___InstallUpdates____3___UpdateData____0______Alloc_sentinel_and_proxy
0x18005e9f5  nop
0x18005e9f6  mov     r14d, r15d
0x18005e9f9  mov     [rsp+3B8h+var_348], r14d
0x18005e9fe  cmp     r14d, [rsp+3B8h+var_2C8]
0x18005ea06  jge     loc_18005F129
0x18005ea0c  mov     [rsp+3B8h+var_2E8], r15
0x18005ea14  mov     rax, [rdi]
0x18005ea17  mov     rbx, [rax+38h]
0x18005ea1b  lea     rcx, [rsp+3B8h+var_2E8]
0x18005ea23  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18005ea28  lea     r8, [rsp+3B8h+var_2E8]
0x18005ea30  mov     edx, r14d
0x18005ea33  mov     rcx, rdi
0x18005ea36  mov     rax, rbx
0x18005ea39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ea3e  test    eax, eax
0x18005ea40  js      loc_18005F114
0x18005ea46  mov     rdx, [rsp+3B8h+var_2E8]
0x18005ea4e  lea     rcx, [rsp+3B8h+string]
0x18005ea56  call    ?AppIdFromUpdateOrEmpty@@YA?AVHString@Wrappers@WRL@Microsoft@@PEAUIUpdate@@@Z; AppIdFromUpdateOrEmpty(IUpdate *)
0x18005ea5b  nop
0x18005ea5c  cmp     [rsp+3B8h+string], r15
0x18005ea64  jz      loc_18005F104
0x18005ea6a  mov     rcx, [rsp+3B8h+var_2E8]; struct IUpdate *
0x18005ea72  call    ?UpdateIsFramework@@YA_NPEAUIUpdate@@@Z; UpdateIsFramework(IUpdate *)
0x18005ea77  test    al, al
0x18005ea79  jz      loc_18005EBA2
0x18005ea7f  xor     edx, edx; length
0x18005ea81  mov     rcx, [rsp+3B8h+string]; string
0x18005ea89  call    cs:__imp_WindowsGetStringRawBuffer
0x18005ea8f  lea     rcx, [rsp+3B8h+var_1D8]
0x18005ea97  mov     [rsp+3B8h+var_370], rcx
0x18005ea9c  mov     [rsp+3B8h+var_378], rax
  ... truncated ...
```
