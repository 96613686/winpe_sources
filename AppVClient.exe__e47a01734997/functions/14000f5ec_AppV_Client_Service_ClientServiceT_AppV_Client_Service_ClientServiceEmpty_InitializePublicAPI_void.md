# AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::InitializePublicAPI(void)

- ea: `0x14000f5ec`
- end: `0x14000fe8a`
- name: `?InitializePublicAPI@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@AEAAKXZ`
- size: `2206`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14000e504`

## callees

- `0x140004280`
- `0x1400042a4`
- `0x1400060e8`
- `0x140006304`
- `0x14000697c`
- `0x140006a08`
- `0x140008e64`
- `0x1400094bc`
- `0x14000f5ec`
- `0x140010158`
- `0x1400114b4`
- `0x140013bd0`
- `0x14002a5a4`
- `0x14003c034`
- `0x14003c414`
- `0x14003c660`
- `0x14003cc80`
- `0x14006a010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x14000f8bb`
- `ole32!CoCreateInstance` at `0x14000f8bb`
- `ole32!CoRegisterClassObject` at `0x14000fb3c`
- `ole32!CoRegisterClassObject` at `0x14000fb3c`
- `ole32!CoResumeClassObjects` at `0x14000fc93`
- `ole32!CoResumeClassObjects` at `0x14000fc93`

## string_xrefs

- `0x14000f658`: `AppV::Client::Service::ClientServiceT<struct AppV::Client::Service::ClientServiceEmpty>::InitializePublicAPI`
- `0x14000f8cd`: `AppV::Client::Service::ClientServiceT<struct AppV::Client::Service::ClientServiceEmpty>::InitializePublicAPI`
- `0x14000f9eb`: `AppV::Client::Service::ClientServiceT<struct AppV::Client::Service::ClientServiceEmpty>::InitializePublicAPI`
- `0x14000fb66`: `AppV::Client::Service::ClientServiceT<struct AppV::Client::Service::ClientServiceEmpty>::InitializePublicAPI`
- `0x14000fca5`: `AppV::Client::Service::ClientServiceT<struct AppV::Client::Service::ClientServiceEmpty>::InitializePublicAPI`
- `0x14000f8fe`: `failed to obtain the COM global process options manager, error = %1%`
- `0x14000fa1e`: `failed to set the COM global exception handling behavior, error = %1%`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
__int64 __fastcall AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::InitializePublicAPI(
        __int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // rbx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rbx
  struct IUnknownVtbl *v10; // rbx
  IUnknown *v11; // r14
  _QWORD *v12; // rdx
  unsigned int v13; // ebx
  __int64 v14; // rdx
  IUnknown *v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rbx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rbx
  HRESULT v24; // ebx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rbx
  IUnknown *v29; // rax
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rax
  __int64 v33; // rbx
  IUnknown *v34; // rcx
  IUnknown *v35; // rcx
  IUnknown *v36; // rcx
  _QWORD *v37; // rdx
  HRESULT v38; // [rsp+30h] [rbp-D0h] BYREF
  LPUNKNOWN pUnk; // [rsp+38h] [rbp-C8h] BYREF
  IUnknown *v40; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-B8h] BYREF
  IUnknown *v42; // [rsp+50h] [rbp-B0h] BYREF
  IUnknown *v43; // [rsp+58h] [rbp-A8h] BYREF
  IUnknown *v44; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v45; // [rsp+68h] [rbp-98h] BYREF
  __int64 v46; // [rsp+78h] [rbp-88h]
  __int64 v47; // [rsp+80h] [rbp-80h]
  __int128 v48; // [rsp+88h] [rbp-78h] BYREF
  __int64 v49; // [rsp+98h] [rbp-68h]
  __int64 v50; // [rsp+A0h] [rbp-60h]
  char *v51[4]; // [rsp+A8h] [rbp-58h] BYREF
  int v52; // [rsp+C8h] [rbp-38h]
  _QWORD v53[2]; // [rsp+D0h] [rbp-30h] BYREF
  char *v54[4]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v55[7]; // [rsp+100h] [rbp+0h] BYREF
  _QWORD *v56; // [rsp+138h] [rbp+38h]
  _QWORD v57[7]; // [rsp+140h] [rbp+40h] BYREF
  _QWORD *v58; // [rsp+178h] [rbp+78h]
  char v59; // [rsp+180h] [rbp+80h]
  struct IUnknownVtbl *v60; // [rsp+188h] [rbp+88h]

  AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::ReportStartPending(a1);
  v2 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 24) + 8LL))(*(_QWORD *)(a1 + 24));
  v3 = v2;
  if ( (v2 & 0x8000000000LL) == 0 )
  {
    if ( (v2 & 0x2000000000LL) == 0 || !(_DWORD)v2 )
      LODWORD(v2) = 575;
    LODWORD(pUnk) = v2;
    std::string::string(
      v51,
      "AppV::Client::Service::ClientServiceT<struct AppV::Client::Service::ClientServiceEmpty>::InitializePublicAPI");
    v52 = 878;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v4);
    v48 = 0;
    v49 = 0;
    v50 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v48,
      L"Notification Manager AllowSubscribers() failed with actual error = %1%, reporting Windows error = %2%",
      0x65u);
    v6 = AppV::Log::fmt(v5, v53, &v48);
    v43 = (IUnknown *)v3;
    v7 = AppV::LogFormatter::operator%(v6, (__int64 *)&v43);
    v8 = AppV::LogFormatter::operator%<unsigned long>(v7, (__int64)&pUnk);
    v45 = 0;
    v46 = 0;
    v47 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v45, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v51, 1, (int)&v45, v8);
    std::wstring::~wstring((char **)&v45);
    v53[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v54);
    std::wstring::~wstring((char **)&v48);
    std::string::~string(v51);
    return (unsigned int)pUnk;
  }
  v55[0] = &std::_Func_impl_no_alloc<std::_Mem_fn<unsigned __int64 (AppV::Client::Service::NotificationManager::*)(bool)>,unsigned __int64,AppV::Client::Service::NotificationManager *,bool>::`vftable';
  v55[1] =  AppV::Client::Service::NotificationManager::`vcall'{16,{flat}};
  v56 = v55;
  v10 = *(struct IUnknownVtbl **)(a1 + 24);
  v58 = 0;
  v58 = std::_Func_impl_no_alloc<std::_Mem_fn<unsigned __int64 (AppV::Client::Service::NotificationManager::*)(bool)>,unsigned __int64,AppV::Client::Service::NotificationManager *,bool>::_Copy(
          (__int64)v55,
          v57);
  v59 = 1;
  v60 = v10;
  v11 = (IUnknown *)operator new(0x58u);
  v43 = v11;
  v11->lpVtbl = (struct IUnknownVtbl *)&appv::utility::scope_guard_func_impl<std::_Binder<std::_Unforced,std::function<unsigned __int64 (AppV::Client::Service::NotificationManager *,bool)> &,AppV::Client::Service::NotificationManager *,bool>>::`vftable';
  pUnk = v11 + 1;
  v11[8].lpVtbl = 0;
  if ( v58 )
    v11[8].lpVtbl = (struct IUnknownVtbl *)(*(__int64 (__fastcall **)(_QWORD *, IUnknown *))*v58)(v58, v11 + 1);
  LOBYTE(v11[9].lpVtbl) = v59;
  v11[10].lpVtbl = v60;
  v40 = v11;
  if ( v58 )
  {
    v12 = v57;
    LOBYTE(v12) = v58 != v57;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v58 + 32LL))(v58, v12);
    v58 = 0;
  }
  AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::ReportStartPending(a1);
  v13 = AppV::Client::Service::AppVClientImpl::PrepareForCallers(
          *(struct AppV::Client::Service::NotificationManager **)(a1 + 24),
          *(struct AppV::Client::ControllerRequests **)(a1 + 96));
  if ( v13 )
    goto LABEL_11;
  v15 = (IUnknown *)operator new(0x18u);
  v43 = v15;
  v15->lpVtbl = (struct IUnknownVtbl *)&appv::utility::scope_guard_func_impl<std::_Binder<std::_Unforced,void (*)(void),>>::`vftable';
  v15[1].lpVtbl = (struct IUnknownVtbl *)AppV::Client::Service::AppVClientImpl::DisallowCallers;
  v42 = v15;
  AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::ReportStartPending(a1);
  ppv = 0;
  v38 = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &IID_IGlobalOptions, &ppv);
  if ( v38 < 0 )
  {
    std::string::string(
      v51,
      "AppV::Client::Service::ClientServiceT<struct AppV::Client::Service::ClientServiceEmpty>::InitializePublicAPI");
    v52 = 902;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v16);
    v45 = 0;
    v46 = 0;
    v47 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v45,
      L"failed to obtain the COM global process options manager, error = %1%",
      0x44u);
    v18 = AppV::Log::fmt(v17, v53, &v45);
    v19 = AppV::LogFormatter::operator%<long>(v18, (__int64)&v38);
    v48 = 0;
    v49 = 0;
    v50 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v48, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v51, 8, (int)&v48, v19);
    std::wstring::~wstring((char **)&v48);
    v53[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v54);
    std::wstring::~wstring((char **)&v45);
    std::string::~string(v51);
    v13 = v38;
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
LABEL_17:
    appv::utility::scope_guard::~scope_guard((appv::utility::scope_guard *)&v42);
LABEL_11:
    appv::utility::scope_guard::~scope_guard((appv::utility::scope_guard *)&v40);
    if ( v56 )
    {
      LOBYTE(v14) = v56 != v55;
      (*(void (__fastcall **)(_QWORD *, __int64))(*v56 + 32LL))(v56, v14);
    }
    return v13;
  }
  v38 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 1, 2);
  if ( v38 < 0 )
  {
    std::string::string(
      v51,
      "AppV::Client::Service::ClientServiceT<struct AppV::Client::Service::ClientServiceEmpty>::InitializePublicAPI");
    v52 = 920;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v20);
    v45 = 0;
    v46 = 0;
    v47 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v45,
      L"failed to set the COM global exception handling behavior, error = %1%",
      0x45u);
    v22 = AppV::Log::fmt(v21, v53, &v45);
    v23 = AppV::LogFormatter::operator%<long>(v22, (__int64)&v38);
    v48 = 0;
    v49 = 0;
    v50 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v48, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v51, 8, (int)&v48, v23);
    std::wstring::~wstring((char **)&v48);
    v53[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v54);
    std::wstring::~wstring((char **)&v45);
    std::string::~string(v51);
    v13 = v38;
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    goto LABEL_17;
  }
  AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::ReportStartPending(a1);
  pUnk = 0;
  if ( off_1400AA010 )
  {
    v24 = off_1400AA010();
    if ( v24 >= 0 )
      v24 = CoRegisterClassObject(AppV::Client::Service::__objMap_AppVClientImpl, pUnk, 4u, 5u, &dwRegister);
  }
  else
  {
    v24 = 0;
  }
  v38 = v24;
  if ( v24 < 0 )
  {
    std::string::string(
      v51,
      "AppV::Client::Service::ClientServiceT<struct AppV::Client::Service::ClientServiceEmpty>::InitializePublicAPI");
    v52 = 933;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v25);
    v45 = 0;
    v46 = 0;
    v47 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v45, L"CoRegisterClassObject() failed, error = %1%", 0x2Bu);
    v27 = AppV::Log::fmt(v26, v53, &v45);
    v28 = AppV::LogFormatter::operator%<long>(v27, (__int64)&v38);
    v48 = 0;
    v49 = 0;
    v50 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v48, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v51, 8, (int)&v48, v28);
    std::wstring::~wstring((char **)&v48);
    v53[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v54);
    std::wstring::~wstring((char **)&v45);
    std::string::~string(v51);
    v13 = v38;
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    goto LABEL_17;
  }
  v29 = (IUnknown *)operator new(0x18u);
  v43 = v29;
  v29->lpVtbl = (struct IUnknownVtbl *)&appv::utility::scope_guard_func_impl<std::_Binder<std::_Unforced,long (ATL::_ATL_OBJMAP_ENTRY30::*)(void),ATL::_ATL_OBJMAP_ENTRY30 *>>::`vftable';
  v29[1].lpVtbl = (struct IUnknownVtbl *)ATL::_ATL_OBJMAP_ENTRY30::RevokeClassObject;
  v29[2].lpVtbl = (struct IUnknownVtbl *)&AppV::Client::Service::__objMap_AppVClientImpl;
  v44 = v29;
  AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::ReportStartPending(a1);
  v38 = CoResumeClassObjects();
  if ( v38 < 0 )
  {
    std::string::string(
      v51,
      "AppV::Client::Service::ClientServiceT<struct AppV::Client::Service::ClientServiceEmpty>::InitializePublicAPI");
    v52 = 944;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v30);
    v45 = 0;
    v46 = 0;
    v47 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v45, L"CoResumeClassObjects() failed, error = %1%", 0x2Au);
    v32 = AppV::Log::fmt(v31, v53, &v45);
    v33 = AppV::LogFormatter::operator%<long>(v32, (__int64)&v38);
    v48 = 0;
    v49 = 0;
    v50 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v48, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v51, 8, (int)&v48, v33);
    std::wstring::~wstring((char **)&v48);
    v53[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v54);
    std::wstring::~wstring((char **)&v45);
    std::string::~string(v51);
    v13 = v38;
    appv::utility::scope_guard::~scope_guard((appv::utility::scope_guard *)&v44);
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    goto LABEL_17;
  }
  AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::ReportStartPending(a1);
  v34 = v44;
  v44 = 0;
  if ( v34 )
    ((void (__fastcall *)(IUnknown *, __int64))v34->lpVtbl->QueryInterface)(v34, 1);
  v35 = v42;
  v42 = 0;
  if ( v35 )
    ((void (__fastcall *)(IUnknown *, __int64))v35->lpVtbl->QueryInterface)(v35, 1);
  v36 = v40;
  v40 = 0;
  if ( v36 )
    ((void (__fastcall *)(IUnknown *, __int64))v36->lpVtbl->QueryInterface)(v36, 1);
  appv::utility::scope_guard::~scope_guard((appv::utility::scope_guard *)&v44);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  appv::utility::scope_guard::~scope_guard((appv::utility::scope_guard *)&v42);
  appv::utility::scope_guard::~scope_guard((appv::utility::scope_guard *)&v40);
  if ( v56 )
  {
    v37 = v55;
    LOBYTE(v37) = v56 != v55;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v56 + 32LL))(v56, v37);
  }
  return 0;
}

```

## disassembly

```asm
0x14000f5ec  mov     [rsp-8+arg_8], rbx
0x14000f5f1  mov     [rsp-8+arg_10], rdi
0x14000f5f6  push    rbp
0x14000f5f7  push    r14
0x14000f5f9  push    r15
0x14000f5fb  lea     rbp, [rsp-0A0h]
0x14000f603  sub     rsp, 1A0h
0x14000f60a  mov     rax, cs:__security_cookie
0x14000f611  xor     rax, rsp
0x14000f614  mov     [rbp+0B0h+var_20], rax
0x14000f61b  mov     rdi, rcx
0x14000f61e  xor     r15d, r15d
0x14000f621  call    ?ReportStartPending@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@AEAAXXZ; AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::ReportStartPending(void)
0x14000f626  mov     rcx, [rdi+18h]
0x14000f62a  mov     rax, [rcx]
0x14000f62d  mov     rax, [rax+8]
0x14000f631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f636  mov     rbx, rax
0x14000f639  bt      rax, 27h ; '''
0x14000f63e  jb      loc_14000F746
0x14000f644  bt      rax, 25h ; '%'
0x14000f649  jnb     short loc_14000F64F
0x14000f64b  test    ebx, ebx
0x14000f64d  jnz     short loc_14000F654
0x14000f64f  mov     eax, 23Fh
0x14000f654  mov     dword ptr [rsp+1B0h+pUnk], eax
0x14000f658  lea     rdx, aAppvClientServ_0; "AppV::Client::Service::ClientServiceT<s"...
0x14000f65f  lea     rcx, [rbp+0B0h+var_108]
0x14000f663  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14000f668  mov     [rbp+0B0h+var_E8], 36Eh
0x14000f66f  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14000f674  xorps   xmm0, xmm0
0x14000f677  movups  [rbp+0B0h+var_128], xmm0
0x14000f67b  mov     [rbp+0B0h+var_118], r15
0x14000f67f  mov     [rbp+0B0h+var_110], r15
0x14000f683  mov     r8d, 65h ; 'e'
0x14000f689  lea     rdx, aNotificationMa; "Notification Manager AllowSubscribers()"...
0x14000f690  lea     rcx, [rbp+0B0h+var_128]
0x14000f694  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14000f699  nop
0x14000f69a  lea     r8, [rbp+0B0h+var_128]
0x14000f69e  lea     rdx, [rbp+0B0h+var_E0]
0x14000f6a2  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14000f6a7  nop
0x14000f6a8  mov     [rsp+1B0h+var_158], rbx
0x14000f6ad  lea     rdx, [rsp+1B0h+var_158]
0x14000f6b2  mov     rcx, rax
0x14000f6b5  call    ??LLogFormatter@AppV@@QEAAAEAV01@AEBVErrorCode@1@@Z; AppV::LogFormatter::operator%(AppV::ErrorCode const &)
0x14000f6ba  lea     rdx, [rsp+1B0h+pUnk]
0x14000f6bf  mov     rcx, rax
0x14000f6c2  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x14000f6c7  mov     rbx, rax
0x14000f6ca  xorps   xmm0, xmm0
0x14000f6cd  movups  [rsp+1B0h+var_148], xmm0
0x14000f6d2  mov     [rsp+1B0h+var_138], r15
0x14000f6d7  mov     [rbp+0B0h+var_130], r15
0x14000f6db  mov     r8d, 6
0x14000f6e1  lea     rdx, aClient; "Client"
0x14000f6e8  lea     rcx, [rsp+1B0h+var_148]
0x14000f6ed  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14000f6f2  nop
0x14000f6f3  mov     r9, rbx
0x14000f6f6  lea     r8, [rsp+1B0h+var_148]
0x14000f6fb  mov     edx, 1
0x14000f700  lea     rcx, [rbp+0B0h+var_108]
0x14000f704  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14000f709  nop
0x14000f70a  lea     rcx, [rsp+1B0h+var_148]
0x14000f70f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000f714  nop
0x14000f715  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14000f71c  mov     [rbp+0B0h+var_E0], rax
0x14000f720  lea     rcx, [rbp+0B0h+var_D0]
0x14000f724  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000f729  nop
0x14000f72a  lea     rcx, [rbp+0B0h+var_128]
0x14000f72e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000f733  nop
0x14000f734  lea     rcx, [rbp+0B0h+var_108]
0x14000f738  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14000f73d  mov     eax, dword ptr [rsp+1B0h+pUnk]
0x14000f741  jmp     loc_14000FE62
0x14000f746  lea     rax, ??_7?$_Func_impl_no_alloc@V?$_Mem_fn@P8NotificationManager@Service@Client@AppV@@EAA_K_N@Z@std@@_KPEAVNotificationManager@Service@Client@AppV@@_N@std@@6B@; const std::_Func_impl_no_alloc<std::_Mem_fn<unsigned __int64 (AppV::Client::Service::NotificationManager::*)(bool)>,unsigned __int64,AppV::Client::Service::NotificationManager *,bool>::`vftable'
0x14000f74d  mov     [rbp+0B0h+var_B0], rax
0x14000f751  lea     rax, ??_9NotificationManager@Service@Client@AppV@@$BBA@AA; [thunk]: AppV::Client::Service::NotificationManager::`vcall'{16,{flat}}
0x14000f758  mov     [rbp+0B0h+var_A8], rax
0x14000f75c  lea     rax, [rbp+0B0h+var_B0]
0x14000f760  mov     [rbp+0B0h+var_78], rax
0x14000f764  mov     rbx, [rdi+18h]
0x14000f768  lea     rax, [rbp+0B0h+var_70]
0x14000f76c  mov     [rsp+1B0h+var_158], rax
0x14000f771  mov     [rbp+0B0h+var_38], r15
0x14000f775  lea     rdx, [rbp+0B0h+var_70]
0x14000f779  lea     rcx, [rbp+0B0h+var_B0]
0x14000f77d  call    ?_Copy@?$_Func_impl_no_alloc@V?$_Mem_fn@P8NotificationManager@Service@Client@AppV@@EAA_K_N@Z@std@@_KPEAVNotificationManager@Service@Client@AppV@@_N@std@@EEBAPEAV?$_Func_base@_KPEAVNotificationManager@Service@Client@AppV@@_N@2@PEAX@Z; std::_Func_impl_no_alloc<std::_Mem_fn<unsigned __int64 (AppV::Client::Service::NotificationManager::*)(bool)>,unsigned __int64,AppV::Client::Service::NotificationManager *,bool>::_Copy(void *)
0x14000f782  mov     [rbp+0B0h+var_38], rax
0x14000f786  mov     [rbp+0B0h+var_30], 1
0x14000f78d  mov     [rbp+0B0h+var_28], rbx
0x14000f794  mov     ecx, 58h ; 'X'; Size
0x14000f799  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000f79e  mov     r14, rax
0x14000f7a1  mov     [rsp+1B0h+var_158], rax
0x14000f7a6  lea     rax, ??_7?$scope_guard_func_impl@V?$_Binder@U_Unforced@std@@AEAV?$function@$$A6A_KPEAVNotificationManager@Service@Client@AppV@@_N@Z@2@PEAVNotificationManager@Service@Client@AppV@@_N@std@@@utility@appv@@6B@; const appv::utility::scope_guard_func_impl<std::_Binder<std::_Unforced,std::function<unsigned __int64 (AppV::Client::Service::NotificationManager *,bool)> &,AppV::Client::Service::NotificationManager *,bool>>::`vftable'
0x14000f7ad  mov     [r14], rax
0x14000f7b0  lea     rbx, [r14+8]
0x14000f7b4  mov     [rsp+1B0h+pUnk], rbx
0x14000f7b9  mov     [rbx+38h], r15
0x14000f7bd  mov     rcx, [rbp+0B0h+var_38]
0x14000f7c1  test    rcx, rcx
0x14000f7c4  jz      short loc_14000F7D8
0x14000f7c6  mov     rax, [rcx]
0x14000f7c9  mov     rdx, rbx
0x14000f7cc  mov     rax, [rax]
0x14000f7cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f7d4  mov     [rbx+38h], rax
0x14000f7d8  mov     al, [rbp+0B0h+var_30]
0x14000f7de  mov     [rbx+40h], al
0x14000f7e1  mov     rax, [rbp+0B0h+var_28]
0x14000f7e8  mov     [rbx+48h], rax
0x14000f7ec  mov     [rsp+1B0h+var_170], r14
0x14000f7f1  mov     rcx, [rbp+0B0h+var_38]
0x14000f7f5  test    rcx, rcx
0x14000f7f8  jz      short loc_14000F814
0x14000f7fa  mov     rax, [rcx]
0x14000f7fd  lea     rdx, [rbp+0B0h+var_70]
0x14000f801  cmp     rcx, rdx
0x14000f804  setnz   dl
0x14000f807  mov     rax, [rax+20h]
0x14000f80b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f810  mov     [rbp+0B0h+var_38], r15
0x14000f814  mov     rcx, rdi
0x14000f817  call    ?ReportStartPending@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@AEAAXXZ; AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::ReportStartPending(void)
0x14000f81c  mov     rdx, [rdi+60h]; struct AppV::Client::ControllerRequests *
0x14000f820  mov     rcx, [rdi+18h]; struct AppV::Client::Service::NotificationManager *
0x14000f824  call    ?PrepareForCallers@AppVClientImpl@Service@Client@AppV@@SAKPEAVNotificationManager@234@PEAVControllerRequests@34@@Z; AppV::Client::Service::AppVClientImpl::PrepareForCallers(AppV::Client::Service::NotificationManager *,AppV::Client::ControllerRequests *)
0x14000f829  mov     ebx, eax
0x14000f82b  test    eax, eax
0x14000f82d  jz      short loc_14000F863
0x14000f82f  lea     rcx, [rsp+1B0h+var_170]; this
0x14000f834  call    ??1scope_guard@utility@appv@@QEAA@XZ; appv::utility::scope_guard::~scope_guard(void)
0x14000f839  nop
0x14000f83a  mov     r8, [rbp+0B0h+var_78]
0x14000f83e  test    r8, r8
0x14000f841  jz      short loc_14000F85C
0x14000f843  mov     rcx, [r8]
0x14000f846  mov     rax, [rcx+20h]
0x14000f84a  lea     rcx, [rbp+0B0h+var_B0]
0x14000f84e  cmp     r8, rcx
0x14000f851  setnz   dl
0x14000f854  mov     rcx, r8
0x14000f857  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f85c  mov     eax, ebx
0x14000f85e  jmp     loc_14000FE62
0x14000f863  mov     r14d, 18h
0x14000f869  mov     ecx, r14d; Size
0x14000f86c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000f871  mov     [rsp+1B0h+var_158], rax
0x14000f876  lea     rcx, ??_7?$scope_guard_func_impl@V?$_Binder@U_Unforced@std@@P6AXXZ$$V@std@@@utility@appv@@6B@; const appv::utility::scope_guard_func_impl<std::_Binder<std::_Unforced,void (*)(void),>>::`vftable'
0x14000f87d  mov     [rax], rcx
0x14000f880  lea     rcx, ?DisallowCallers@AppVClientImpl@Service@Client@AppV@@SAXXZ; AppV::Client::Service::AppVClientImpl::DisallowCallers(void)
0x14000f887  mov     [rax+8], rcx
0x14000f88b  mov     [rsp+1B0h+var_160], rax
0x14000f890  mov     rcx, rdi
0x14000f893  call    ?ReportStartPending@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@AEAAXXZ; AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::ReportStartPending(void)
0x14000f898  mov     [rsp+1B0h+var_168], r15
0x14000f89d  lea     rax, [rsp+1B0h+var_168]
0x14000f8a2  mov     [rsp+1B0h+ppv], rax; ppv
0x14000f8a7  lea     r9, IID_IGlobalOptions; riid
0x14000f8ae  xor     edx, edx; pUnkOuter
0x14000f8b0  lea     r8d, [r14-17h]; dwClsContext
0x14000f8b4  lea     rcx, CLSID_GlobalOptions; rclsid
0x14000f8bb  call    cs:__imp_CoCreateInstance
0x14000f8c1  mov     [rsp+1B0h+var_180], eax
0x14000f8c5  test    eax, eax
0x14000f8c7  jns     loc_14000F9C5
0x14000f8cd  lea     rdx, aAppvClientServ_0; "AppV::Client::Service::ClientServiceT<s"...
0x14000f8d4  lea     rcx, [rbp+0B0h+var_108]
0x14000f8d8  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14000f8dd  mov     [rbp+0B0h+var_E8], 386h
0x14000f8e4  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14000f8e9  xorps   xmm0, xmm0
0x14000f8ec  movups  [rsp+1B0h+var_148], xmm0
0x14000f8f1  mov     [rsp+1B0h+var_138], r15
0x14000f8f6  mov     [rbp+0B0h+var_130], r15
0x14000f8fa  lea     r8d, [r14+2Ch]
0x14000f8fe  lea     rdx, aFailedToObtain; "failed to obtain the COM global process"...
0x14000f905  lea     rcx, [rsp+1B0h+var_148]
0x14000f90a  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14000f90f  nop
0x14000f910  lea     r8, [rsp+1B0h+var_148]
0x14000f915  lea     rdx, [rbp+0B0h+var_E0]
0x14000f919  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14000f91e  nop
0x14000f91f  lea     rdx, [rsp+1B0h+var_180]
0x14000f924  mov     rcx, rax
0x14000f927  call    ??$?LJ@LogFormatter@AppV@@QEAAAEAV01@AEAJ@Z; AppV::LogFormatter::operator%<long>(long &)
0x14000f92c  mov     rbx, rax
0x14000f92f  xorps   xmm0, xmm0
0x14000f932  movups  [rbp+0B0h+var_128], xmm0
0x14000f936  mov     [rbp+0B0h+var_118], r15
0x14000f93a  mov     [rbp+0B0h+var_110], r15
0x14000f93e  lea     r8d, [r14-12h]
0x14000f942  lea     rdx, aClient; "Client"
0x14000f949  lea     rcx, [rbp+0B0h+var_128]
0x14000f94d  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14000f952  nop
0x14000f953  mov     r9, rbx
0x14000f956  lea     r8, [rbp+0B0h+var_128]
0x14000f95a  lea     edx, [r14-10h]
0x14000f95e  lea     rcx, [rbp+0B0h+var_108]
0x14000f962  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14000f967  nop
0x14000f968  lea     rcx, [rbp+0B0h+var_128]
0x14000f96c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000f971  nop
0x14000f972  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14000f979  mov     [rbp+0B0h+var_E0], rax
0x14000f97d  lea     rcx, [rbp+0B0h+var_D0]
0x14000f981  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000f986  nop
0x14000f987  lea     rcx, [rsp+1B0h+var_148]
0x14000f98c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000f991  nop
0x14000f992  lea     rcx, [rbp+0B0h+var_108]
0x14000f996  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14000f99b  mov     ebx, [rsp+1B0h+var_180]
0x14000f99f  mov     rcx, [rsp+1B0h+var_168]
0x14000f9a4  test    rcx, rcx
0x14000f9a7  jz      short loc_14000F9B6
0x14000f9a9  mov     rax, [rcx]
0x14000f9ac  mov     rax, [rax+10h]
0x14000f9b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f9b5  nop
0x14000f9b6  lea     rcx, [rsp+1B0h+var_160]; this
0x14000f9bb  call    ??1scope_guard@utility@appv@@QEAA@XZ; appv::utility::scope_guard::~scope_guard(void)
0x14000f9c0  jmp     loc_14000F82F
0x14000f9c5  mov     rcx, [rsp+1B0h+var_168]
0x14000f9ca  mov     rax, [rcx]
0x14000f9cd  mov     edx, 1
0x14000f9d2  lea     r8d, [rdx+1]
0x14000f9d6  mov     rax, [rax+18h]
0x14000f9da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f9df  mov     [rsp+1B0h+var_180], eax
0x14000f9e3  test    eax, eax
0x14000f9e5  jns     loc_14000FADE
0x14000f9eb  lea     rdx, aAppvClientServ_0; "AppV::Client::Service::ClientServiceT<s"...
0x14000f9f2  lea     rcx, [rbp+0B0h+var_108]
0x14000f9f6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14000f9fb  mov     [rbp+0B0h+var_E8], 398h
0x14000fa02  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14000fa07  xorps   xmm0, xmm0
0x14000fa0a  movups  [rsp+1B0h+var_148], xmm0
0x14000fa0f  mov     [rsp+1B0h+var_138], r15
0x14000fa14  mov     [rbp+0B0h+var_130], r15
0x14000fa18  mov     r8d, 45h ; 'E'
0x14000fa1e  lea     rdx, aFailedToSetThe; "failed to set the COM global exception "...
0x14000fa25  lea     rcx, [rsp+1B0h+var_148]
0x14000fa2a  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14000fa2f  nop
0x14000fa30  lea     r8, [rsp+1B0h+var_148]
0x14000fa35  lea     rdx, [rbp+0B0h+var_E0]
0x14000fa39  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14000fa3e  nop
0x14000fa3f  lea     rdx, [rsp+1B0h+var_180]
0x14000fa44  mov     rcx, rax
0x14000fa47  call    ??$?LJ@LogFormatter@AppV@@QEAAAEAV01@AEAJ@Z; AppV::LogFormatter::operator%<long>(long &)
0x14000fa4c  mov     rbx, rax
0x14000fa4f  xorps   xmm0, xmm0
0x14000fa52  movups  [rbp+0B0h+var_128], xmm0
0x14000fa56  mov     [rbp+0B0h+var_118], r15
0x14000fa5a  mov     [rbp+0B0h+var_110], r15
0x14000fa5e  mov     r8d, 6
0x14000fa64  lea     rdx, aClient; "Client"
0x14000fa6b  lea     rcx, [rbp+0B0h+var_128]
0x14000fa6f  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14000fa74  nop
0x14000fa75  mov     r9, rbx
0x14000fa78  lea     r8, [rbp+0B0h+var_128]
0x14000fa7c  mov     edx, 8
0x14000fa81  lea     rcx, [rbp+0B0h+var_108]
0x14000fa85  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14000fa8a  nop
0x14000fa8b  lea     rcx, [rbp+0B0h+var_128]
0x14000fa8f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000fa94  nop
0x14000fa95  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14000fa9c  mov     [rbp+0B0h+var_E0], rax
0x14000faa0  lea     rcx, [rbp+0B0h+var_D0]
0x14000faa4  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000faa9  nop
0x14000faaa  lea     rcx, [rsp+1B0h+var_148]
0x14000faaf  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000fab4  nop
0x14000fab5  lea     rcx, [rbp+0B0h+var_108]
0x14000fab9  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14000fabe  mov     ebx, [rsp+1B0h+var_180]
0x14000fac2  mov     rcx, [rsp+1B0h+var_168]
0x14000fac7  test    rcx, rcx
0x14000faca  jz      short loc_14000FAD9
0x14000facc  mov     rax, [rcx]
  ... truncated ...
```
