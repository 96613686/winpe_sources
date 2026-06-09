# ServiceMain_Internal(wchar_t const *)

- ea: `0x1800349a8`
- end: `0x180034ef7`
- name: `?ServiceMain_Internal@@YAJPEB_W@Z`
- size: `1359`
- prototype: `__int64 __fastcall(LPCWSTR lpServiceName)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180034f00`

## callees

- `0x1800081c0`
- `0x180008c90`
- `0x180008e64`
- `0x180008e88`
- `0x180008ea8`
- `0x1800112d0`
- `0x18001b064`
- `0x18002e0d0`
- `0x18003224c`
- `0x180033814`
- `0x180033ad8`
- `0x180034588`
- `0x180034874`
- `0x1800349a8`
- `0x180035258`
- `0x1800352d4`
- `0x1800353e0`
- `0x1800354ec`
- `0x1800356fc`
- `0x180039510`
- `0x18006ea28`
- `0x1800dd930`
- `0x1800e4630`
- `0x1800e46b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034d9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034de3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034d9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034de3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034dbd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034df6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034dbd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034df6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034da8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034e9c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034da8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034e9c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180034cd2`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180034cd2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180034e74`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180034e74`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180034b35`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180034b35`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180034dee`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180034e89`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180034dee`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180034e89`

## string_xrefs

- `0x180034ee5`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x180034b4b`: `C:\__w\1\s\src\orchestrator\core\USOSvc\Service.cpp`
- `0x180034c07`: `C:\__w\1\s\src\orchestrator\core\USOSvc\Service.cpp`
- `0x180034c4e`: `C:\__w\1\s\src\orchestrator\core\USOSvc\Service.cpp`
- `0x180034cb6`: `C:\__w\1\s\src\orchestrator\core\USOSvc\Service.cpp`
- `0x180034cfe`: `C:\__w\1\s\src\orchestrator\core\USOSvc\Service.cpp`
- `0x180034d5c`: `C:\__w\1\s\src\orchestrator\core\USOSvc\Service.cpp`
- `0x180034bca`: `UsoSvc setting service state to: SERVICE_START_PENDING`
- `0x180034d1c`: `UsoSvc setting service state to: SERVICE_RUNNING`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall ServiceMain_Internal(LPCWSTR lpServiceName)
{
  __int64 *System; // rax
  _QWORD *v4; // rax
  volatile signed __int32 *v5; // rbx
  volatile signed __int32 *v6; // rbx
  char v7; // r14
  unsigned int LastError; // edi
  __int64 v9; // r9
  __int64 v10; // rdx
  const char *v11; // r9
  void (__fastcall ***v12)(_QWORD, __int64); // rcx
  int updated; // eax
  wil::details *v14; // rcx
  int LastErrorFailHr; // eax
  HANDLE v16; // rbx
  __int64 (__fastcall *v17)(HANDLE *, LPCWSTR, HANDLE, __int64 (__fastcall *)()); // rax
  unsigned int v18; // eax
  HRESULT v19; // eax
  int v20; // eax
  char v21; // si
  int v22; // eax
  void *v23; // rsi
  HANDLE v24; // rdi
  DWORD v25; // r14d
  unsigned int v26; // r8d
  const char *v27; // r9
  HANDLE v28; // r14
  HANDLE v29; // rsi
  DWORD v30; // edi
  __int64 *v31; // rax
  __int64 v32; // rdx
  void (__fastcall ***v33)(_QWORD, __int64); // rcx
  unsigned int v34; // r8d
  const char *v35; // r9
  const struct wil::FailureInfo *v36; // rdx
  int v37; // [rsp+20h] [rbp-E0h]
  HANDLE hObject; // [rsp+48h] [rbp-B8h] BYREF
  const wchar_t *v39; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v40; // [rsp+58h] [rbp-A8h]
  _QWORD *v41; // [rsp+60h] [rbp-A0h] BYREF
  volatile signed __int32 *v42; // [rsp+68h] [rbp-98h]
  _BYTE v43[160]; // [rsp+70h] [rbp-90h] BYREF
  void (__fastcall ***v44)(_QWORD, __int64); // [rsp+110h] [rbp+10h] BYREF
  HANDLE WaitHandle; // [rsp+118h] [rbp+18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  if ( IsSysprepInProgress() )
    return 2149884193LL;
  v44 = 0;
  System = SystemInterface::Service::GetSystem((__int64 *)&v39);
  v4 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)*System + 104LL))(*System, &v41);
  (*(void (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)*v4 + 8LL))(*v4, &v44);
  v5 = v42;
  if ( v42 )
  {
    if ( _InterlockedExchangeAdd(v42 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
      if ( _InterlockedExchangeAdd(v5 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
    }
  }
  v6 = (volatile signed __int32 *)v40;
  if ( v40 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v40 + 8), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
      if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
    }
  }
  v41 = &v44;
  v7 = 1;
  LOBYTE(v42) = 1;
  if ( qword_180150118 )
  {
    StartUpdateLogging();
    if ( wil::details::g_pfnTelemetryCallback
      && (void (__fastcall *)(bool, const struct wil::FailureInfo *))wil::details::g_pfnTelemetryCallback != Windows::Telemetry::ServiceErrors::FallbackTelemetryCallback )
    {
      memset(v43, 0, 0x98u);
      wil::details::WilFailFast((wil::details *)v43, v36);
    }
    wil::details::g_pfnTelemetryCallback = (__int64)Windows::Telemetry::ServiceErrors::FallbackTelemetryCallback;
    *(_OWORD *)&ServiceStatus.dwCurrentState = 0;
    *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
    ServiceStatus.dwServiceType = 32;
    hServiceStatus = RegisterServiceCtrlHandlerExW(lpServiceName, ServiceHandler, 0);
    if ( !hServiceStatus )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x3CA,
                    (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Service.cpp",
                    v11);
      goto LABEL_17;
    }
    if ( IsServicingInProgress() )
    {
      LastError = -2145083104;
      goto LABEL_17;
    }
    v39 = L"UsoSvc setting service state to: SERVICE_START_PENDING";
    v40 = 54;
    SystemInterface::Log<>(&v39);
    updated = ServiceHelpers::UpdateServiceStatus(2u, 0, 0x7530u);
    LastError = updated;
    if ( updated >= 0 )
    {
      hObject = 0;
      if ( (unsigned __int8)_try_create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAA_NW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
                              &hObject,
                              1,
                              0,
                              0)
        || (LastErrorFailHr = wil::details::GetLastErrorFailHr(v14), LastError = LastErrorFailHr, LastErrorFailHr >= 0) )
      {
        WaitHandle = (HANDLE)-1LL;
        v17 = *(__int64 (__fastcall **)(HANDLE *, LPCWSTR, HANDLE, __int64 (__fastcall *)()))(qword_180150118 + 192);
        WaitHandle = (HANDLE)-1LL;
        v16 = hObject;
        v18 = v17(&WaitHandle, lpServiceName, hObject, StopService);
        if ( v18 )
        {
          LastError = wil::details::in1diag3::Return_Win32(
                        retaddr,
                        (void *)0x3E0,
                        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Service.cpp",
                        (const char *)v18,
                        0);
        }
        else
        {
          v19 = CoInitializeEx(0, 0);
          if ( v19 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1284,
              (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
              (const char *)(unsigned int)v19,
              0);
          v20 = InitializeService(v16);
          LastError = v20;
          if ( v20 >= 0 )
          {
            v21 = 1;
            v39 = L"UsoSvc setting service state to: SERVICE_RUNNING";
            v40 = 48;
            SystemInterface::Log<>(&v39);
            ServiceStatus.dwControlsAccepted = 1;
            v22 = ServiceHelpers::UpdateServiceStatus(4u, 0, 0);
            LastError = v22;
            if ( v22 >= 0 )
            {
              ServiceHelpers::CreateOrchestratorKey();
              ServiceHelpers::CreateInstallAtShutdownKey();
              SvcAddRef();
              SvcRelease();
              v23 = v16;
              v16 = 0;
              hObject = 0;
              v24 = ::hObject;
              if ( ::hObject )
              {
                v25 = GetLastError();
                if ( !CloseHandle(v24) )
                  wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v26, v27);
                SetLastError(v25);
              }
              ::hObject = v23;
              v28 = WaitHandle;
              WaitHandle = (HANDLE)-1LL;
              v29 = ::WaitHandle;
              if ( ::WaitHandle != (HANDLE)-1LL && ::WaitHandle )
              {
                v30 = GetLastError();
                UnregisterWait(v29);
                SetLastError(v30);
              }
              ::WaitHandle = v28;
              v21 = 0;
              v7 = 0;
              LOBYTE(v42) = 0;
              v31 = (__int64 *)((__int64 (__fastcall *)(_QWORD, const wchar_t **))(*v44)[2])(v44, &v39);
              v32 = *v31;
              *v31 = 0;
              v33 = (void (__fastcall ***)(_QWORD, __int64))g_svcActivity;
              g_svcActivity = v32;
              if ( v33 )
                (**v33)(v33, 1);
              if ( v39 )
                (**(void (__fastcall ***)(const wchar_t *, __int64))v39)(v39, 1);
              LastError = 0;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x3EA,
                (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Service.cpp",
                (const char *)(unsigned int)v22,
                0);
            }
            if ( v21 )
              UninitializeService();
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x3E4,
              (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Service.cpp",
              (const char *)(unsigned int)v20,
              0);
          }
          CoUninitialize();
        }
        if ( (char *)WaitHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          UnregisterWait(WaitHandle);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3D6,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Service.cpp",
          (const char *)(unsigned int)LastErrorFailHr,
          v37);
        v16 = hObject;
      }
      if ( v16 && !CloseHandle(v16) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v34, v35);
      goto LABEL_17;
    }
    v9 = (unsigned int)updated;
    v10 = 979;
  }
  else
  {
    LastError = -2145083117;
    v9 = 2149884179LL;
    v10 = 958;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\Service.cpp",
    (const char *)v9,
    v37);
LABEL_17:
  v12 = v44;
  if ( v7 && v44 )
  {
    ((void (*)(void))(*v44)[3])();
    v12 = v44;
  }
  if ( v12 )
    (**v12)(v12, 1);
  return LastError;
}

```

## disassembly

```asm
0x1800349a8  mov     [rsp-8+arg_8], rbx
0x1800349ad  mov     [rsp-8+arg_10], rsi
0x1800349b2  push    rbp
0x1800349b3  push    rdi
0x1800349b4  push    r12
0x1800349b6  push    r13
0x1800349b8  push    r14
0x1800349ba  lea     rbp, [rsp-30h]
0x1800349bf  sub     rsp, 130h
0x1800349c6  mov     rax, cs:__security_cookie
0x1800349cd  xor     rax, rsp
0x1800349d0  mov     [rbp+50h+var_30], rax
0x1800349d4  mov     rsi, rcx
0x1800349d7  call    ?IsSysprepInProgress@@YA_NXZ; IsSysprepInProgress(void)
0x1800349dc  test    al, al
0x1800349de  jz      short loc_1800349EA
0x1800349e0  mov     eax, 8024A121h
0x1800349e5  jmp     loc_180034B91
0x1800349ea  mov     [rbp+50h+var_40], 0
0x1800349f2  lea     rcx, [rsp+150h+var_100]
0x1800349f7  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x1800349fc  nop
0x1800349fd  mov     rcx, [rax]
0x180034a00  mov     rax, [rcx]
0x180034a03  lea     rdx, [rsp+150h+var_F0]
0x180034a08  mov     rax, [rax+68h]
0x180034a0c  call    _guard_dispatch_icall
0x180034a11  nop
0x180034a12  mov     rcx, [rax]
0x180034a15  mov     rax, [rcx]
0x180034a18  lea     rdx, [rbp+50h+var_40]
0x180034a1c  mov     rax, [rax+8]
0x180034a20  call    _guard_dispatch_icall
0x180034a25  nop
0x180034a26  or      r12, 0FFFFFFFFFFFFFFFFh
0x180034a2a  mov     rbx, [rsp+150h+var_E8]
0x180034a2f  test    rbx, rbx
0x180034a32  jz      short loc_180034A6C
0x180034a34  mov     eax, r12d
0x180034a37  lock xadd [rbx+8], eax
0x180034a3c  add     eax, r12d
0x180034a3f  jnz     short loc_180034A6C
0x180034a41  mov     rax, [rbx]
0x180034a44  mov     rcx, rbx
0x180034a47  mov     rax, [rax]
0x180034a4a  call    _guard_dispatch_icall
0x180034a4f  mov     eax, r12d
0x180034a52  lock xadd [rbx+0Ch], eax
0x180034a57  add     eax, r12d
0x180034a5a  jnz     short loc_180034A6C
0x180034a5c  mov     rax, [rbx]
0x180034a5f  mov     rcx, rbx
0x180034a62  mov     rax, [rax+8]
0x180034a66  call    _guard_dispatch_icall
0x180034a6b  nop
0x180034a6c  mov     rbx, [rsp+150h+var_F8]
0x180034a71  test    rbx, rbx
0x180034a74  jz      short loc_180034AAD
0x180034a76  mov     eax, r12d
0x180034a79  lock xadd [rbx+8], eax
0x180034a7e  add     eax, r12d
0x180034a81  jnz     short loc_180034AAD
0x180034a83  mov     rax, [rbx]
0x180034a86  mov     rcx, rbx
0x180034a89  mov     rax, [rax]
0x180034a8c  call    _guard_dispatch_icall
0x180034a91  mov     eax, r12d
0x180034a94  lock xadd [rbx+0Ch], eax
0x180034a99  add     eax, r12d
0x180034a9c  jnz     short loc_180034AAD
0x180034a9e  mov     rax, [rbx]
0x180034aa1  mov     rcx, rbx
0x180034aa4  mov     rax, [rax+8]
0x180034aa8  call    _guard_dispatch_icall
0x180034aad  lea     rax, [rbp+50h+var_40]
0x180034ab1  mov     [rsp+150h+var_F0], rax
0x180034ab6  mov     r13d, 1
0x180034abc  mov     r14b, r13b
0x180034abf  mov     byte ptr [rsp+150h+var_E8], r13b
0x180034ac4  cmp     cs:qword_180150118, 0
0x180034acc  jnz     short loc_180034AE0
0x180034ace  mov     edi, 8024A113h
0x180034ad3  mov     r9d, edi
0x180034ad6  mov     edx, 3BEh
0x180034adb  jmp     loc_180034C07
0x180034ae0  call    ?StartUpdateLogging@@YAXXZ; StartUpdateLogging(void)
0x180034ae5  lea     rcx, ?FallbackTelemetryCallback@ServiceErrors@Telemetry@Windows@@SAX_NAEBUFailureInfo@wil@@@Z; Windows::Telemetry::ServiceErrors::FallbackTelemetryCallback(bool,wil::FailureInfo const &)
0x180034aec  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180034af3  test    rax, rax
0x180034af6  jz      short loc_180034B01
0x180034af8  cmp     rax, rcx
0x180034afb  jnz     loc_180034EC5
0x180034b01  mov     cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA, rcx
0x180034b08  xorps   xmm0, xmm0
0x180034b0b  movdqu  xmmword ptr cs:ServiceStatus.dwCurrentState, xmm0
0x180034b13  mov     qword ptr cs:ServiceStatus.dwCheckPoint, 0
0x180034b1e  mov     cs:ServiceStatus.dwServiceType, 20h ; ' '
0x180034b28  xor     r8d, r8d; lpContext
0x180034b2b  lea     rdx, ServiceHandler; lpHandlerProc
0x180034b32  mov     rcx, rsi; lpServiceName
0x180034b35  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180034b3b  mov     cs:hServiceStatus, rax
0x180034b42  test    rax, rax
0x180034b45  jnz     short loc_180034BB9
0x180034b47  mov     rcx, [rbp+58h]; this
0x180034b4b  lea     r8, aCW1SSrcOrchest_40; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x180034b52  mov     edx, 3CAh; void *
0x180034b57  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180034b5c  mov     edi, eax
0x180034b5e  mov     rcx, [rbp+50h+var_40]
0x180034b62  test    r14b, r14b
0x180034b65  jz      short loc_180034B7C
0x180034b67  test    rcx, rcx
0x180034b6a  jz      short loc_180034B7C
0x180034b6c  mov     rax, [rcx]
0x180034b6f  mov     rax, [rax+18h]
0x180034b73  call    _guard_dispatch_icall
0x180034b78  mov     rcx, [rbp+50h+var_40]
0x180034b7c  test    rcx, rcx
0x180034b7f  jz      short loc_180034B8F
0x180034b81  mov     rax, [rcx]
0x180034b84  mov     edx, r13d
0x180034b87  mov     rax, [rax]
0x180034b8a  call    _guard_dispatch_icall
0x180034b8f  mov     eax, edi
0x180034b91  mov     rcx, [rbp+50h+var_30]
0x180034b95  xor     rcx, rsp; StackCookie
0x180034b98  call    __security_check_cookie
0x180034b9d  lea     r11, [rsp+150h+var_20]
0x180034ba5  mov     rbx, [r11+38h]
0x180034ba9  mov     rsi, [r11+40h]
0x180034bad  mov     rsp, r11
0x180034bb0  pop     r14
0x180034bb2  pop     r13
0x180034bb4  pop     r12
0x180034bb6  pop     rdi
0x180034bb7  pop     rbp
0x180034bb8  retn
0x180034bb9  call    ?IsServicingInProgress@@YA_NXZ; IsServicingInProgress(void)
0x180034bbe  nop
0x180034bbf  test    al, al
0x180034bc1  jz      short loc_180034BCA
0x180034bc3  mov     edi, 8024A120h
0x180034bc8  jmp     short loc_180034B5E
0x180034bca  lea     rax, aUsosvcSettingS_2; "UsoSvc setting service state to: SERVIC"...
0x180034bd1  mov     [rsp+150h+var_100], rax
0x180034bd6  mov     [rsp+150h+var_F8], 36h ; '6'
0x180034bdf  lea     rcx, [rsp+150h+var_100]
0x180034be4  call    ??$Log@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::Log<>(std::wstring_view)
0x180034be9  xor     edx, edx; unsigned int
0x180034beb  lea     ecx, [rdx+2]; unsigned int
0x180034bee  mov     r8d, 7530h; unsigned int
0x180034bf4  call    ?UpdateServiceStatus@ServiceHelpers@@SAJKKK@Z; ServiceHelpers::UpdateServiceStatus(ulong,ulong,ulong)
0x180034bf9  mov     edi, eax
0x180034bfb  test    eax, eax
0x180034bfd  jns     short loc_180034C1C
0x180034bff  mov     r9d, eax; char *
0x180034c02  mov     edx, 3D3h; void *
0x180034c07  lea     r8, aCW1SSrcOrchest_40; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x180034c0e  mov     rcx, [rbp+58h]; this
0x180034c12  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034c17  jmp     loc_180034B5E
0x180034c1c  mov     [rsp+150h+hObject], 0
0x180034c25  xor     r9d, r9d
0x180034c28  xor     r8d, r8d
0x180034c2b  mov     edx, r13d
0x180034c2e  lea     rcx, [rsp+150h+hObject]
0x180034c33  call    ?try_create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAA_NW4EventOptions@2@PEB_WPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180034c38  test    al, al
0x180034c3a  jnz     short loc_180034C69
0x180034c3c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180034c41  mov     edi, eax
0x180034c43  test    eax, eax
0x180034c45  jns     short loc_180034C69
0x180034c47  mov     rcx, [rbp+58h]; this
0x180034c4b  mov     r9d, eax; char *
0x180034c4e  lea     r8, aCW1SSrcOrchest_40; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x180034c55  mov     edx, 3D6h; void *
0x180034c5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034c5f  mov     rbx, [rsp+150h+hObject]
0x180034c64  jmp     loc_180034E90
0x180034c69  mov     [rbp+50h+WaitHandle], r12
0x180034c6d  mov     rax, cs:qword_180150118
0x180034c74  mov     rax, [rax+0C0h]
0x180034c7b  mov     [rbp+50h+WaitHandle], r12
0x180034c7f  mov     [rsp+150h+var_128], 8
0x180034c87  mov     qword ptr [rsp+150h+var_130], 0; int
0x180034c90  lea     r9, StopService
0x180034c97  mov     rbx, [rsp+150h+hObject]
0x180034c9c  mov     r8, rbx
0x180034c9f  mov     rdx, rsi
0x180034ca2  lea     rcx, [rbp+50h+WaitHandle]
0x180034ca6  call    _guard_dispatch_icall
0x180034cab  test    eax, eax
0x180034cad  jz      short loc_180034CCE
0x180034caf  mov     rcx, [rbp+58h]; this
0x180034cb3  mov     r9d, eax; char *
0x180034cb6  lea     r8, aCW1SSrcOrchest_40; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x180034cbd  mov     edx, 3E0h; void *
0x180034cc2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180034cc7  mov     edi, eax
0x180034cc9  jmp     loc_180034E7B
0x180034cce  xor     edx, edx; dwCoInit
0x180034cd0  xor     ecx, ecx; pvReserved
0x180034cd2  call    cs:__imp_CoInitializeEx
0x180034cd8  mov     rcx, [rbp+58h]; this
0x180034cdc  test    eax, eax
0x180034cde  js      loc_180034EE2
0x180034ce4  mov     [rsp+150h+var_110], r13b
0x180034ce9  mov     rcx, rbx; void *
0x180034cec  call    ?InitializeService@@YAJPEAX@Z; InitializeService(void *)
0x180034cf1  mov     edi, eax
0x180034cf3  test    eax, eax
0x180034cf5  jns     short loc_180034D14
0x180034cf7  mov     rcx, [rbp+58h]; this
0x180034cfb  mov     r9d, eax; char *
0x180034cfe  lea     r8, aCW1SSrcOrchest_40; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x180034d05  mov     edx, 3E4h; void *
0x180034d0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034d0f  jmp     loc_180034E74
0x180034d14  mov     sil, r13b
0x180034d17  mov     [rsp+150h+var_10B], r13b
0x180034d1c  lea     rax, aUsosvcSettingS; "UsoSvc setting service state to: SERVIC"...
0x180034d23  mov     [rsp+150h+var_100], rax
0x180034d28  mov     [rsp+150h+var_F8], 30h ; '0'
0x180034d31  lea     rcx, [rsp+150h+var_100]
0x180034d36  call    ??$Log@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::Log<>(std::wstring_view)
0x180034d3b  mov     cs:ServiceStatus.dwControlsAccepted, r13d
0x180034d42  xor     r8d, r8d; unsigned int
0x180034d45  xor     edx, edx; unsigned int
0x180034d47  lea     ecx, [rdx+4]; unsigned int
0x180034d4a  call    ?UpdateServiceStatus@ServiceHelpers@@SAJKKK@Z; ServiceHelpers::UpdateServiceStatus(ulong,ulong,ulong)
0x180034d4f  mov     edi, eax
0x180034d51  test    eax, eax
0x180034d53  jns     short loc_180034D72
0x180034d55  mov     rcx, [rbp+58h]; this
0x180034d59  mov     r9d, eax; char *
0x180034d5c  lea     r8, aCW1SSrcOrchest_40; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x180034d63  mov     edx, 3EAh; void *
0x180034d68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034d6d  jmp     loc_180034E69
0x180034d72  call    ?CreateOrchestratorKey@ServiceHelpers@@SAJXZ; ServiceHelpers::CreateOrchestratorKey(void)
0x180034d77  call    ?CreateInstallAtShutdownKey@ServiceHelpers@@SAJXZ; ServiceHelpers::CreateInstallAtShutdownKey(void)
0x180034d7c  call    ?SvcAddRef@@YAXXZ; SvcAddRef(void)
0x180034d81  call    ?SvcRelease@@YAXXZ; SvcRelease(void)
0x180034d86  mov     rsi, rbx
0x180034d89  xor     ebx, ebx
0x180034d8b  mov     [rsp+150h+hObject], rbx
0x180034d90  mov     rdi, cs:hObject
0x180034d97  test    rdi, rdi
0x180034d9a  jz      short loc_180034DC3
0x180034d9c  call    cs:__imp_GetLastError
0x180034da2  mov     r14d, eax
0x180034da5  mov     rcx, rdi; hObject
0x180034da8  call    cs:__imp_CloseHandle
0x180034dae  mov     rcx, [rbp+58h]; this
0x180034db2  test    eax, eax
0x180034db4  jz      loc_180034EAF
0x180034dba  mov     ecx, r14d; dwErrCode
0x180034dbd  call    cs:__imp_SetLastError
0x180034dc3  mov     cs:hObject, rsi
0x180034dca  mov     r14, [rbp+50h+WaitHandle]
0x180034dce  mov     [rbp+50h+WaitHandle], r12
0x180034dd2  mov     rsi, cs:WaitHandle
0x180034dd9  cmp     rsi, r12
0x180034ddc  jz      short loc_180034DFC
0x180034dde  test    rsi, rsi
0x180034de1  jz      short loc_180034DFC
0x180034de3  call    cs:__imp_GetLastError
0x180034de9  mov     edi, eax
0x180034deb  mov     rcx, rsi; WaitHandle
0x180034dee  call    cs:__imp_UnregisterWait
0x180034df4  mov     ecx, edi; dwErrCode
0x180034df6  call    cs:__imp_SetLastError
0x180034dfc  mov     cs:WaitHandle, r14
0x180034e03  xor     sil, sil
0x180034e06  mov     [rsp+150h+var_10B], sil
0x180034e0b  xor     r14b, r14b
0x180034e0e  mov     byte ptr [rsp+150h+var_E8], r14b
0x180034e13  mov     rcx, [rbp+50h+var_40]
0x180034e17  mov     rax, [rcx]
0x180034e1a  lea     rdx, [rsp+150h+var_100]
0x180034e1f  mov     rax, [rax+10h]
0x180034e23  call    _guard_dispatch_icall
0x180034e28  mov     rdx, [rax]
0x180034e2b  mov     [rax], rbx
0x180034e2e  mov     rcx, cs:?g_svcActivity@@3V?$unique_ptr@VServiceActivity@Telemetry@SystemInterface@@U?$default_delete@VServiceActivity@Telemetry@SystemInterface@@@std@@@std@@A; std::unique_ptr<SystemInterface::Telemetry::ServiceActivity> g_svcActivity
0x180034e35  mov     cs:?g_svcActivity@@3V?$unique_ptr@VServiceActivity@Telemetry@SystemInterface@@U?$default_delete@VServiceActivity@Telemetry@SystemInterface@@@std@@@std@@A, rdx; std::unique_ptr<SystemInterface::Telemetry::ServiceActivity> g_svcActivity
0x180034e3c  test    rcx, rcx
0x180034e3f  jz      short loc_180034E4F
0x180034e41  mov     rax, [rcx]
0x180034e44  mov     edx, r13d
0x180034e47  mov     rax, [rax]
0x180034e4a  call    _guard_dispatch_icall
0x180034e4f  mov     rcx, [rsp+150h+var_100]
0x180034e54  test    rcx, rcx
0x180034e57  jz      short loc_180034E67
0x180034e59  mov     rax, [rcx]
0x180034e5c  mov     edx, r13d
0x180034e5f  mov     rax, [rax]
  ... truncated ...
```
