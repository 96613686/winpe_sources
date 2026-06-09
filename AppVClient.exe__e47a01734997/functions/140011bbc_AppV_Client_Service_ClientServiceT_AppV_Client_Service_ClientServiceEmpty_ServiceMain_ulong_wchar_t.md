# AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::ServiceMain(ulong,wchar_t * *)

- ea: `0x140011bbc`
- end: `0x14001252e`
- name: `?ServiceMain@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@AEAAKKPEAPEA_W@Z`
- size: `2418`
- prototype: `__int64 __fastcall(LPVOID lpContext)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140011850`

## callees

- `0x140001008`
- `0x140004280`
- `0x1400042a4`
- `0x1400060e8`
- `0x140006304`
- `0x140006a08`
- `0x140008e64`
- `0x1400094bc`
- `0x14000af00`
- `0x14000bbc4`
- `0x14000e504`
- `0x140010158`
- `0x1400114b4`
- `0x1400114f0`
- `0x140011bbc`
- `0x1400136f0`
- `0x1400147fc`
- `0x14003c034`
- `0x14003c258`
- `0x14003c414`
- `0x14003c660`
- `0x140045a4c`
- `0x14006a010`

## import_xrefs

- `ADVAPI32!EventActivityIdControl` at `0x140011ff9`
- `ADVAPI32!EventActivityIdControl` at `0x1400121f8`
- `ADVAPI32!EventActivityIdControl` at `0x140011ff9`
- `ADVAPI32!EventActivityIdControl` at `0x1400121f8`
- `ADVAPI32!RegisterServiceCtrlHandlerExW` at `0x140011cba`
- `ADVAPI32!RegisterServiceCtrlHandlerExW` at `0x140011cba`
- `KERNEL32!GetLastError` at `0x140011ccd`
- `KERNEL32!GetLastError` at `0x140011efc`
- `KERNEL32!GetLastError` at `0x140012456`
- `KERNEL32!GetLastError` at `0x140011ccd`
- `KERNEL32!GetLastError` at `0x140011efc`
- `KERNEL32!GetLastError` at `0x140012456`
- `KERNEL32!SetProcessMitigationPolicy` at `0x140012010`
- `KERNEL32!SetProcessMitigationPolicy` at `0x140012010`
- `KERNEL32!GetCurrentThreadId` at `0x140011c86`
- `KERNEL32!GetCurrentThreadId` at `0x140011c86`
- `USER32!TranslateMessage` at `0x1400121b6`
- `USER32!TranslateMessage` at `0x1400121b6`
- `USER32!GetMessageW` at `0x1400121d4`
- `USER32!GetMessageW` at `0x1400121d4`
- `USER32!DispatchMessageW` at `0x1400121c1`
- `USER32!DispatchMessageW` at `0x1400121c1`

## string_xrefs

- `0x140011be6`: `AppV::Client::Service::ClientServiceT<struct AppV::Client::Service::ClientServiceEmpty>::ServiceMain`
- `0x140011c17`: `ServiceMain started`
- `0x140011d03`: `RegisterServiceCtrlHandlerEx() failed, error = %1%`
- `0x14001248e`: `ServiceMain message loop [GetMessage()] failed, error = %1%`
- `0x14001223b`: `Service exit code = %1%`
- `0x140012330`: `ServiceMain exited normally`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::ServiceMain(
        LPVOID lpContext)
{
  SERVICE_STATUS_HANDLE v2; // rax
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rax
  __int64 v6; // rbx
  __int64 v7; // r8
  __int64 v8; // r9
  const wchar_t *v9; // rdx
  AppV::Client::Common *v10; // rcx
  const wchar_t *v11; // r8
  DWORD v12; // eax
  __int64 v13; // r8
  __int64 v14; // r9
  _QWORD *v16; // rax
  DWORD v17; // eax
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // r8
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rbx
  __int64 v24; // rcx
  int MessageW; // eax
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rax
  __int64 v29; // rbx
  int v30; // eax
  void (__fastcall ***v31)(_QWORD, __int64); // rcx
  __int64 v32; // r8
  __int64 v33; // r9
  DWORD v34; // ebx
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rax
  __int64 v38; // rbx
  char v39; // [rsp+40h] [rbp-C0h] BYREF
  int v40; // [rsp+44h] [rbp-BCh] BYREF
  int v41; // [rsp+48h] [rbp-B8h] BYREF
  DWORD v42; // [rsp+4Ch] [rbp-B4h] BYREF
  int wParam; // [rsp+50h] [rbp-B0h] BYREF
  DWORD LastError; // [rsp+54h] [rbp-ACh] BYREF
  int v45; // [rsp+58h] [rbp-A8h] BYREF
  void (__fastcall ***v46)(_QWORD, __int64); // [rsp+60h] [rbp-A0h] BYREF
  MSG Msg; // [rsp+68h] [rbp-98h] BYREF
  __int128 v48; // [rsp+98h] [rbp-68h] BYREF
  __int64 v49; // [rsp+A8h] [rbp-58h]
  __int64 v50; // [rsp+B0h] [rbp-50h]
  __int128 v51; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v52; // [rsp+C8h] [rbp-38h]
  __int64 v53; // [rsp+D0h] [rbp-30h]
  char *v54[4]; // [rsp+D8h] [rbp-28h] BYREF
  int v55; // [rsp+F8h] [rbp-8h]
  GUID ActivityId; // [rsp+100h] [rbp+0h] BYREF
  GUID v57; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v58[2]; // [rsp+120h] [rbp+20h] BYREF
  char *v59[4]; // [rsp+130h] [rbp+30h] BYREF

  std::string::string(
    v54,
    "AppV::Client::Service::ClientServiceT<struct AppV::Client::Service::ClientServiceEmpty>::ServiceMain");
  v55 = 371;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v51, L"ServiceMain started", 0x13u);
  v48 = 0;
  v49 = 0;
  v50 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v48, L"Client", 6u);
  AppV::DecoratedLog::operator()((char *)v54, 8, (int)&v48, (__int64)&v51);
  std::wstring::~wstring((char **)&v48);
  std::wstring::~wstring((char **)&v51);
  std::string::~string(v54);
  *((_DWORD *)lpContext + 18) = GetCurrentThreadId();
  AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::GenerateCorrelationIDs();
  v57 = AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::st_startupCorrelationID;
  v42 = 1064;
  v2 = RegisterServiceCtrlHandlerExW(
         L"AppVClient",
         AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::HandleControl,
         lpContext);
  *((_QWORD *)lpContext + 10) = v2;
  if ( !v2 )
  {
    LastError = GetLastError();
    std::string::string(
      v54,
      "AppV::Client::Service::ClientServiceT<struct AppV::Client::Service::ClientServiceEmpty>::ServiceMain");
    v55 = 384;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v3);
    v48 = 0;
    v49 = 0;
    v50 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v48,
      L"RegisterServiceCtrlHandlerEx() failed, error = %1%",
      0x32u);
    v5 = AppV::Log::fmt(v4, v58, &v48);
    v6 = AppV::LogFormatter::operator%<unsigned long>(v5, (__int64)&LastError);
    v51 = 0;
    v52 = 0;
    v53 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v51, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v54, 8, (int)&v51, v6);
    std::wstring::~wstring((char **)&v51);
    v58[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v59);
    std::wstring::~wstring((char **)&v48);
    std::string::~string(v54);
    if ( (unsigned int)dword_1400AA2E8 > 5
      && (qword_1400AA2F8 & 0x400000000000LL) != 0
      && (qword_1400AA300 & 0x400000000000LL) == qword_1400AA300 )
    {
      v40 = LastError;
      *(_QWORD *)&v48 = &v57;
      v41 = 1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
        qword_1400AA300,
        (__int64)byte_14009D119,
        v7,
        v8,
        (__int64)&v41,
        (__int64 *)&v48,
        (__int64)&v40);
    }
    return v42;
  }
  AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::ReportStartPending(lpContext);
  AppV::Client::Common::CleanupTemporaryPersistedVfsLocks(v10, v9, v11);
  v12 = AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::InitializeClient(lpContext);
  if ( v12 )
  {
    v42 = v12;
    if ( (unsigned int)dword_1400AA2E8 > 5
      && (qword_1400AA2F8 & 0x400000000000LL) != 0
      && (qword_1400AA300 & 0x400000000000LL) == qword_1400AA300 )
    {
      v41 = v42;
      *(_QWORD *)&v48 = &v57;
      v40 = 1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
        qword_1400AA300,
        (__int64)byte_14009D203,
        v13,
        v14,
        (__int64)&v40,
        (__int64 *)&v48,
        (__int64)&v41);
    }
    return v42;
  }
  v39 = 1;
  v16 = operator new(0x28u);
  *(_QWORD *)&v48 = v16;
  *v16 = &appv::utility::scope_guard_func_impl<std::_Binder<std::_Unforced,unsigned long (AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::*)(bool),AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty> *,std::reference_wrapper<bool>>>::`vftable';
  v16[1] = AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::DeinitializeClient;
  *((_DWORD *)v16 + 4) = 0;
  *((_DWORD *)v16 + 5) = *(_DWORD *)&v57.Data4[4];
  v16[3] = &v39;
  v16[4] = lpContext;
  v46 = (void (__fastcall ***)(_QWORD, __int64))v16;
  v17 = GetLastError();
  if ( (unsigned int)dword_1400AA2E8 > 5
    && (qword_1400AA2F8 & 0x400000000000LL) != 0
    && (qword_1400AA300 & 0x400000000000LL) == qword_1400AA300 )
  {
    v41 = v17;
    *(_QWORD *)&v48 = &v57;
    v40 = 1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
      qword_1400AA300 & 0x400000000000LL,
      (__int64)&byte_14009D167,
      v18,
      v19,
      (__int64)&v40,
      (__int64 *)&v48,
      (__int64)&v41);
  }
  AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::UpdateServiceStatus(
    4u,
    0xC5u,
    0,
    *((SERVICE_STATUS_HANDLE *)lpContext + 10),
    0,
    0);
  v39 = 0;
  if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(
      PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context,
      Service_StartupEnd,
      v20,
      1,
      &v48);
  if ( (Microsoft_AppV_ClientEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(
      PROVIDER_MICROSOFT_APPV_CLIENT_Context,
      APPV_CLIENT_Evt_ServiceStarted,
      v20,
      1,
      &v48);
  ActivityId = GUID_NULL;
  EventActivityIdControl(2u, &ActivityId);
  v45 = 1;
  if ( (unsigned int)SetProcessMitigationPolicy(16, &v45, 4) )
  {
    std::string::string(
      v54,
      "AppV::Client::Service::ClientServiceT<struct AppV::Client::Service::ClientServiceEmpty>::ServiceMain");
    v55 = 444;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v24);
    v48 = 0;
    v49 = 0;
    v50 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v48,
      L"Successfully Enabled Enforce Redirection Trust Policy",
      0x35u);
  }
  else
  {
    std::string::string(
      v54,
      "AppV::Client::Service::ClientServiceT<struct AppV::Client::Service::ClientServiceEmpty>::ServiceMain");
    v55 = 438;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v21);
    v48 = 0;
    v49 = 0;
    v50 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v48,
      L"Error While Enabling Enforce Redirection Trust Policy",
      0x35u);
  }
  v23 = AppV::Log::fmt(v22, v58, &v48);
  v51 = 0;
  v52 = 0;
  v53 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v51, L"Client", 6u);
  AppV::DecoratedLog::operator()((char *)v54, 8, (int)&v51, v23);
  std::wstring::~wstring((char **)&v51);
  v58[0] = &AppV::LogFormatter::`vftable';
  std::wstring::~wstring(v59);
  std::wstring::~wstring((char **)&v48);
  std::string::~string(v54);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)lpContext + 5) + 24LL))(*((_QWORD *)lpContext + 5));
  memset(&Msg, 0, sizeof(Msg));
  while ( 1 )
  {
    MessageW = GetMessageW(&Msg, 0, 0, 0);
    if ( !MessageW )
      break;
    if ( MessageW == -1 )
    {
      v42 = GetLastError();
      std::string::string(
        v54,
        "AppV::Client::Service::ClientServiceT<struct AppV::Client::Service::ClientServiceEmpty>::ServiceMain");
      v55 = 463;
      AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v35);
      v48 = 0;
      v49 = 0;
      v50 = 0;
      std::wstring::_Construct<1,wchar_t const *>(
        (char **)&v48,
        L"ServiceMain message loop [GetMessage()] failed, error = %1%",
        0x3Bu);
      v37 = AppV::Log::fmt(v36, v58, &v48);
      v38 = AppV::LogFormatter::operator%<unsigned long>(v37, (__int64)&v42);
      v51 = 0;
      v52 = 0;
      v53 = 0;
      std::wstring::_Construct<1,wchar_t const *>((char **)&v51, L"Client", 6u);
      AppV::DecoratedLog::operator()((char *)v54, 8, (int)&v51, v38);
      std::wstring::~wstring((char **)&v51);
      v58[0] = &AppV::LogFormatter::`vftable';
      std::wstring::~wstring(v59);
      std::wstring::~wstring((char **)&v48);
      std::string::~string(v54);
      v34 = v42;
      goto LABEL_39;
    }
    TranslateMessage(&Msg);
    DispatchMessageW(&Msg);
  }
  AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::GenerateCorrelationIDs();
  ActivityId = AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::st_shutdownCorrelationID;
  EventActivityIdControl(2u, &ActivityId);
  AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::ReportStopPending(lpContext);
  wParam = Msg.wParam;
  std::string::string(
    v54,
    "AppV::Client::Service::ClientServiceT<struct AppV::Client::Service::ClientServiceEmpty>::ServiceMain");
  v55 = 478;
  AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v26);
  v48 = 0;
  v49 = 0;
  v50 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v48, L"Service exit code = %1%", 0x17u);
  v28 = AppV::Log::fmt(v27, v58, &v48);
  v29 = AppV::LogFormatter::operator%<unsigned long>(v28, (__int64)&wParam);
  v51 = 0;
  v52 = 0;
  v53 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v51, L"Client", 6u);
  AppV::DecoratedLog::operator()((char *)v54, 8, (int)&v51, v29);
  std::wstring::~wstring((char **)&v51);
  v58[0] = &AppV::LogFormatter::`vftable';
  std::wstring::~wstring(v59);
  std::wstring::~wstring((char **)&v48);
  std::string::~string(v54);
  v30 = AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::DeinitializeClient(
          lpContext,
          0);
  if ( v30 && !wParam )
    wParam = v30;
  v31 = v46;
  v46 = 0;
  if ( v31 )
    (**v31)(v31, 1);
  std::string::string(
    v54,
    "AppV::Client::Service::ClientServiceT<struct AppV::Client::Service::ClientServiceEmpty>::ServiceMain");
  v55 = 485;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v48, L"ServiceMain exited normally", 0x1Bu);
  v51 = 0;
  v52 = 0;
  v53 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v51, L"Client", 6u);
  AppV::DecoratedLog::operator()((char *)v54, 8, (int)&v51, (__int64)&v48);
  std::wstring::~wstring((char **)&v51);
  std::wstring::~wstring((char **)&v48);
  std::string::~string(v54);
  if ( (Microsoft_AppV_ClientEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(
      PROVIDER_MICROSOFT_APPV_CLIENT_Context,
      APPV_CLIENT_Evt_ServiceShutdown,
      v32,
      1,
      &v48);
  if ( (unsigned int)dword_1400AA2E8 > 5
    && (qword_1400AA2F8 & 0x400000000000LL) != 0
    && (qword_1400AA300 & 0x400000000000LL) == qword_1400AA300 )
  {
    v41 = wParam;
    *(_QWORD *)&v48 = &ActivityId;
    v40 = 1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
      qword_1400AA300,
      (__int64)byte_14009D1B5,
      v32,
      v33,
      (__int64)&v40,
      (__int64 *)&v48,
      (__int64)&v41);
  }
  v34 = wParam;
LABEL_39:
  appv::utility::scope_guard::~scope_guard((appv::utility::scope_guard *)&v46);
  return v34;
}

```

## disassembly

```asm
0x140011bbc  push    rbp
0x140011bbe  push    rbx
0x140011bbf  push    rsi
0x140011bc0  push    rdi
0x140011bc1  push    r12
0x140011bc3  push    r13
0x140011bc5  push    r14
0x140011bc7  push    r15
0x140011bc9  lea     rbp, [rsp-68h]
0x140011bce  sub     rsp, 168h
0x140011bd5  mov     rax, cs:__security_cookie
0x140011bdc  xor     rax, rsp
0x140011bdf  mov     [rbp+0A0h+var_50], rax
0x140011be3  mov     r14, rcx
0x140011be6  lea     r13, aAppvClientServ_19; "AppV::Client::Service::ClientServiceT<s"...
0x140011bed  mov     rdx, r13
0x140011bf0  lea     rcx, [rbp+0A0h+var_C8]
0x140011bf4  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140011bf9  mov     [rbp+0A0h+var_A8], 173h
0x140011c00  xorps   xmm0, xmm0
0x140011c03  movups  [rbp+0A0h+var_E8], xmm0
0x140011c07  xor     r12d, r12d
0x140011c0a  mov     [rbp+0A0h+var_D8], r12
0x140011c0e  mov     [rbp+0A0h+var_D0], r12
0x140011c12  lea     r8d, [r12+13h]
0x140011c17  lea     rdx, aServicemainSta; "ServiceMain started"
0x140011c1e  lea     rcx, [rbp+0A0h+var_E8]
0x140011c22  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140011c27  nop
0x140011c28  xorps   xmm0, xmm0
0x140011c2b  movups  [rbp+0A0h+var_108], xmm0
0x140011c2f  mov     [rbp+0A0h+var_F8], r12
0x140011c33  mov     [rbp+0A0h+var_F0], r12
0x140011c37  lea     r15d, [r12+6]
0x140011c3c  mov     r8d, r15d
0x140011c3f  lea     rdx, aClient; "Client"
0x140011c46  lea     rcx, [rbp+0A0h+var_108]
0x140011c4a  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140011c4f  nop
0x140011c50  lea     r9, [rbp+0A0h+var_E8]
0x140011c54  lea     r8, [rbp+0A0h+var_108]
0x140011c58  lea     edi, [r12+8]
0x140011c5d  mov     edx, edi
0x140011c5f  lea     rcx, [rbp+0A0h+var_C8]
0x140011c63  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,std::wstring const &)
0x140011c68  nop
0x140011c69  lea     rcx, [rbp+0A0h+var_108]
0x140011c6d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140011c72  nop
0x140011c73  lea     rcx, [rbp+0A0h+var_E8]
0x140011c77  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140011c7c  nop
0x140011c7d  lea     rcx, [rbp+0A0h+var_C8]
0x140011c81  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140011c86  call    cs:__imp_GetCurrentThreadId
0x140011c8c  mov     [r14+48h], eax
0x140011c90  call    ?GenerateCorrelationIDs@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@CAXXZ; AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::GenerateCorrelationIDs(void)
0x140011c95  movups  xmm0, xmmword ptr cs:?st_startupCorrelationID@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@0U_GUID@@A.Data1; _GUID AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::st_startupCorrelationID ...
0x140011c9c  movdqu  [rbp+0A0h+var_90], xmm0
0x140011ca1  mov     [rsp+1A0h+var_154], 428h
0x140011ca9  mov     r8, r14; lpContext
0x140011cac  lea     rdx, ?HandleControl@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@CAKKKPEAX0@Z; lpHandlerProc
0x140011cb3  lea     rcx, ServiceName; "AppVClient"
0x140011cba  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x140011cc0  mov     [r14+50h], rax
0x140011cc4  test    rax, rax
0x140011cc7  jnz     loc_140011E16
0x140011ccd  call    cs:__imp_GetLastError
0x140011cd3  mov     [rsp+1A0h+var_14C], eax
0x140011cd7  mov     rdx, r13
0x140011cda  lea     rcx, [rbp+0A0h+var_C8]
0x140011cde  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140011ce3  mov     [rbp+0A0h+var_A8], 180h
0x140011cea  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x140011cef  xorps   xmm0, xmm0
0x140011cf2  movups  [rbp+0A0h+var_108], xmm0
0x140011cf6  mov     [rbp+0A0h+var_F8], r12
0x140011cfa  mov     [rbp+0A0h+var_F0], r12
0x140011cfe  lea     r8d, [r12+32h]
0x140011d03  lea     rdx, aRegisterservic; "RegisterServiceCtrlHandlerEx() failed, "...
0x140011d0a  lea     rcx, [rbp+0A0h+var_108]
0x140011d0e  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140011d13  nop
0x140011d14  lea     r8, [rbp+0A0h+var_108]
0x140011d18  lea     rdx, [rbp+0A0h+var_80]
0x140011d1c  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x140011d21  nop
0x140011d22  lea     rdx, [rsp+1A0h+var_14C]
0x140011d27  mov     rcx, rax
0x140011d2a  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x140011d2f  mov     rbx, rax
0x140011d32  xorps   xmm0, xmm0
0x140011d35  movups  [rbp+0A0h+var_E8], xmm0
0x140011d39  mov     [rbp+0A0h+var_D8], r12
0x140011d3d  mov     [rbp+0A0h+var_D0], r12
0x140011d41  mov     r8d, r15d
0x140011d44  lea     rdx, aClient; "Client"
0x140011d4b  lea     rcx, [rbp+0A0h+var_E8]
0x140011d4f  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140011d54  nop
0x140011d55  mov     r9, rbx
0x140011d58  lea     r8, [rbp+0A0h+var_E8]
0x140011d5c  mov     edx, edi
0x140011d5e  lea     rcx, [rbp+0A0h+var_C8]
0x140011d62  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x140011d67  nop
0x140011d68  lea     rcx, [rbp+0A0h+var_E8]
0x140011d6c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140011d71  nop
0x140011d72  lea     r15, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x140011d79  mov     [rbp+0A0h+var_80], r15
0x140011d7d  lea     rcx, [rbp+0A0h+var_70]
0x140011d81  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140011d86  nop
0x140011d87  lea     rcx, [rbp+0A0h+var_108]
0x140011d8b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140011d90  nop
0x140011d91  lea     rcx, [rbp+0A0h+var_C8]
0x140011d95  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140011d9a  mov     eax, cs:dword_1400AA2E8
0x140011da0  cmp     eax, 5
0x140011da3  jbe     loc_140011EAC
0x140011da9  mov     rcx, cs:qword_1400AA300
0x140011db0  mov     rax, cs:qword_1400AA2F8
0x140011db7  mov     rsi, 400000000000h
0x140011dc1  test    rsi, rax
0x140011dc4  jz      loc_140011EAC
0x140011dca  mov     rax, rcx
0x140011dcd  and     rax, rsi
0x140011dd0  cmp     rax, rcx
0x140011dd3  jnz     loc_140011EAC
0x140011dd9  mov     eax, [rsp+1A0h+var_14C]
0x140011ddd  mov     [rsp+1A0h+var_15C], eax
0x140011de1  lea     rax, [rbp+0A0h+var_90]
0x140011de5  mov     qword ptr [rbp+0A0h+var_108], rax
0x140011de9  lea     edi, [r12+1]
0x140011dee  mov     [rsp+1A0h+var_158], edi
0x140011df2  lea     rax, [rsp+1A0h+var_15C]
0x140011df7  mov     [rsp+1A0h+var_170], rax
0x140011dfc  lea     rax, [rbp+0A0h+var_108]
0x140011e00  mov     [rsp+1A0h+var_178], rax
0x140011e05  lea     rax, [rsp+1A0h+var_158]
0x140011e0a  lea     rdx, byte_14009D119
0x140011e11  jmp     loc_140011EA2
0x140011e16  mov     rcx, r14
0x140011e19  call    ?ReportStartPending@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@AEAAXXZ; AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::ReportStartPending(void)
0x140011e1e  call    ?CleanupTemporaryPersistedVfsLocks@Common@Client@AppV@@YA_NXZ; AppV::Client::Common::CleanupTemporaryPersistedVfsLocks(void)
0x140011e23  mov     rcx, r14
0x140011e26  call    ?InitializeClient@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@AEAAKXZ; AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::InitializeClient(void)
0x140011e2b  test    eax, eax
0x140011e2d  jz      loc_140011EB5
0x140011e33  mov     [rsp+1A0h+var_154], eax
0x140011e37  mov     eax, cs:dword_1400AA2E8
0x140011e3d  cmp     eax, 5
0x140011e40  jbe     short loc_140011EAC
0x140011e42  mov     rcx, cs:qword_1400AA300
0x140011e49  mov     rax, cs:qword_1400AA2F8
0x140011e50  mov     rsi, 400000000000h
0x140011e5a  test    rsi, rax
0x140011e5d  jz      short loc_140011EAC
0x140011e5f  mov     rax, rcx
0x140011e62  and     rax, rsi
0x140011e65  cmp     rax, rcx
0x140011e68  jnz     short loc_140011EAC
0x140011e6a  mov     eax, [rsp+1A0h+var_154]
0x140011e6e  mov     [rsp+1A0h+var_158], eax
0x140011e72  lea     rax, [rbp+0A0h+var_90]
0x140011e76  mov     qword ptr [rbp+0A0h+var_108], rax
0x140011e7a  mov     edi, 1
0x140011e7f  mov     [rsp+1A0h+var_15C], edi
0x140011e83  lea     rax, [rsp+1A0h+var_158]
0x140011e88  mov     [rsp+1A0h+var_170], rax
0x140011e8d  lea     rax, [rbp+0A0h+var_108]
0x140011e91  mov     [rsp+1A0h+var_178], rax
0x140011e96  lea     rax, [rsp+1A0h+var_15C]
0x140011e9b  lea     rdx, byte_14009D203
0x140011ea2  mov     [rsp+1A0h+var_180], rax
0x140011ea7  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x140011eac  mov     eax, [rsp+1A0h+var_154]
0x140011eb0  jmp     loc_140012436
0x140011eb5  mov     edi, 1
0x140011eba  mov     [rsp+1A0h+var_160], dil
0x140011ebf  lea     ecx, [rdi+27h]; Size
0x140011ec2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140011ec7  mov     qword ptr [rbp+0A0h+var_108], rax
0x140011ecb  lea     rcx, ??_7?$scope_guard_func_impl@V?$_Binder@U_Unforced@std@@P8?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@EAAK_N@ZPEAV3456@V?$reference_wrapper@_N@2@@std@@@utility@appv@@6B@; const appv::utility::scope_guard_func_impl<std::_Binder<std::_Unforced,ulong (AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::*)(bool),AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty> *,std::reference_wrapper<bool>>>::`vftable'
0x140011ed2  mov     [rax], rcx
0x140011ed5  lea     rcx, ?DeinitializeClient@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@AEAAK_N@Z; AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::DeinitializeClient(bool)
0x140011edc  mov     [rax+8], rcx
0x140011ee0  mov     [rax+10h], r12d
0x140011ee4  mov     ecx, dword ptr [rbp+0A0h+var_90+0Ch]
0x140011ee7  mov     [rax+14h], ecx
0x140011eea  lea     rcx, [rsp+1A0h+var_160]
0x140011eef  mov     [rax+18h], rcx
0x140011ef3  mov     [rax+20h], r14
0x140011ef7  mov     [rsp+1A0h+var_140], rax
0x140011efc  call    cs:__imp_GetLastError
0x140011f02  mov     ecx, cs:dword_1400AA2E8
0x140011f08  mov     rsi, 400000000000h
0x140011f12  cmp     ecx, 5
0x140011f15  jbe     short loc_140011F6E
0x140011f17  mov     rdx, cs:qword_1400AA300
0x140011f1e  mov     rcx, cs:qword_1400AA2F8
0x140011f25  test    rsi, rcx
0x140011f28  jz      short loc_140011F6E
0x140011f2a  mov     rcx, rdx
0x140011f2d  and     rcx, rsi
0x140011f30  cmp     rcx, rdx
0x140011f33  jnz     short loc_140011F6E
0x140011f35  mov     [rsp+1A0h+var_158], eax
0x140011f39  lea     rax, [rbp+0A0h+var_90]
0x140011f3d  mov     qword ptr [rbp+0A0h+var_108], rax
0x140011f41  mov     [rsp+1A0h+var_15C], edi
0x140011f45  lea     rax, [rsp+1A0h+var_158]
0x140011f4a  mov     [rsp+1A0h+var_170], rax
0x140011f4f  lea     rax, [rbp+0A0h+var_108]
0x140011f53  mov     [rsp+1A0h+var_178], rax
0x140011f58  lea     rax, [rsp+1A0h+var_15C]
0x140011f5d  mov     [rsp+1A0h+var_180], rax
0x140011f62  lea     rdx, byte_14009D167
0x140011f69  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x140011f6e  mov     dword ptr [rsp+1A0h+var_178], r12d
0x140011f73  mov     dword ptr [rsp+1A0h+var_180], r12d
0x140011f78  mov     r9, [r14+50h]
0x140011f7c  xor     r8d, r8d
0x140011f7f  mov     edx, 0C5h
0x140011f84  lea     ebx, [r8+4]
0x140011f88  mov     ecx, ebx
0x140011f8a  call    ?UpdateServiceStatus@?$ClientServiceT@UClientServiceEmpty@Service@Client@AppV@@@Service@Client@AppV@@CAXKKKPEAUSERVICE_STATUS_HANDLE__@@KK@Z; AppV::Client::Service::ClientServiceT<AppV::Client::Service::ClientServiceEmpty>::UpdateServiceStatus(ulong,ulong,ulong,SERVICE_STATUS_HANDLE__ *,ulong,ulong)
0x140011f8f  mov     [rsp+1A0h+var_160], r12b
0x140011f94  test    byte ptr cs:Microsoft_AppV_SharedPerformanceEnableBits, dil
0x140011f9b  jz      short loc_140011FBC
0x140011f9d  lea     rax, [rbp+0A0h+var_108]
0x140011fa1  mov     [rsp+1A0h+var_180], rax
0x140011fa6  mov     r9d, edi
0x140011fa9  lea     rdx, Service_StartupEnd
0x140011fb0  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context
0x140011fb7  call    McGenEventWrite_EventWriteTransfer
0x140011fbc  test    cs:Microsoft_AppV_ClientEnableBits, dil
0x140011fc3  jz      short loc_140011FE4
0x140011fc5  lea     rax, [rbp+0A0h+var_108]
0x140011fc9  mov     [rsp+1A0h+var_180], rax
0x140011fce  mov     r9d, edi
0x140011fd1  lea     rdx, APPV_CLIENT_Evt_ServiceStarted
0x140011fd8  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_Context
0x140011fdf  call    McGenEventWrite_EventWriteTransfer
0x140011fe4  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140011feb  movdqu  xmmword ptr [rbp+0A0h+ActivityId.Data1], xmm0
0x140011ff0  lea     rdx, [rbp+0A0h+ActivityId]; ActivityId
0x140011ff4  mov     ecx, 2; ControlCode
0x140011ff9  call    cs:__imp_EventActivityIdControl
0x140011fff  mov     [rsp+1A0h+var_148], edi
0x140012003  mov     r8, rbx
0x140012006  lea     rdx, [rsp+1A0h+var_148]
0x14001200b  mov     ecx, 10h
0x140012010  call    cs:__imp_SetProcessMitigationPolicy
0x140012016  mov     rdx, r13
0x140012019  lea     rcx, [rbp+0A0h+var_C8]
0x14001201d  test    eax, eax
0x14001201f  jnz     loc_1400120D3
0x140012025  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14001202a  mov     [rbp+0A0h+var_A8], 1B6h
0x140012031  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x140012036  xorps   xmm0, xmm0
0x140012039  movups  [rbp+0A0h+var_108], xmm0
0x14001203d  mov     [rbp+0A0h+var_F8], r12
0x140012041  mov     [rbp+0A0h+var_F0], r12
0x140012045  mov     r8d, 35h ; '5'
0x14001204b  lea     rdx, aErrorWhileEnab; "Error While Enabling Enforce Redirectio"...
0x140012052  lea     rcx, [rbp+0A0h+var_108]
0x140012056  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14001205b  nop
0x14001205c  lea     r8, [rbp+0A0h+var_108]
0x140012060  lea     rdx, [rbp+0A0h+var_80]
0x140012064  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x140012069  mov     rbx, rax
0x14001206c  xorps   xmm0, xmm0
0x14001206f  movups  [rbp+0A0h+var_E8], xmm0
0x140012073  mov     [rbp+0A0h+var_D8], r12
0x140012077  mov     [rbp+0A0h+var_D0], r12
0x14001207b  mov     r8, r15
0x14001207e  lea     rdx, aClient; "Client"
0x140012085  lea     rcx, [rbp+0A0h+var_E8]
0x140012089  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14001208e  nop
0x14001208f  mov     r9, rbx
0x140012092  lea     r8, [rbp+0A0h+var_E8]
0x140012096  mov     edx, 8
0x14001209b  lea     rcx, [rbp+0A0h+var_C8]
0x14001209f  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x1400120a4  nop
0x1400120a5  lea     rcx, [rbp+0A0h+var_E8]
0x1400120a9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400120ae  nop
0x1400120af  lea     r15, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x1400120b6  mov     [rbp+0A0h+var_80], r15
0x1400120ba  lea     rcx, [rbp+0A0h+var_70]
0x1400120be  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400120c3  nop
0x1400120c4  lea     rcx, [rbp+0A0h+var_108]
  ... truncated ...
```
