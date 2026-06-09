# AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::InitializeCOM(void)

- ea: `0x14000e140`
- end: `0x14000e4fe`
- name: `?InitializeCOM@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@AEAAKXZ`
- size: `958`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14000e504`

## callees

- `0x140004280`
- `0x1400042a4`
- `0x1400060e8`
- `0x140006304`
- `0x14000697c`
- `0x140008e64`
- `0x1400094bc`
- `0x14000a480`
- `0x14000a5a0`
- `0x14000e140`
- `0x140010158`
- `0x1400114b4`
- `0x14003c034`
- `0x14003c258`
- `0x14003c414`
- `0x14003c660`
- `0x14006a010`

## import_xrefs

- `ole32!CoUninitialize` at `0x14000e175`
- `ole32!CoInitializeSecurity` at `0x14000e3b3`
- `ole32!CoInitializeSecurity` at `0x14000e3b3`
- `ole32!CoInitializeEx` at `0x14000e16b`
- `ole32!CoInitializeEx` at `0x14000e16b`

## string_xrefs

- `0x14000e1d2`: `AppV::Client::Service::ClientServiceT<struct AppV::Client::Service::ClientServiceEmpty>::InitializeCOM`
- `0x14000e2d2`: `AppV::Client::Service::ClientServiceT<struct AppV::Client::Service::ClientServiceEmpty>::InitializeCOM`
- `0x14000e3c5`: `AppV::Client::Service::ClientServiceT<struct AppV::Client::Service::ClientServiceEmpty>::InitializeCOM`
- `0x14000e2ff`: `failed to create a security descriptor to use with CoInitializeSecurity`
- `0x14000e3f7`: `CoInitializeSecurity() failed, error = %1%`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::InitializeCOM(
        __int64 a1)
{
  _QWORD *v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rax
  __int64 v6; // rbx
  unsigned int v7; // ebx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rbx
  void (__fastcall ***v12)(_QWORD, __int64); // rcx
  HRESULT v14; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v15; // [rsp+58h] [rbp-A8h] BYREF
  void **v16; // [rsp+60h] [rbp-A0h] BYREF
  PSECURITY_DESCRIPTOR pSecDesc; // [rsp+68h] [rbp-98h]
  _QWORD *v18; // [rsp+70h] [rbp-90h]
  __int128 v19; // [rsp+78h] [rbp-88h] BYREF
  __int64 v20; // [rsp+88h] [rbp-78h]
  __int64 v21; // [rsp+90h] [rbp-70h]
  __int128 v22; // [rsp+98h] [rbp-68h] BYREF
  __int64 v23; // [rsp+A8h] [rbp-58h]
  __int64 v24; // [rsp+B0h] [rbp-50h]
  char *v25[4]; // [rsp+B8h] [rbp-48h] BYREF
  int v26; // [rsp+D8h] [rbp-28h]
  _QWORD v27[2]; // [rsp+E0h] [rbp-20h] BYREF
  char *v28[4]; // [rsp+F0h] [rbp-10h] BYREF

  AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::ReportStartPending(a1);
  v14 = CoInitializeEx(0, 0);
  v2 = operator new(0x18u);
  v18 = v2;
  *v2 = &appv::utility::scope_guard_func_impl<std::_Binder<std::_Unforced,void (*)(void),>>::`vftable';
  v2[1] = CoUninitialize;
  v15 = v2;
  if ( v14 >= 0 || (v15 = 0, (*(void (__fastcall **)(_QWORD *, __int64))*v2)(v2, 1), v14 == -2147417850) )
  {
    AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::ReportStartPending(a1);
    v16 = &ATL::CSecurityDesc::`vftable';
    pSecDesc = 0;
    if ( ConstructSecurityDescriptor((void **)&v16) )
    {
      v14 = CoInitializeSecurity(pSecDesc, -1, 0, 0, 4u, 2u, 0, 0, 0);
      if ( v14 >= 0 )
      {
        v12 = (void (__fastcall ***)(_QWORD, __int64))v15;
        v15 = 0;
        if ( v12 )
          (**v12)(v12, 1);
        v16 = &ATL::CSecurityDesc::`vftable';
        ATL::CSecurityDesc::Clear((ATL::CSecurityDesc *)&v16);
        v7 = 0;
      }
      else
      {
        std::string::string(
          v25,
          "AppV::Client::Service::ClientServiceT<struct AppV::Client::Service::ClientServiceEmpty>::InitializeCOM");
        v26 = 772;
        AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v8);
        v19 = 0;
        v20 = 0;
        v21 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v19, L"CoInitializeSecurity() failed, error = %1%", 0x2Au);
        v10 = AppV::Log::fmt(v9, v27, &v19);
        v11 = AppV::LogFormatter::operator%<long>(v10, (__int64)&v14);
        v22 = 0;
        v23 = 0;
        v24 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v22, L"Client", 6u);
        AppV::DecoratedLog::operator()((char *)v25, 8, (int)&v22, v11);
        std::wstring::~wstring((char **)&v22);
        v27[0] = &AppV::LogFormatter::`vftable';
        std::wstring::~wstring(v28);
        std::wstring::~wstring((char **)&v19);
        std::string::~string(v25);
        v7 = v14;
        v16 = &ATL::CSecurityDesc::`vftable';
        ATL::CSecurityDesc::Clear((ATL::CSecurityDesc *)&v16);
      }
    }
    else
    {
      std::string::string(
        v25,
        "AppV::Client::Service::ClientServiceT<struct AppV::Client::Service::ClientServiceEmpty>::InitializeCOM");
      v26 = 763;
      v19 = 0;
      v20 = 0;
      v21 = 0;
      std::wstring::_Construct<1,wchar_t const *>(
        (char **)&v19,
        L"failed to create a security descriptor to use with CoInitializeSecurity",
        0x47u);
      v22 = 0;
      v23 = 0;
      v24 = 0;
      std::wstring::_Construct<1,wchar_t const *>((char **)&v22, L"Client", 6u);
      AppV::DecoratedLog::operator()((char *)v25, 8, (int)&v22, (__int64)&v19);
      std::wstring::~wstring((char **)&v22);
      std::wstring::~wstring((char **)&v19);
      std::string::~string(v25);
      v16 = &ATL::CSecurityDesc::`vftable';
      ATL::CSecurityDesc::Clear((ATL::CSecurityDesc *)&v16);
      v7 = 1338;
    }
  }
  else
  {
    std::string::string(
      v25,
      "AppV::Client::Service::ClientServiceT<struct AppV::Client::Service::ClientServiceEmpty>::InitializeCOM");
    v26 = 752;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v3);
    v22 = 0;
    v23 = 0;
    v24 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v22, L"CoInitializeEx() failed, error = %1%", 0x24u);
    v5 = AppV::Log::fmt(v4, v27, &v22);
    v6 = AppV::LogFormatter::operator%<long>(v5, (__int64)&v14);
    v19 = 0;
    v20 = 0;
    v21 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v19, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v25, 8, (int)&v19, v6);
    std::wstring::~wstring((char **)&v19);
    v27[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v28);
    std::wstring::~wstring((char **)&v22);
    std::string::~string(v25);
    v7 = v14;
  }
  appv::utility::scope_guard::~scope_guard((appv::utility::scope_guard *)&v15);
  return v7;
}

```

## disassembly

```asm
0x14000e140  push    rbp
0x14000e142  push    rbx
0x14000e143  push    rsi
0x14000e144  push    rdi
0x14000e145  lea     rbp, [rsp-28h]
0x14000e14a  sub     rsp, 128h
0x14000e151  mov     rax, cs:__security_cookie
0x14000e158  xor     rax, rsp
0x14000e15b  mov     [rbp+40h+var_30], rax
0x14000e15f  mov     rdi, rcx
0x14000e162  call    ?ReportStartPending@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@AEAAXXZ; AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::ReportStartPending(void)
0x14000e167  xor     edx, edx; dwCoInit
0x14000e169  xor     ecx, ecx; pvReserved
0x14000e16b  call    cs:__imp_CoInitializeEx
0x14000e171  mov     [rsp+140h+var_F0], eax
0x14000e175  mov     rbx, cs:__imp_CoUninitialize
0x14000e17c  mov     ecx, 18h; Size
0x14000e181  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000e186  mov     rcx, rax
0x14000e189  mov     [rsp+140h+var_D0], rax
0x14000e18e  lea     rax, ??_7?$scope_guard_func_impl@V?$_Binder@U_Unforced@std@@P6AXXZ$$V@std@@@utility@appv@@6B@; const appv::utility::scope_guard_func_impl<std::_Binder<std::_Unforced,void (*)(void),>>::`vftable'
0x14000e195  mov     [rcx], rax
0x14000e198  mov     [rcx+8], rbx
0x14000e19c  mov     [rsp+140h+var_E8], rcx
0x14000e1a1  mov     ebx, 1
0x14000e1a6  xor     esi, esi
0x14000e1a8  cmp     [rsp+140h+var_F0], esi
0x14000e1ac  jge     loc_14000E2A7
0x14000e1b2  mov     [rsp+140h+var_E8], rsi
0x14000e1b7  mov     rax, [rcx]
0x14000e1ba  mov     edx, ebx
0x14000e1bc  mov     rax, [rax]
0x14000e1bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e1c4  cmp     [rsp+140h+var_F0], 80010106h
0x14000e1cc  jz      loc_14000E2A7
0x14000e1d2  lea     rdx, aAppvClientServ_3; "AppV::Client::Service::ClientServiceT<s"...
0x14000e1d9  lea     rcx, [rbp+40h+var_88]
0x14000e1dd  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14000e1e2  mov     [rbp+40h+var_68], 2F0h
0x14000e1e9  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14000e1ee  xorps   xmm0, xmm0
0x14000e1f1  movups  [rbp+40h+var_A8], xmm0
0x14000e1f5  mov     [rbp+40h+var_98], rsi
0x14000e1f9  mov     [rbp+40h+var_90], rsi
0x14000e1fd  lea     r8d, [rbx+23h]
0x14000e201  lea     rdx, aCoinitializeex; "CoInitializeEx() failed, error = %1%"
0x14000e208  lea     rcx, [rbp+40h+var_A8]
0x14000e20c  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14000e211  nop
0x14000e212  lea     r8, [rbp+40h+var_A8]
0x14000e216  lea     rdx, [rbp+40h+var_60]
0x14000e21a  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14000e21f  nop
0x14000e220  lea     rdx, [rsp+140h+var_F0]
0x14000e225  mov     rcx, rax
0x14000e228  call    ??$?LJ@LogFormatter@AppV@@QEAAAEAV01@AEAJ@Z; AppV::LogFormatter::operator%<long>(long &)
0x14000e22d  mov     rbx, rax
0x14000e230  xorps   xmm0, xmm0
0x14000e233  movups  [rsp+140h+var_C8], xmm0
0x14000e238  mov     [rbp+40h+var_B8], rsi
0x14000e23c  mov     [rbp+40h+var_B0], rsi
0x14000e240  lea     r8d, [rsi+6]
0x14000e244  lea     rdx, aClient; "Client"
0x14000e24b  lea     rcx, [rsp+140h+var_C8]
0x14000e250  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14000e255  nop
0x14000e256  mov     r9, rbx
0x14000e259  lea     r8, [rsp+140h+var_C8]
0x14000e25e  lea     edx, [rsi+8]
0x14000e261  lea     rcx, [rbp+40h+var_88]
0x14000e265  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14000e26a  nop
0x14000e26b  lea     rcx, [rsp+140h+var_C8]
0x14000e270  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000e275  nop
0x14000e276  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14000e27d  mov     [rbp+40h+var_60], rax
0x14000e281  lea     rcx, [rbp+40h+var_50]
0x14000e285  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000e28a  nop
0x14000e28b  lea     rcx, [rbp+40h+var_A8]
0x14000e28f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000e294  nop
0x14000e295  lea     rcx, [rbp+40h+var_88]
0x14000e299  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14000e29e  mov     ebx, [rsp+140h+var_F0]
0x14000e2a2  jmp     loc_14000E4DA
0x14000e2a7  mov     rcx, rdi
0x14000e2aa  call    ?ReportStartPending@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@AEAAXXZ; AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::ReportStartPending(void)
0x14000e2af  lea     rdi, ??_7CSecurityDesc@ATL@@6B@; const ATL::CSecurityDesc::`vftable'
0x14000e2b6  mov     [rsp+140h+var_E0], rdi
0x14000e2bb  mov     [rsp+140h+pSecDesc], rsi
0x14000e2c0  lea     rcx, [rsp+140h+var_E0]; this
0x14000e2c5  call    ConstructSecurityDescriptor
0x14000e2ca  test    al, al
0x14000e2cc  jnz     loc_14000E387
0x14000e2d2  lea     rdx, aAppvClientServ_3; "AppV::Client::Service::ClientServiceT<s"...
0x14000e2d9  lea     rcx, [rbp+40h+var_88]
0x14000e2dd  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14000e2e2  mov     [rbp+40h+var_68], 2FBh
0x14000e2e9  xorps   xmm0, xmm0
0x14000e2ec  movups  [rsp+140h+var_C8], xmm0
0x14000e2f1  mov     [rbp+40h+var_B8], rsi
0x14000e2f5  mov     [rbp+40h+var_B0], rsi
0x14000e2f9  mov     r8d, 47h ; 'G'
0x14000e2ff  lea     rdx, aFailedToCreate_3; "failed to create a security descriptor "...
0x14000e306  lea     rcx, [rsp+140h+var_C8]
0x14000e30b  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14000e310  nop
0x14000e311  xorps   xmm0, xmm0
0x14000e314  movups  [rbp+40h+var_A8], xmm0
0x14000e318  mov     [rbp+40h+var_98], rsi
0x14000e31c  mov     [rbp+40h+var_90], rsi
0x14000e320  mov     r8d, 6
0x14000e326  lea     rdx, aClient; "Client"
0x14000e32d  lea     rcx, [rbp+40h+var_A8]
0x14000e331  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14000e336  nop
0x14000e337  lea     r9, [rsp+140h+var_C8]
0x14000e33c  lea     r8, [rbp+40h+var_A8]
0x14000e340  mov     edx, 8
0x14000e345  lea     rcx, [rbp+40h+var_88]
0x14000e349  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,std::wstring const &)
0x14000e34e  nop
0x14000e34f  lea     rcx, [rbp+40h+var_A8]
0x14000e353  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000e358  nop
0x14000e359  lea     rcx, [rsp+140h+var_C8]
0x14000e35e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000e363  nop
0x14000e364  lea     rcx, [rbp+40h+var_88]
0x14000e368  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14000e36d  nop
0x14000e36e  mov     [rsp+140h+var_E0], rdi
0x14000e373  lea     rcx, [rsp+140h+var_E0]; this
0x14000e378  call    ?Clear@CSecurityDesc@ATL@@MEAAXXZ; ATL::CSecurityDesc::Clear(void)
0x14000e37d  mov     ebx, 53Ah
0x14000e382  jmp     loc_14000E4DA
0x14000e387  mov     [rsp+140h+pReserved3], rsi; pReserved3
0x14000e38c  mov     [rsp+140h+dwCapabilities], esi; dwCapabilities
0x14000e390  mov     [rsp+140h+pAuthList], rsi; pAuthList
0x14000e395  mov     [rsp+140h+dwImpLevel], 2; dwImpLevel
0x14000e39d  mov     [rsp+140h+dwAuthnLevel], 4; dwAuthnLevel
0x14000e3a5  xor     r9d, r9d; pReserved1
0x14000e3a8  xor     r8d, r8d; asAuthSvc
0x14000e3ab  or      edx, 0FFFFFFFFh; cAuthSvc
0x14000e3ae  mov     rcx, [rsp+140h+pSecDesc]; pSecDesc
0x14000e3b3  call    cs:__imp_CoInitializeSecurity
0x14000e3b9  mov     [rsp+140h+var_F0], eax
0x14000e3bd  test    eax, eax
0x14000e3bf  jns     loc_14000E4AC
0x14000e3c5  lea     rdx, aAppvClientServ_3; "AppV::Client::Service::ClientServiceT<s"...
0x14000e3cc  lea     rcx, [rbp+40h+var_88]
0x14000e3d0  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14000e3d5  mov     [rbp+40h+var_68], 304h
0x14000e3dc  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14000e3e1  xorps   xmm0, xmm0
0x14000e3e4  movups  [rsp+140h+var_C8], xmm0
0x14000e3e9  mov     [rbp+40h+var_B8], rsi
0x14000e3ed  mov     [rbp+40h+var_B0], rsi
0x14000e3f1  mov     r8d, 2Ah ; '*'
0x14000e3f7  lea     rdx, aCoinitializese; "CoInitializeSecurity() failed, error = "...
0x14000e3fe  lea     rcx, [rsp+140h+var_C8]
0x14000e403  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14000e408  nop
0x14000e409  lea     r8, [rsp+140h+var_C8]
0x14000e40e  lea     rdx, [rbp+40h+var_60]
0x14000e412  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14000e417  nop
0x14000e418  lea     rdx, [rsp+140h+var_F0]
0x14000e41d  mov     rcx, rax
0x14000e420  call    ??$?LJ@LogFormatter@AppV@@QEAAAEAV01@AEAJ@Z; AppV::LogFormatter::operator%<long>(long &)
0x14000e425  mov     rbx, rax
0x14000e428  xorps   xmm0, xmm0
0x14000e42b  movups  [rbp+40h+var_A8], xmm0
0x14000e42f  mov     [rbp+40h+var_98], rsi
0x14000e433  mov     [rbp+40h+var_90], rsi
0x14000e437  mov     r8d, 6
0x14000e43d  lea     rdx, aClient; "Client"
0x14000e444  lea     rcx, [rbp+40h+var_A8]
0x14000e448  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14000e44d  nop
0x14000e44e  mov     r9, rbx
0x14000e451  lea     r8, [rbp+40h+var_A8]
0x14000e455  mov     edx, 8
0x14000e45a  lea     rcx, [rbp+40h+var_88]
0x14000e45e  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14000e463  nop
0x14000e464  lea     rcx, [rbp+40h+var_A8]
0x14000e468  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000e46d  nop
0x14000e46e  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14000e475  mov     [rbp+40h+var_60], rax
0x14000e479  lea     rcx, [rbp+40h+var_50]
0x14000e47d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000e482  nop
0x14000e483  lea     rcx, [rsp+140h+var_C8]
0x14000e488  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000e48d  nop
0x14000e48e  lea     rcx, [rbp+40h+var_88]
0x14000e492  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14000e497  mov     ebx, [rsp+140h+var_F0]
0x14000e49b  mov     [rsp+140h+var_E0], rdi
0x14000e4a0  lea     rcx, [rsp+140h+var_E0]; this
0x14000e4a5  call    ?Clear@CSecurityDesc@ATL@@MEAAXXZ; ATL::CSecurityDesc::Clear(void)
0x14000e4aa  jmp     short loc_14000E4DA
0x14000e4ac  mov     rcx, [rsp+140h+var_E8]
0x14000e4b1  mov     [rsp+140h+var_E8], rsi
0x14000e4b6  test    rcx, rcx
0x14000e4b9  jz      short loc_14000E4C9
0x14000e4bb  mov     rax, [rcx]
0x14000e4be  mov     edx, ebx
0x14000e4c0  mov     rax, [rax]
0x14000e4c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e4c8  nop
0x14000e4c9  mov     [rsp+140h+var_E0], rdi
0x14000e4ce  lea     rcx, [rsp+140h+var_E0]; this
0x14000e4d3  call    ?Clear@CSecurityDesc@ATL@@MEAAXXZ; ATL::CSecurityDesc::Clear(void)
0x14000e4d8  mov     ebx, esi
0x14000e4da  lea     rcx, [rsp+140h+var_E8]; this
0x14000e4df  call    ??1scope_guard@utility@appv@@QEAA@XZ; appv::utility::scope_guard::~scope_guard(void)
0x14000e4e4  mov     eax, ebx
0x14000e4e6  mov     rcx, [rbp+40h+var_30]
0x14000e4ea  xor     rcx, rsp; StackCookie
0x14000e4ed  call    __security_check_cookie
0x14000e4f2  add     rsp, 128h
0x14000e4f9  pop     rdi
0x14000e4fa  pop     rsi
0x14000e4fb  pop     rbx
0x14000e4fc  pop     rbp
0x14000e4fd  retn
```
