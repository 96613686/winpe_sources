# AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::ServiceControlHandlerEx(ulong,ulong,void *)

- ea: `0x140011924`
- end: `0x140011bb6`
- name: `?ServiceControlHandlerEx@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@AEAAKKKPEAX@Z`
- size: `658`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14000d760`

## callees

- `0x140004280`
- `0x1400060e8`
- `0x140006304`
- `0x140006a94`
- `0x140008224`
- `0x140008e64`
- `0x14000bbc4`
- `0x14000d7d4`
- `0x14000dd08`
- `0x140010158`
- `0x140011924`
- `0x1400147fc`
- `0x14003c034`
- `0x14003c414`
- `0x14003c660`

## import_xrefs

- `ADVAPI32!EventActivityIdControl` at `0x140011b0e`
- `ADVAPI32!EventActivityIdControl` at `0x140011b75`
- `ADVAPI32!EventActivityIdControl` at `0x140011b8b`
- `ADVAPI32!EventActivityIdControl` at `0x140011b0e`
- `ADVAPI32!EventActivityIdControl` at `0x140011b75`
- `ADVAPI32!EventActivityIdControl` at `0x140011b8b`
- `USER32!PostThreadMessageW` at `0x140011b5f`
- `USER32!PostThreadMessageW` at `0x140011b5f`

## string_xrefs

- `0x14001195f`: `AppV::Client::Service::ClientServiceT<struct AppV::Client::Service::ClientServiceEmpty>::ServiceControlHandlerEx`
- `0x140011993`: `Service Control: %1%`
- `0x1400119ec`: `ServiceControlShutdown`
- `0x1400119fe`: `ServiceControlStop`
- `0x1400119f5`: `ServiceControlInterrogate`
- `0x1400119da`: `ServiceControlSessionChange`
- `0x1400119e3`: `ServiceControlPowerEvent`
- `0x1400119d1`: `Unknown ServiceControl Type`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::ServiceControlHandlerEx(
        __int64 a1,
        int a2,
        unsigned int a3,
        __int64 a4)
{
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // r8
  const wchar_t *v11; // rax
  __int64 v12; // rbx
  unsigned int v13; // ebx
  int v14; // edi
  int v15; // edi
  int v16; // edi
  int v17; // edi
  __int64 v18; // rdi
  __int64 v19; // rbx
  __int64 v20; // r8
  _BYTE ActivityId[36]; // [rsp+30h] [rbp-D0h] BYREF
  _OWORD v23[2]; // [rsp+58h] [rbp-A8h] BYREF
  char *v24[4]; // [rsp+78h] [rbp-88h] BYREF
  int v25; // [rsp+98h] [rbp-68h]
  _BYTE v26[4]; // [rsp+A0h] [rbp-60h] BYREF
  GUID v27; // [rsp+A4h] [rbp-5Ch] BYREF
  void **v28; // [rsp+C8h] [rbp-38h] BYREF
  char *v29; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v30[2]; // [rsp+F8h] [rbp-8h] BYREF

  AppV::ETW::ScopedActivity<AppV::ETW::UserModeActivityIdControl>::ScopedActivity<AppV::ETW::UserModeActivityIdControl>((__int64)v26);
  std::string::string(
    v24,
    "AppV::Client::Service::ClientServiceT<struct AppV::Client::Service::ClientServiceEmpty>::ServiceControlHandlerEx");
  v25 = 521;
  AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v8);
  memset(ActivityId, 0, 32);
  std::wstring::_Construct<1,wchar_t const *>((char **)ActivityId, L"Service Control: %1%", 0x14u);
  v10 = AppV::Log::fmt(v9, &v28, ActivityId);
  switch ( a2 )
  {
    case 1:
      v11 = L"ServiceControlStop";
      break;
    case 4:
      v11 = L"ServiceControlInterrogate";
      break;
    case 5:
      v11 = L"ServiceControlShutdown";
      break;
    case 13:
      v11 = L"ServiceControlPowerEvent";
      break;
    case 14:
      v11 = L"ServiceControlSessionChange";
      break;
    default:
      v11 = L"Unknown ServiceControl Type";
      break;
  }
  v30[0] = v11;
  v12 = AppV::LogFormatter::operator%<wchar_t const *>(v10, v30);
  memset(v23, 0, sizeof(v23));
  std::wstring::_Construct<1,wchar_t const *>((char **)v23, L"Client", 6u);
  AppV::DecoratedLog::operator()((char *)v24, 8, (int)v23, v12);
  std::wstring::~wstring((char **)v23);
  v28 = &AppV::LogFormatter::`vftable';
  std::wstring::~wstring(&v29);
  std::wstring::~wstring((char **)ActivityId);
  std::string::~string(v24);
  v13 = 120;
  v14 = a2 - 1;
  if ( v14 )
  {
    v15 = v14 - 3;
    if ( !v15 )
    {
LABEL_19:
      v13 = 0;
      goto LABEL_26;
    }
    v16 = v15 - 1;
    if ( v16 )
    {
      v17 = v16 - 8;
      if ( v17 )
      {
        if ( v17 != 1 )
          goto LABEL_26;
        AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::HandleSessionChange(
          a1,
          a3,
          a4);
      }
      else
      {
        AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::HandlePowerEvent(a1, a3, a4);
      }
      goto LABEL_19;
    }
  }
  AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::GenerateCorrelationIDs();
  v18 = *(_QWORD *)&AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::st_shutdownCorrelationID.Data1;
  v19 = *(_QWORD *)AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::st_shutdownCorrelationID.Data4;
  ActivityId[0] = 0;
  *(GUID *)&ActivityId[20] = GUID_NULL;
  *(GUID *)&ActivityId[4] = AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::st_shutdownCorrelationID;
  if ( !EventActivityIdControl(4u, (LPGUID)&ActivityId[4]) )
  {
    *(_QWORD *)&ActivityId[20] = v18;
    *(_QWORD *)&ActivityId[28] = v19;
    ActivityId[0] = 1;
  }
  if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(
      PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
      Service_ShutdownBegin,
      v20,
      1,
      v30);
  PostThreadMessageW(*(_DWORD *)(a1 + 72), 0x12u, 0, 0);
  v13 = 0;
  if ( ActivityId[0] )
    EventActivityIdControl(2u, (LPGUID)&ActivityId[4]);
LABEL_26:
  if ( v26[0] )
    EventActivityIdControl(2u, &v27);
  return v13;
}

```

## disassembly

```asm
0x140011924  mov     [rsp-8+arg_8], rbx
0x140011929  push    rbp
0x14001192a  push    rsi
0x14001192b  push    rdi
0x14001192c  push    r14
0x14001192e  push    r15
0x140011930  lea     rbp, [rsp-10h]
0x140011935  sub     rsp, 110h
0x14001193c  mov     rax, cs:__security_cookie
0x140011943  xor     rax, rsp
0x140011946  mov     [rbp+30h+var_28], rax
0x14001194a  mov     r15, r9
0x14001194d  mov     r14d, r8d
0x140011950  mov     edi, edx
0x140011952  mov     rsi, rcx
0x140011955  lea     rcx, [rbp+30h+var_90]
0x140011959  call    ??0?$ScopedActivity@VUserModeActivityIdControl@ETW@AppV@@@ETW@AppV@@QEAA@XZ; AppV::ETW::ScopedActivity<AppV::ETW::UserModeActivityIdControl>::ScopedActivity<AppV::ETW::UserModeActivityIdControl>(void)
0x14001195e  nop
0x14001195f  lea     rdx, aAppvClientServ_2; "AppV::Client::Service::ClientServiceT<s"...
0x140011966  lea     rcx, [rsp+130h+var_B8]
0x14001196b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140011970  mov     [rbp+30h+var_98], 209h
0x140011977  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14001197c  xorps   xmm0, xmm0
0x14001197f  movups  xmmword ptr [rsp+130h+ActivityId.Data1], xmm0
0x140011984  xorps   xmm1, xmm1
0x140011987  movdqu  [rsp+130h+var_F0], xmm1
0x14001198d  mov     r8d, 14h
0x140011993  lea     rdx, aServiceControl; "Service Control: %1%"
0x14001199a  lea     rcx, [rsp+130h+ActivityId]
0x14001199f  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400119a4  nop
0x1400119a5  lea     r8, [rsp+130h+ActivityId]
0x1400119aa  lea     rdx, [rbp+30h+var_68]
0x1400119ae  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x1400119b3  mov     r8, rax
0x1400119b6  mov     edx, edi
0x1400119b8  sub     edx, 1
0x1400119bb  jz      short loc_1400119FE
0x1400119bd  sub     edx, 3
0x1400119c0  jz      short loc_1400119F5
0x1400119c2  sub     edx, 1
0x1400119c5  jz      short loc_1400119EC
0x1400119c7  sub     edx, 8
0x1400119ca  jz      short loc_1400119E3
0x1400119cc  cmp     edx, 1
0x1400119cf  jz      short loc_1400119DA
0x1400119d1  lea     rax, aUnknownService_0; "Unknown ServiceControl Type"
0x1400119d8  jmp     short loc_140011A05
0x1400119da  lea     rax, aServicecontrol; "ServiceControlSessionChange"
0x1400119e1  jmp     short loc_140011A05
0x1400119e3  lea     rax, aServicecontrol_0; "ServiceControlPowerEvent"
0x1400119ea  jmp     short loc_140011A05
0x1400119ec  lea     rax, aServicecontrol_3; "ServiceControlShutdown"
0x1400119f3  jmp     short loc_140011A05
0x1400119f5  lea     rax, aServicecontrol_1; "ServiceControlInterrogate"
0x1400119fc  jmp     short loc_140011A05
0x1400119fe  lea     rax, aServicecontrol_2; "ServiceControlStop"
0x140011a05  mov     [rbp+30h+var_38], rax
0x140011a09  lea     rdx, [rbp+30h+var_38]
0x140011a0d  mov     rcx, r8
0x140011a10  call    ??$?LPEB_W@LogFormatter@AppV@@QEAAAEAV01@AEBQEB_W@Z; AppV::LogFormatter::operator%<wchar_t const *>(wchar_t const * const &)
0x140011a15  mov     rbx, rax
0x140011a18  xorps   xmm0, xmm0
0x140011a1b  movups  [rsp+130h+var_D8], xmm0
0x140011a20  xorps   xmm1, xmm1
0x140011a23  movdqu  [rsp+130h+var_C8], xmm1
0x140011a29  mov     r8d, 6
0x140011a2f  lea     rdx, aClient; "Client"
0x140011a36  lea     rcx, [rsp+130h+var_D8]
0x140011a3b  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140011a40  nop
0x140011a41  mov     r9, rbx
0x140011a44  lea     r8, [rsp+130h+var_D8]
0x140011a49  mov     edx, 8
0x140011a4e  lea     rcx, [rsp+130h+var_B8]
0x140011a53  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x140011a58  nop
0x140011a59  lea     rcx, [rsp+130h+var_D8]
0x140011a5e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140011a63  nop
0x140011a64  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x140011a6b  mov     [rbp+30h+var_68], rax
0x140011a6f  lea     rcx, [rbp+30h+var_58]
0x140011a73  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140011a78  nop
0x140011a79  lea     rcx, [rsp+130h+ActivityId]
0x140011a7e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140011a83  nop
0x140011a84  lea     rcx, [rsp+130h+var_B8]
0x140011a89  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140011a8e  mov     ebx, 78h ; 'x'
0x140011a93  sub     edi, 1
0x140011a96  jz      short loc_140011AD5
0x140011a98  sub     edi, 3
0x140011a9b  jz      short loc_140011ACE
0x140011a9d  sub     edi, 1
0x140011aa0  jz      short loc_140011AD5
0x140011aa2  sub     edi, 8
0x140011aa5  jz      short loc_140011AC0
0x140011aa7  cmp     edi, 1
0x140011aaa  jnz     loc_140011B7C
0x140011ab0  mov     r8, r15
0x140011ab3  mov     edx, r14d
0x140011ab6  mov     rcx, rsi
0x140011ab9  call    ?HandleSessionChange@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@AEAAXKPEAX@Z; AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::HandleSessionChange(ulong,void *)
0x140011abe  jmp     short loc_140011ACE
0x140011ac0  mov     r8, r15
0x140011ac3  mov     edx, r14d
0x140011ac6  mov     rcx, rsi
0x140011ac9  call    ?HandlePowerEvent@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@AEAAXKPEAX@Z; AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::HandlePowerEvent(ulong,void *)
0x140011ace  xor     ebx, ebx
0x140011ad0  jmp     loc_140011B7C
0x140011ad5  call    ?GenerateCorrelationIDs@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@CAXXZ; AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::GenerateCorrelationIDs(void)
0x140011ada  mov     rdi, qword ptr cs:?st_shutdownCorrelationID@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@0U_GUID@@A.Data1; _GUID AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::st_shutdownCorrelationID ...
0x140011ae1  mov     rbx, qword ptr cs:?st_shutdownCorrelationID@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@0U_GUID@@A.Data4; _GUID AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::st_shutdownCorrelationID ...
0x140011ae8  mov     byte ptr [rsp+130h+ActivityId.Data1], 0
0x140011aed  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140011af4  movdqu  [rsp+130h+var_F0+4], xmm0
0x140011afa  mov     qword ptr [rsp+130h+ActivityId.Data2], rdi
0x140011aff  mov     qword ptr [rsp+130h+ActivityId.Data4+4], rbx
0x140011b04  lea     rdx, [rsp+130h+ActivityId.Data2]; ActivityId
0x140011b09  mov     ecx, 4; ControlCode
0x140011b0e  call    cs:__imp_EventActivityIdControl
0x140011b14  mov     r9d, 1
0x140011b1a  test    eax, eax
0x140011b1c  jnz     short loc_140011B2D
0x140011b1e  mov     qword ptr [rsp+130h+var_F0+4], rdi
0x140011b23  mov     qword ptr [rsp+130h+var_F0+0Ch], rbx
0x140011b28  mov     byte ptr [rsp+130h+ActivityId.Data1], r9b
0x140011b2d  test    byte ptr cs:Microsoft_AppV_SharedPerformanceEnableBits, r9b
0x140011b34  jz      short loc_140011B52
0x140011b36  lea     rax, [rbp+30h+var_38]
0x140011b3a  mov     [rsp+130h+var_110], rax
0x140011b3f  lea     rdx, Service_ShutdownBegin
0x140011b46  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context
0x140011b4d  call    McGenEventWrite_EventWriteTransfer
0x140011b52  xor     r9d, r9d; lParam
0x140011b55  xor     r8d, r8d; wParam
0x140011b58  lea     edx, [r9+12h]; Msg
0x140011b5c  mov     ecx, [rsi+48h]; idThread
0x140011b5f  call    cs:__imp_PostThreadMessageW
0x140011b65  xor     ebx, ebx
0x140011b67  cmp     byte ptr [rsp+130h+ActivityId.Data1], bl
0x140011b6b  jz      short loc_140011B7C
0x140011b6d  lea     rdx, [rsp+130h+ActivityId.Data2]; ActivityId
0x140011b72  lea     ecx, [rbx+2]; ControlCode
0x140011b75  call    cs:__imp_EventActivityIdControl
0x140011b7b  nop
0x140011b7c  cmp     [rbp+30h+var_90], 0
0x140011b80  jz      short loc_140011B91
0x140011b82  lea     rdx, [rbp+30h+var_8C]; ActivityId
0x140011b86  mov     ecx, 2; ControlCode
0x140011b8b  call    cs:__imp_EventActivityIdControl
0x140011b91  mov     eax, ebx
0x140011b93  mov     rcx, [rbp+30h+var_28]
0x140011b97  xor     rcx, rsp; StackCookie
0x140011b9a  call    __security_check_cookie
0x140011b9f  mov     rbx, [rsp+130h+arg_8]
0x140011ba7  add     rsp, 110h
0x140011bae  pop     r15
0x140011bb0  pop     r14
0x140011bb2  pop     rdi
0x140011bb3  pop     rsi
0x140011bb4  pop     rbp
0x140011bb5  retn
```
