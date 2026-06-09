# ServiceMain

- ea: `0x180005920`
- end: `0x180005d3c`
- name: `ServiceMain`
- size: `1052`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180005280`
- `0x180005920`
- `0x180006214`
- `0x1800063a0`
- `0x180006580`
- `0x180006634`
- `0x1800072cc`
- `0x18000827c`
- `0x180008360`
- `0x18000b2e0`
- `0x180013464`
- `0x18001bcba`
- `0x18001bcf0`
- `0x18001d010`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180005ab1`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180005c26`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180005ab1`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180005c26`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180005a26`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180005a26`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005b87`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005b87`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005baf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005baf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a3c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800059cb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800059cb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800059df`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800059df`
- `sstpcfg!GetSstpProxyConfig` at `0x180005af9`
- `sstpcfg!GetSstpProxyConfig` at `0x180005af9`

## string_xrefs

- `0x18000598b`: `ServiceMain`
- `0x180005a5c`: `RegisterServiceCtrlHandlerEx fails with 0x%x (%d)`
- `0x180005b29`: `ServiceMain: InitializeSstpServer failed with error %d`
- `0x180005b5f`: `ServiceMain failed to load proxy config from xml. LoadSstpProxyConfigFromXmlFile failed with error %d`
- `0x180005bcd`: `ServiceMain failed to initialize RPC server`
- `0x180005c98`: `ServiceMain failed to retrieve the svchost RegisterStopCallback`
- `0x180005c86`: `ServiceMain failed to register stop callback`
- `0x180005cd3`: `ServiceMain fails with 0x%x (%d)`

## pseudocode

```c
__int64 ServiceMain()
{
  unsigned int v0; // ebx
  HANDLE ProcessHeap; // rax
  _QWORD *v2; // rax
  const wchar_t *v3; // r8
  SERVICE_STATUS_HANDLE v4; // rax
  LPVOID v5; // rcx
  DWORD LastError; // eax
  int v7; // ebx
  unsigned int v8; // eax
  unsigned int SstpProxyConfigFromXmlFile; // eax
  RTL_SRWLOCK *v10; // rcx
  LPVOID v11; // rcx
  __int64 (__fastcall *v12)(char *, const WCHAR *, _QWORD, __int64 (__fastcall *)(_QWORD, _QWORD), _QWORD, int); // rax
  __int64 result; // rax
  int v14; // [rsp+40h] [rbp-C0h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+48h] [rbp-B8h] BYREF
  int v16; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v17[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  v14 = 0;
  v16 = 0;
  memset_0(v17, 0, sizeof(v17));
  if ( (int)McGenEventRegister_EventRegister() >= 0 )
    SetLibParams();
  if ( (byte_18002D803 & 0x10) != 0 )
  {
    LOWORD(v16) = 0;
    FormatRRASErrorString((wchar_t *)&v16, L"Entering %ws", L"ServiceMain");
    if ( (byte_18002D803 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(
        (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)RasSSTPSvcTraceInfo,
        (const wchar_t *)&v16);
  }
  v0 = 0;
  ProcessHeap = GetProcessHeap();
  v2 = HeapAlloc(ProcessHeap, 8u, 0x310u);
  SstpSvcGlobals = v2;
  if ( !v2 )
  {
    if ( (byte_18002D803 & 8) == 0 )
      goto LABEL_38;
    v3 = L"Unable to allocate memory for SstpSvcGlobals";
    goto LABEL_37;
  }
  v2[94] = -1;
  v4 = RegisterServiceCtrlHandlerExW(L"sstpsvc", (LPHANDLER_FUNCTION_EX)ServiceHandlerEx, 0);
  v5 = SstpSvcGlobals;
  *((_QWORD *)SstpSvcGlobals + 5) = v4;
  if ( !v4 )
  {
    LastError = GetLastError();
    v0 = LastError;
    if ( (byte_18002D803 & 8) == 0 )
      goto LABEL_38;
    LOWORD(v16) = 0;
    FormatRRASErrorString((wchar_t *)&v16, L"RegisterServiceCtrlHandlerEx fails with 0x%x (%d)", LastError, LastError);
LABEL_12:
    if ( (byte_18002D803 & 8) == 0 )
      goto LABEL_38;
    v3 = (const wchar_t *)&v16;
    goto LABEL_37;
  }
  ServiceStatus.dwServiceType = 32;
  *(_DWORD *)v5 = 2;
  ServiceStatus.dwCheckPoint = 1;
  ServiceStatus.dwWaitHint = 3000;
  ServiceStatus.dwCurrentState = *(_DWORD *)v5;
  SetServiceStatus(*((SERVICE_STATUS_HANDLE *)v5 + 5), &ServiceStatus);
  if ( (unsigned int)ConfigureMiniports(0x10u, 5u, (_QWORD *)SstpSvcGlobals + 37, (LPVOID *)SstpSvcGlobals + 38) )
    goto LABEL_38;
  v0 = InitializeService();
  if ( v0 )
    goto LABEL_38;
  GetSstpProxyConfig(0, &v14);
  v7 = v14;
  if ( v14 )
  {
    v8 = InitializeSstpServer(0);
    v0 = v8;
    if ( v8 )
    {
      if ( (byte_18002D803 & 8) == 0 )
        goto LABEL_38;
      LOWORD(v16) = 0;
      FormatRRASErrorString((wchar_t *)&v16, L"ServiceMain: InitializeSstpServer failed with error %d", v8);
      goto LABEL_12;
    }
    SstpProxyConfigFromXmlFile = LoadSstpProxyConfigFromXmlFile();
    v0 = SstpProxyConfigFromXmlFile;
    if ( SstpProxyConfigFromXmlFile )
    {
      if ( (byte_18002D803 & 8) == 0 )
        goto LABEL_38;
      LOWORD(v16) = 0;
      FormatRRASErrorString(
        (wchar_t *)&v16,
        L"ServiceMain failed to load proxy config from xml. LoadSstpProxyConfigFromXmlFile failed with error %d",
        SstpProxyConfigFromXmlFile);
      goto LABEL_12;
    }
    v7 = v14;
  }
  AcquireSRWLockExclusive((PSRWLOCK)SstpSvcGlobals + 96);
  v10 = (RTL_SRWLOCK *)SstpSvcGlobals;
  if ( v7 )
    *((_DWORD *)SstpSvcGlobals + 194) |= 1u;
  else
    *((_DWORD *)SstpSvcGlobals + 194) &= ~1u;
  ReleaseSRWLockExclusive(v10 + 96);
  v0 = InitializeSstpSvcRpcServer();
  if ( v0 )
  {
    if ( (byte_18002D803 & 8) == 0 )
      goto LABEL_38;
    v3 = L"ServiceMain failed to initialize RPC server";
    goto LABEL_37;
  }
  v11 = SstpSvcGlobals;
  *((_DWORD *)SstpSvcGlobals + 1) = 5;
  *((_DWORD *)v11 + 190) = 1;
  *(_DWORD *)v11 = 4;
  ServiceStatus.dwCurrentState = 4;
  ServiceStatus.dwControlsAccepted = *((_DWORD *)v11 + 1);
  _InterlockedExchange((volatile __int32 *)v11 + 2, 0);
  ServiceStatus.dwCheckPoint = *((_DWORD *)SstpSvcGlobals + 2);
  ServiceStatus.dwWaitHint = 0;
  SetServiceStatus(*((SERVICE_STATUS_HANDLE *)SstpSvcGlobals + 5), &ServiceStatus);
  if ( !SstpSvchostGlobal
    || (v12 = *(__int64 (__fastcall **)(char *, const WCHAR *, _QWORD, __int64 (__fastcall *)(_QWORD, _QWORD), _QWORD, int))(SstpSvchostGlobal + 192)) == 0 )
  {
    if ( (byte_18002D803 & 8) == 0 )
      goto LABEL_38;
    v3 = L"ServiceMain failed to retrieve the svchost RegisterStopCallback";
    goto LABEL_37;
  }
  result = v12((char *)SstpSvcGlobals + 32, L"sstpsvc", *((_QWORD *)SstpSvcGlobals + 3), StartServiceCleanup, 0, 8);
  v0 = result;
  if ( !(_DWORD)result )
    return result;
  if ( (byte_18002D803 & 8) != 0 )
  {
    v3 = L"ServiceMain failed to register stop callback";
LABEL_37:
    McTemplateU0z_EventWriteTransfer(
      (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)RasSSTPSvcTraceError,
      v3);
  }
LABEL_38:
  if ( SstpSvcGlobals && v0 )
  {
    if ( (byte_18002D803 & 8) != 0 )
    {
      LOWORD(v16) = 0;
      FormatRRASErrorString((wchar_t *)&v16, L"ServiceMain fails with 0x%x (%d)", v0, v0);
      if ( (byte_18002D803 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(
          (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (const EVENT_DESCRIPTOR *)RasSSTPSvcTraceError,
          (const wchar_t *)&v16);
    }
    *((_DWORD *)SstpSvcGlobals + 3) = v0;
  }
  return StartServiceCleanup(0, 0);
}

```

## disassembly

```asm
0x180005920  mov     [rsp-8+arg_0], rbx
0x180005925  mov     [rsp-8+arg_8], rdi
0x18000592a  push    rbp
0x18000592b  lea     rbp, [rsp-780h]
0x180005933  sub     rsp, 880h
0x18000593a  mov     rax, cs:__security_cookie
0x180005941  xor     rax, rsp
0x180005944  mov     [rbp+780h+var_10], rax
0x18000594b  xorps   xmm0, xmm0
0x18000594e  lea     rcx, [rsp+880h+var_80C]; void *
0x180005953  xor     edi, edi
0x180005955  xor     edx, edx; Val
0x180005957  movups  xmmword ptr [rsp+880h+ServiceStatus.dwServiceType], xmm0
0x18000595c  mov     r8d, 7FCh; Size
0x180005962  mov     [rsp+880h+var_840], edi
0x180005966  movups  xmmword ptr [rsp+880h+ServiceStatus.dwWin32ExitCode], xmm0
0x18000596b  mov     [rsp+880h+var_810], edi
0x18000596f  call    memset_0
0x180005974  call    McGenEventRegister_EventRegister
0x180005979  test    eax, eax
0x18000597b  js      short loc_180005982
0x18000597d  call    SetLibParams
0x180005982  test    cs:byte_18002D803, 10h
0x180005989  jz      short loc_1800059C9
0x18000598b  lea     r8, aServicemain_0; "ServiceMain"
0x180005992  mov     word ptr [rsp+880h+var_810], di
0x180005997  lea     rdx, aEnteringWs; "Entering %ws"
0x18000599e  lea     rcx, [rsp+880h+var_810]
0x1800059a3  call    FormatRRASErrorString
0x1800059a8  test    cs:byte_18002D803, 10h
0x1800059af  jz      short loc_1800059C9
0x1800059b1  lea     r8, [rsp+880h+var_810]
0x1800059b6  lea     rdx, RasSSTPSvcTraceInfo
0x1800059bd  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800059c4  call    McTemplateU0z_EventWriteTransfer
0x1800059c9  mov     ebx, edi
0x1800059cb  call    cs:__imp_GetProcessHeap
0x1800059d1  mov     edx, 8; dwFlags
0x1800059d6  mov     r8d, 310h; dwBytes
0x1800059dc  mov     rcx, rax; hHeap
0x1800059df  call    cs:__imp_HeapAlloc
0x1800059e5  mov     cs:SstpSvcGlobals, rax
0x1800059ec  test    rax, rax
0x1800059ef  jnz     short loc_180005A0A
0x1800059f1  test    cs:byte_18002D803, 8
0x1800059f8  jz      loc_180005CB2
0x1800059fe  lea     r8, aUnableToAlloca_1; "Unable to allocate memory for SstpSvcGl"...
0x180005a05  jmp     loc_180005C9F
0x180005a0a  xor     r8d, r8d; lpContext
0x180005a0d  mov     qword ptr [rax+2F0h], 0FFFFFFFFFFFFFFFFh
0x180005a18  lea     rdx, ServiceHandlerEx; lpHandlerProc
0x180005a1f  lea     rcx, ServiceName; "sstpsvc"
0x180005a26  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180005a2c  mov     rcx, cs:SstpSvcGlobals
0x180005a33  mov     [rcx+28h], rax
0x180005a37  test    rax, rax
0x180005a3a  jnz     short loc_180005A84
0x180005a3c  call    cs:__imp_GetLastError
0x180005a42  test    cs:byte_18002D803, 8
0x180005a49  mov     ebx, eax
0x180005a4b  jz      loc_180005CB2
0x180005a51  mov     r9d, eax
0x180005a54  mov     word ptr [rsp+880h+var_810], di
0x180005a59  mov     r8d, eax
0x180005a5c  lea     rdx, aRegisterservic; "RegisterServiceCtrlHandlerEx fails with"...
0x180005a63  lea     rcx, [rsp+880h+var_810]
0x180005a68  call    FormatRRASErrorString
0x180005a6d  test    cs:byte_18002D803, 8
0x180005a74  jz      loc_180005CB2
0x180005a7a  lea     r8, [rsp+880h+var_810]
0x180005a7f  jmp     loc_180005C9F
0x180005a84  mov     [rsp+880h+ServiceStatus.dwServiceType], 20h ; ' '
0x180005a8c  lea     rdx, [rsp+880h+ServiceStatus]; lpServiceStatus
0x180005a91  mov     dword ptr [rcx], 2
0x180005a97  mov     [rsp+880h+ServiceStatus.dwCheckPoint], 1
0x180005a9f  mov     [rsp+880h+ServiceStatus.dwWaitHint], 0BB8h
0x180005aa7  mov     eax, [rcx]
0x180005aa9  mov     [rsp+880h+ServiceStatus.dwCurrentState], eax
0x180005aad  mov     rcx, [rcx+28h]; hServiceStatus
0x180005ab1  call    cs:__imp_SetServiceStatus
0x180005ab7  mov     r8, cs:SstpSvcGlobals
0x180005abe  mov     edx, 5
0x180005ac3  mov     ecx, 10h
0x180005ac8  lea     r9, [r8+130h]
0x180005acf  add     r8, 128h
0x180005ad6  call    ConfigureMiniports
0x180005adb  test    eax, eax
0x180005add  jnz     loc_180005CB2
0x180005ae3  call    InitializeService
0x180005ae8  mov     ebx, eax
0x180005aea  test    eax, eax
0x180005aec  jnz     loc_180005CB2
0x180005af2  lea     rdx, [rsp+880h+var_840]
0x180005af7  xor     ecx, ecx
0x180005af9  call    cs:__imp_GetSstpProxyConfig
0x180005aff  mov     ebx, [rsp+880h+var_840]
0x180005b03  test    ebx, ebx
0x180005b05  jz      short loc_180005B79
0x180005b07  xor     ecx, ecx
0x180005b09  call    InitializeSstpServer
0x180005b0e  mov     ebx, eax
0x180005b10  test    eax, eax
0x180005b12  jz      short loc_180005B3F
0x180005b14  test    cs:byte_18002D803, 8
0x180005b1b  jz      loc_180005CB2
0x180005b21  mov     r8d, eax
0x180005b24  mov     word ptr [rsp+880h+var_810], di
0x180005b29  lea     rdx, aServicemainIni; "ServiceMain: InitializeSstpServer faile"...
0x180005b30  lea     rcx, [rsp+880h+var_810]
0x180005b35  call    FormatRRASErrorString
0x180005b3a  jmp     loc_180005A6D
0x180005b3f  call    LoadSstpProxyConfigFromXmlFile
0x180005b44  mov     ebx, eax
0x180005b46  test    eax, eax
0x180005b48  jz      short loc_180005B75
0x180005b4a  test    cs:byte_18002D803, 8
0x180005b51  jz      loc_180005CB2
0x180005b57  mov     r8d, eax
0x180005b5a  mov     word ptr [rsp+880h+var_810], di
0x180005b5f  lea     rdx, aServicemainFai_0; "ServiceMain failed to load proxy config"...
0x180005b66  lea     rcx, [rsp+880h+var_810]
0x180005b6b  call    FormatRRASErrorString
0x180005b70  jmp     loc_180005A6D
0x180005b75  mov     ebx, [rsp+880h+var_840]
0x180005b79  mov     rcx, cs:SstpSvcGlobals
0x180005b80  add     rcx, 300h; SRWLock
0x180005b87  call    cs:__imp_AcquireSRWLockExclusive
0x180005b8d  mov     rcx, cs:SstpSvcGlobals
0x180005b94  test    ebx, ebx
0x180005b96  jz      short loc_180005BA1
0x180005b98  or      dword ptr [rcx+308h], 1
0x180005b9f  jmp     short loc_180005BA8
0x180005ba1  and     dword ptr [rcx+308h], 0FFFFFFFEh
0x180005ba8  add     rcx, 300h; SRWLock
0x180005baf  call    cs:__imp_ReleaseSRWLockExclusive
0x180005bb5  call    InitializeSstpSvcRpcServer
0x180005bba  mov     ebx, eax
0x180005bbc  test    eax, eax
0x180005bbe  jz      short loc_180005BD9
0x180005bc0  test    cs:byte_18002D803, 8
0x180005bc7  jz      loc_180005CB2
0x180005bcd  lea     r8, aServicemainFai_3; "ServiceMain failed to initialize RPC se"...
0x180005bd4  jmp     loc_180005C9F
0x180005bd9  mov     rcx, cs:SstpSvcGlobals
0x180005be0  lea     rdx, [rsp+880h+ServiceStatus]; lpServiceStatus
0x180005be5  mov     dword ptr [rcx+4], 5
0x180005bec  mov     dword ptr [rcx+2F8h], 1
0x180005bf6  mov     dword ptr [rcx], 4
0x180005bfc  mov     [rsp+880h+ServiceStatus.dwCurrentState], 4
0x180005c04  mov     eax, [rcx+4]
0x180005c07  mov     [rsp+880h+ServiceStatus.dwControlsAccepted], eax
0x180005c0b  mov     eax, edi
0x180005c0d  xchg    eax, [rcx+8]
0x180005c10  mov     rcx, cs:SstpSvcGlobals
0x180005c17  mov     eax, [rcx+8]
0x180005c1a  mov     [rsp+880h+ServiceStatus.dwCheckPoint], eax
0x180005c1e  mov     [rsp+880h+ServiceStatus.dwWaitHint], edi
0x180005c22  mov     rcx, [rcx+28h]; hServiceStatus
0x180005c26  call    cs:__imp_SetServiceStatus
0x180005c2c  mov     rax, cs:SstpSvchostGlobal
0x180005c33  test    rax, rax
0x180005c36  jz      short loc_180005C8F
0x180005c38  mov     rax, [rax+0C0h]
0x180005c3f  test    rax, rax
0x180005c42  jz      short loc_180005C8F
0x180005c44  mov     r8, cs:SstpSvcGlobals
0x180005c4b  lea     r9, StartServiceCleanup
0x180005c52  mov     [rsp+880h+var_858], 8
0x180005c5a  lea     rdx, ServiceName; "sstpsvc"
0x180005c61  mov     [rsp+880h+var_860], rdi
0x180005c66  lea     rcx, [r8+20h]
0x180005c6a  mov     r8, [r8+18h]
0x180005c6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c73  mov     ebx, eax
0x180005c75  test    eax, eax
0x180005c77  jz      loc_180005D18
0x180005c7d  test    cs:byte_18002D803, 8
0x180005c84  jz      short loc_180005CB2
0x180005c86  lea     r8, aServicemainFai_2; "ServiceMain failed to register stop cal"...
0x180005c8d  jmp     short loc_180005C9F
0x180005c8f  test    cs:byte_18002D803, 8
0x180005c96  jz      short loc_180005CB2
0x180005c98  lea     r8, aServicemainFai; "ServiceMain failed to retrieve the svch"...
0x180005c9f  lea     rdx, RasSSTPSvcTraceError
0x180005ca6  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180005cad  call    McTemplateU0z_EventWriteTransfer
0x180005cb2  cmp     cs:SstpSvcGlobals, rdi
0x180005cb9  jz      short loc_180005D0F
0x180005cbb  test    ebx, ebx
0x180005cbd  jz      short loc_180005D0F
0x180005cbf  test    cs:byte_18002D803, 8
0x180005cc6  jz      short loc_180005D05
0x180005cc8  mov     r9d, ebx
0x180005ccb  mov     word ptr [rsp+880h+var_810], di
0x180005cd0  mov     r8d, ebx
0x180005cd3  lea     rdx, aServicemainFai_1; "ServiceMain fails with 0x%x (%d)"
0x180005cda  lea     rcx, [rsp+880h+var_810]
0x180005cdf  call    FormatRRASErrorString
0x180005ce4  test    cs:byte_18002D803, 8
0x180005ceb  jz      short loc_180005D05
0x180005ced  lea     r8, [rsp+880h+var_810]
0x180005cf2  lea     rdx, RasSSTPSvcTraceError
0x180005cf9  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180005d00  call    McTemplateU0z_EventWriteTransfer
0x180005d05  mov     rax, cs:SstpSvcGlobals
0x180005d0c  mov     [rax+0Ch], ebx
0x180005d0f  xor     edx, edx
0x180005d11  xor     ecx, ecx
0x180005d13  call    StartServiceCleanup
0x180005d18  mov     rcx, [rbp+780h+var_10]
0x180005d1f  xor     rcx, rsp; StackCookie
0x180005d22  call    __security_check_cookie
0x180005d27  lea     r11, [rsp+880h+var_s0]
0x180005d2f  mov     rbx, [r11+10h]
0x180005d33  mov     rdi, [r11+18h]
0x180005d37  mov     rsp, r11
0x180005d3a  pop     rbp
0x180005d3b  retn
```
