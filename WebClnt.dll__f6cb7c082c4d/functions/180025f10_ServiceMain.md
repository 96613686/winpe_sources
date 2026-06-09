# ServiceMain

- ea: `0x180025f10`
- end: `0x180026962`
- name: `ServiceMain`
- size: `2642`
- prototype: `__int64 __fastcall(__int64, const wchar_t **)`
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000b7b4`
- `0x18000b7dc`
- `0x18000b93c`
- `0x18000c25c`
- `0x18000c2b8`
- `0x18000c350`
- `0x18000c730`
- `0x18000c7a4`
- `0x1800118c0`
- `0x18002550c`
- `0x180025bf8`
- `0x180025f10`
- `0x180026980`
- `0x180029134`
- `0x180029310`
- `0x18002cf6e`
- `0x18002e010`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x18002662f`
- `ntdll!NtQueryInformationProcess` at `0x18002662f`
- `ntdll!EtwRegisterTraceGuidsW` at `0x180025fa9`
- `ntdll!EtwRegisterTraceGuidsW` at `0x180025fa9`
- `ntdll!RtlInitUnicodeString` at `0x18002620c`
- `ntdll!RtlInitUnicodeString` at `0x18002620c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026021`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800264ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026502`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026547`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026684`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026021`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800264ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026502`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026547`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026684`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026759`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026759`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026915`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026915`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800263d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026497`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800263d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026497`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800263a0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002645e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800263a0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002645e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800260f9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800260f9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180026008`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180026008`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800261a2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800261a2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18002652c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18002652c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x1800264f8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x1800264f8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x1800264b8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x1800264b8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180026532`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180026532`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x180026114`
- `api-ms-win-service-winsvc-l1-1-0!RegisterServiceCtrlHandlerW` at `0x180026114`
- `RPCRT4!RpcServerRegisterIfEx` at `0x1800266f0`
- `RPCRT4!RpcServerRegisterIfEx` at `0x1800266f0`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x1800266a8`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x1800266a8`
- `KERNEL32!LocalFree` at `0x1800266b4`
- `KERNEL32!LocalFree` at `0x1800268e3`
- `KERNEL32!LocalFree` at `0x1800266b4`
- `KERNEL32!LocalFree` at `0x1800268e3`
- `KERNEL32!UnregisterWait` at `0x1800268fc`
- `KERNEL32!UnregisterWait` at `0x1800268fc`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002667a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002667a`
- `WS2_32!__imp_WSAGetLastError` at `0x180026818`
- `WS2_32!__imp_WSAGetLastError` at `0x180026818`
- `WS2_32!__imp_WSAStartup` at `0x1800262e9`
- `WS2_32!__imp_WSAStartup` at `0x1800262e9`
- `WS2_32!__imp_WSACleanup` at `0x18002680d`
- `WS2_32!__imp_WSACleanup` at `0x18002680d`

## string_xrefs

- `0x1800260a1`: `notservice`
- `0x180026392`: `System\CurrentControlSet\Services\WebClient\Parameters`
- `0x180026450`: `System\CurrentControlSet\Services\WebClient\Parameters`
- `0x1800263b2`: `MaxThreads`
- `0x1800263c2`: `Threads`
- `0x180026470`: `MaxThreadPoolThreads`
- `0x180026480`: `ThreadPoolThreads`
- `0x180026695`: `\PIPE\DAV RPC SERVICE`

## pseudocode

```c
__int64 __fastcall ServiceMain(__int64 a1, const wchar_t **a2)
{
  __int64 *v3; // rbx
  __int64 *v4; // rdi
  __int64 v5; // r8
  DWORD LastError; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  DWORD v9; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  _BYTE *v13; // rbx
  __int64 v14; // rcx
  __int64 v15; // rdx
  unsigned int v16; // esi
  DWORD Redir; // eax
  DWORD v18; // eax
  DWORD inited; // eax
  __int64 v20; // rdx
  __int64 v21; // r9
  unsigned int v22; // eax
  int DWord; // ebx
  unsigned int v24; // esi
  DWORD v25; // esi
  DWORD v26; // ebx
  struct _TP_POOL *Threadpool; // rax
  DWORD v28; // eax
  _QWORD *v29; // rcx
  __int64 v30; // rdx
  bool v31; // sf
  int v32; // eax
  unsigned int v33; // ebx
  __int64 result; // rax
  unsigned int Error; // eax
  _QWORD v36[2]; // [rsp+40h] [rbp-10h] BYREF
  PSECURITY_DESCRIPTOR ProcessInformation; // [rsp+A0h] [rbp+50h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp+58h] BYREF

  hKey = 0;
  qword_180039390 = 0;
  qword_180039398 = 1;
  v3 = &WPP_MAIN_CB;
  WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_WebClntTrace;
  WPP_GLOBAL_Control = &WPP_MAIN_CB;
  v4 = &WPP_REGISTRATION_GUIDS;
  WPP_MAIN_CB = 0;
  do
  {
    v5 = *v4;
    v36[0] = v5;
    ++v4;
    v36[1] = 0;
    v3[4] = v5;
    ((void (__fastcall *)(__int64 (__fastcall *)(), __int64 *, __int64, __int64, _QWORD *, _QWORD, _QWORD, __int64 *))EtwRegisterTraceGuidsW)(
      WppControlCallback,
      v3,
      v5,
      1,
      v36,
      0,
      0,
      v3 + 1);
    v3 = (__int64 *)*v3;
  }
  while ( v3 );
  DavReadRegistryValues();
  g_RedirLoaded = 0;
  g_WorkersActive = 0;
  g_ThreadPoolActive = 0;
  g_registeredService = 0;
  g_status.dwServiceType = 16;
  *(_OWORD *)&g_status.dwCurrentState = 0;
  g_status.dwCheckPoint = 1;
  g_status.dwWaitHint = 60000;
  g_DavstopServiceEvent = CreateEventW(0, 0, 0, 0);
  if ( !g_DavstopServiceEvent )
  {
    LastError = GetLastError();
    v9 = LastError;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v11 = 20;
      v12 = LastError;
LABEL_126:
      WPP_SF_d(v10[2], v11, WPP_3c901703a5983ce609c0997329a96280_Traceguids, v12);
      goto LABEL_127;
    }
    goto LABEL_127;
  }
  UpdateServiceStatus(2);
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_3c901703a5983ce609c0997329a96280_Traceguids, *a2);
    v13 = WPP_GLOBAL_Control;
  }
  if ( *a2 && !wcscmp_0(*a2, L"notservice") )
  {
    if ( v13 == (_BYTE *)&WPP_GLOBAL_Control || (v13[28] & 2) == 0 )
      goto LABEL_25;
    v14 = *((_QWORD *)v13 + 2);
    v15 = 22;
  }
  else
  {
    if ( v13 != (_BYTE *)&WPP_GLOBAL_Control && (v13[28] & 2) != 0 )
      WPP_SF_(*((_QWORD *)v13 + 2), 23, WPP_3c901703a5983ce609c0997329a96280_Traceguids);
    if ( !g_DavServiceLockSet )
    {
      InitializeCriticalSection(&g_DavServiceLock);
      g_DavServiceLockSet = 1;
    }
    g_hStatus = RegisterServiceCtrlHandlerW(L"WebClient", DavServiceHandler);
    if ( !g_hStatus )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_3c901703a5983ce609c0997329a96280_Traceguids);
      goto LABEL_132;
    }
    g_registeredService = 1;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_25;
    v14 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v15 = 24;
  }
  WPP_SF_(v14, v15, WPP_3c901703a5983ce609c0997329a96280_Traceguids);
LABEL_25:
  v16 = 0;
  while ( 1 )
  {
    UpdateServiceStatus(2);
    Redir = WsLoadRedir();
    v9 = Redir;
    if ( Redir == 1056 || !Redir )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_3c901703a5983ce609c0997329a96280_Traceguids);
      ++g_status.dwCheckPoint;
      g_RedirLoaded = 1;
      UpdateServiceStatus(2);
      RtlInitUnicodeString(&RedirDeviceName, L"\\Device\\WebDavRedirector");
      v18 = UMReflectorRegister();
      v9 = v18;
      if ( DavReflectorHandle )
      {
        if ( !v18 )
        {
          ++g_status.dwCheckPoint;
          UpdateServiceStatus(2);
          inited = UMReflectorStart();
          v9 = inited;
          if ( inited )
          {
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_128;
            v20 = 31;
            goto LABEL_43;
          }
          ++g_status.dwCheckPoint;
          UpdateServiceStatus(2);
          v22 = WSAStartup(2u, &g_wsaData);
          v9 = v22;
          if ( v22 )
          {
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
              goto LABEL_128;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_4dec6104274634fe1b76984699e07cb1_Traceguids, v22);
              v10 = WPP_GLOBAL_Control;
            }
            goto LABEL_117;
          }
          if ( g_wsaData.wVersion == 2 )
          {
            g_socketinit = 1;
            inited = DavInit();
            v9 = inited;
            if ( inited )
            {
              v10 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              {
                goto LABEL_128;
              }
              v20 = 33;
              goto LABEL_43;
            }
            if ( RegOpenKeyExW(
                   HKEY_LOCAL_MACHINE,
                   L"System\\CurrentControlSet\\Services\\WebClient\\Parameters",
                   0,
                   1u,
                   &hKey) )
            {
              DWord = 6;
              v24 = 2;
            }
            else
            {
              DWord = ReadDWord(hKey, L"MaxThreads", 6);
              v24 = ReadDWord(hKey, L"Threads", 2);
              RegCloseKey(hKey);
            }
            ++g_status.dwCheckPoint;
            UpdateServiceStatus(2);
            inited = DavInitWorkerThreads(v24, DWord);
            v9 = inited;
            if ( inited )
            {
              v10 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              {
                goto LABEL_128;
              }
              v20 = 34;
LABEL_43:
              v21 = inited;
LABEL_44:
              WPP_SF_d(v10[2], v20, WPP_3c901703a5983ce609c0997329a96280_Traceguids, v21);
              goto LABEL_128;
            }
            ++g_status.dwCheckPoint;
            g_WorkersActive = 1;
            UpdateServiceStatus(2);
            if ( RegOpenKeyExW(
                   HKEY_LOCAL_MACHINE,
                   L"System\\CurrentControlSet\\Services\\WebClient\\Parameters",
                   0,
                   1u,
                   &hKey) )
            {
              v25 = 32;
              v26 = 2;
            }
            else
            {
              v25 = ReadDWord(hKey, L"MaxThreadPoolThreads", 32);
              v26 = ReadDWord(hKey, L"ThreadPoolThreads", 2);
              RegCloseKey(hKey);
            }
            ++g_status.dwCheckPoint;
            UpdateServiceStatus(2);
            Threadpool = CreateThreadpool(0);
            DavThreadPool = Threadpool;
            if ( Threadpool )
            {
              if ( SetThreadpoolThreadMinimum(Threadpool, v26) )
              {
                SetThreadpoolThreadMaximum(DavThreadPool, v25);
                DavCleanupGroup = CreateThreadpoolCleanupGroup();
                if ( DavCleanupGroup )
                {
                  *(_OWORD *)&DavCallbackEnviron.RaceDll = 0;
                  DavCallbackEnviron.Pool = DavThreadPool;
                  DavCallbackEnviron.Version = 3;
                  DavCallbackEnviron.FinalizationCallback = 0;
                  DavCallbackEnviron.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
                  DavCallbackEnviron.Size = 72;
                  DavCallbackEnviron.CleanupGroup = DavCleanupGroup;
                  DavCallbackEnviron.CleanupGroupCancelCallback = 0;
                  DavCallbackEnviron.u.Flags = 1;
                  g_DavCallbackEnvironInitialized = 1;
                  goto LABEL_89;
                }
                v28 = GetLastError();
                v9 = v28;
                v29 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  v30 = 19;
                  goto LABEL_83;
                }
              }
              else
              {
                v28 = GetLastError();
                v9 = v28;
                v29 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  v30 = 18;
                  goto LABEL_83;
                }
              }
            }
            else
            {
              v28 = GetLastError();
              v9 = v28;
              v29 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v30 = 17;
LABEL_83:
                WPP_SF_d(v29[2], v30, WPP_186e50dd2e3d3df6c9407dc12bb7d723_Traceguids, v28);
              }
            }
            DavCleanupThreadPool();
            if ( v9 )
            {
              v10 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              {
                goto LABEL_128;
              }
              v20 = 35;
LABEL_120:
              v21 = v9;
              goto LABEL_44;
            }
LABEL_89:
            ++g_status.dwCheckPoint;
            g_ThreadPoolActive = 1;
            UpdateServiceStatus(2);
            LODWORD(ProcessInformation) = 0;
            v31 = NtQueryInformationProcess(
                    (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                    ProcessLUIDDeviceMapsEnabled,
                    &ProcessInformation,
                    4u,
                    0) < 0;
            v32 = 0;
            if ( !v31 )
              LOBYTE(v32) = (_DWORD)ProcessInformation != 0;
            ++g_status.dwCheckPoint;
            g_LUIDDeviceMapsEnabled = v32;
            UpdateServiceStatus(2);
            if ( !g_RpcActive )
            {
              ProcessInformation = 0;
              if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
                      L"O:LSG:LSD:(A;;0x12019B;;;AN)(A;;0x12019B;;;WD)(A;;0x1F01FF;;;LS)S:(ML;;0x1;;;LW)",
                      1u,
                      &ProcessInformation,
                      0) )
              {
                v9 = GetLastError();
                goto LABEL_127;
              }
              v33 = RpcServerUseProtseqEpW(
                      (RPC_WSTR)L"ncacn_np",
                      0xAu,
                      (RPC_WSTR)L"\\PIPE\\DAV RPC SERVICE",
                      ProcessInformation);
              LocalFree(ProcessInformation);
              if ( v33 && v33 != 1740
                || (v33 = RpcServerRegisterIfEx(
                            qword_18002F6B0,
                            0,
                            0,
                            0x11u,
                            0x4D2u,
                            (RPC_IF_CALLBACK_FN *)DavRpcSecurityCallback)) != 0 )
              {
                v10 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    36,
                    WPP_3c901703a5983ce609c0997329a96280_Traceguids,
                    v33);
                }
                goto LABEL_132;
              }
              g_RpcActive = 1;
            }
            g_status.dwControlsAccepted = 1;
            UpdateServiceStatus(4);
            result = (*(__int64 (__fastcall **)(HANDLE *, const WCHAR *, HANDLE, __int64 (__fastcall *)(), _QWORD, int))(DavSvcsGlobalData + 192))(
                       &g_DavwaitObject,
                       L"WebClient",
                       g_DavstopServiceEvent,
                       DavStopServiceCallback,
                       0,
                       24);
            v9 = result;
            if ( !(_DWORD)result )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
              {
                return WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_3c901703a5983ce609c0997329a96280_Traceguids);
              }
              return result;
            }
            SetLastError(result);
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_128;
            v20 = 37;
LABEL_51:
            v21 = v9;
            goto LABEL_44;
          }
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_4dec6104274634fe1b76984699e07cb1_Traceguids);
          if ( WSACleanup() == -1 )
          {
            Error = WSAGetLastError();
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_116;
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_4dec6104274634fe1b76984699e07cb1_Traceguids, Error);
          }
          v10 = WPP_GLOBAL_Control;
LABEL_116:
          v9 = 50;
LABEL_117:
          if ( v10 == &WPP_GLOBAL_Control || (*((_BYTE *)v10 + 28) & 1) == 0 )
            goto LABEL_128;
          v20 = 32;
          goto LABEL_120;
        }
      }
      else if ( !v18 )
      {
        v9 = 2001;
      }
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v11 = 30;
        v12 = v9;
        goto LABEL_126;
      }
LABEL_127:
      if ( v9 )
        goto LABEL_128;
      goto LABEL_132;
    }
    if ( Redir != 3 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_128;
      v20 = 29;
      goto LABEL_51;
    }
    ++v16;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), Redir + 24, WPP_3c901703a5983ce609c0997329a96280_Traceguids, v16);
      v10 = WPP_GLOBAL_Control;
    }
    if ( v16 >= 4 )
      break;
    Sleep(0xBB8u);
    ++g_status.dwCheckPoint;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 )
  {
    v20 = 28;
    v21 = 3;
    goto LABEL_44;
  }
LABEL_128:
  g_status.dwWin32ExitCode = v9;
  g_status.dwServiceSpecificExitCode = 0;
LABEL_132:
  DavServiceStop((__int64)v10, v7, v8);
  if ( pBypassServerNames )
  {
    LocalFree(pBypassServerNames);
    pBypassServerNames = 0;
  }
  if ( g_DavwaitObject )
  {
    UnregisterWait(g_DavwaitObject);
    g_DavwaitObject = 0;
  }
  if ( g_DavstopServiceEvent )
  {
    CloseHandle(g_DavstopServiceEvent);
    g_DavstopServiceEvent = 0;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_3c901703a5983ce609c0997329a96280_Traceguids);
  return WppCleanupUm();
}

```

## disassembly

```asm
0x180025f10  mov     [rsp-38h+arg_0], rbx
0x180025f15  push    rbp
0x180025f16  push    rsi
0x180025f17  push    rdi
0x180025f18  push    r12
0x180025f1a  push    r13
0x180025f1c  push    r14
0x180025f1e  push    r15
0x180025f20  mov     rbp, rsp
0x180025f23  sub     rsp, 50h
0x180025f27  xor     r14d, r14d
0x180025f2a  mov     rsi, rdx
0x180025f2d  mov     [rbp+hKey], r14
0x180025f31  lea     r15d, [r14+1]
0x180025f35  mov     cs:qword_180039390, r14
0x180025f3c  lea     rax, WPP_ThisDir_CTLGUID_WebClntTrace
0x180025f43  mov     cs:qword_180039398, r15
0x180025f4a  lea     rbx, WPP_MAIN_CB
0x180025f51  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180025f58  mov     cs:WPP_GLOBAL_Control, rbx
0x180025f5f  lea     rdi, WPP_REGISTRATION_GUIDS
0x180025f66  mov     cs:WPP_MAIN_CB, r14
0x180025f6d  mov     r8, [rdi]
0x180025f70  lea     rax, [rbx+8]
0x180025f74  mov     [rsp+50h+var_18], rax
0x180025f79  lea     rcx, WppControlCallback
0x180025f80  mov     [rsp+50h+var_20], r14
0x180025f85  lea     rax, [rbp+var_10]
0x180025f89  mov     [rbp+var_10], r8
0x180025f8d  lea     rdi, [rdi+8]
0x180025f91  mov     [rbp+var_8], r14
0x180025f95  mov     r9d, r15d
0x180025f98  mov     [rsp+50h+IfCallback], r14
0x180025f9d  mov     rdx, rbx
0x180025fa0  mov     [rsp+50h+phkResult], rax
0x180025fa5  mov     [rbx+20h], r8
0x180025fa9  call    cs:__imp_EtwRegisterTraceGuidsW
0x180025faf  mov     rbx, [rbx]
0x180025fb2  test    rbx, rbx
0x180025fb5  jnz     short loc_180025F6D
0x180025fb7  call    DavReadRegistryValues
0x180025fbc  xorps   xmm0, xmm0
0x180025fbf  mov     cs:g_RedirLoaded, r14d
0x180025fc6  xor     r9d, r9d; lpName
0x180025fc9  mov     cs:g_WorkersActive, r14d
0x180025fd0  xor     r8d, r8d; bInitialState
0x180025fd3  mov     cs:g_ThreadPoolActive, r14d
0x180025fda  xor     edx, edx; bManualReset
0x180025fdc  mov     cs:g_registeredService, r14d
0x180025fe3  xor     ecx, ecx; lpEventAttributes
0x180025fe5  mov     cs:g_status.dwServiceType, 10h
0x180025fef  movdqu  xmmword ptr cs:g_status.dwCurrentState, xmm0
0x180025ff7  mov     cs:g_status.dwCheckPoint, r15d
0x180025ffe  mov     cs:g_status.dwWaitHint, 0EA60h
0x180026008  call    cs:__imp_CreateEventW
0x18002600e  mov     cs:g_DavstopServiceEvent, rax
0x180026015  lea     r13, WPP_3c901703a5983ce609c0997329a96280_Traceguids
0x18002601c  test    rax, rax
0x18002601f  jnz     short loc_180026057
0x180026021  call    cs:__imp_GetLastError
0x180026027  mov     ebx, eax
0x180026029  mov     rcx, cs:WPP_GLOBAL_Control
0x180026030  lea     rdi, WPP_GLOBAL_Control
0x180026037  cmp     rcx, rdi
0x18002603a  jz      loc_18002689C
0x180026040  test    [rcx+1Ch], r15b
0x180026044  jz      loc_18002689C
0x18002604a  mov     edx, 14h
0x18002604f  mov     r9d, eax
0x180026052  jmp     loc_180026890
0x180026057  mov     r12d, 2
0x18002605d  mov     ecx, r12d
0x180026060  call    UpdateServiceStatus
0x180026065  mov     rbx, cs:WPP_GLOBAL_Control
0x18002606c  lea     rdi, WPP_GLOBAL_Control
0x180026073  cmp     rbx, rdi
0x180026076  jz      short loc_180026099
0x180026078  test    [rbx+1Ch], r12b
0x18002607c  jz      short loc_180026099
0x18002607e  mov     r9, [rsi]
0x180026081  lea     edx, [r12+13h]
0x180026086  mov     rcx, [rbx+10h]
0x18002608a  mov     r8, r13
0x18002608d  call    WPP_SF_S
0x180026092  mov     rbx, cs:WPP_GLOBAL_Control
0x180026099  mov     rcx, [rsi]; String1
0x18002609c  test    rcx, rcx
0x18002609f  jz      short loc_1800260CD
0x1800260a1  lea     rdx, aNotservice; "notservice"
0x1800260a8  call    wcscmp_0
0x1800260ad  test    eax, eax
0x1800260af  jnz     short loc_1800260CD
0x1800260b1  cmp     rbx, rdi
0x1800260b4  jz      loc_180026154
0x1800260ba  test    [rbx+1Ch], r12b
0x1800260be  jz      loc_180026154
0x1800260c4  mov     rcx, [rbx+10h]
0x1800260c8  lea     edx, [rax+16h]
0x1800260cb  jmp     short loc_18002614C
0x1800260cd  cmp     rbx, rdi
0x1800260d0  jz      short loc_1800260E9
0x1800260d2  test    [rbx+1Ch], r12b
0x1800260d6  jz      short loc_1800260E9
0x1800260d8  mov     rcx, [rbx+10h]
0x1800260dc  mov     edx, 17h
0x1800260e1  mov     r8, r13
0x1800260e4  call    WPP_SF_
0x1800260e9  cmp     cs:g_DavServiceLockSet, r14b
0x1800260f0  jnz     short loc_180026106
0x1800260f2  lea     rcx, g_DavServiceLock; lpCriticalSection
0x1800260f9  call    cs:__imp_InitializeCriticalSection
0x1800260ff  mov     cs:g_DavServiceLockSet, r15b
0x180026106  lea     rdx, DavServiceHandler; lpHandlerProc
0x18002610d  lea     rcx, ServiceName; "WebClient"
0x180026114  call    cs:__imp_RegisterServiceCtrlHandlerW
0x18002611a  mov     cs:g_hStatus, rax
0x180026121  test    rax, rax
0x180026124  jz      loc_1800268AF
0x18002612a  mov     cs:g_registeredService, r15d
0x180026131  mov     rcx, cs:WPP_GLOBAL_Control
0x180026138  cmp     rcx, rdi
0x18002613b  jz      short loc_180026154
0x18002613d  test    byte ptr [rcx+1Ch], 10h
0x180026141  jz      short loc_180026154
0x180026143  mov     rcx, [rcx+10h]
0x180026147  mov     edx, 18h
0x18002614c  mov     r8, r13
0x18002614f  call    WPP_SF_
0x180026154  mov     esi, r14d
0x180026157  jmp     short loc_1800261AF
0x180026159  test    ebx, ebx
0x18002615b  jz      short loc_1800261C5
0x18002615d  cmp     ebx, 3
0x180026160  jnz     loc_1800262AC
0x180026166  add     esi, r15d
0x180026169  mov     rcx, cs:WPP_GLOBAL_Control
0x180026170  cmp     rcx, rdi
0x180026173  jz      short loc_180026194
0x180026175  test    [rcx+1Ch], r15b
0x180026179  jz      short loc_180026194
0x18002617b  mov     rcx, [rcx+10h]
0x18002617f  lea     edx, [rbx+18h]
0x180026182  mov     r9d, esi
0x180026185  mov     r8, r13
0x180026188  call    WPP_SF_d
0x18002618d  mov     rcx, cs:WPP_GLOBAL_Control
0x180026194  cmp     esi, 4
0x180026197  jnb     loc_18002627F
0x18002619d  mov     ecx, 0BB8h; dwMilliseconds
0x1800261a2  call    cs:__imp_Sleep
0x1800261a8  add     cs:g_status.dwCheckPoint, r15d
0x1800261af  mov     ecx, r12d
0x1800261b2  call    UpdateServiceStatus
0x1800261b7  call    WsLoadRedir
0x1800261bc  mov     ebx, eax
0x1800261be  cmp     eax, 420h
0x1800261c3  jnz     short loc_180026159
0x1800261c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800261cc  cmp     rcx, rdi
0x1800261cf  jz      short loc_1800261E8
0x1800261d1  test    [rcx+1Ch], r12b
0x1800261d5  jz      short loc_1800261E8
0x1800261d7  mov     rcx, [rcx+10h]
0x1800261db  mov     edx, 1Ah
0x1800261e0  mov     r8, r13
0x1800261e3  call    WPP_SF_
0x1800261e8  add     cs:g_status.dwCheckPoint, r15d
0x1800261ef  mov     ecx, r12d
0x1800261f2  mov     cs:g_RedirLoaded, r15d
0x1800261f9  call    UpdateServiceStatus
0x1800261fe  lea     rdx, aDeviceWebdavre_1; "\\Device\\WebDavRedirector"
0x180026205  lea     rcx, RedirDeviceName; DestinationString
0x18002620c  call    cs:__imp_RtlInitUnicodeString
0x180026212  call    UMReflectorRegister
0x180026217  cmp     cs:DavReflectorHandle, r14
0x18002621e  mov     ebx, eax
0x180026220  jz      loc_18002686C
0x180026226  test    eax, eax
0x180026228  jnz     loc_180026876
0x18002622e  add     cs:g_status.dwCheckPoint, r15d
0x180026235  mov     ecx, r12d
0x180026238  call    UpdateServiceStatus
0x18002623d  call    UMReflectorStart
0x180026242  mov     ebx, eax
0x180026244  test    eax, eax
0x180026246  jz      loc_1800262D0
0x18002624c  mov     rcx, cs:WPP_GLOBAL_Control
0x180026253  cmp     rcx, rdi
0x180026256  jz      loc_1800268A0
0x18002625c  test    [rcx+1Ch], r15b
0x180026260  jz      loc_1800268A0
0x180026266  mov     edx, 1Fh
0x18002626b  mov     r9d, eax
0x18002626e  mov     rcx, [rcx+10h]
0x180026272  mov     r8, r13
0x180026275  call    WPP_SF_d
0x18002627a  jmp     loc_1800268A0
0x18002627f  cmp     rcx, rdi
0x180026282  jz      loc_1800268A0
0x180026288  test    [rcx+1Ch], r15b
0x18002628c  jz      loc_1800268A0
0x180026292  mov     edx, 1Ch
0x180026297  lea     r9d, [rdx-19h]
0x18002629b  mov     rcx, [rcx+10h]
0x18002629f  mov     r8, r13
0x1800262a2  call    WPP_SF_d
0x1800262a7  jmp     loc_1800268A0
0x1800262ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800262b3  cmp     rcx, rdi
0x1800262b6  jz      loc_1800268A0
0x1800262bc  test    [rcx+1Ch], r15b
0x1800262c0  jz      loc_1800268A0
0x1800262c6  mov     edx, 1Dh
0x1800262cb  mov     r9d, ebx
0x1800262ce  jmp     short loc_18002629B
0x1800262d0  add     cs:g_status.dwCheckPoint, r15d
0x1800262d7  mov     ecx, r12d
0x1800262da  call    UpdateServiceStatus
0x1800262df  mov     ecx, r12d; wVersionRequested
0x1800262e2  lea     rdx, g_wsaData; lpWSAData
0x1800262e9  call    cs:__imp_WSAStartup
0x1800262ef  mov     ebx, eax
0x1800262f1  test    eax, eax
0x1800262f3  jz      short loc_180026333
0x1800262f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800262fc  cmp     rcx, rdi
0x1800262ff  jz      loc_1800268A0
0x180026305  test    [rcx+1Ch], r15b
0x180026309  jz      loc_180026854
0x18002630f  mov     rcx, [rcx+10h]
0x180026313  lea     r8, WPP_4dec6104274634fe1b76984699e07cb1_Traceguids
0x18002631a  mov     edx, 0Ah
0x18002631f  mov     r9d, eax
0x180026322  call    WPP_SF_d
0x180026327  mov     rcx, cs:WPP_GLOBAL_Control
0x18002632e  jmp     loc_180026854
0x180026333  cmp     byte ptr cs:g_wsaData.wVersion, r12b
0x18002633a  jnz     loc_1800267E6
0x180026340  cmp     byte ptr cs:g_wsaData.wVersion+1, r14b
0x180026347  jnz     loc_1800267E6
0x18002634d  mov     cs:g_socketinit, r15b
0x180026354  call    DavInit
0x180026359  mov     ebx, eax
0x18002635b  test    eax, eax
0x18002635d  jz      short loc_180026383
0x18002635f  mov     rcx, cs:WPP_GLOBAL_Control
0x180026366  cmp     rcx, rdi
0x180026369  jz      loc_1800268A0
0x18002636f  test    [rcx+1Ch], r15b
0x180026373  jz      loc_1800268A0
0x180026379  mov     edx, 21h ; '!'
0x18002637e  jmp     loc_18002626B
0x180026383  lea     rax, [rbp+hKey]
0x180026387  mov     r9d, r15d; samDesired
0x18002638a  xor     r8d, r8d; ulOptions
0x18002638d  mov     [rsp+50h+phkResult], rax; phkResult
0x180026392  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\We"...
0x180026399  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800263a0  call    cs:__imp_RegOpenKeyExW
0x1800263a6  test    eax, eax
0x1800263a8  jnz     short loc_1800263E1
0x1800263aa  mov     rcx, [rbp+hKey]
0x1800263ae  lea     r8d, [rax+6]
0x1800263b2  lea     rdx, aMaxthreads; "MaxThreads"
0x1800263b9  call    ReadDWord
0x1800263be  mov     rcx, [rbp+hKey]
0x1800263c2  lea     rdx, aThreads; "Threads"
0x1800263c9  mov     r8d, r12d
0x1800263cc  mov     ebx, eax
0x1800263ce  call    ReadDWord
0x1800263d3  mov     rcx, [rbp+hKey]; hKey
0x1800263d7  mov     esi, eax
0x1800263d9  call    cs:__imp_RegCloseKey
0x1800263df  jmp     short loc_1800263E9
0x1800263e1  mov     ebx, 6
0x1800263e6  mov     esi, r12d
0x1800263e9  add     cs:g_status.dwCheckPoint, r15d
0x1800263f0  mov     ecx, r12d
0x1800263f3  call    UpdateServiceStatus
0x1800263f8  mov     edx, ebx
0x1800263fa  mov     ecx, esi
0x1800263fc  call    DavInitWorkerThreads
0x180026401  mov     ebx, eax
0x180026403  test    eax, eax
0x180026405  jz      short loc_18002642B
0x180026407  mov     rcx, cs:WPP_GLOBAL_Control
0x18002640e  cmp     rcx, rdi
0x180026411  jz      loc_1800268A0
0x180026417  test    [rcx+1Ch], r15b
0x18002641b  jz      loc_1800268A0
0x180026421  mov     edx, 22h ; '"'
0x180026426  jmp     loc_18002626B
0x18002642b  add     cs:g_status.dwCheckPoint, r15d
0x180026432  mov     ecx, r12d
0x180026435  mov     cs:g_WorkersActive, r15d
0x18002643c  call    UpdateServiceStatus
0x180026441  lea     rax, [rbp+hKey]
0x180026445  mov     r9d, r15d; samDesired
0x180026448  xor     r8d, r8d; ulOptions
0x18002644b  mov     [rsp+50h+phkResult], rax; phkResult
  ... truncated ...
```
