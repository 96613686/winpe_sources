# AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::Run(HINSTANCE__ *,wchar_t *)

- ea: `0x140011674`
- end: `0x140011842`
- name: `?Run@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@SAKPEAUHINSTANCE__@@PEA_W@Z`
- size: `462`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, installer_update`

## callers

- `0x1400148f0`

## callees

- `0x140004280`
- `0x1400046c0`
- `0x140004728`
- `0x1400060e8`
- `0x140006304`
- `0x140006a08`
- `0x140008e64`
- `0x14000bbc4`
- `0x140010158`
- `0x140011674`
- `0x14003c034`
- `0x14003c414`
- `0x14003c660`

## import_xrefs

- `ADVAPI32!EventActivityIdControl` at `0x1400116e4`
- `ADVAPI32!EventActivityIdControl` at `0x1400116e4`
- `ADVAPI32!StartServiceCtrlDispatcherW` at `0x1400116c2`
- `ADVAPI32!StartServiceCtrlDispatcherW` at `0x1400116c2`
- `KERNEL32!GetLastError` at `0x1400116f2`
- `KERNEL32!GetLastError` at `0x1400116f2`

## string_xrefs

- `0x1400116fb`: `AppV::Client::Service::ClientServiceT<struct AppV::Client::Service::ClientServiceEmpty>::Run`
- `0x14001172a`: `StartServiceCtrlDispatcher result = %1%`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::Run()
{
  BOOL started; // ebx
  __int64 v1; // rcx
  __int64 v2; // rcx
  __int64 v3; // rax
  __int64 v4; // rbx
  DWORD LastError; // [rsp+20h] [rbp-69h] BYREF
  _OWORD v7[2]; // [rsp+28h] [rbp-61h] BYREF
  GUID v8[2]; // [rsp+48h] [rbp-41h] BYREF
  GUID ActivityId; // [rsp+68h] [rbp-21h] BYREF
  char *v10[4]; // [rsp+78h] [rbp-11h] BYREF
  int v11; // [rsp+98h] [rbp+Fh]
  void **v12; // [rsp+A0h] [rbp+17h] BYREF
  char *v13; // [rsp+B0h] [rbp+27h] BYREF

  if ( __TSS0__1__Run___ClientServiceT_UClientServiceEmpty_Service_Client_AppV___Service_Client_AppV__SAKPEAUHINSTANCE____PEA_W_Z_4HA > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 4LL) )
  {
    Init_thread_header(&__TSS0__1__Run___ClientServiceT_UClientServiceEmpty_Service_Client_AppV___Service_Client_AppV__SAKPEAUHINSTANCE____PEA_W_Z_4HA);
    if ( __TSS0__1__Run___ClientServiceT_UClientServiceEmpty_Service_Client_AppV___Service_Client_AppV__SAKPEAUHINSTANCE____PEA_W_Z_4HA == -1 )
    {
      `AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::Run'::`2'::serviceTable.lpServiceName = (LPWSTR)L"AppVClient";
      `AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::Run'::`2'::serviceTable.lpServiceProc = (LPSERVICE_MAIN_FUNCTIONW)AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::RunService;
      qword_1400B0A68 = 0;
      qword_1400B0A70 = 0;
      Init_thread_footer(&__TSS0__1__Run___ClientServiceT_UClientServiceEmpty_Service_Client_AppV___Service_Client_AppV__SAKPEAUHINSTANCE____PEA_W_Z_4HA);
    }
  }
  LastError = 0;
  started = StartServiceCtrlDispatcherW(&`AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::Run'::`2'::serviceTable);
  AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::GenerateCorrelationIDs();
  ActivityId = AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::st_shutdownCorrelationID;
  EventActivityIdControl(2u, &ActivityId);
  if ( !started )
  {
    LastError = GetLastError();
    std::string::string(
      v10,
      "AppV::Client::Service::ClientServiceT<struct AppV::Client::Service::ClientServiceEmpty>::Run");
    v11 = 318;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v1);
    memset(v8, 0, sizeof(v8));
    std::wstring::_Construct<1,wchar_t const *>((char **)v8, L"StartServiceCtrlDispatcher result = %1%", 0x27u);
    v3 = AppV::Log::fmt(v2, &v12, v8);
    v4 = AppV::LogFormatter::operator%<unsigned long>(v3, (__int64)&LastError);
    memset(v7, 0, sizeof(v7));
    std::wstring::_Construct<1,wchar_t const *>((char **)v7, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v10, 8, (int)v7, v4);
    std::wstring::~wstring((char **)v7);
    v12 = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(&v13);
    std::wstring::~wstring((char **)v8);
    std::string::~string(v10);
  }
  return LastError;
}

```

## disassembly

```asm
0x140011674  mov     [rsp-8+arg_0], rbx
0x140011679  push    rbp
0x14001167a  lea     rbp, [rsp-57h]
0x14001167f  sub     rsp, 0E0h
0x140011686  mov     rax, cs:__security_cookie
0x14001168d  xor     rax, rsp
0x140011690  mov     [rbp+57h+var_10], rax
0x140011694  mov     ecx, 4
0x140011699  mov     rax, gs:58h
0x1400116a2  mov     rax, [rax]
0x1400116a5  mov     eax, [rcx+rax]
0x1400116a8  cmp     cs:?$TSS0@?1??Run@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@SAKPEAUHINSTANCE__@@PEA_W@Z@4HA, eax
0x1400116ae  jg      loc_1400117E6
0x1400116b4  mov     [rbp+57h+var_C0], 0
0x1400116bb  lea     rcx, ?serviceTable@?1??Run@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@SAKPEAUHINSTANCE__@@PEA_W@Z@4QBU_SERVICE_TABLE_ENTRYW@@B; lpServiceStartTable
0x1400116c2  call    cs:__imp_StartServiceCtrlDispatcherW
0x1400116c8  mov     ebx, eax
0x1400116ca  call    ?GenerateCorrelationIDs@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@CAXXZ; AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::GenerateCorrelationIDs(void)
0x1400116cf  movups  xmm0, xmmword ptr cs:?st_shutdownCorrelationID@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@0U_GUID@@A.Data1; _GUID AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::st_shutdownCorrelationID ...
0x1400116d6  movdqu  xmmword ptr [rbp+57h+ActivityId.Data1], xmm0
0x1400116db  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x1400116df  mov     ecx, 2; ControlCode
0x1400116e4  call    cs:__imp_EventActivityIdControl
0x1400116ea  test    ebx, ebx
0x1400116ec  jnz     loc_1400117C6
0x1400116f2  call    cs:__imp_GetLastError
0x1400116f8  mov     [rbp+57h+var_C0], eax
0x1400116fb  lea     rdx, aAppvClientServ_46; "AppV::Client::Service::ClientServiceT<s"...
0x140011702  lea     rcx, [rbp+57h+var_68]
0x140011706  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14001170b  mov     [rbp+57h+var_48], 13Eh
0x140011712  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x140011717  xorps   xmm0, xmm0
0x14001171a  movups  [rbp+57h+var_98], xmm0
0x14001171e  xorps   xmm1, xmm1
0x140011721  movdqu  [rbp+57h+var_88], xmm1
0x140011726  lea     r8d, [rbx+27h]
0x14001172a  lea     rdx, aStartservicect; "StartServiceCtrlDispatcher result = %1%"
0x140011731  lea     rcx, [rbp+57h+var_98]
0x140011735  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14001173a  nop
0x14001173b  lea     r8, [rbp+57h+var_98]
0x14001173f  lea     rdx, [rbp+57h+var_40]
0x140011743  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x140011748  nop
0x140011749  lea     rdx, [rbp+57h+var_C0]
0x14001174d  mov     rcx, rax
0x140011750  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x140011755  mov     rbx, rax
0x140011758  xorps   xmm0, xmm0
0x14001175b  movups  [rbp+57h+var_B8], xmm0
0x14001175f  xorps   xmm1, xmm1
0x140011762  movdqu  [rbp+57h+var_A8], xmm1
0x140011767  mov     r8d, 6
0x14001176d  lea     rdx, aClient; "Client"
0x140011774  lea     rcx, [rbp+57h+var_B8]
0x140011778  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14001177d  nop
0x14001177e  mov     r9, rbx
0x140011781  lea     r8, [rbp+57h+var_B8]
0x140011785  mov     edx, 8
0x14001178a  lea     rcx, [rbp+57h+var_68]
0x14001178e  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x140011793  nop
0x140011794  lea     rcx, [rbp+57h+var_B8]
0x140011798  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001179d  nop
0x14001179e  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x1400117a5  mov     [rbp+57h+var_40], rax
0x1400117a9  lea     rcx, [rbp+57h+var_30]
0x1400117ad  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400117b2  nop
0x1400117b3  lea     rcx, [rbp+57h+var_98]
0x1400117b7  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400117bc  nop
0x1400117bd  lea     rcx, [rbp+57h+var_68]
0x1400117c1  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1400117c6  mov     eax, [rbp+57h+var_C0]
0x1400117c9  mov     rcx, [rbp+57h+var_10]
0x1400117cd  xor     rcx, rsp; StackCookie
0x1400117d0  call    __security_check_cookie
0x1400117d5  mov     rbx, [rsp+0E0h+arg_0]
0x1400117dd  add     rsp, 0E0h
0x1400117e4  pop     rbp
0x1400117e5  retn
0x1400117e6  lea     rcx, ?$TSS0@?1??Run@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@SAKPEAUHINSTANCE__@@PEA_W@Z@4HA
0x1400117ed  call    _Init_thread_header
0x1400117f2  cmp     cs:?$TSS0@?1??Run@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@SAKPEAUHINSTANCE__@@PEA_W@Z@4HA, 0FFFFFFFFh
0x1400117f9  jnz     loc_1400116B4
0x1400117ff  lea     rax, ServiceName; "AppVClient"
0x140011806  mov     cs:?serviceTable@?1??Run@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@SAKPEAUHINSTANCE__@@PEA_W@Z@4QBU_SERVICE_TABLE_ENTRYW@@B.lpServiceName, rax; _SERVICE_TABLE_ENTRYW const near * const `AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::Run(HINSTANCE__ *,wchar_t *)'::`2'::serviceTable ...
0x14001180d  lea     rax, ?RunService@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@CAXKPEAPEA_W@Z; AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::RunService(ulong,wchar_t * *)
0x140011814  mov     cs:?serviceTable@?1??Run@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@SAKPEAUHINSTANCE__@@PEA_W@Z@4QBU_SERVICE_TABLE_ENTRYW@@B.lpServiceProc, rax; _SERVICE_TABLE_ENTRYW const near * const `AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::Run(HINSTANCE__ *,wchar_t *)'::`2'::serviceTable ...
0x14001181b  mov     cs:qword_1400B0A68, 0
0x140011826  mov     cs:qword_1400B0A70, 0
0x140011831  lea     rcx, ?$TSS0@?1??Run@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@SAKPEAUHINSTANCE__@@PEA_W@Z@4HA
0x140011838  call    _Init_thread_footer
0x14001183d  jmp     loc_1400116B4
```
