# AppV::Client::Service::AppVClientImpl::PrepareForCallers(AppV::Client::Service::NotificationManager *,AppV::Client::ControllerRequests *)

- ea: `0x14002a5a4`
- end: `0x14002a70f`
- name: `?PrepareForCallers@AppVClientImpl@Service@Client@AppV@@SAKPEAVNotificationManager@234@PEAVControllerRequests@34@@Z`
- size: `363`
- prototype: `unsigned int __fastcall(struct AppV::Client::Service::NotificationManager *, struct AppV::Client::ControllerRequests *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task`

## callers

- `0x14000f5ec`

## callees

- `0x140004280`
- `0x1400060e8`
- `0x140006304`
- `0x140006a08`
- `0x140008e64`
- `0x140010158`
- `0x14002a5a4`
- `0x14003c034`
- `0x14003c414`
- `0x14003c660`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x14002a5ed`
- `KERNEL32!CreateEventW` at `0x14002a5ed`
- `KERNEL32!GetLastError` at `0x14002a603`
- `KERNEL32!GetLastError` at `0x14002a603`

## string_xrefs

- `0x14002a60c`: `AppV::Client::Service::AppVClientImpl::APICaller::PrepareForCallers`
- `0x14002a63d`: `Failed to create event used to signal when API calls are idle, error = %1%`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall AppV::Client::Service::AppVClientImpl::PrepareForCallers(
        struct AppV::Client::Service::NotificationManager *a1,
        struct AppV::Client::ControllerRequests *a2)
{
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rax
  __int64 v7; // rbx
  __int64 result; // rax
  DWORD LastError; // [rsp+20h] [rbp-79h] BYREF
  _OWORD v10[2]; // [rsp+28h] [rbp-71h] BYREF
  _OWORD v11[2]; // [rsp+48h] [rbp-51h] BYREF
  char *v12[4]; // [rsp+68h] [rbp-31h] BYREF
  int v13; // [rsp+88h] [rbp-11h]
  void **v14; // [rsp+90h] [rbp-9h] BYREF
  char *v15; // [rsp+A0h] [rbp+7h] BYREF

  AppV::Client::Service::AppVClientImpl::APICaller::st_activeCallers = 0;
  if ( AppV::Client::Service::AppVClientImpl::APICaller::st_callersIdle )
    goto LABEL_4;
  AppV::Client::Service::AppVClientImpl::APICaller::st_callersIdle = CreateEventW(0, 1, 1, 0);
  if ( AppV::Client::Service::AppVClientImpl::APICaller::st_callersIdle )
    goto LABEL_4;
  LastError = GetLastError();
  std::string::string(v12, "AppV::Client::Service::AppVClientImpl::APICaller::PrepareForCallers");
  v13 = 361;
  AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v4);
  memset(v11, 0, sizeof(v11));
  std::wstring::_Construct<1,wchar_t const *>(
    (char **)v11,
    L"Failed to create event used to signal when API calls are idle, error = %1%",
    0x4Au);
  v6 = AppV::Log::fmt(v5, &v14, v11);
  v7 = AppV::LogFormatter::operator%<unsigned long>(v6, (__int64)&LastError);
  memset(v10, 0, sizeof(v10));
  std::wstring::_Construct<1,wchar_t const *>((char **)v10, L"Client", 6u);
  AppV::DecoratedLog::operator()((char *)v12, 8, (int)v10, v7);
  std::wstring::~wstring((char **)v10);
  v14 = &AppV::LogFormatter::`vftable';
  std::wstring::~wstring(&v15);
  std::wstring::~wstring((char **)v11);
  std::string::~string(v12);
  result = LastError;
  if ( !LastError )
  {
LABEL_4:
    AppV::Client::Service::AppVClientImpl::st_notificationManager = a1;
    AppV::Client::Service::AppVClientImpl::st_controllerRequests = a2;
    AppV::Client::Service::AppVClientImpl::st_allowCalls = 1;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14002a5a4  push    rbp
0x14002a5a6  push    rbx
0x14002a5a7  push    rsi
0x14002a5a8  push    rdi
0x14002a5a9  lea     rbp, [rsp-3Fh]
0x14002a5ae  sub     rsp, 0D8h
0x14002a5b5  mov     rax, cs:__security_cookie
0x14002a5bc  xor     rax, rsp
0x14002a5bf  mov     [rbp+57h+var_30], rax
0x14002a5c3  mov     rdi, rdx
0x14002a5c6  mov     rsi, rcx
0x14002a5c9  mov     cs:?st_activeCallers@APICaller@AppVClientImpl@Service@Client@AppV@@0KA, 0; ulong AppV::Client::Service::AppVClientImpl::APICaller::st_activeCallers
0x14002a5d3  cmp     cs:?st_callersIdle@APICaller@AppVClientImpl@Service@Client@AppV@@0Vevent@shared@softricity@@A, 0; softricity::shared::event AppV::Client::Service::AppVClientImpl::APICaller::st_callersIdle
0x14002a5db  jnz     loc_14002A6E0
0x14002a5e1  xor     r9d, r9d; lpName
0x14002a5e4  lea     edx, [r9+1]; bManualReset
0x14002a5e8  mov     r8d, edx; bInitialState
0x14002a5eb  xor     ecx, ecx; lpEventAttributes
0x14002a5ed  call    cs:__imp_CreateEventW
0x14002a5f3  mov     cs:?st_callersIdle@APICaller@AppVClientImpl@Service@Client@AppV@@0Vevent@shared@softricity@@A, rax; softricity::shared::event AppV::Client::Service::AppVClientImpl::APICaller::st_callersIdle
0x14002a5fa  test    rax, rax
0x14002a5fd  jnz     loc_14002A6E0
0x14002a603  call    cs:__imp_GetLastError
0x14002a609  mov     [rbp+57h+var_D0], eax
0x14002a60c  lea     rdx, aAppvClientServ_41; "AppV::Client::Service::AppVClientImpl::"...
0x14002a613  lea     rcx, [rbp+57h+var_88]
0x14002a617  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14002a61c  mov     [rbp+57h+var_68], 169h
0x14002a623  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14002a628  xorps   xmm0, xmm0
0x14002a62b  movups  [rbp+57h+var_A8], xmm0
0x14002a62f  xorps   xmm1, xmm1
0x14002a632  movdqu  [rbp+57h+var_98], xmm1
0x14002a637  mov     r8d, 4Ah ; 'J'
0x14002a63d  lea     rdx, aFailedToCreate_0; "Failed to create event used to signal w"...
0x14002a644  lea     rcx, [rbp+57h+var_A8]
0x14002a648  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14002a64d  nop
0x14002a64e  lea     r8, [rbp+57h+var_A8]
0x14002a652  lea     rdx, [rbp+57h+var_60]
0x14002a656  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14002a65b  nop
0x14002a65c  lea     rdx, [rbp+57h+var_D0]
0x14002a660  mov     rcx, rax
0x14002a663  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x14002a668  mov     rbx, rax
0x14002a66b  xorps   xmm0, xmm0
0x14002a66e  movups  [rbp+57h+var_C8], xmm0
0x14002a672  xorps   xmm1, xmm1
0x14002a675  movdqu  [rbp+57h+var_B8], xmm1
0x14002a67a  mov     r8d, 6
0x14002a680  lea     rdx, aClient; "Client"
0x14002a687  lea     rcx, [rbp+57h+var_C8]
0x14002a68b  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14002a690  nop
0x14002a691  mov     r9, rbx
0x14002a694  lea     r8, [rbp+57h+var_C8]
0x14002a698  mov     edx, 8
0x14002a69d  lea     rcx, [rbp+57h+var_88]
0x14002a6a1  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14002a6a6  nop
0x14002a6a7  lea     rcx, [rbp+57h+var_C8]
0x14002a6ab  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002a6b0  nop
0x14002a6b1  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14002a6b8  mov     [rbp+57h+var_60], rax
0x14002a6bc  lea     rcx, [rbp+57h+var_50]
0x14002a6c0  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002a6c5  nop
0x14002a6c6  lea     rcx, [rbp+57h+var_A8]
0x14002a6ca  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002a6cf  nop
0x14002a6d0  lea     rcx, [rbp+57h+var_88]
0x14002a6d4  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002a6d9  mov     eax, [rbp+57h+var_D0]
0x14002a6dc  test    eax, eax
0x14002a6de  jnz     short loc_14002A6F7
0x14002a6e0  mov     cs:?st_notificationManager@AppVClientImpl@Service@Client@AppV@@0REAVNotificationManager@234@EA, rsi; AppV::Client::Service::NotificationManager * AppV::Client::Service::AppVClientImpl::st_notificationManager
0x14002a6e7  mov     cs:?st_controllerRequests@AppVClientImpl@Service@Client@AppV@@0REAVControllerRequests@34@EA, rdi; AppV::Client::ControllerRequests * AppV::Client::Service::AppVClientImpl::st_controllerRequests
0x14002a6ee  mov     cs:?st_allowCalls@AppVClientImpl@Service@Client@AppV@@0_NC, 1; bool volatile AppV::Client::Service::AppVClientImpl::st_allowCalls
0x14002a6f5  xor     eax, eax
0x14002a6f7  mov     rcx, [rbp+57h+var_30]
0x14002a6fb  xor     rcx, rsp; StackCookie
0x14002a6fe  call    __security_check_cookie
0x14002a703  add     rsp, 0D8h
0x14002a70a  pop     rdi
0x14002a70b  pop     rsi
0x14002a70c  pop     rbx
0x14002a70d  pop     rbp
0x14002a70e  retn
```
