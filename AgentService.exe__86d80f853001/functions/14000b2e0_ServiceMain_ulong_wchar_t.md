# ServiceMain(ulong,wchar_t * *)

- ea: `0x14000b2e0`
- end: `0x14000b8c5`
- name: `?ServiceMain@@YAXKPEAPEA_W@Z`
- size: `1509`
- prototype: `void __fastcall(__int64, wchar_t **)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x14000108c`
- `0x140003e50`
- `0x140003e74`
- `0x14000ac58`
- `0x14000ac88`
- `0x14000acc4`
- `0x14000b1c4`
- `0x14000b2e0`
- `0x14000bc28`
- `0x14000bc7c`
- `0x14000d940`
- `0x14000d950`
- `0x1400125ac`
- `0x140019b3c`
- `0x14001a65c`
- `0x14009b010`

## import_xrefs

- `ADVAPI32!EventSetInformation` at `0x14000b3c0`
- `ADVAPI32!EventSetInformation` at `0x14000b3c0`
- `ADVAPI32!RegisterServiceCtrlHandlerW` at `0x14000b40f`
- `ADVAPI32!RegisterServiceCtrlHandlerW` at `0x14000b40f`
- `ADVAPI32!SetServiceStatus` at `0x14000b43b`
- `ADVAPI32!SetServiceStatus` at `0x14000b7ab`
- `ADVAPI32!SetServiceStatus` at `0x14000b43b`
- `ADVAPI32!SetServiceStatus` at `0x14000b7ab`
- `ADVAPI32!EventRegister` at `0x14000b3a1`
- `ADVAPI32!EventRegister` at `0x14000b3a1`
- `KERNEL32!SetProcessMitigationPolicy` at `0x14000b5e6`
- `KERNEL32!SetProcessMitigationPolicy` at `0x14000b5e6`
- `KERNEL32!GetLastError` at `0x14000b5f0`
- `KERNEL32!GetLastError` at `0x14000b604`
- `KERNEL32!GetLastError` at `0x14000b888`
- `KERNEL32!GetLastError` at `0x14000b5f0`
- `KERNEL32!GetLastError` at `0x14000b604`
- `KERNEL32!GetLastError` at `0x14000b888`
- `KERNEL32!OutputDebugStringW` at `0x14000b325`
- `KERNEL32!OutputDebugStringW` at `0x14000b34c`
- `KERNEL32!OutputDebugStringW` at `0x14000b325`
- `KERNEL32!OutputDebugStringW` at `0x14000b34c`

## string_xrefs

- `0x14000b31e`: `Failed to register the UE-V event log service for Agent Service`
- `0x14000b345`: `Failed to register the UE-V event log service for IPC`
- `0x14000b3c6`: `AgentService.ServiceMain: Entry`
- `0x14000b405`: `UevAgentService`
- `0x14000b5f8`: `AgentService.ServiceMain: Failed to set image mitigation policy options, error = 0x%X`
- `0x14000b650`: `AgentService.ServiceMain: NotificationListener was successfully started.`
- `0x14000b68b`: `AgentService.ServiceMain: Failed to start listening for notifications, status = 0x%X`
- `0x14000b6a0`: `AgentService.ServiceMain: Failed to set necessary privilege, status = 0x%X`
- `0x14000b777`: `AgentService.ServiceMain: Initialization failed: Returning service-specific error code = 0x%X`
- `0x14000b75c`: `AgentService.ServiceMain: The service was successfully initialized`
- `0x14000b890`: `AgentService.ServiceMain: Service control handler registration failed, error = 0x%X`
- `0x14000b89c`: `AgentService.ServiceMain: Exit`
- `0x14000b44a`: `UevAgentService1`
- `0x14000b45b`: `VirtualRegistryPassthroughEx`
- `0x14000b473`: `SOFTWARE\Wow6432Node\Microsoft\SoftGrid\4.5\Client\AppFS\ServiceInclusions`
- `0x14000b4e8`: `PassThroughPaths`
- `0x14000b50e`: `Software\Microsoft\AppV\Subsystem\VirtualRegistry`

## pseudocode

```c
void __fastcall ServiceMain(__int64 a1, wchar_t **a2)
{
  __int64 v2; // rdx
  SERVICE_STATUS_HANDLE v3; // rax
  DWORD v4; // esi
  const wchar_t *v5; // rcx
  signed int v6; // edi
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 *v9; // rdx
  signed int LastError; // eax
  Uev::NotificationListener *v11; // rcx
  bool v12; // [rsp+30h] [rbp-168h] BYREF
  bool v13; // [rsp+31h] [rbp-167h] BYREF
  int v14; // [rsp+34h] [rbp-164h] BYREF
  Uev::UevException *v15; // [rsp+38h] [rbp-160h] BYREF
  _DWORD v16[4]; // [rsp+40h] [rbp-158h] BYREF
  _QWORD v17[8]; // [rsp+50h] [rbp-148h] BYREF
  _QWORD v18[8]; // [rsp+90h] [rbp-108h] BYREF
  GUID ProviderId; // [rsp+D0h] [rbp-C8h] BYREF
  int *v20; // [rsp+F0h] [rbp-A8h]
  __int64 v21; // [rsp+F8h] [rbp-A0h]
  _DWORD *v22; // [rsp+100h] [rbp-98h]
  __int64 v23; // [rsp+108h] [rbp-90h]
  struct _EVENT_DATA_DESCRIPTOR v24; // [rsp+110h] [rbp-88h] BYREF
  GUID *p_ProviderId; // [rsp+130h] [rbp-68h]
  __int64 v26; // [rsp+138h] [rbp-60h]
  int *v27; // [rsp+140h] [rbp-58h]
  __int64 v28; // [rsp+148h] [rbp-50h]
  _DWORD *v29; // [rsp+150h] [rbp-48h]
  __int64 v30; // [rsp+158h] [rbp-40h]

  if ( (unsigned int)McGenEventRegister_EventRegister(
                       UevAppAgentProvider,
                       a2,
                       UevAppAgentProvider_Context,
                       UevAppAgentProvider_Context) )
    OutputDebugStringW(L"Failed to register the UE-V event log service for Agent Service");
  if ( (unsigned int)McGenEventRegister_EventRegister(
                       UevIPCProvider,
                       v2,
                       UevIPCProvider_Context,
                       UevIPCProvider_Context) )
    OutputDebugStringW(L"Failed to register the UE-V event log service for IPC");
  ProviderId = (GUID)*((_OWORD *)off_1400CB250 - 1);
  if ( RegHandle )
    __fastfail(5u);
  qword_1400CB270 = 0;
  qword_1400CB278 = 0;
  if ( !EventRegister(&ProviderId, tlgEnableCallback, &dword_1400CB248, &RegHandle) )
    EventSetInformation(RegHandle, 2, off_1400CB250, *(unsigned __int16 *)off_1400CB250);
  DbgTrace<5>(L"AgentService.ServiceMain: Entry");
  ServiceStatus.dwServiceType = 48;
  ServiceStatus.dwCurrentState = 2;
  *(_QWORD *)&ServiceStatus.dwControlsAccepted = 5;
  *(_QWORD *)&ServiceStatus.dwServiceSpecificExitCode = 0;
  ServiceStatus.dwWaitHint = 0;
  v3 = RegisterServiceCtrlHandlerW(L"UevAgentService", ControlHandler);
  hStatus = v3;
  if ( !v3 )
  {
    GetLastError();
    DbgTraceFrmtErr<long>((wchar_t *)L"AgentService.ServiceMain: Service control handler registration failed, error = 0x%X");
    goto LABEL_43;
  }
  v4 = 0;
  ServiceStatus.dwCurrentState = 4;
  SetServiceStatus(v3, &ServiceStatus);
  v17[1] = -2147483646;
  v17[2] = L"UevAgentService1";
  v17[3] = L"UevAgentService";
  v17[4] = L"VirtualRegistryPassthroughEx";
  v17[5] = L"HKEY_CURRENT_USER\\SOFTWARE\\Microsoft\\UEV";
  v17[6] = L"SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS\\ServiceInclusions";
  v17[7] = L"SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\SystemGuard\\Overrides";
  v17[0] = &Uev::AppV4xServiceInclusion::`vftable';
  if ( !(unsigned int)Uev::AppVServiceInclusion::AddServiceInclusion((Uev::AppVServiceInclusion *)v17) )
    (*(void (__fastcall **)(_QWORD *))(v17[0] + 8LL))(v17);
  v18[1] = -2147483646;
  v18[2] = Uev::AppV5xServiceInclusion::VALUE_NAME;
  v18[3] = Uev::AppV5xServiceInclusion::VALUE_DATA;
  v18[4] = L"PassThroughPaths";
  v18[5] = L"HKEY_CURRENT_USER\\SOFTWARE\\Microsoft\\UEV";
  v18[6] = Uev::AppV5xServiceInclusion::APP_V_SERVICE_INCLUSIONS_KEY;
  v18[7] = L"Software\\Microsoft\\AppV\\Subsystem\\VirtualRegistry";
  v18[0] = &Uev::AppV5xServiceInclusion::`vftable';
  if ( !(unsigned int)_scrt_initialize_winrt(v18) )
    (*(void (__fastcall **)(_QWORD *))(v18[0] + 8LL))(v18);
  try
  {
    v6 = Uev::Util::EnablePrivilege(v5);
    if ( v6 < 0 )
    {
      DbgTraceFrmtErr<long>((wchar_t *)L"AgentService.ServiceMain: Failed to set necessary privilege, status = 0x%X");
      v4 = 3;
      goto LABEL_48;
    }
    v12 = 0;
    v13 = 0;
    GetUevStatus(&v12, &v13);
    if ( v12 )
    {
      if ( v13 )
      {
        v6 = -2147162110;
        v4 = 6;
        if ( (Microsoft_User_Experience_Virtualization_App_AgentEnableBits & 0x10) != 0 )
        {
          v9 = AgentServiceLog_RebootRequiredToStartService;
          goto LABEL_28;
        }
      }
      else
      {
        v16[0] = 1;
        if ( !(unsigned int)SetProcessMitigationPolicy(16, v16) )
        {
          GetLastError();
          DbgTraceFrmtErr<long>((wchar_t *)L"AgentService.ServiceMain: Failed to set image mitigation policy options, error = 0x%X");
          LastError = GetLastError();
          v6 = LastError;
          if ( LastError > 0 )
            v6 = (unsigned __int16)LastError | 0x80070000;
          v4 = 11;
          goto LABEL_48;
        }
        *(_QWORD *)&ProviderId.Data1 = operator new(0x128u);
        pCreateProcNotificationListener = (LPVOID)Uev::CreateProcNotificationListener::CreateProcNotificationListener(*(Uev::CreateProcNotificationListener **)&ProviderId.Data1);
        v6 = Uev::NotificationListener::Start(v11);
        if ( v6 < 0 )
        {
          DbgTraceFrmtErr<long>((wchar_t *)L"AgentService.ServiceMain: Failed to start listening for notifications, status = 0x%X");
          v4 = 1;
          goto LABEL_48;
        }
        DbgTrace<5>(L"AgentService.ServiceMain: NotificationListener was successfully started.");
        if ( (Microsoft_User_Experience_Virtualization_App_AgentEnableBits & 2) != 0 )
        {
          v9 = AgentServiceLog_ServiceStarted;
          goto LABEL_28;
        }
      }
    }
    else
    {
      v6 = -2147162109;
      v4 = 7;
      if ( (Microsoft_User_Experience_Virtualization_App_AgentEnableBits & 0x10) != 0 )
      {
        v9 = AgentServiceLog_UevDisabled;
LABEL_28:
        McGenEventWrite_EventWriteTransfer(UevAppAgentProvider_Context, v9, v8, 1, &ProviderId);
      }
    }
  }
  catch ( Uev::UevException *v15 )
  {
    std::wstring::wstring(&ProviderId, (char *)v15 + 24);
    DbgTraceFrmtErr<wchar_t const *>((wchar_t *)L"AgentService.ServiceMain: Unexpected exception caught, msg = %s");
    std::wstring::_Tidy_deallocate(&ProviderId);
    v16[0] = 5;
    v14 = -2147467259;
    v4 = 5;
    v6 = -2147467259;
    goto LABEL_37;
  }
  catch ( ... )
  {
    DbgTrace<2>(L"AgentService.ServiceMain: Unexpected exception caught");
    v16[0] = 4;
    v14 = -2147467259;
    v4 = 4;
    v6 = -2147467259;
    goto LABEL_37;
  }
LABEL_48:
  if ( v6 < 0 )
  {
LABEL_37:
    DbgTraceFrmtErr<long>((wchar_t *)L"AgentService.ServiceMain: Initialization failed: Returning service-specific error code = 0x%X");
    ServiceStatus.dwCurrentState = 1;
    ServiceStatus.dwWin32ExitCode = 1066;
    ServiceStatus.dwServiceSpecificExitCode = v4;
    SetServiceStatus(hStatus, &ServiceStatus);
    if ( (unsigned int)dword_1400CB248 > 5
      && (qword_1400CB258 & 0x400000000000LL) != 0
      && (qword_1400CB260 & 0x400000000000LL) == qword_1400CB260 )
    {
      v16[0] = ServiceStatus.dwServiceSpecificExitCode;
      v14 = v6;
      ProviderId.Data1 = 1;
      v29 = v16;
      v30 = 4;
      v27 = &v14;
      v28 = 4;
      p_ProviderId = &ProviderId;
      v26 = 4;
      tlgWriteTransfer_EventWriteTransfer((int)&dword_1400CB248, (int)&byte_1400B7691, 0, 0, 5u, &v24);
    }
  }
  else
  {
    if ( (unsigned int)dword_1400CB248 > 5 )
    {
      v7 = qword_1400CB260;
      if ( (qword_1400CB258 & 0x400000000000LL) != 0 && (qword_1400CB260 & 0x400000000000LL) == qword_1400CB260 )
      {
        v16[0] = v6;
        v14 = 1;
        v22 = v16;
        v23 = 4;
        v20 = &v14;
        v21 = 4;
        tlgWriteTransfer_EventWriteTransfer(
          (int)&dword_1400CB248,
          (int)&byte_1400B774F,
          0,
          0,
          4u,
          (PEVENT_DATA_DESCRIPTOR)&ProviderId);
      }
    }
    DbgTrace<4>(L"AgentService.ServiceMain: The service was successfully initialized", v7);
  }
LABEL_43:
  DbgTrace<5>(L"AgentService.ServiceMain: Exit");
}

```

## disassembly

```asm
0x14000b2e0  push    rbx
0x14000b2e2  push    rsi
0x14000b2e3  push    rdi
0x14000b2e4  push    r15
0x14000b2e6  sub     rsp, 178h
0x14000b2ed  mov     rax, cs:__security_cookie
0x14000b2f4  xor     rax, rsp
0x14000b2f7  mov     [rsp+198h+var_38], rax
0x14000b2ff  xor     ebx, ebx
0x14000b301  lea     r15, UevAppAgentProvider_Context
0x14000b308  mov     r9, r15
0x14000b30b  mov     r8, r15
0x14000b30e  lea     rcx, UevAppAgentProvider
0x14000b315  call    McGenEventRegister_EventRegister
0x14000b31a  test    eax, eax
0x14000b31c  jz      short loc_14000B32B
0x14000b31e  lea     rcx, aFailedToRegist; "Failed to register the UE-V event log s"...
0x14000b325  call    cs:__imp_OutputDebugStringW
0x14000b32b  lea     r8, UevIPCProvider_Context
0x14000b332  mov     r9, r8
0x14000b335  lea     rcx, UevIPCProvider
0x14000b33c  call    McGenEventRegister_EventRegister
0x14000b341  test    eax, eax
0x14000b343  jz      short loc_14000B352
0x14000b345  lea     rcx, aFailedToRegist_0; "Failed to register the UE-V event log s"...
0x14000b34c  call    cs:__imp_OutputDebugStringW
0x14000b352  mov     rax, cs:off_1400CB250
0x14000b359  movups  xmm0, xmmword ptr [rax-10h]
0x14000b35d  movdqu  xmmword ptr [rsp+198h+ProviderId.Data1], xmm0
0x14000b366  cmp     cs:RegHandle, rbx
0x14000b36d  jz      short loc_14000B376
0x14000b36f  mov     ecx, 5
0x14000b374  int     29h; Win8: RtlFailFast(ecx)
0x14000b376  mov     cs:qword_1400CB270, rbx
0x14000b37d  mov     cs:qword_1400CB278, rbx
0x14000b384  lea     r9, RegHandle; RegHandle
0x14000b38b  lea     r8, dword_1400CB248; CallbackContext
0x14000b392  lea     rdx, _tlgEnableCallback; EnableCallback
0x14000b399  lea     rcx, [rsp+198h+ProviderId]; ProviderId
0x14000b3a1  call    cs:__imp_EventRegister
0x14000b3a7  test    eax, eax
0x14000b3a9  jnz     short loc_14000B3C6
0x14000b3ab  mov     r8, cs:off_1400CB250
0x14000b3b2  movzx   r9d, word ptr [r8]
0x14000b3b6  lea     edx, [rax+2]
0x14000b3b9  mov     rcx, cs:RegHandle
0x14000b3c0  call    cs:__imp_EventSetInformation
0x14000b3c6  lea     rcx, aAgentserviceSe; "AgentService.ServiceMain: Entry"
0x14000b3cd  call    ??$DbgTrace@$04@@YAXPEB_W@Z; DbgTrace<5>(wchar_t const *)
0x14000b3d2  mov     cs:?ServiceStatus@@3U_SERVICE_STATUS@@A.dwServiceType, 30h ; '0'; _SERVICE_STATUS ServiceStatus ...
0x14000b3dc  mov     cs:?ServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 2; _SERVICE_STATUS ServiceStatus ...
0x14000b3e6  mov     qword ptr cs:?ServiceStatus@@3U_SERVICE_STATUS@@A.dwControlsAccepted, 5; _SERVICE_STATUS ServiceStatus ...
0x14000b3f1  mov     qword ptr cs:?ServiceStatus@@3U_SERVICE_STATUS@@A.dwServiceSpecificExitCode, rbx; _SERVICE_STATUS ServiceStatus ...
0x14000b3f8  mov     cs:?ServiceStatus@@3U_SERVICE_STATUS@@A.dwWaitHint, ebx; _SERVICE_STATUS ServiceStatus ...
0x14000b3fe  lea     rdx, ?ControlHandler@@YAXK@Z; lpHandlerProc
0x14000b405  lea     rdi, ServiceName; "UevAgentService"
0x14000b40c  mov     rcx, rdi; lpServiceName
0x14000b40f  call    cs:__imp_RegisterServiceCtrlHandlerW
0x14000b415  mov     cs:?hStatus@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * hStatus
0x14000b41c  test    rax, rax
0x14000b41f  jz      loc_14000B888
0x14000b425  mov     esi, ebx
0x14000b427  mov     cs:?ServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 4; _SERVICE_STATUS ServiceStatus ...
0x14000b431  lea     rdx, ?ServiceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x14000b438  mov     rcx, rax; hServiceStatus
0x14000b43b  call    cs:__imp_SetServiceStatus
0x14000b441  mov     [rsp+198h+var_140], 0FFFFFFFF80000002h
0x14000b44a  lea     rax, aUevagentservic; "UevAgentService1"
0x14000b451  mov     [rsp+198h+var_138], rax
0x14000b456  mov     [rsp+198h+var_130], rdi
0x14000b45b  lea     rax, aVirtualregistr; "VirtualRegistryPassthroughEx"
0x14000b462  mov     [rsp+198h+var_128], rax
0x14000b467  lea     rdi, aHkeyCurrentUse; "HKEY_CURRENT_USER\\SOFTWARE\\Microsoft"...
0x14000b46e  mov     [rsp+198h+var_120], rdi
0x14000b473  lea     rax, aSoftwareWow643_0; "SOFTWARE\\Wow6432Node\\Microsoft\\SoftG"...
0x14000b47a  mov     [rsp+198h+var_118], rax
0x14000b482  lea     rax, aSoftwareWow643; "SOFTWARE\\Wow6432Node\\Microsoft\\SoftG"...
0x14000b489  mov     [rsp+198h+var_110], rax
0x14000b491  lea     rax, ??_7AppV4xServiceInclusion@Uev@@6B@; const Uev::AppV4xServiceInclusion::`vftable'
0x14000b498  mov     [rsp+198h+var_148], rax
0x14000b49d  lea     rcx, [rsp+198h+var_148]; this
0x14000b4a2  call    ?AddServiceInclusion@AppVServiceInclusion@Uev@@MEAAJXZ; Uev::AppVServiceInclusion::AddServiceInclusion(void)
0x14000b4a7  test    eax, eax
0x14000b4a9  jnz     short loc_14000B4BE
0x14000b4ab  mov     rax, [rsp+198h+var_148]
0x14000b4b0  lea     rcx, [rsp+198h+var_148]
0x14000b4b5  mov     rax, [rax+8]
0x14000b4b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b4be  mov     [rsp+198h+var_100], 0FFFFFFFF80000002h
0x14000b4ca  mov     rax, cs:?VALUE_NAME@AppV5xServiceInclusion@Uev@@0PEB_WEB; wchar_t const * const Uev::AppV5xServiceInclusion::VALUE_NAME
0x14000b4d1  mov     [rsp+198h+var_F8], rax
0x14000b4d9  mov     rax, cs:?VALUE_DATA@AppV5xServiceInclusion@Uev@@0PEB_WEB; wchar_t const * const Uev::AppV5xServiceInclusion::VALUE_DATA
0x14000b4e0  mov     [rsp+198h+var_F0], rax
0x14000b4e8  lea     rax, aPassthroughpat; "PassThroughPaths"
0x14000b4ef  mov     [rsp+198h+var_E8], rax
0x14000b4f7  mov     [rsp+198h+var_E0], rdi
0x14000b4ff  mov     rax, cs:?APP_V_SERVICE_INCLUSIONS_KEY@AppV5xServiceInclusion@Uev@@0PEB_WEB; wchar_t const * const Uev::AppV5xServiceInclusion::APP_V_SERVICE_INCLUSIONS_KEY
0x14000b506  mov     [rsp+198h+var_D8], rax
0x14000b50e  lea     rax, aSoftwareMicros_1; "Software\\Microsoft\\AppV\\Subsystem\\V"...
0x14000b515  mov     [rsp+198h+var_D0], rax
0x14000b51d  lea     rax, ??_7AppV5xServiceInclusion@Uev@@6B@; const Uev::AppV5xServiceInclusion::`vftable'
0x14000b524  mov     [rsp+198h+var_108], rax
0x14000b52c  lea     rcx, [rsp+198h+var_108]
0x14000b534  call    __scrt_initialize_winrt
0x14000b539  test    eax, eax
0x14000b53b  jnz     short loc_14000B557
0x14000b53d  mov     rax, [rsp+198h+var_108]
0x14000b545  lea     rcx, [rsp+198h+var_108]
0x14000b54d  mov     rax, [rax+8]
0x14000b551  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b556  nop
0x14000b557  call    ?EnablePrivilege@Util@Uev@@SAJPEB_W@Z; Uev::Util::EnablePrivilege(wchar_t const *)
0x14000b55c  mov     edi, eax
0x14000b55e  test    eax, eax
0x14000b560  js      loc_14000B69E
0x14000b566  mov     [rsp+198h+var_168], bl
0x14000b56a  mov     [rsp+198h+var_167], bl
0x14000b56e  lea     rdx, [rsp+198h+var_167]; bool *
0x14000b573  lea     rcx, [rsp+198h+var_168]; bool *
0x14000b578  call    ?GetUevStatus@@YAXPEA_N0@Z; GetUevStatus(bool *,bool *)
0x14000b57d  cmp     [rsp+198h+var_168], bl
0x14000b581  jnz     short loc_14000B5A6
0x14000b583  mov     edi, 8004E803h
0x14000b588  mov     esi, 7
0x14000b58d  test    cs:Microsoft_User_Experience_Virtualization_App_AgentEnableBits, 10h
0x14000b594  jz      loc_14000B6B1
0x14000b59a  lea     rdx, AgentServiceLog_UevDisabled
0x14000b5a1  jmp     loc_14000B66C
0x14000b5a6  cmp     [rsp+198h+var_167], bl
0x14000b5aa  jz      short loc_14000B5CF
0x14000b5ac  mov     edi, 8004E802h
0x14000b5b1  mov     esi, 6
0x14000b5b6  test    cs:Microsoft_User_Experience_Virtualization_App_AgentEnableBits, 10h
0x14000b5bd  jz      loc_14000B6B1
0x14000b5c3  lea     rdx, AgentServiceLog_RebootRequiredToStartService
0x14000b5ca  jmp     loc_14000B66C
0x14000b5cf  mov     [rsp+198h+var_158], 1
0x14000b5d7  mov     r8d, 4
0x14000b5dd  lea     rdx, [rsp+198h+var_158]
0x14000b5e2  lea     ecx, [r8+0Ch]
0x14000b5e6  call    cs:__imp_SetProcessMitigationPolicy
0x14000b5ec  test    eax, eax
0x14000b5ee  jnz     short loc_14000B623
0x14000b5f0  call    cs:__imp_GetLastError
0x14000b5f6  mov     edx, eax
0x14000b5f8  lea     rcx, aAgentserviceSe_5; "AgentService.ServiceMain: Failed to set"...
0x14000b5ff  call    ??$DbgTraceFrmtErr@J@@YAXPEB_WJ@Z; DbgTraceFrmtErr<long>(wchar_t const *,long)
0x14000b604  call    cs:__imp_GetLastError
0x14000b60a  mov     edi, eax
0x14000b60c  test    eax, eax
0x14000b60e  jle     short loc_14000B619
0x14000b610  movzx   edi, ax
0x14000b613  or      edi, 80070000h
0x14000b619  mov     esi, 0Bh
0x14000b61e  jmp     loc_14000B6B1
0x14000b623  mov     ecx, 128h; Size
0x14000b628  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000b62d  mov     qword ptr [rsp+198h+ProviderId.Data1], rax
0x14000b635  mov     rcx, rax; this
0x14000b638  call    ??0CreateProcNotificationListener@Uev@@QEAA@XZ; Uev::CreateProcNotificationListener::CreateProcNotificationListener(void)
0x14000b63d  nop
0x14000b63e  mov     cs:?pCreateProcNotificationListener@@3PEAVCreateProcNotificationListener@Uev@@EA, rax; Uev::CreateProcNotificationListener * pCreateProcNotificationListener
0x14000b645  call    ?Start@NotificationListener@Uev@@QEAAJXZ; Uev::NotificationListener::Start(void)
0x14000b64a  mov     edi, eax
0x14000b64c  test    eax, eax
0x14000b64e  js      short loc_14000B689
0x14000b650  lea     rcx, aAgentserviceSe_8; "AgentService.ServiceMain: NotificationL"...
0x14000b657  call    ??$DbgTrace@$04@@YAXPEB_W@Z; DbgTrace<5>(wchar_t const *)
0x14000b65c  test    cs:Microsoft_User_Experience_Virtualization_App_AgentEnableBits, 2
0x14000b663  jz      short loc_14000B6B1
0x14000b665  lea     rdx, AgentServiceLog_ServiceStarted
0x14000b66c  lea     rax, [rsp+198h+ProviderId]
0x14000b674  mov     qword ptr [rsp+198h+var_178], rax
0x14000b679  mov     r9d, 1
0x14000b67f  mov     rcx, r15
0x14000b682  call    McGenEventWrite_EventWriteTransfer
0x14000b687  jmp     short loc_14000B6B1
0x14000b689  mov     edx, eax
0x14000b68b  lea     rcx, aAgentserviceSe_0; "AgentService.ServiceMain: Failed to sta"...
0x14000b692  call    ??$DbgTraceFrmtErr@J@@YAXPEB_WJ@Z; DbgTraceFrmtErr<long>(wchar_t const *,long)
0x14000b697  mov     esi, 1
0x14000b69c  jmp     short loc_14000B6B1
0x14000b69e  mov     edx, eax
0x14000b6a0  lea     rcx, aAgentserviceSe_1; "AgentService.ServiceMain: Failed to set"...
0x14000b6a7  call    ??$DbgTraceFrmtErr@J@@YAXPEB_WJ@Z; DbgTraceFrmtErr<long>(wchar_t const *,long)
0x14000b6ac  mov     esi, 3
0x14000b6b1  test    edi, edi
0x14000b6b3  js      loc_14000B775
0x14000b6b9  mov     eax, cs:dword_1400CB248
0x14000b6bf  cmp     eax, 5
0x14000b6c2  jbe     loc_14000B75C
0x14000b6c8  mov     rdx, cs:qword_1400CB260
0x14000b6cf  mov     rax, cs:qword_1400CB258
0x14000b6d6  mov     rcx, 400000000000h
0x14000b6e0  test    rcx, rax
0x14000b6e3  jz      short loc_14000B75C
0x14000b6e5  mov     rax, rdx
0x14000b6e8  and     rax, rcx
0x14000b6eb  cmp     rax, rdx
0x14000b6ee  jnz     short loc_14000B75C
0x14000b6f0  mov     [rsp+198h+var_158], edi
0x14000b6f4  mov     [rsp+198h+var_164], 1
0x14000b6fc  lea     rax, [rsp+198h+var_158]
0x14000b701  mov     [rsp+198h+var_98], rax
0x14000b709  mov     [rsp+198h+var_90], 4
0x14000b715  lea     rax, [rsp+198h+var_164]
0x14000b71a  mov     [rsp+198h+var_A8], rax
0x14000b722  mov     [rsp+198h+var_A0], 4
0x14000b72e  lea     rax, [rsp+198h+ProviderId]
0x14000b736  mov     [rsp+198h+var_170], rax; PEVENT_DATA_DESCRIPTOR
0x14000b73b  mov     [rsp+198h+var_178], 4; ULONG
0x14000b743  xor     r9d, r9d; int
0x14000b746  xor     r8d, r8d; int
0x14000b749  lea     rdx, byte_1400B774F; int
0x14000b750  lea     rcx, dword_1400CB248; int
0x14000b757  call    _tlgWriteTransfer_EventWriteTransfer
0x14000b75c  lea     rcx, aAgentserviceSe_3; "AgentService.ServiceMain: The service w"...
0x14000b763  call    ??$DbgTrace@$03@@YAXPEB_W@Z; DbgTrace<4>(wchar_t const *)
0x14000b768  jmp     loc_14000B886
0x14000b76d  mov     esi, [rsp+198h+var_158]
0x14000b771  mov     edi, [rsp+198h+var_164]
0x14000b775  mov     edx, esi
0x14000b777  lea     rcx, aAgentserviceSe_6; "AgentService.ServiceMain: Initializatio"...
0x14000b77e  call    ??$DbgTraceFrmtErr@J@@YAXPEB_WJ@Z; DbgTraceFrmtErr<long>(wchar_t const *,long)
0x14000b783  mov     cs:?ServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 1; _SERVICE_STATUS ServiceStatus ...
0x14000b78d  mov     cs:?ServiceStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, 42Ah; _SERVICE_STATUS ServiceStatus ...
0x14000b797  mov     cs:?ServiceStatus@@3U_SERVICE_STATUS@@A.dwServiceSpecificExitCode, esi; _SERVICE_STATUS ServiceStatus ...
0x14000b79d  lea     rdx, ?ServiceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x14000b7a4  mov     rcx, cs:?hStatus@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x14000b7ab  call    cs:__imp_SetServiceStatus
0x14000b7b1  mov     eax, cs:dword_1400CB248
0x14000b7b7  cmp     eax, 5
0x14000b7ba  jbe     loc_14000B886
0x14000b7c0  mov     rdx, cs:qword_1400CB260
0x14000b7c7  mov     rax, cs:qword_1400CB258
0x14000b7ce  mov     rcx, 400000000000h
0x14000b7d8  test    rcx, rax
0x14000b7db  jz      loc_14000B886
0x14000b7e1  mov     rax, rdx
0x14000b7e4  and     rax, rcx
0x14000b7e7  cmp     rax, rdx
0x14000b7ea  jnz     loc_14000B886
0x14000b7f0  mov     eax, cs:?ServiceStatus@@3U_SERVICE_STATUS@@A.dwServiceSpecificExitCode; _SERVICE_STATUS ServiceStatus ...
0x14000b7f6  mov     [rsp+198h+var_158], eax
0x14000b7fa  mov     [rsp+198h+var_164], edi
0x14000b7fe  mov     [rsp+198h+ProviderId.Data1], 1
0x14000b809  lea     rax, [rsp+198h+var_158]
0x14000b80e  mov     [rsp+198h+var_48], rax
0x14000b816  mov     [rsp+198h+var_40], 4
0x14000b822  lea     rax, [rsp+198h+var_164]
0x14000b827  mov     [rsp+198h+var_58], rax
0x14000b82f  mov     [rsp+198h+var_50], 4
0x14000b83b  lea     rax, [rsp+198h+ProviderId]
0x14000b843  mov     [rsp+198h+var_68], rax
0x14000b84b  mov     [rsp+198h+var_60], 4
0x14000b857  lea     rax, [rsp+198h+var_88]
0x14000b85f  mov     [rsp+198h+var_170], rax; PEVENT_DATA_DESCRIPTOR
0x14000b864  mov     [rsp+198h+var_178], 5; ULONG
0x14000b86c  xor     r9d, r9d; int
0x14000b86f  xor     r8d, r8d; int
0x14000b872  lea     rdx, byte_1400B7691; int
0x14000b879  lea     rcx, dword_1400CB248; int
0x14000b880  call    _tlgWriteTransfer_EventWriteTransfer
0x14000b885  nop
0x14000b886  jmp     short loc_14000B89C
0x14000b888  call    cs:__imp_GetLastError
0x14000b88e  mov     edx, eax
0x14000b890  lea     rcx, aAgentserviceSe_2; "AgentService.ServiceMain: Service contr"...
0x14000b897  call    ??$DbgTraceFrmtErr@J@@YAXPEB_WJ@Z; DbgTraceFrmtErr<long>(wchar_t const *,long)
0x14000b89c  lea     rcx, aAgentserviceSe_9; "AgentService.ServiceMain: Exit"
0x14000b8a3  call    ??$DbgTrace@$04@@YAXPEB_W@Z; DbgTrace<5>(wchar_t const *)
0x14000b8a8  mov     rcx, [rsp+198h+var_38]
0x14000b8b0  xor     rcx, rsp; StackCookie
0x14000b8b3  call    __security_check_cookie
0x14000b8b8  add     rsp, 178h
0x14000b8bf  pop     r15
0x14000b8c1  pop     rdi
0x14000b8c2  pop     rsi
0x14000b8c3  pop     rbx
0x14000b8c4  retn
```
