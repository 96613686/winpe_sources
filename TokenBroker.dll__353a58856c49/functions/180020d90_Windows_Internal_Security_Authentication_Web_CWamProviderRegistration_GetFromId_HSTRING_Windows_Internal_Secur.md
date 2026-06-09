# Windows::Internal::Security::Authentication::Web::CWamProviderRegistration::GetFromId(HSTRING__ *,Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation * *)

- ea: `0x180020d90`
- end: `0x1800216ae`
- name: `?GetFromId@CWamProviderRegistration@Web@Authentication@Security@Internal@Windows@@UEAAJPEAUHSTRING__@@PEAPEAUIWamProviderRegistrationInformation@23456@@Z`
- size: `2334`
- prototype: `int(Windows::Internal::Security::Authentication::Web::CWamProviderRegistration *__hidden this, HSTRING, struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation **)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18006e4c4`

## callees

- `0x18000bd40`
- `0x18000bd70`
- `0x18001eaac`
- `0x18001ece0`
- `0x18001ed3c`
- `0x18001ffdc`
- `0x180020620`
- `0x18002071c`
- `0x180020c60`
- `0x180020d90`
- `0x1800216b4`
- `0x180021750`
- `0x1800228a8`
- `0x1800228e0`
- `0x180023090`
- `0x1800231c0`
- `0x18002413c`
- `0x1800455a4`
- `0x180064734`
- `0x180064e7c`
- `0x18008e690`
- `0x18008e6b4`
- `0x18009c7fc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002161f`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18002161f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180021333`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800213a6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180021451`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180021333`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800213a6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180021451`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180021385`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800214a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800214c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180021385`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800214a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800214c7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800214f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002166f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800214f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002166f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800214e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021661`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800214e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021661`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020fa1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020fb0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020fbf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020fce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020fdd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020fec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021163`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021172`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021181`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021190`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002119f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800211ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020fa1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020fb0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020fbf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020fce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020fdd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020fec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021163`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021172`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021181`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021190`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002119f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800211ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180020ee1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180020ee1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020f68`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002112a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800215f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021601`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002160c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002162f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002163a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021645`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020f68`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002112a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800215f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021601`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002160c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002162f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002163a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021645`

## string_xrefs

- `0x180020ec0`: `Windows::Internal::Security::Authentication::Web::CWamProviderRegistration::GetFromId`
- `0x180020f1b`: `onecore\ds\security\tokenbroker\broker\lib\wamproviderregistration.cpp`
- `0x180021279`: `onecore\ds\security\tokenbroker\broker\lib\wamproviderregistration.cpp`
- `0x1800213f2`: `onecore\ds\security\tokenbroker\broker\lib\wamproviderregistration.cpp`
- `0x180021561`: `onecore\ds\security\tokenbroker\broker\lib\wamproviderregistration.cpp`
- `0x1800215ac`: `onecore\ds\security\tokenbroker\broker\lib\wamproviderregistration.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Internal::Security::Authentication::Web::CWamProviderRegistration::GetFromId(
        struct IUnknown *this,
        HSTRING a2,
        struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation **a3)
{
  struct IUnknown *v6; // rcx
  Windows::Internal::Security::Authentication::Web::CallerContext *v7; // rbx
  const char *v8; // r9
  __int64 result; // rax
  char *v10; // rcx
  char *v11; // rcx
  HSTRING v12; // rcx
  HSTRING v13; // rcx
  HSTRING v14; // rcx
  HSTRING v15; // rcx
  HSTRING v16; // rcx
  HSTRING v17; // rcx
  int v18; // eax
  unsigned int v19; // edi
  int v20; // eax
  unsigned int v21; // edi
  char *v22; // rcx
  void *v23; // rcx
  char *v24; // rcx
  char *v25; // rcx
  HSTRING v26; // rcx
  HSTRING v27; // rcx
  HSTRING v28; // rcx
  HSTRING v29; // rcx
  HSTRING v30; // rcx
  HSTRING v31; // rcx
  _QWORD *v32; // rbx
  char *v33; // rcx
  void *v34; // rcx
  void *v35; // rdi
  RTL_SRWLOCK *v36; // rdi
  char v37; // bl
  unsigned int v38; // eax
  RTL_SRWLOCK *v39; // rdi
  char v40; // bl
  RTL_SRWLOCK *v41; // rdi
  char v42; // bl
  unsigned int v43; // eax
  unsigned int v44; // eax
  void *v45; // rbx
  HANDLE v46; // rax
  void *v47; // rbx
  HANDLE ProcessHeap; // rax
  unsigned int *v49; // rax
  int v50; // [rsp+20h] [rbp-1B8h]
  Windows::Internal::Security::Authentication::Web::CallerContext *v51; // [rsp+30h] [rbp-1A8h] BYREF
  _BYTE v52[8]; // [rsp+38h] [rbp-1A0h] BYREF
  void *Block; // [rsp+40h] [rbp-198h] BYREF
  void **v54; // [rsp+50h] [rbp-188h] BYREF
  int v55; // [rsp+58h] [rbp-180h] BYREF
  char v56; // [rsp+5Ch] [rbp-17Ch]
  _BYTE v57[32]; // [rsp+60h] [rbp-178h] BYREF
  int v58; // [rsp+80h] [rbp-158h] BYREF
  const char *v59; // [rsp+88h] [rbp-150h]
  LPVOID lpMem; // [rsp+90h] [rbp-148h]
  char v61; // [rsp+98h] [rbp-140h]
  int v62; // [rsp+A0h] [rbp-138h]
  __int128 v63; // [rsp+A8h] [rbp-130h]
  __int128 v64; // [rsp+B8h] [rbp-120h]
  __int128 v65; // [rsp+C8h] [rbp-110h]
  __int128 v66; // [rsp+D8h] [rbp-100h]
  __int128 v67; // [rsp+E8h] [rbp-F0h]
  __int128 v68; // [rsp+F8h] [rbp-E0h]
  __int128 v69; // [rsp+108h] [rbp-D0h]
  __int128 v70; // [rsp+118h] [rbp-C0h]
  __int128 v71; // [rsp+128h] [rbp-B0h]
  __int64 v72; // [rsp+138h] [rbp-A0h]
  LPVOID v73[2]; // [rsp+140h] [rbp-98h]
  int v74; // [rsp+150h] [rbp-88h]
  __int64 v75; // [rsp+158h] [rbp-80h]
  int *v76; // [rsp+160h] [rbp-78h]
  void *v77; // [rsp+168h] [rbp-70h] BYREF
  _QWORD v78[3]; // [rsp+170h] [rbp-68h] BYREF
  int v79; // [rsp+188h] [rbp-50h]
  int *v80; // [rsp+190h] [rbp-48h]
  char v81; // [rsp+198h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+0h]

  v55 = 0;
  v56 = 0;
  v61 = 0;
  v58 = 0;
  v59 = "WamProviderRegistrationGetFromId";
  lpMem = 0;
  v62 = 0;
  *(_OWORD *)v73 = 0;
  v63 = 0;
  v64 = 0;
  v65 = 0;
  v66 = 0;
  v67 = 0;
  v68 = 0;
  v69 = 0;
  v70 = 0;
  v71 = 0;
  v72 = 0;
  v74 = 1;
  v75 = 0;
  v76 = &v55;
  v77 = 0;
  v78[0] = 0;
  v78[1] = &v54;
  v78[2] = 0;
  v79 = 0;
  v80 = &v58;
  v81 = 0;
  v54 = &TbLogProvider::WamProviderRegistrationGetFromId::`vftable';
  TbLogProvider::WamProviderRegistrationGetFromId::StartActivity((TbLogProvider::WamProviderRegistrationGetFromId *)&v54);
  v6 = this - 5;
  if ( this == (struct IUnknown *)40 )
    this = 0;
  LOBYTE(v50) = 0;
  try
  {
    Windows::Internal::Security::Authentication::Web::CWamCallerProfiler::ProfileCaller(
      v6,
      v52,
      this,
      "Windows::Internal::Security::Authentication::Web::CWamProviderRegistration::GetFromId");
    if ( a3 )
    {
      if ( WindowsIsStringEmpty(a2) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4CF,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamproviderregistration.cpp",
          (const char *)0x80070057LL,
          v50);
        Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v52);
        v54 = &TbLogProvider::WamProviderRegistrationGetFromId::`vftable';
        wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v54);
        wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v54);
        result = 2147942487LL;
      }
      else
      {
        wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v51, &Block);
        v7 = v51;
        if ( !v51 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x4D2,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamproviderregistration.cpp",
            (const char *)0x8007000ELL,
            v50);
          wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
            &v51,
            0);
          Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v52);
          v54 = &TbLogProvider::WamProviderRegistrationGetFromId::`vftable';
          wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v54);
          wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v54);
          return 2147942414LL;
        }
        if ( !*(_BYTE *)v51 )
        {
          v18 = Windows::Internal::Security::Authentication::Web::CallerContext::Initialize(v51, this, 0, 0);
          v19 = v18;
          if ( v18 == -2147023584 )
          {
            TbLogProvider::WamProviderRegistrationGetFromId::CallerIsSystemOrService((TbLogProvider::WamProviderRegistrationGetFromId *)&v54);
            wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v54);
            wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
              &v51,
              0);
            Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v52);
            v54 = &TbLogProvider::WamProviderRegistrationGetFromId::`vftable';
            wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v54);
            wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v54);
            return 2147943712LL;
          }
          if ( v18 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x4DC,
              (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamproviderregistration.cpp",
              (const char *)(unsigned int)v18,
              v50);
            wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
              &v51,
              0);
            Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v52);
            v54 = &TbLogProvider::WamProviderRegistrationGetFromId::`vftable';
            wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v54);
            wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v54);
            return v19;
          }
        }
        v20 = Windows::Internal::Security::Authentication::Web::CWamProviderRegistrationInternal::GetFromId(a2, v7, a3);
        v21 = v20;
        if ( v20 == -2146893805 )
        {
          if ( v7 )
          {
            Windows::Internal::Security::Authentication::Web::CallerContext::~CallerContext(v7);
            operator delete(v7);
          }
          Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v52);
          v54 = &TbLogProvider::WamProviderRegistrationGetFromId::`vftable';
          if ( !v77 )
            goto LABEL_74;
          v39 = (RTL_SRWLOCK *)((char *)v77 + 264);
          AcquireSRWLockExclusive((PSRWLOCK)v77 + 33);
          if ( v77 && *(_DWORD *)v77 == 1 )
          {
            v40 = 1;
          }
          else
          {
            v40 = 0;
            wil::details::shared_object<wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<TbLogProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(&v77);
          }
          if ( v39 )
            ReleaseSRWLockExclusive(v39);
          if ( v40 )
          {
LABEL_74:
            if ( *v76 == 1 )
            {
              v43 = wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<TbLogProvider,_TlgReflectorTag_Param0IsProviderType>::SetUnhandledException(v76);
              wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
                &v54,
                v43);
            }
          }
          wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v54);
          result = 2148073491LL;
        }
        else if ( v20 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x4E1,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamproviderregistration.cpp",
            (const char *)(unsigned int)v20,
            v50);
          wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
            &v51,
            0);
          Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v52);
          v54 = &TbLogProvider::WamProviderRegistrationGetFromId::`vftable';
          wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v54);
          wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v54);
          result = v21;
        }
        else
        {
          wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v54);
          if ( v7 )
          {
            v22 = (char *)*((_QWORD *)v7 + 39);
            if ( (unsigned __int64)(v22 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
              CloseHandle(v22);
            v23 = (void *)*((_QWORD *)v7 + 38);
            if ( v23 )
              CloseHandle(v23);
            v24 = (char *)*((_QWORD *)v7 + 37);
            if ( (unsigned __int64)(v24 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
              CloseHandle(v24);
            v25 = (char *)*((_QWORD *)v7 + 36);
            if ( (unsigned __int64)(v25 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
              CloseHandle(v25);
            v26 = (HSTRING)*((_QWORD *)v7 + 9);
            if ( v26 )
              WindowsDeleteString(v26);
            v27 = (HSTRING)*((_QWORD *)v7 + 8);
            if ( v27 )
              WindowsDeleteString(v27);
            v28 = (HSTRING)*((_QWORD *)v7 + 7);
            if ( v28 )
              WindowsDeleteString(v28);
            v29 = (HSTRING)*((_QWORD *)v7 + 6);
            if ( v29 )
              WindowsDeleteString(v29);
            v30 = (HSTRING)*((_QWORD *)v7 + 5);
            if ( v30 )
              WindowsDeleteString(v30);
            v31 = (HSTRING)*((_QWORD *)v7 + 4);
            if ( v31 )
              WindowsDeleteString(v31);
            operator delete(v7);
          }
          if ( v52[0] )
          {
            TlsSetValue(dwTlsIndex, 0);
            v52[0] = 0;
          }
          v32 = Block;
          Block = 0;
          if ( v32 )
          {
            v33 = (char *)v32[39];
            if ( (unsigned __int64)(v33 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
              CloseHandle(v33);
            v34 = (void *)v32[38];
            if ( v34 )
              CloseHandle(v34);
            v10 = (char *)v32[37];
            if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
              CloseHandle(v10);
            v11 = (char *)v32[36];
            if ( (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
              CloseHandle(v11);
            v12 = (HSTRING)v32[9];
            if ( v12 )
              WindowsDeleteString(v12);
            v13 = (HSTRING)v32[8];
            if ( v13 )
              WindowsDeleteString(v13);
            v14 = (HSTRING)v32[7];
            if ( v14 )
              WindowsDeleteString(v14);
            v15 = (HSTRING)v32[6];
            if ( v15 )
              WindowsDeleteString(v15);
            v16 = (HSTRING)v32[5];
            if ( v16 )
              WindowsDeleteString(v16);
            v17 = (HSTRING)v32[4];
            if ( v17 )
              WindowsDeleteString(v17);
            operator delete(v32);
          }
          v54 = &TbLogProvider::WamProviderRegistrationGetFromId::`vftable';
          if ( !v77 )
            goto LABEL_26;
          v36 = (RTL_SRWLOCK *)((char *)v77 + 264);
          AcquireSRWLockExclusive((PSRWLOCK)v77 + 33);
          if ( v77 && *(_DWORD *)v77 == 1 )
          {
            v37 = 1;
          }
          else
          {
            v37 = 0;
            wil::details::shared_object<wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<TbLogProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(&v77);
          }
          if ( v36 )
            ReleaseSRWLockExclusive(v36);
          if ( v37 )
          {
LABEL_26:
            if ( *v76 == 1 )
            {
              v38 = wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<TbLogProvider,_TlgReflectorTag_Param0IsProviderType>::SetUnhandledException(v76);
              wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
                &v54,
                v38);
            }
          }
          if ( v79 )
            wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v78);
          if ( v77 )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v77, 0xFFFFFFFF) == 1 )
            {
              v35 = v77;
              if ( v77 )
              {
                wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<TbLogProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<TbLogProvider,_TlgReflectorTag_Param0IsProviderType>((char *)v77 + 8);
                operator delete(v35);
              }
            }
            v77 = 0;
          }
          if ( v73[0] )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v73[0], 0xFFFFFFFF) == 1 )
            {
              v47 = v73[0];
              ProcessHeap = GetProcessHeap();
              HeapFree(ProcessHeap, 0, v47);
            }
            *(_OWORD *)v73 = 0;
          }
          if ( v61 )
          {
            v45 = lpMem;
            v46 = GetProcessHeap();
            HeapFree(v46, 0, v45);
            v61 = 0;
          }
          lpMem = 0;
          if ( v55 == 1 )
          {
            v55 = 2;
            v49 = (unsigned int *)TbLogProvider::Provider();
            _tlgWriteActivityAutoStop<0,5>(v49, (__int64)v57);
          }
          result = 0;
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4CE,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamproviderregistration.cpp",
        (const char *)0x80004003LL,
        v50);
      Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v52);
      v54 = &TbLogProvider::WamProviderRegistrationGetFromId::`vftable';
      if ( !v77 )
        goto LABEL_78;
      v41 = (RTL_SRWLOCK *)((char *)v77 + 264);
      AcquireSRWLockExclusive((PSRWLOCK)v77 + 33);
      if ( v77 && *(_DWORD *)v77 == 1 )
      {
        v42 = 1;
      }
      else
      {
        v42 = 0;
        wil::details::shared_object<wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<TbLogProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(&v77);
      }
      if ( v41 )
        ReleaseSRWLockExclusive(v41);
      if ( v42 )
      {
LABEL_78:
        if ( *v76 == 1 )
        {
          v44 = ((__int64 (*)(void))wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<TbLogProvider,_TlgReflectorTag_Param0IsProviderType>::SetUnhandledException)();
          wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(&v54, v44);
        }
      }
      wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v54);
      result = 2147500035LL;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x4E6,
                           (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamproviderregistration.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x180020d90  mov     r11, rsp
0x180020d93  mov     [r11+20h], rbx
0x180020d97  push    rsi
0x180020d98  push    rdi
0x180020d99  push    r12
0x180020d9b  push    r14
0x180020d9d  push    r15
0x180020d9f  sub     rsp, 1B0h
0x180020da6  mov     rax, cs:__security_cookie
0x180020dad  xor     rax, rsp
0x180020db0  mov     [rsp+1D8h+var_38], rax
0x180020db8  mov     rsi, r8
0x180020dbb  mov     r14, rdx
0x180020dbe  mov     rdi, rcx
0x180020dc1  xor     r15d, r15d
0x180020dc4  mov     [rsp+1D8h+var_180], r15d
0x180020dc9  mov     [rsp+1D8h+var_17C], r15b
0x180020dce  mov     [rsp+1D8h+var_140], r15b
0x180020dd6  mov     [r11-158h], r15d
0x180020ddd  lea     rax, aWamproviderreg_3; "WamProviderRegistrationGetFromId"
0x180020de4  mov     [r11-150h], rax
0x180020deb  mov     [r11-148h], r15
0x180020df2  mov     [r11-138h], r15d
0x180020df9  xorps   xmm0, xmm0
0x180020dfc  movdqa  xmmword ptr [rsp+1D8h+var_98], xmm0
0x180020e05  xorps   xmm1, xmm1
0x180020e08  xor     eax, eax
0x180020e0a  movups  [rsp+1D8h+var_130], xmm1
0x180020e12  movups  [rsp+1D8h+var_120], xmm1
0x180020e1a  movups  [rsp+1D8h+var_110], xmm1
0x180020e22  movups  [rsp+1D8h+var_100], xmm1
0x180020e2a  movups  [rsp+1D8h+var_F0], xmm1
0x180020e32  movups  [rsp+1D8h+var_E0], xmm1
0x180020e3a  movups  [rsp+1D8h+var_D0], xmm1
0x180020e42  movups  [rsp+1D8h+var_C0], xmm1
0x180020e4a  movups  [rsp+1D8h+var_B0], xmm1
0x180020e52  mov     [r11-0A0h], rax
0x180020e59  mov     [rsp+1D8h+var_88], 1
0x180020e64  mov     [r11-80h], rax
0x180020e68  lea     rax, [rsp+1D8h+var_180]
0x180020e6d  mov     [r11-78h], rax
0x180020e71  mov     [r11-70h], r15
0x180020e75  mov     [r11-68h], r15
0x180020e79  lea     rax, [rsp+1D8h+var_188]
0x180020e7e  mov     [r11-60h], rax
0x180020e82  mov     [r11-58h], r15
0x180020e86  mov     [r11-50h], r15d
0x180020e8a  lea     rax, [r11-158h]
0x180020e91  mov     [r11-48h], rax
0x180020e95  mov     [r11-40h], r15b
0x180020e99  lea     r12, ??_7WamProviderRegistrationGetFromId@TbLogProvider@@6B@; const TbLogProvider::WamProviderRegistrationGetFromId::`vftable'
0x180020ea0  mov     [rsp+1D8h+var_188], r12
0x180020ea5  lea     rcx, [rsp+1D8h+var_188]; this
0x180020eaa  call    ?StartActivity@WamProviderRegistrationGetFromId@TbLogProvider@@QEAAXXZ; TbLogProvider::WamProviderRegistrationGetFromId::StartActivity(void)
0x180020eaf  nop
0x180020eb0  lea     rcx, [rdi-28h]
0x180020eb4  test    rcx, rcx
0x180020eb7  cmovz   rdi, r15
0x180020ebb  mov     byte ptr [rsp+1D8h+var_1B8], r15b; int
0x180020ec0  lea     r9, aWindowsInterna_25; "Windows::Internal::Security::Authentica"...
0x180020ec7  mov     r8, rdi
0x180020eca  lea     rdx, [rsp+1D8h+var_1A0]
0x180020ecf  call    ?ProfileCaller@CWamCallerProfiler@Web@Authentication@Security@Internal@Windows@@QEAA?AVCWamProfilerThreadScope@23456@PEAUIUnknown@@PEBD_N@Z; Windows::Internal::Security::Authentication::Web::CWamCallerProfiler::ProfileCaller(IUnknown *,char const *,bool)
0x180020ed4  nop
0x180020ed5  test    rsi, rsi
0x180020ed8  jz      loc_18002126B
0x180020ede  mov     rcx, r14; string
0x180020ee1  call    cs:__imp_WindowsIsStringEmpty
0x180020ee7  test    eax, eax
0x180020ee9  jnz     loc_180021553
0x180020eef  lea     rdx, [rsp+1D8h+Block]
0x180020ef4  lea     rcx, [rsp+1D8h+var_1A8]
0x180020ef9  call    ??0?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@$$QEAV01@@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(wistd::unique_ptr<void,wil::process_heap_deleter> &&)
0x180020efe  nop
0x180020eff  mov     rbx, [rsp+1D8h+var_1A8]
0x180020f04  test    rbx, rbx
0x180020f07  jnz     loc_1800210A7
0x180020f0d  mov     rcx, [rsp+1D8h]; this
0x180020f15  mov     r9d, 8007000Eh; char *
0x180020f1b  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\tokenbroker\\bro"...
0x180020f22  mov     edx, 4D2h; void *
0x180020f27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020f2c  nop
0x180020f2d  xor     edx, edx
0x180020f2f  lea     rcx, [rsp+1D8h+var_1A8]
0x180020f34  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x180020f39  nop
0x180020f3a  lea     rcx, [rsp+1D8h+var_1A0]; this
0x180020f3f  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x180020f44  nop
0x180020f45  mov     [rsp+1D8h+var_188], r12
0x180020f4a  lea     rcx, [rsp+1D8h+var_188]
0x180020f4f  call    ?Destroy@?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180020f54  lea     rcx, [rsp+1D8h+var_188]
0x180020f59  call    ??1?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180020f5e  mov     eax, 8007000Eh
0x180020f63  jmp     loc_18002107F
0x180020f68  call    cs:__imp_CloseHandle
0x180020f6e  mov     rcx, [rbx+128h]; hObject
0x180020f75  lea     rax, [rcx-1]
0x180020f79  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180020f7d  jbe     loc_18002163A
0x180020f83  mov     rcx, [rbx+120h]; hObject
0x180020f8a  lea     rax, [rcx-1]
0x180020f8e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180020f92  jbe     loc_180021645
0x180020f98  mov     rcx, [rbx+48h]; string
0x180020f9c  test    rcx, rcx
0x180020f9f  jz      short loc_180020FA7
0x180020fa1  call    cs:__imp_WindowsDeleteString
0x180020fa7  mov     rcx, [rbx+40h]; string
0x180020fab  test    rcx, rcx
0x180020fae  jz      short loc_180020FB6
0x180020fb0  call    cs:__imp_WindowsDeleteString
0x180020fb6  mov     rcx, [rbx+38h]; string
0x180020fba  test    rcx, rcx
0x180020fbd  jz      short loc_180020FC5
0x180020fbf  call    cs:__imp_WindowsDeleteString
0x180020fc5  mov     rcx, [rbx+30h]; string
0x180020fc9  test    rcx, rcx
0x180020fcc  jz      short loc_180020FD4
0x180020fce  call    cs:__imp_WindowsDeleteString
0x180020fd4  mov     rcx, [rbx+28h]; string
0x180020fd8  test    rcx, rcx
0x180020fdb  jz      short loc_180020FE3
0x180020fdd  call    cs:__imp_WindowsDeleteString
0x180020fe3  mov     rcx, [rbx+20h]; string
0x180020fe7  test    rcx, rcx
0x180020fea  jz      short loc_180020FF2
0x180020fec  call    cs:__imp_WindowsDeleteString
0x180020ff2  mov     edx, 140h
0x180020ff7  mov     rcx, rbx; Block
0x180020ffa  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180020fff  nop
0x180021000  mov     [rsp+1D8h+var_188], r12
0x180021005  mov     rdx, [rsp+1D8h+var_70]
0x18002100d  test    rdx, rdx
0x180021010  jnz     loc_18002131E
0x180021016  mov     rcx, [rsp+1D8h+var_78]
0x18002101e  cmp     dword ptr [rcx], 1
0x180021021  jz      loc_18002136C
0x180021027  cmp     [rsp+1D8h+var_50], 0
0x18002102f  jnz     loc_18002130C
0x180021035  mov     rcx, [rsp+1D8h+var_70]
0x18002103d  mov     ebx, 0FFFFFFFFh
0x180021042  test    rcx, rcx
0x180021045  jnz     loc_1800212D1
0x18002104b  mov     rax, [rsp+1D8h+var_98]
0x180021053  test    rax, rax
0x180021056  jnz     loc_180021650
0x18002105c  cmp     [rsp+1D8h+var_140], 0
0x180021064  jnz     loc_1800214DA
0x18002106a  mov     [rsp+1D8h+lpMem], r15
0x180021072  cmp     [rsp+1D8h+var_180], 1
0x180021077  jz      loc_180021686
0x18002107d  xor     eax, eax
0x18002107f  mov     rcx, [rsp+1D8h+var_38]
0x180021087  xor     rcx, rsp; StackCookie
0x18002108a  call    __security_check_cookie
0x18002108f  mov     rbx, [rsp+1D8h+arg_18]
0x180021097  add     rsp, 1B0h
0x18002109e  pop     r15
0x1800210a0  pop     r14
0x1800210a2  pop     r12
0x1800210a4  pop     rdi
0x1800210a5  pop     rsi
0x1800210a6  retn
0x1800210a7  cmp     byte ptr [rbx], 0
0x1800210aa  jnz     short loc_1800210D2
0x1800210ac  xor     r9d, r9d; bool
0x1800210af  xor     r8d, r8d; unsigned __int64
0x1800210b2  mov     rdx, rdi; struct IUnknown *
0x1800210b5  mov     rcx, rbx; this
0x1800210b8  call    ?Initialize@CallerContext@Web@Authentication@Security@Internal@Windows@@QEAAJPEAUIUnknown@@_K_N@Z; Windows::Internal::Security::Authentication::Web::CallerContext::Initialize(IUnknown *,unsigned __int64,bool)
0x1800210bd  mov     edi, eax
0x1800210bf  cmp     eax, 80070520h
0x1800210c4  jz      loc_180021503
0x1800210ca  test    eax, eax
0x1800210cc  js      loc_1800213E7
0x1800210d2  mov     r8, rsi; struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation **
0x1800210d5  mov     rdx, rbx; this
0x1800210d8  mov     rcx, r14; HSTRING
0x1800210db  call    ?GetFromId@CWamProviderRegistrationInternal@Web@Authentication@Security@Internal@Windows@@SAJPEAUHSTRING__@@AEAVCallerContext@23456@PEAPEAUIWamProviderRegistrationInformation@23456@@Z; Windows::Internal::Security::Authentication::Web::CWamProviderRegistrationInternal::GetFromId(HSTRING__ *,Windows::Internal::Security::Authentication::Web::CallerContext &,Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation * *)
0x1800210e0  mov     edi, eax
0x1800210e2  cmp     eax, 80090013h
0x1800210e7  jz      loc_18002120A
0x1800210ed  test    eax, eax
0x1800210ef  js      loc_1800215A1
0x1800210f5  lea     rcx, [rsp+1D8h+var_188]
0x1800210fa  call    ?Stop@?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800210ff  nop
0x180021100  test    rbx, rbx
0x180021103  jz      loc_1800211C2
0x180021109  mov     rcx, [rbx+138h]; hObject
0x180021110  lea     rax, [rcx-1]
0x180021114  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180021118  jbe     loc_1800215F6
0x18002111e  mov     rcx, [rbx+130h]; hObject
0x180021125  test    rcx, rcx
0x180021128  jz      short loc_180021130
0x18002112a  call    cs:__imp_CloseHandle
0x180021130  mov     rcx, [rbx+128h]; hObject
0x180021137  lea     rax, [rcx-1]
0x18002113b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002113f  jbe     loc_180021601
0x180021145  mov     rcx, [rbx+120h]; hObject
0x18002114c  lea     rax, [rcx-1]
0x180021150  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180021154  jbe     loc_18002160C
0x18002115a  mov     rcx, [rbx+48h]; string
0x18002115e  test    rcx, rcx
0x180021161  jz      short loc_180021169
0x180021163  call    cs:__imp_WindowsDeleteString
0x180021169  mov     rcx, [rbx+40h]; string
0x18002116d  test    rcx, rcx
0x180021170  jz      short loc_180021178
0x180021172  call    cs:__imp_WindowsDeleteString
0x180021178  mov     rcx, [rbx+38h]; string
0x18002117c  test    rcx, rcx
0x18002117f  jz      short loc_180021187
0x180021181  call    cs:__imp_WindowsDeleteString
0x180021187  mov     rcx, [rbx+30h]; string
0x18002118b  test    rcx, rcx
0x18002118e  jz      short loc_180021196
0x180021190  call    cs:__imp_WindowsDeleteString
0x180021196  mov     rcx, [rbx+28h]; string
0x18002119a  test    rcx, rcx
0x18002119d  jz      short loc_1800211A5
0x18002119f  call    cs:__imp_WindowsDeleteString
0x1800211a5  mov     rcx, [rbx+20h]; string
0x1800211a9  test    rcx, rcx
0x1800211ac  jz      short loc_1800211B4
0x1800211ae  call    cs:__imp_WindowsDeleteString
0x1800211b4  mov     edx, 140h
0x1800211b9  mov     rcx, rbx; Block
0x1800211bc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800211c1  nop
0x1800211c2  cmp     [rsp+1D8h+var_1A0], 0
0x1800211c7  jnz     loc_180021617
0x1800211cd  mov     rbx, [rsp+1D8h+Block]
0x1800211d2  mov     [rsp+1D8h+Block], r15
0x1800211d7  test    rbx, rbx
0x1800211da  jz      loc_180021000
0x1800211e0  mov     rcx, [rbx+138h]; hObject
0x1800211e7  lea     rax, [rcx-1]
0x1800211eb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800211ef  jbe     loc_18002162F
0x1800211f5  mov     rcx, [rbx+130h]; hObject
0x1800211fc  test    rcx, rcx
0x1800211ff  jz      loc_180020F6E
0x180021205  jmp     loc_180020F68
0x18002120a  test    rbx, rbx
0x18002120d  jz      short loc_180021225
0x18002120f  mov     rcx, rbx; this
0x180021212  call    ??1CallerContext@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CallerContext::~CallerContext(void)
0x180021217  mov     edx, 140h
0x18002121c  mov     rcx, rbx; Block
0x18002121f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180021224  nop
0x180021225  lea     rcx, [rsp+1D8h+var_1A0]; this
0x18002122a  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x18002122f  nop
0x180021230  mov     [rsp+1D8h+var_188], r12
0x180021235  mov     rdx, [rsp+1D8h+var_70]
0x18002123d  test    rdx, rdx
0x180021240  jnz     loc_180021391
0x180021246  mov     rcx, [rsp+1D8h+var_78]
0x18002124e  cmp     dword ptr [rcx], 1
0x180021251  jz      loc_18002148A
0x180021257  lea     rcx, [rsp+1D8h+var_188]
0x18002125c  call    ??1?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180021261  mov     eax, 80090013h
0x180021266  jmp     loc_18002107F
0x18002126b  mov     rcx, [rsp+1D8h]; this
0x180021273  mov     r9d, 80004003h; char *
0x180021279  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\tokenbroker\\bro"...
0x180021280  mov     edx, 4CEh; void *
0x180021285  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002128a  nop
0x18002128b  lea     rcx, [rsp+1D8h+var_1A0]; this
0x180021290  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x180021295  nop
0x180021296  mov     [rsp+1D8h+var_188], r12
0x18002129b  mov     rdx, [rsp+1D8h+var_70]
0x1800212a3  test    rdx, rdx
0x1800212a6  jnz     loc_18002143C
0x1800212ac  mov     rcx, [rsp+1D8h+var_78]
0x1800212b4  cmp     dword ptr [rcx], 1
0x1800212b7  jz      loc_1800214AE
0x1800212bd  lea     rcx, [rsp+1D8h+var_188]
0x1800212c2  call    ??1?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800212c7  mov     eax, 80004003h
0x1800212cc  jmp     loc_18002107F
0x1800212d1  mov     eax, ebx
0x1800212d3  lock xadd [rcx], eax
0x1800212d7  cmp     eax, 1
0x1800212da  jnz     short loc_1800212FF
0x1800212dc  mov     rdi, [rsp+1D8h+var_70]
0x1800212e4  test    rdi, rdi
0x1800212e7  jz      short loc_1800212FF
  ... truncated ...
```
