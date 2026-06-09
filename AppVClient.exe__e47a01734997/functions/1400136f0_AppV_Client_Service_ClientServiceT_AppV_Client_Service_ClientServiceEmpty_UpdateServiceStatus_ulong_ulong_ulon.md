# AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::UpdateServiceStatus(ulong,ulong,ulong,SERVICE_STATUS_HANDLE__ *,ulong,ulong)

- ea: `0x1400136f0`
- end: `0x1400139b7`
- name: `?UpdateServiceStatus@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@CAXKKKPEAUSERVICE_STATUS_HANDLE__@@KK@Z`
- size: `711`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: `service_task, installer_update`

## callers

- `0x1400114b4`
- `0x1400114f0`
- `0x140011850`
- `0x140011bbc`

## callees

- `0x140004280`
- `0x1400060e8`
- `0x140006304`
- `0x140006a08`
- `0x140006a94`
- `0x140008e64`
- `0x140010158`
- `0x1400136f0`
- `0x14003c034`
- `0x14003c414`
- `0x14003c660`

## import_xrefs

- `ADVAPI32!SetServiceStatus` at `0x1400138bf`
- `ADVAPI32!SetServiceStatus` at `0x1400138bf`
- `KERNEL32!GetLastError` at `0x1400138cd`
- `KERNEL32!GetLastError` at `0x1400138cd`

## string_xrefs

- `0x140013754`: `AppV::Client::Service::ClientServiceT<struct AppV::Client::Service::ClientServiceEmpty>::UpdateServiceStatus`
- `0x1400138d7`: `AppV::Client::Service::ClientServiceT<struct AppV::Client::Service::ClientServiceEmpty>::UpdateServiceStatus`
- `0x140013785`: `Service Status: %1%\nCheckpoint: %2%\nWait Hint: %3%\nControls Accepted: 0x%4:X%`
- `0x140013908`: `SetServiceStatus() failed, error = %1%`
- `0x140013808`: `ServiceStopped`
- `0x1400137ff`: `ServiceStartPending`
- `0x1400137f6`: `ServiceStopPending`
- `0x1400137ed`: `ServiceRunning`
- `0x1400137e4`: `ServiceContinuePending`
- `0x1400137db`: `ServicePausePending`
- `0x1400137d2`: `ServicePaused`
- `0x1400137c9`: `Unknown ServiceState Type`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::UpdateServiceStatus(
        DWORD a1,
        DWORD a2,
        DWORD a3,
        SERVICE_STATUS_HANDLE a4,
        DWORD a5,
        DWORD a6)
{
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // r8
  DWORD v11; // ebx
  DWORD v12; // ebx
  DWORD v13; // ebx
  DWORD v14; // ebx
  DWORD v15; // ebx
  DWORD v16; // ebx
  const wchar_t *v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rbx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rbx
  DWORD v26; // [rsp+20h] [rbp-A9h] BYREF
  const wchar_t *v27; // [rsp+28h] [rbp-A1h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+30h] [rbp-99h] BYREF
  __int128 v29; // [rsp+50h] [rbp-79h] BYREF
  __int128 v30; // [rsp+60h] [rbp-69h]
  __int128 v31; // [rsp+70h] [rbp-59h] BYREF
  __int128 v32; // [rsp+80h] [rbp-49h]
  char *v33[4]; // [rsp+90h] [rbp-39h] BYREF
  int v34; // [rsp+B0h] [rbp-19h]
  _QWORD v35[2]; // [rsp+B8h] [rbp-11h] BYREF
  char *v36[4]; // [rsp+C8h] [rbp-1h] BYREF

  v26 = a2;
  ServiceStatus.dwServiceType = 16;
  ServiceStatus.dwCurrentState = a1;
  ServiceStatus.dwControlsAccepted = a2;
  if ( a3 )
  {
    ServiceStatus.dwWin32ExitCode = 1066;
    ServiceStatus.dwServiceSpecificExitCode = a3;
  }
  else
  {
    *(_QWORD *)&ServiceStatus.dwWin32ExitCode = 0;
  }
  ServiceStatus.dwCheckPoint = a5;
  ServiceStatus.dwWaitHint = a6;
  std::string::string(
    v33,
    "AppV::Client::Service::ClientServiceT<struct AppV::Client::Service::ClientServiceEmpty>::UpdateServiceStatus");
  v34 = 627;
  AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v8);
  v31 = 0;
  v32 = 0;
  std::wstring::_Construct<1,wchar_t const *>(
    (char **)&v31,
    L"Service Status: %1%\nCheckpoint: %2%\nWait Hint: %3%\nControls Accepted: 0x%4:X%",
    0x4Du);
  v10 = AppV::Log::fmt(v9, v35, &v31);
  v11 = a1 - 1;
  if ( v11 )
  {
    v12 = v11 - 1;
    if ( v12 )
    {
      v13 = v12 - 1;
      if ( v13 )
      {
        v14 = v13 - 1;
        if ( v14 )
        {
          v15 = v14 - 1;
          if ( v15 )
          {
            v16 = v15 - 1;
            if ( v16 )
            {
              if ( v16 == 1 )
                v17 = L"ServicePaused";
              else
                v17 = L"Unknown ServiceState Type";
            }
            else
            {
              v17 = L"ServicePausePending";
            }
          }
          else
          {
            v17 = L"ServiceContinuePending";
          }
        }
        else
        {
          v17 = L"ServiceRunning";
        }
      }
      else
      {
        v17 = L"ServiceStopPending";
      }
    }
    else
    {
      v17 = L"ServiceStartPending";
    }
  }
  else
  {
    v17 = L"ServiceStopped";
  }
  v27 = v17;
  v18 = AppV::LogFormatter::operator%<wchar_t const *>(v10, &v27);
  v19 = AppV::LogFormatter::operator%<unsigned long>(v18, (__int64)&a5);
  v20 = AppV::LogFormatter::operator%<unsigned long>(v19, (__int64)&a6);
  v21 = AppV::LogFormatter::operator%<unsigned long>(v20, (__int64)&v26);
  v29 = 0;
  v30 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v29, L"Client", 6u);
  AppV::DecoratedLog::operator()((char *)v33, 8, (int)&v29, v21);
  std::wstring::~wstring((char **)&v29);
  v35[0] = &AppV::LogFormatter::`vftable';
  std::wstring::~wstring(v36);
  std::wstring::~wstring((char **)&v31);
  std::string::~string(v33);
  if ( !SetServiceStatus(a4, &ServiceStatus) )
  {
    LODWORD(v27) = GetLastError();
    std::string::string(
      v33,
      "AppV::Client::Service::ClientServiceT<struct AppV::Client::Service::ClientServiceEmpty>::UpdateServiceStatus");
    v34 = 631;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v22);
    v29 = 0;
    v30 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v29, L"SetServiceStatus() failed, error = %1%", 0x26u);
    v24 = AppV::Log::fmt(v23, v35, &v29);
    v25 = AppV::LogFormatter::operator%<unsigned long>(v24, (__int64)&v27);
    v31 = 0;
    v32 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v31, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v33, 8, (int)&v31, v25);
    std::wstring::~wstring((char **)&v31);
    v35[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v36);
    std::wstring::~wstring((char **)&v29);
    std::string::~string(v33);
  }
}

```

## disassembly

```asm
0x1400136f0  push    rbp
0x1400136f2  push    rbx
0x1400136f3  push    rdi
0x1400136f4  push    r15
0x1400136f6  lea     rbp, [rsp-2Fh]
0x1400136fb  sub     rsp, 0F8h
0x140013702  mov     rax, cs:__security_cookie
0x140013709  xor     rax, rsp
0x14001370c  mov     [rbp+47h+var_28], rax
0x140013710  mov     rdi, r9
0x140013713  mov     ebx, ecx
0x140013715  mov     [rsp+110h+var_F0], edx
0x140013719  mov     [rsp+110h+ServiceStatus.dwServiceType], 10h
0x140013721  mov     [rsp+110h+ServiceStatus.dwCurrentState], ecx
0x140013725  mov     [rsp+110h+ServiceStatus.dwControlsAccepted], edx
0x140013729  test    r8d, r8d
0x14001372c  jnz     short loc_140013739
0x14001372e  mov     qword ptr [rsp+110h+ServiceStatus.dwWin32ExitCode], 0
0x140013737  jmp     short loc_140013746
0x140013739  mov     [rsp+110h+ServiceStatus.dwWin32ExitCode], 42Ah
0x140013741  mov     [rsp+110h+ServiceStatus.dwServiceSpecificExitCode], r8d
0x140013746  mov     eax, [rbp+47h+arg_20]
0x140013749  mov     [rsp+110h+ServiceStatus.dwCheckPoint], eax
0x14001374d  mov     eax, [rbp+47h+arg_28]
0x140013750  mov     [rsp+110h+ServiceStatus.dwWaitHint], eax
0x140013754  lea     rdx, aAppvClientServ_57; "AppV::Client::Service::ClientServiceT<s"...
0x14001375b  lea     rcx, [rbp+47h+var_80]
0x14001375f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140013764  mov     [rbp+47h+var_60], 273h
0x14001376b  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x140013770  xorps   xmm0, xmm0
0x140013773  movups  [rbp+47h+var_A0], xmm0
0x140013777  xorps   xmm1, xmm1
0x14001377a  movdqu  [rbp+47h+var_90], xmm1
0x14001377f  mov     r8d, 4Dh ; 'M'
0x140013785  lea     rdx, aServiceStatus1; "Service Status: %1%\nCheckpoint: %2%\nW"...
0x14001378c  lea     rcx, [rbp+47h+var_A0]
0x140013790  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140013795  nop
0x140013796  lea     r8, [rbp+47h+var_A0]
0x14001379a  lea     rdx, [rbp+47h+var_58]
0x14001379e  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x1400137a3  mov     r8, rax
0x1400137a6  sub     ebx, 1
0x1400137a9  jz      short loc_140013808
0x1400137ab  sub     ebx, 1
0x1400137ae  jz      short loc_1400137FF
0x1400137b0  sub     ebx, 1
0x1400137b3  jz      short loc_1400137F6
0x1400137b5  sub     ebx, 1
0x1400137b8  jz      short loc_1400137ED
0x1400137ba  sub     ebx, 1
0x1400137bd  jz      short loc_1400137E4
0x1400137bf  sub     ebx, 1
0x1400137c2  jz      short loc_1400137DB
0x1400137c4  cmp     ebx, 1
0x1400137c7  jz      short loc_1400137D2
0x1400137c9  lea     rax, aUnknownService; "Unknown ServiceState Type"
0x1400137d0  jmp     short loc_14001380F
0x1400137d2  lea     rax, aServicepaused; "ServicePaused"
0x1400137d9  jmp     short loc_14001380F
0x1400137db  lea     rax, aServicepausepe; "ServicePausePending"
0x1400137e2  jmp     short loc_14001380F
0x1400137e4  lea     rax, aServicecontinu; "ServiceContinuePending"
0x1400137eb  jmp     short loc_14001380F
0x1400137ed  lea     rax, aServicerunning; "ServiceRunning"
0x1400137f4  jmp     short loc_14001380F
0x1400137f6  lea     rax, aServicestoppen; "ServiceStopPending"
0x1400137fd  jmp     short loc_14001380F
0x1400137ff  lea     rax, aServicestartpe; "ServiceStartPending"
0x140013806  jmp     short loc_14001380F
0x140013808  lea     rax, aServicestopped; "ServiceStopped"
0x14001380f  mov     [rsp+110h+var_E8], rax
0x140013814  lea     rdx, [rsp+110h+var_E8]
0x140013819  mov     rcx, r8
0x14001381c  call    ??$?LPEB_W@LogFormatter@AppV@@QEAAAEAV01@AEBQEB_W@Z; AppV::LogFormatter::operator%<wchar_t const *>(wchar_t const * const &)
0x140013821  lea     rdx, [rbp+47h+arg_20]
0x140013825  mov     rcx, rax
0x140013828  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x14001382d  lea     rdx, [rbp+47h+arg_28]
0x140013831  mov     rcx, rax
0x140013834  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x140013839  lea     rdx, [rsp+110h+var_F0]
0x14001383e  mov     rcx, rax
0x140013841  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x140013846  mov     rbx, rax
0x140013849  xorps   xmm0, xmm0
0x14001384c  movups  [rbp+47h+var_C0], xmm0
0x140013850  xorps   xmm1, xmm1
0x140013853  movdqu  [rbp+47h+var_B0], xmm1
0x140013858  mov     r8d, 6
0x14001385e  lea     rdx, aClient; "Client"
0x140013865  lea     rcx, [rbp+47h+var_C0]
0x140013869  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14001386e  nop
0x14001386f  mov     r9, rbx
0x140013872  lea     r8, [rbp+47h+var_C0]
0x140013876  mov     edx, 8
0x14001387b  lea     rcx, [rbp+47h+var_80]
0x14001387f  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x140013884  nop
0x140013885  lea     rcx, [rbp+47h+var_C0]
0x140013889  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001388e  nop
0x14001388f  lea     r15, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x140013896  mov     [rbp+47h+var_58], r15
0x14001389a  lea     rcx, [rbp+47h+var_48]
0x14001389e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400138a3  nop
0x1400138a4  lea     rcx, [rbp+47h+var_A0]
0x1400138a8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400138ad  nop
0x1400138ae  lea     rcx, [rbp+47h+var_80]
0x1400138b2  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1400138b7  lea     rdx, [rsp+110h+ServiceStatus]; lpServiceStatus
0x1400138bc  mov     rcx, rdi; hServiceStatus
0x1400138bf  call    cs:__imp_SetServiceStatus
0x1400138c5  test    eax, eax
0x1400138c7  jnz     loc_14001399E
0x1400138cd  call    cs:__imp_GetLastError
0x1400138d3  mov     dword ptr [rsp+110h+var_E8], eax
0x1400138d7  lea     rdx, aAppvClientServ_57; "AppV::Client::Service::ClientServiceT<s"...
0x1400138de  lea     rcx, [rbp+47h+var_80]
0x1400138e2  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400138e7  mov     [rbp+47h+var_60], 277h
0x1400138ee  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x1400138f3  xorps   xmm0, xmm0
0x1400138f6  movups  [rbp+47h+var_C0], xmm0
0x1400138fa  xorps   xmm1, xmm1
0x1400138fd  movdqu  [rbp+47h+var_B0], xmm1
0x140013902  mov     r8d, 26h ; '&'
0x140013908  lea     rdx, aSetservicestat; "SetServiceStatus() failed, error = %1%"
0x14001390f  lea     rcx, [rbp+47h+var_C0]
0x140013913  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140013918  nop
0x140013919  lea     r8, [rbp+47h+var_C0]
0x14001391d  lea     rdx, [rbp+47h+var_58]
0x140013921  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x140013926  nop
0x140013927  lea     rdx, [rsp+110h+var_E8]
0x14001392c  mov     rcx, rax
0x14001392f  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x140013934  mov     rbx, rax
0x140013937  xorps   xmm0, xmm0
0x14001393a  movups  [rbp+47h+var_A0], xmm0
0x14001393e  xorps   xmm1, xmm1
0x140013941  movdqu  [rbp+47h+var_90], xmm1
0x140013946  mov     r8d, 6
0x14001394c  lea     rdx, aClient; "Client"
0x140013953  lea     rcx, [rbp+47h+var_A0]
0x140013957  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14001395c  nop
0x14001395d  mov     r9, rbx
0x140013960  lea     r8, [rbp+47h+var_A0]
0x140013964  mov     edx, 8
0x140013969  lea     rcx, [rbp+47h+var_80]
0x14001396d  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x140013972  nop
0x140013973  lea     rcx, [rbp+47h+var_A0]
0x140013977  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001397c  nop
0x14001397d  mov     [rbp+47h+var_58], r15
0x140013981  lea     rcx, [rbp+47h+var_48]
0x140013985  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001398a  nop
0x14001398b  lea     rcx, [rbp+47h+var_C0]
0x14001398f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140013994  nop
0x140013995  lea     rcx, [rbp+47h+var_80]
0x140013999  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14001399e  mov     rcx, [rbp+47h+var_28]
0x1400139a2  xor     rcx, rsp; StackCookie
0x1400139a5  call    __security_check_cookie
0x1400139aa  add     rsp, 0F8h
0x1400139b1  pop     r15
0x1400139b3  pop     rdi
0x1400139b4  pop     rbx
0x1400139b5  pop     rbp
0x1400139b6  retn
```
