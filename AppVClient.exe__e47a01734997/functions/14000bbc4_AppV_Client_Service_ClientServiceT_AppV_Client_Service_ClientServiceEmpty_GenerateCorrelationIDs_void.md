# AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::GenerateCorrelationIDs(void)

- ea: `0x14000bbc4`
- end: `0x14000be51`
- name: `?GenerateCorrelationIDs@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@CAXXZ`
- size: `653`
- prototype: ``
- caller_count: `5`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x140011674`
- `0x140011850`
- `0x140011924`
- `0x140011bbc`
- `0x1400148f0`

## callees

- `0x140004280`
- `0x1400060e8`
- `0x140006304`
- `0x140006a08`
- `0x140008e64`
- `0x14000bbc4`
- `0x140010158`
- `0x14003c034`
- `0x14003c414`
- `0x14003c660`

## import_xrefs

- `ADVAPI32!EventActivityIdControl` at `0x14000bc50`
- `ADVAPI32!EventActivityIdControl` at `0x14000bd3c`
- `ADVAPI32!EventActivityIdControl` at `0x14000bc50`
- `ADVAPI32!EventActivityIdControl` at `0x14000bd3c`
- `KERNEL32!GetCurrentThreadId` at `0x14000bc17`
- `KERNEL32!GetCurrentThreadId` at `0x14000bc17`
- `KERNEL32!LeaveCriticalSection` at `0x14000be32`
- `KERNEL32!LeaveCriticalSection` at `0x14000be32`
- `KERNEL32!EnterCriticalSection` at `0x14000bbfe`
- `KERNEL32!EnterCriticalSection` at `0x14000bbfe`

## string_xrefs

- `0x14000bc69`: `AppV::Client::Service::ClientServiceT<struct AppV::Client::Service::ClientServiceEmpty>::GenerateCorrelationIDs`
- `0x14000bd4e`: `AppV::Client::Service::ClientServiceT<struct AppV::Client::Service::ClientServiceEmpty>::GenerateCorrelationIDs`
- `0x14000bc9a`: `Failed to create ETW activity ID for service startup events, error = %1%; correlation will require other means`
- `0x14000bd7f`: `Failed to create ETW activity ID for service shutdown events, error = %1%; correlation will require other means`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::GenerateCorrelationIDs()
{
  int v0; // eax
  bool v1; // zf
  int v2; // eax
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rax
  __int64 v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rbx
  ULONG v11; // [rsp+20h] [rbp-89h] BYREF
  void **v12; // [rsp+28h] [rbp-81h]
  char v13; // [rsp+30h] [rbp-79h]
  struct _RTL_CRITICAL_SECTION *v14; // [rsp+38h] [rbp-71h]
  __int128 v15; // [rsp+40h] [rbp-69h] BYREF
  __int128 v16; // [rsp+50h] [rbp-59h]
  __int128 v17; // [rsp+60h] [rbp-49h] BYREF
  __int128 v18; // [rsp+70h] [rbp-39h]
  char *v19[4]; // [rsp+80h] [rbp-29h] BYREF
  int v20; // [rsp+A0h] [rbp-9h]
  _QWORD v21[2]; // [rsp+A8h] [rbp-1h] BYREF
  char *v22[4]; // [rsp+B8h] [rbp+Fh] BYREF

  v12 = &softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable';
  v14 = &AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::st_lockCorrelationIDs;
  EnterCriticalSection(&AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::st_lockCorrelationIDs);
  v0 = qword_1400B14D0 + 1;
  LODWORD(qword_1400B14D0) = v0;
  if ( v0 == 1 )
  {
    HIDWORD(qword_1400B14D0) = GetCurrentThreadId();
    v0 = qword_1400B14D0;
  }
  v13 = 1;
  if ( AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::st_generatedCorrelationIDs )
  {
    v2 = v0 - 1;
    v1 = v2 == 0;
    LODWORD(qword_1400B14D0) = v2;
  }
  else
  {
    v11 = EventActivityIdControl(
            3u,
            &AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::st_startupCorrelationID);
    if ( v11 )
    {
      std::string::string(
        v19,
        "AppV::Client::Service::ClientServiceT<struct AppV::Client::Service::ClientServiceEmpty>::GenerateCorrelationIDs");
      v20 = 276;
      AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v3);
      v17 = 0;
      v18 = 0;
      std::wstring::_Construct<1,wchar_t const *>(
        (char **)&v17,
        L"Failed to create ETW activity ID for service startup events, error = %1%; correlation will require other means",
        0x6Eu);
      v5 = AppV::Log::fmt(v4, v21, &v17);
      v6 = AppV::LogFormatter::operator%<unsigned long>(v5, (__int64)&v11);
      v15 = 0;
      v16 = 0;
      std::wstring::_Construct<1,wchar_t const *>((char **)&v15, L"Client", 6u);
      AppV::DecoratedLog::operator()((char *)v19, 8, (int)&v15, v6);
      std::wstring::~wstring((char **)&v15);
      v21[0] = &AppV::LogFormatter::`vftable';
      std::wstring::~wstring(v22);
      std::wstring::~wstring((char **)&v17);
      std::string::~string(v19);
    }
    v11 = EventActivityIdControl(
            3u,
            &AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::st_shutdownCorrelationID);
    if ( v11 )
    {
      std::string::string(
        v19,
        "AppV::Client::Service::ClientServiceT<struct AppV::Client::Service::ClientServiceEmpty>::GenerateCorrelationIDs");
      v20 = 286;
      AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v7);
      v15 = 0;
      v16 = 0;
      std::wstring::_Construct<1,wchar_t const *>(
        (char **)&v15,
        L"Failed to create ETW activity ID for service shutdown events, error = %1%; correlation will require other means",
        0x6Fu);
      v9 = AppV::Log::fmt(v8, v21, &v15);
      v10 = AppV::LogFormatter::operator%<unsigned long>(v9, (__int64)&v11);
      v17 = 0;
      v18 = 0;
      std::wstring::_Construct<1,wchar_t const *>((char **)&v17, L"Client", 6u);
      AppV::DecoratedLog::operator()((char *)v19, 8, (int)&v17, v10);
      std::wstring::~wstring((char **)&v17);
      v21[0] = &AppV::LogFormatter::`vftable';
      std::wstring::~wstring(v22);
      std::wstring::~wstring((char **)&v15);
      std::string::~string(v19);
    }
    AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::st_generatedCorrelationIDs = 1;
    v1 = (_DWORD)qword_1400B14D0 == 1;
    LODWORD(qword_1400B14D0) = qword_1400B14D0 - 1;
  }
  if ( v1 )
    HIDWORD(qword_1400B14D0) = 0;
  LeaveCriticalSection(&AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::st_lockCorrelationIDs);
}

```

## disassembly

```asm
0x14000bbc4  push    rbp
0x14000bbc6  push    rbx
0x14000bbc7  push    rsi
0x14000bbc8  push    r13
0x14000bbca  lea     rbp, [rsp-3Fh]
0x14000bbcf  sub     rsp, 0E8h
0x14000bbd6  mov     rax, cs:__security_cookie
0x14000bbdd  xor     rax, rsp
0x14000bbe0  mov     [rbp+57h+var_28], rax
0x14000bbe4  lea     rax, ??_7?$lock_holder@Vcritical_section@shared@softricity@@@shared@softricity@@6B@; const softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable'
0x14000bbeb  mov     [rsp+100h+var_D8], rax
0x14000bbf0  lea     rsi, ?st_lockCorrelationIDs@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@0Vcritical_section@shared@softricity@@A; softricity::shared::critical_section AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::st_lockCorrelationIDs
0x14000bbf7  mov     [rbp+57h+var_C8], rsi
0x14000bbfb  mov     rcx, rsi; lpCriticalSection
0x14000bbfe  call    cs:__imp_EnterCriticalSection
0x14000bc04  mov     eax, dword ptr cs:qword_1400B14D0
0x14000bc0a  inc     eax
0x14000bc0c  mov     dword ptr cs:qword_1400B14D0, eax
0x14000bc12  cmp     eax, 1
0x14000bc15  jnz     short loc_14000BC29
0x14000bc17  call    cs:__imp_GetCurrentThreadId
0x14000bc1d  mov     dword ptr cs:qword_1400B14D0+4, eax
0x14000bc23  mov     eax, dword ptr cs:qword_1400B14D0
0x14000bc29  mov     [rbp+57h+var_D0], 1
0x14000bc2d  cmp     cs:?st_generatedCorrelationIDs@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@0_NA, 0; bool AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::st_generatedCorrelationIDs
0x14000bc34  jz      short loc_14000BC44
0x14000bc36  sub     eax, 1
0x14000bc39  mov     dword ptr cs:qword_1400B14D0, eax
0x14000bc3f  jmp     loc_14000BE23
0x14000bc44  lea     rdx, ?st_startupCorrelationID@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@0U_GUID@@A; ActivityId
0x14000bc4b  mov     ecx, 3; ControlCode
0x14000bc50  call    cs:__imp_EventActivityIdControl
0x14000bc56  mov     [rsp+100h+var_E0], eax
0x14000bc5a  lea     r13, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14000bc61  test    eax, eax
0x14000bc63  jz      loc_14000BD30
0x14000bc69  lea     rdx, aAppvClientServ_54; "AppV::Client::Service::ClientServiceT<s"...
0x14000bc70  lea     rcx, [rbp+57h+var_80]
0x14000bc74  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14000bc79  mov     [rbp+57h+var_60], 114h
0x14000bc80  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14000bc85  xorps   xmm0, xmm0
0x14000bc88  movups  [rbp+57h+var_A0], xmm0
0x14000bc8c  xorps   xmm1, xmm1
0x14000bc8f  movdqu  [rbp+57h+var_90], xmm1
0x14000bc94  mov     r8d, 6Eh ; 'n'
0x14000bc9a  lea     rdx, aFailedToCreate_4; "Failed to create ETW activity ID for se"...
0x14000bca1  lea     rcx, [rbp+57h+var_A0]
0x14000bca5  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14000bcaa  nop
0x14000bcab  lea     r8, [rbp+57h+var_A0]
0x14000bcaf  lea     rdx, [rbp+57h+var_58]
0x14000bcb3  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14000bcb8  nop
0x14000bcb9  lea     rdx, [rsp+100h+var_E0]
0x14000bcbe  mov     rcx, rax
0x14000bcc1  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x14000bcc6  mov     rbx, rax
0x14000bcc9  xorps   xmm0, xmm0
0x14000bccc  movups  [rbp+57h+var_C0], xmm0
0x14000bcd0  xorps   xmm1, xmm1
0x14000bcd3  movdqu  [rbp+57h+var_B0], xmm1
0x14000bcd8  mov     r8d, 6
0x14000bcde  lea     rdx, aClient; "Client"
0x14000bce5  lea     rcx, [rbp+57h+var_C0]
0x14000bce9  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14000bcee  nop
0x14000bcef  mov     r9, rbx
0x14000bcf2  lea     r8, [rbp+57h+var_C0]
0x14000bcf6  mov     edx, 8
0x14000bcfb  lea     rcx, [rbp+57h+var_80]
0x14000bcff  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14000bd04  nop
0x14000bd05  lea     rcx, [rbp+57h+var_C0]
0x14000bd09  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000bd0e  nop
0x14000bd0f  mov     [rbp+57h+var_58], r13
0x14000bd13  lea     rcx, [rbp+57h+var_48]
0x14000bd17  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000bd1c  nop
0x14000bd1d  lea     rcx, [rbp+57h+var_A0]
0x14000bd21  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000bd26  nop
0x14000bd27  lea     rcx, [rbp+57h+var_80]
0x14000bd2b  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14000bd30  lea     rdx, ?st_shutdownCorrelationID@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@0U_GUID@@A; ActivityId
0x14000bd37  mov     ecx, 3; ControlCode
0x14000bd3c  call    cs:__imp_EventActivityIdControl
0x14000bd42  mov     [rsp+100h+var_E0], eax
0x14000bd46  test    eax, eax
0x14000bd48  jz      loc_14000BE15
0x14000bd4e  lea     rdx, aAppvClientServ_54; "AppV::Client::Service::ClientServiceT<s"...
0x14000bd55  lea     rcx, [rbp+57h+var_80]
0x14000bd59  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14000bd5e  mov     [rbp+57h+var_60], 11Eh
0x14000bd65  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14000bd6a  xorps   xmm0, xmm0
0x14000bd6d  movups  [rbp+57h+var_C0], xmm0
0x14000bd71  xorps   xmm1, xmm1
0x14000bd74  movdqu  [rbp+57h+var_B0], xmm1
0x14000bd79  mov     r8d, 6Fh ; 'o'
0x14000bd7f  lea     rdx, aFailedToCreate; "Failed to create ETW activity ID for se"...
0x14000bd86  lea     rcx, [rbp+57h+var_C0]
0x14000bd8a  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14000bd8f  nop
0x14000bd90  lea     r8, [rbp+57h+var_C0]
0x14000bd94  lea     rdx, [rbp+57h+var_58]
0x14000bd98  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14000bd9d  nop
0x14000bd9e  lea     rdx, [rsp+100h+var_E0]
0x14000bda3  mov     rcx, rax
0x14000bda6  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x14000bdab  mov     rbx, rax
0x14000bdae  xorps   xmm0, xmm0
0x14000bdb1  movups  [rbp+57h+var_A0], xmm0
0x14000bdb5  xorps   xmm1, xmm1
0x14000bdb8  movdqu  [rbp+57h+var_90], xmm1
0x14000bdbd  mov     r8d, 6
0x14000bdc3  lea     rdx, aClient; "Client"
0x14000bdca  lea     rcx, [rbp+57h+var_A0]
0x14000bdce  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14000bdd3  nop
0x14000bdd4  mov     r9, rbx
0x14000bdd7  lea     r8, [rbp+57h+var_A0]
0x14000bddb  mov     edx, 8
0x14000bde0  lea     rcx, [rbp+57h+var_80]
0x14000bde4  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14000bde9  nop
0x14000bdea  lea     rcx, [rbp+57h+var_A0]
0x14000bdee  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000bdf3  nop
0x14000bdf4  mov     [rbp+57h+var_58], r13
0x14000bdf8  lea     rcx, [rbp+57h+var_48]
0x14000bdfc  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000be01  nop
0x14000be02  lea     rcx, [rbp+57h+var_C0]
0x14000be06  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000be0b  nop
0x14000be0c  lea     rcx, [rbp+57h+var_80]
0x14000be10  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14000be15  mov     cs:?st_generatedCorrelationIDs@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@0_NA, 1; bool AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::st_generatedCorrelationIDs
0x14000be1c  sub     dword ptr cs:qword_1400B14D0, 1
0x14000be23  jnz     short loc_14000BE2F
0x14000be25  mov     dword ptr cs:qword_1400B14D0+4, 0
0x14000be2f  mov     rcx, rsi; lpCriticalSection
0x14000be32  call    cs:__imp_LeaveCriticalSection
0x14000be38  mov     rcx, [rbp+57h+var_28]
0x14000be3c  xor     rcx, rsp; StackCookie
0x14000be3f  call    __security_check_cookie
0x14000be44  add     rsp, 0E8h
0x14000be4b  pop     r13
0x14000be4d  pop     rsi
0x14000be4e  pop     rbx
0x14000be4f  pop     rbp
0x14000be50  retn
```
