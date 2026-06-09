# AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::DeinitializePublicAPI(bool)

- ea: `0x14000b640`
- end: `0x14000b917`
- name: `?DeinitializePublicAPI@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@AEAAK_N@Z`
- size: `727`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `service_task`

## callers

- `0x14000af00`

## callees

- `0x140004280`
- `0x1400060e8`
- `0x140006304`
- `0x14000697c`
- `0x140008e64`
- `0x14000b640`
- `0x140010158`
- `0x1400114b4`
- `0x1400114f0`
- `0x14003c034`
- `0x14003c414`
- `0x14003c660`
- `0x14006a010`

## import_xrefs

- `ole32!CoSuspendClassObjects` at `0x14000b6f3`
- `ole32!CoSuspendClassObjects` at `0x14000b6f3`
- `ole32!CoRevokeClassObject` at `0x14000b7f9`
- `ole32!CoRevokeClassObject` at `0x14000b7f9`

## string_xrefs

- `0x14000b704`: `AppV::Client::Service::ClientServiceT<struct AppV::Client::Service::ClientServiceEmpty>::DeinitializePublicAPI`
- `0x14000b80a`: `AppV::Client::Service::ClientServiceT<struct AppV::Client::Service::ClientServiceEmpty>::DeinitializePublicAPI`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::DeinitializePublicAPI(
        __int64 a1,
        char a2)
{
  __int64 v4; // rax
  unsigned int v5; // esi
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rbx
  HRESULT v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rbx
  HRESULT v16; // [rsp+20h] [rbp-69h] BYREF
  __int128 v17; // [rsp+28h] [rbp-61h] BYREF
  __int128 v18; // [rsp+38h] [rbp-51h]
  __int128 v19; // [rsp+48h] [rbp-41h] BYREF
  __int128 v20; // [rsp+58h] [rbp-31h]
  char *v21[4]; // [rsp+68h] [rbp-21h] BYREF
  int v22; // [rsp+88h] [rbp-1h]
  _QWORD v23[2]; // [rsp+90h] [rbp+7h] BYREF
  char *v24[4]; // [rsp+A0h] [rbp+17h] BYREF

  if ( a2 )
    AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::ReportStartPending(a1);
  else
    AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::ReportStopPending(a1);
  AppV::Client::Service::AppVClientImpl::st_allowCalls = 0;
  AppV::Client::Service::AppVClientImpl::st_notificationManager = 0;
  AppV::Client::Service::AppVClientImpl::st_controllerRequests = 0;
  if ( a2 )
    AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::ReportStartPending(a1);
  else
    AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::ReportStopPending(a1);
  v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 24) + 16LL))(*(_QWORD *)(a1 + 24), 0);
  v5 = v4;
  if ( (v4 & 0x8000000000LL) != 0 )
  {
    v5 = 0;
  }
  else if ( (v4 & 0x2000000000LL) == 0 || !(_DWORD)v4 )
  {
    v5 = 351;
  }
  if ( a2 )
    AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::ReportStartPending(a1);
  else
    AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::ReportStopPending(a1);
  v16 = CoSuspendClassObjects();
  if ( v16 < 0 )
  {
    std::string::string(
      v21,
      "AppV::Client::Service::ClientServiceT<struct AppV::Client::Service::ClientServiceEmpty>::DeinitializePublicAPI");
    v22 = 1141;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v6);
    v19 = 0;
    v20 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v19, L"CoSuspendClassObjects() failed, error = %1%", 0x2Bu);
    v8 = AppV::Log::fmt(v7, v23, &v19);
    v9 = AppV::LogFormatter::operator%<long>(v8, (__int64)&v16);
    v17 = 0;
    v18 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v17, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v21, 8, (int)&v17, v9);
    std::wstring::~wstring((char **)&v17);
    v23[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v24);
    std::wstring::~wstring((char **)&v19);
    std::string::~string(v21);
    if ( !v5 )
      v5 = v16;
  }
  if ( a2 )
    AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::ReportStartPending(a1);
  else
    AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::ReportStopPending(a1);
  if ( dwRegister )
    v10 = CoRevokeClassObject(dwRegister);
  else
    v10 = 0;
  v16 = v10;
  if ( v10 < 0 )
  {
    std::string::string(
      v21,
      "AppV::Client::Service::ClientServiceT<struct AppV::Client::Service::ClientServiceEmpty>::DeinitializePublicAPI");
    v22 = 1151;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v11);
    v17 = 0;
    v18 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v17, L"CoRevokeClassObject() failed, error = %1%", 0x29u);
    v13 = AppV::Log::fmt(v12, v23, &v17);
    v14 = AppV::LogFormatter::operator%<long>(v13, (__int64)&v16);
    v19 = 0;
    v20 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v19, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v21, 8, (int)&v19, v14);
    std::wstring::~wstring((char **)&v19);
    v23[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v24);
    std::wstring::~wstring((char **)&v17);
    std::string::~string(v21);
    if ( !v5 )
      v5 = v16;
  }
  if ( a2 )
    AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::ReportStartPending(a1);
  else
    AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::ReportStopPending(a1);
  return v5;
}

```

## disassembly

```asm
0x14000b640  mov     [rsp-8+arg_8], rbx
0x14000b645  mov     [rsp-8+arg_10], rsi
0x14000b64a  push    rbp
0x14000b64b  push    rdi
0x14000b64c  push    r14
0x14000b64e  lea     rbp, [rsp-47h]
0x14000b653  sub     rsp, 0D0h
0x14000b65a  mov     rax, cs:__security_cookie
0x14000b661  xor     rax, rsp
0x14000b664  mov     [rbp+57h+var_20], rax
0x14000b668  mov     r14b, dl
0x14000b66b  mov     rdi, rcx
0x14000b66e  test    dl, dl
0x14000b670  jz      short loc_14000B679
0x14000b672  call    ?ReportStartPending@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@AEAAXXZ; AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::ReportStartPending(void)
0x14000b677  jmp     short loc_14000B67E
0x14000b679  call    ?ReportStopPending@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@AEAAXXZ; AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::ReportStopPending(void)
0x14000b67e  mov     cs:?st_allowCalls@AppVClientImpl@Service@Client@AppV@@0_NC, 0; bool volatile AppV::Client::Service::AppVClientImpl::st_allowCalls
0x14000b685  mov     cs:?st_notificationManager@AppVClientImpl@Service@Client@AppV@@0REAVNotificationManager@234@EA, 0; AppV::Client::Service::NotificationManager * AppV::Client::Service::AppVClientImpl::st_notificationManager
0x14000b690  mov     cs:?st_controllerRequests@AppVClientImpl@Service@Client@AppV@@0REAVControllerRequests@34@EA, 0; AppV::Client::ControllerRequests * AppV::Client::Service::AppVClientImpl::st_controllerRequests
0x14000b69b  mov     rcx, rdi
0x14000b69e  test    r14b, r14b
0x14000b6a1  jz      short loc_14000B6AA
0x14000b6a3  call    ?ReportStartPending@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@AEAAXXZ; AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::ReportStartPending(void)
0x14000b6a8  jmp     short loc_14000B6AF
0x14000b6aa  call    ?ReportStopPending@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@AEAAXXZ; AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::ReportStopPending(void)
0x14000b6af  mov     rcx, [rdi+18h]
0x14000b6b3  mov     rax, [rcx]
0x14000b6b6  xor     edx, edx
0x14000b6b8  mov     rax, [rax+10h]
0x14000b6bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b6c1  mov     rsi, rax
0x14000b6c4  bt      rax, 27h ; '''
0x14000b6c9  jnb     short loc_14000B6CF
0x14000b6cb  xor     esi, esi
0x14000b6cd  jmp     short loc_14000B6DF
0x14000b6cf  bt      rax, 25h ; '%'
0x14000b6d4  jnb     short loc_14000B6DA
0x14000b6d6  test    eax, eax
0x14000b6d8  jnz     short loc_14000B6DF
0x14000b6da  mov     esi, 15Fh
0x14000b6df  mov     rcx, rdi
0x14000b6e2  test    r14b, r14b
0x14000b6e5  jz      short loc_14000B6EE
0x14000b6e7  call    ?ReportStartPending@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@AEAAXXZ; AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::ReportStartPending(void)
0x14000b6ec  jmp     short loc_14000B6F3
0x14000b6ee  call    ?ReportStopPending@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@AEAAXXZ; AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::ReportStopPending(void)
0x14000b6f3  call    cs:__imp_CoSuspendClassObjects
0x14000b6f9  mov     [rbp+57h+var_C0], eax
0x14000b6fc  test    eax, eax
0x14000b6fe  jns     loc_14000B7D7
0x14000b704  lea     rdx, aAppvClientServ_8; "AppV::Client::Service::ClientServiceT<s"...
0x14000b70b  lea     rcx, [rbp+57h+var_78]
0x14000b70f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14000b714  mov     [rbp+57h+var_58], 475h
0x14000b71b  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14000b720  xorps   xmm0, xmm0
0x14000b723  movups  [rbp+57h+var_98], xmm0
0x14000b727  xorps   xmm1, xmm1
0x14000b72a  movdqu  [rbp+57h+var_88], xmm1
0x14000b72f  mov     r8d, 2Bh ; '+'
0x14000b735  lea     rdx, aCosuspendclass; "CoSuspendClassObjects() failed, error ="...
0x14000b73c  lea     rcx, [rbp+57h+var_98]
0x14000b740  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14000b745  nop
0x14000b746  lea     r8, [rbp+57h+var_98]
0x14000b74a  lea     rdx, [rbp+57h+var_50]
0x14000b74e  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14000b753  nop
0x14000b754  lea     rdx, [rbp+57h+var_C0]
0x14000b758  mov     rcx, rax
0x14000b75b  call    ??$?LJ@LogFormatter@AppV@@QEAAAEAV01@AEAJ@Z; AppV::LogFormatter::operator%<long>(long &)
0x14000b760  mov     rbx, rax
0x14000b763  xorps   xmm0, xmm0
0x14000b766  movups  [rbp+57h+var_B8], xmm0
0x14000b76a  xorps   xmm1, xmm1
0x14000b76d  movdqu  [rbp+57h+var_A8], xmm1
0x14000b772  mov     r8d, 6
0x14000b778  lea     rdx, aClient; "Client"
0x14000b77f  lea     rcx, [rbp+57h+var_B8]
0x14000b783  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14000b788  nop
0x14000b789  mov     r9, rbx
0x14000b78c  lea     r8, [rbp+57h+var_B8]
0x14000b790  mov     edx, 8
0x14000b795  lea     rcx, [rbp+57h+var_78]
0x14000b799  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14000b79e  nop
0x14000b79f  lea     rcx, [rbp+57h+var_B8]
0x14000b7a3  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000b7a8  nop
0x14000b7a9  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14000b7b0  mov     [rbp+57h+var_50], rax
0x14000b7b4  lea     rcx, [rbp+57h+var_40]
0x14000b7b8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000b7bd  nop
0x14000b7be  lea     rcx, [rbp+57h+var_98]
0x14000b7c2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000b7c7  nop
0x14000b7c8  lea     rcx, [rbp+57h+var_78]
0x14000b7cc  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14000b7d1  test    esi, esi
0x14000b7d3  cmovz   esi, [rbp+57h+var_C0]
0x14000b7d7  mov     rcx, rdi
0x14000b7da  test    r14b, r14b
0x14000b7dd  jz      short loc_14000B7E6
0x14000b7df  call    ?ReportStartPending@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@AEAAXXZ; AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::ReportStartPending(void)
0x14000b7e4  jmp     short loc_14000B7EB
0x14000b7e6  call    ?ReportStopPending@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@AEAAXXZ; AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::ReportStopPending(void)
0x14000b7eb  mov     ecx, cs:dwRegister; dwRegister
0x14000b7f1  test    ecx, ecx
0x14000b7f3  jnz     short loc_14000B7F9
0x14000b7f5  xor     eax, eax
0x14000b7f7  jmp     short loc_14000B7FF
0x14000b7f9  call    cs:__imp_CoRevokeClassObject
0x14000b7ff  mov     [rbp+57h+var_C0], eax
0x14000b802  test    eax, eax
0x14000b804  jns     loc_14000B8DD
0x14000b80a  lea     rdx, aAppvClientServ_8; "AppV::Client::Service::ClientServiceT<s"...
0x14000b811  lea     rcx, [rbp+57h+var_78]
0x14000b815  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14000b81a  mov     [rbp+57h+var_58], 47Fh
0x14000b821  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14000b826  xorps   xmm0, xmm0
0x14000b829  movups  [rbp+57h+var_B8], xmm0
0x14000b82d  xorps   xmm1, xmm1
0x14000b830  movdqu  [rbp+57h+var_A8], xmm1
0x14000b835  mov     r8d, 29h ; ')'
0x14000b83b  lea     rdx, aCorevokeclasso; "CoRevokeClassObject() failed, error = %"...
0x14000b842  lea     rcx, [rbp+57h+var_B8]
0x14000b846  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14000b84b  nop
0x14000b84c  lea     r8, [rbp+57h+var_B8]
0x14000b850  lea     rdx, [rbp+57h+var_50]
0x14000b854  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14000b859  nop
0x14000b85a  lea     rdx, [rbp+57h+var_C0]
0x14000b85e  mov     rcx, rax
0x14000b861  call    ??$?LJ@LogFormatter@AppV@@QEAAAEAV01@AEAJ@Z; AppV::LogFormatter::operator%<long>(long &)
0x14000b866  mov     rbx, rax
0x14000b869  xorps   xmm0, xmm0
0x14000b86c  movups  [rbp+57h+var_98], xmm0
0x14000b870  xorps   xmm1, xmm1
0x14000b873  movdqu  [rbp+57h+var_88], xmm1
0x14000b878  mov     r8d, 6
0x14000b87e  lea     rdx, aClient; "Client"
0x14000b885  lea     rcx, [rbp+57h+var_98]
0x14000b889  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14000b88e  nop
0x14000b88f  mov     r9, rbx
0x14000b892  lea     r8, [rbp+57h+var_98]
0x14000b896  mov     edx, 8
0x14000b89b  lea     rcx, [rbp+57h+var_78]
0x14000b89f  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14000b8a4  nop
0x14000b8a5  lea     rcx, [rbp+57h+var_98]
0x14000b8a9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000b8ae  nop
0x14000b8af  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14000b8b6  mov     [rbp+57h+var_50], rax
0x14000b8ba  lea     rcx, [rbp+57h+var_40]
0x14000b8be  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000b8c3  nop
0x14000b8c4  lea     rcx, [rbp+57h+var_B8]
0x14000b8c8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000b8cd  nop
0x14000b8ce  lea     rcx, [rbp+57h+var_78]
0x14000b8d2  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14000b8d7  test    esi, esi
0x14000b8d9  cmovz   esi, [rbp+57h+var_C0]
0x14000b8dd  mov     rcx, rdi
0x14000b8e0  test    r14b, r14b
0x14000b8e3  jz      short loc_14000B8EC
0x14000b8e5  call    ?ReportStartPending@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@AEAAXXZ; AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::ReportStartPending(void)
0x14000b8ea  jmp     short loc_14000B8F1
0x14000b8ec  call    ?ReportStopPending@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@AEAAXXZ; AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::ReportStopPending(void)
0x14000b8f1  mov     eax, esi
0x14000b8f3  mov     rcx, [rbp+57h+var_20]
0x14000b8f7  xor     rcx, rsp; StackCookie
0x14000b8fa  call    __security_check_cookie
0x14000b8ff  lea     r11, [rsp+0E0h+var_10]
0x14000b907  mov     rbx, [r11+28h]
0x14000b90b  mov     rsi, [r11+30h]
0x14000b90f  mov     rsp, r11
0x14000b912  pop     r14
0x14000b914  pop     rdi
0x14000b915  pop     rbp
0x14000b916  retn
```
