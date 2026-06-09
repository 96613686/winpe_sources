# InitializeServiceGlobals

- ea: `0x140025b04`
- end: `0x140026382`
- name: `InitializeServiceGlobals`
- size: `2174`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1400246b0`

## callees

- `0x1400023ec`
- `0x140002926`
- `0x140002c73`
- `0x140004c78`
- `0x140004ca8`
- `0x14000effc`
- `0x140025b04`
- `0x140026ca8`
- `0x140026ce8`
- `0x140026d28`
- `0x140026d68`
- `0x140053c20`
- `0x14006af2c`
- `0x140075190`
- `0x14007abf8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140025da9`
- `KERNEL32!GetLastError` at `0x140025de0`
- `KERNEL32!GetLastError` at `0x140025e4f`
- `KERNEL32!GetLastError` at `0x140025eaa`
- `KERNEL32!GetLastError` at `0x140025da9`
- `KERNEL32!GetLastError` at `0x140025de0`
- `KERNEL32!GetLastError` at `0x140025e4f`
- `KERNEL32!GetLastError` at `0x140025eaa`
- `KERNEL32!SetLastError` at `0x14002633e`
- `KERNEL32!SetLastError` at `0x14002633e`
- `KERNEL32!CreateEventW` at `0x140025dc8`
- `KERNEL32!CreateEventW` at `0x140025e37`
- `KERNEL32!CreateEventW` at `0x140025dc8`
- `KERNEL32!CreateEventW` at `0x140025e37`
- `KERNEL32!CreateSemaphoreW` at `0x140025e92`
- `KERNEL32!CreateSemaphoreW` at `0x140025e92`
- `KERNEL32!InitializeCriticalSection` at `0x140025eed`
- `KERNEL32!InitializeCriticalSection` at `0x140025f00`
- `KERNEL32!InitializeCriticalSection` at `0x140025f13`
- `KERNEL32!InitializeCriticalSection` at `0x140025f26`
- `KERNEL32!InitializeCriticalSection` at `0x140025f39`
- `KERNEL32!InitializeCriticalSection` at `0x140025f4c`
- `KERNEL32!InitializeCriticalSection` at `0x140025f5f`
- `KERNEL32!InitializeCriticalSection` at `0x140025f72`
- `KERNEL32!InitializeCriticalSection` at `0x140025f85`
- `KERNEL32!InitializeCriticalSection` at `0x140025f98`
- `KERNEL32!InitializeCriticalSection` at `0x140025fab`
- `KERNEL32!InitializeCriticalSection` at `0x140025fbe`
- `KERNEL32!InitializeCriticalSection` at `0x140025fd1`
- `KERNEL32!InitializeCriticalSection` at `0x140025fe4`
- `KERNEL32!InitializeCriticalSection` at `0x140025eed`
- `KERNEL32!InitializeCriticalSection` at `0x140025f00`
- `KERNEL32!InitializeCriticalSection` at `0x140025f13`
- `KERNEL32!InitializeCriticalSection` at `0x140025f26`
- `KERNEL32!InitializeCriticalSection` at `0x140025f39`
- `KERNEL32!InitializeCriticalSection` at `0x140025f4c`
- `KERNEL32!InitializeCriticalSection` at `0x140025f5f`
- `KERNEL32!InitializeCriticalSection` at `0x140025f72`
- `KERNEL32!InitializeCriticalSection` at `0x140025f85`
- `KERNEL32!InitializeCriticalSection` at `0x140025f98`
- `KERNEL32!InitializeCriticalSection` at `0x140025fab`
- `KERNEL32!InitializeCriticalSection` at `0x140025fbe`
- `KERNEL32!InitializeCriticalSection` at `0x140025fd1`
- `KERNEL32!InitializeCriticalSection` at `0x140025fe4`

## string_xrefs

- `0x140026361`: `CFaxConfiguration::CFaxConfiguration - StringDup on lpRegKeyName failed`
- `0x140025d3f`: `Microsoft-Windows-Fax-Common-DeviceLimit`

## pseudocode

```c
__int64 InitializeServiceGlobals()
{
  CMapDeviceId *v0; // rbx
  __int64 i; // rcx
  __int64 j; // rcx
  __int64 k; // rcx
  unsigned int v4; // ebx
  DWORD LastError; // ebx
  DWORD v6; // eax
  CMapDeviceId *v7; // rcx
  __int64 v8; // rdx
  _QWORD *v9; // rbx
  unsigned __int16 *v10; // rax
  _DWORD *v11; // rax
  CFaxAccountList *v12; // rax
  __int64 v13; // rcx
  CFaxAccountList *v14; // rbx
  _QWORD *v15; // rax
  CClientsMap *v16; // rax
  CClientsMap *v17; // rbx
  _QWORD *v18; // rdi
  _QWORD *v19; // rax
  void *v20; // rbx
  COutboundRoutingGroupsMap *v21; // rax
  COutboundRoutingGroupsMap *v22; // rbx
  COutboundRulesMap *v23; // rax
  COutboundRulesMap *v24; // rbx
  _BYTE pExceptionObject[32]; // [rsp+20h] [rbp-20h] BYREF

  v0 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids);
    v0 = WPP_GLOBAL_Control;
  }
  g_pFaxPerfCounters = 0;
  qword_1400A7838 = 0;
  dword_1400A7840 = 0;
  dword_1400A7844 = 0;
  *(_DWORD *)&Data = 0;
  memset_0(&g_ReceiptsConfig, 0, 0x50u);
  g_ReceiptsConfig = 80;
  g_ActivityLoggingConfig = 0;
  *(_OWORD *)&fDesiredAccess = 0;
  qword_1400A7630 = 0;
  g_ActivityLoggingConfig = 40;
  *(_OWORD *)((char *)&g_ServerActivity + 4) = 0;
  *(__int128 *)((char *)&xmmword_1400A3BA0 + 4) = 0;
  g_ServerActivity = 36;
  g_hDispatchEventsCompPort = 0;
  g_hSendEventsCompPort = 0;
  g_dwlClientID = 0;
  g_FaxQuotaWarn = 0;
  g_hArchiveQuotaWarningEvent = 0;
  g_dwConnectionCount = 0;
  g_hInboxActivityLogFile = (HANDLE)-1LL;
  g_hOutboxActivityLogFile = (HANDLE)-1LL;
  g_fLogStringTableInit = 0;
  g_dwQueueCount = 0;
  g_hJobQueueEvent = 0;
  g_ScanQueueAfterTimeout = 0;
  g_dwReceiveDevicesCount = 0;
  g_bDelaySuicideAttempt = 0;
  g_bServiceCanSuicide = 1;
  g_dwCountRoutingMethods = 0;
  g_pLineCountryList = 0;
  g_dwLastUniqueId = 0;
  g_bServiceIsDown = 0;
  g_TapiCompletionPort = 0;
  g_hLineApp = 0;
  ServiceStatus.dwServiceType = 48;
  ServiceStatus.dwCurrentState = 2;
  *(_OWORD *)&ServiceStatus.dwWin32ExitCode = 0;
  g_hRPCListeningThread = 0;
  g_lServiceThreadsCount = 0;
  g_hThreadCountEvent = 0;
  for ( i = 0; i != 14; ++i )
    qword_1400A3688[4 * i] = 0;
  for ( j = 0; j != 50; ++j )
    qword_1400A3048[4 * j] = 0;
  for ( k = 0; k != 59; ++k )
    qword_1400A3BC8[2 * k] = 0;
  g_StatusCompletionPortHandle = 0;
  g_pFaxSD = 0;
  g_dwDeviceCount = 0;
  g_dwDeviceEnabledCount = 0;
  if ( v0 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v0 + 28) & 2) != 0 && *((_BYTE *)v0 + 25) >= 5u )
    WPP_SF_(*((_QWORD *)v0 + 2), 17, WPP_62ed8e7de8ef3265f87aee086930cd18_Traceguids);
  if ( (int)GetLicensingPolicyValue((wchar_t *)L"Microsoft-Windows-Fax-Common-DeviceLimit") < 0 )
  {
    v4 = 1;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_62ed8e7de8ef3265f87aee086930cd18_Traceguids);
    }
  }
  else
  {
    v4 = 0;
  }
  g_dwDeviceEnabledLimit = v4;
  g_hTapiWorkerThread = 0;
  g_hJobQueueThread = 0;
  g_hResource = GetResInst();
  if ( !g_hResource )
  {
    LastError = GetLastError();
    goto LABEL_74;
  }
  g_hServiceShutDownEvent = CreateEventW(0, 1, 0, 0);
  if ( !g_hServiceShutDownEvent )
  {
    v6 = GetLastError();
    LastError = v6;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_74;
    }
    v8 = 14;
    goto LABEL_28;
  }
  g_hSCMServiceShutDownEvent = CreateEventW(0, 1, 0, 0);
  if ( !g_hSCMServiceShutDownEvent )
  {
    v6 = GetLastError();
    LastError = v6;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_74;
    }
    v8 = 15;
    goto LABEL_28;
  }
  g_hServiceIsDownSemaphore = CreateSemaphoreW(0, 0, 2, 0);
  if ( !g_hServiceIsDownSemaphore )
  {
    v6 = GetLastError();
    LastError = v6;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_74;
    }
    v8 = 16;
LABEL_28:
    WPP_SF_d(*((_QWORD *)v7 + 2), v8, &WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids, v6);
    goto LABEL_74;
  }
  InitializeCriticalSection(&g_CsConfig);
  InitializeCriticalSection(&g_CsInboundActivityLogging);
  InitializeCriticalSection(&g_CsOutboundActivityLogging);
  InitializeCriticalSection(&g_CsJob);
  InitializeCriticalSection(&g_CsQueue);
  InitializeCriticalSection(&g_CsPerfCounters);
  InitializeCriticalSection(&g_CsSecurity);
  InitializeCriticalSection(&g_csUniqueQueueFile);
  InitializeCriticalSection(&g_CsLine);
  InitializeCriticalSection(&g_CsRouting);
  InitializeCriticalSection(&g_CsServiceThreads);
  InitializeCriticalSection(&g_CsHandleTable);
  InitializeCriticalSection(&g_CsActivity);
  InitializeCriticalSection(&g_CsClients);
  qword_1400A7358 = (__int64)&g_DeviceProvidersListHead;
  g_DeviceProvidersListHead = (struct _DEVICE_PROVIDER *)&g_DeviceProvidersListHead;
  qword_1400A7468 = (__int64)&g_HandleTableListHead;
  g_HandleTableListHead = (struct _HANDLE_ENTRY *)&g_HandleTableListHead;
  qword_1400A74C8 = (__int64)&g_JobListHead;
  g_JobListHead.Flink = &g_JobListHead;
  g_QueueListHead.Blink = &g_QueueListHead;
  g_QueueListHead.Flink = &g_QueueListHead;
  qword_1400A7550 = (__int64)&g_lstRoutingExtensions;
  g_lstRoutingExtensions = &g_lstRoutingExtensions;
  qword_1400A7588 = (__int64)&g_lstRoutingMethods;
  g_lstRoutingMethods.Flink = &g_lstRoutingMethods;
  qword_1400A7740 = (__int64)&g_TapiLinesListHead;
  g_TapiLinesListHead = (DWORD_PTR)&g_TapiLinesListHead;
  qword_1400A7788 = (__int64)&g_RemovedTapiLinesListHead;
  g_RemovedTapiLinesListHead = (struct _LINE_INFO *)&g_RemovedTapiLinesListHead;
  g_pFaxConfig = 0;
  g_pFaxArchiving = 0;
  g_pClientsMap = 0;
  g_pNotificationMap = 0;
  g_pTAPIDevicesIdsMap = 0;
  g_pGroupsMap = 0;
  g_pRulesMap = 0;
  g_pAccountList = 0;
  g_pAccountDefaults = 0;
  v9 = operator new(0x88u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v9 )
  {
    *v9 = &CFaxConfiguration::`vftable';
    v9[6] = 0;
    v9[7] = 0;
    v9[12] = 0;
    *((_DWORD *)v9 + 32) = 0;
    v10 = StringDup(L"Software\\Microsoft\\Fax");
    v9[15] = v10;
    if ( !v10 )
    {
      std::runtime_error::runtime_error(
        (std::runtime_error *)pExceptionObject,
        "CFaxConfiguration::CFaxConfiguration - StringDup on lpRegKeyName failed");
      throw (std::runtime_error *)pExceptionObject;
    }
  }
  else
  {
    v9 = 0;
  }
  g_pFaxConfig = (CFaxConfiguration *)v9;
  if ( v9 )
  {
    v11 = operator new(4u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v11 )
    {
      *v11 = 0;
      g_pFaxArchiving = v11;
      v12 = (CFaxAccountList *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
      v14 = v12;
      if ( v12 )
      {
        *(_QWORD *)v12 = 0;
        *((_QWORD *)v12 + 1) = 0;
        *(_QWORD *)v12 = std::_List_alloc<0,std::_List_base_types<unsigned long>>::_Buynode0(v13, 0, 0);
        *((_DWORD *)v14 + 4) = 0;
      }
      else
      {
        v14 = 0;
      }
      g_pAccountList = v14;
      if ( v14 )
      {
        v15 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
        if ( v15 )
        {
          *v15 = &CFaxAccount::`vftable';
          v15[1] = 0;
          v15[2] = 0;
          *((_DWORD *)v15 + 6) = 0;
          g_pAccountDefaults = (CFaxAccount *)v15;
          v16 = (CClientsMap *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
          v17 = v16;
          if ( v16 )
          {
            *(_QWORD *)v16 = 0;
            *((_QWORD *)v16 + 1) = 0;
            *(_QWORD *)v16 = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<CClientID const,CClient>>>::_Buyheadnode();
          }
          else
          {
            v17 = 0;
          }
          g_pClientsMap = v17;
          if ( v17 )
          {
            v18 = operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
            if ( v18 )
            {
              *v18 = &CNotificationMap::`vftable';
              v18[1] = 0;
              *((_BYTE *)v18 + 56) = 0;
              v18[8] = 0;
              v18[9] = 0;
              v18[8] = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<CDeviceAndGUID const,CSinksList *>>>::_Buyheadnode();
              *((_DWORD *)v18 + 20) = 0;
            }
            else
            {
              v18 = 0;
            }
            g_pNotificationMap = (struct CNotificationMap *)v18;
            if ( v18 )
            {
              v19 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
              v20 = v19;
              if ( v19 )
              {
                *v19 = 0;
                v19[1] = 0;
                *v19 = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<unsigned long const,unsigned long>>>::_Buyheadnode();
              }
              else
              {
                v20 = 0;
              }
              g_pTAPIDevicesIdsMap = v20;
              if ( v20 )
              {
                v21 = (COutboundRoutingGroupsMap *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
                v22 = v21;
                if ( v21 )
                {
                  *(_QWORD *)v21 = 0;
                  *((_QWORD *)v21 + 1) = 0;
                  *(_QWORD *)v21 = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,COutboundRoutingGroup>>>::_Buyheadnode();
                }
                else
                {
                  v22 = 0;
                }
                g_pGroupsMap = v22;
                if ( v22 )
                {
                  v23 = (COutboundRulesMap *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
                  v24 = v23;
                  if ( v23 )
                  {
                    *(_QWORD *)v23 = 0;
                    *((_QWORD *)v23 + 1) = 0;
                    *(_QWORD *)v23 = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<CDeviceAndGUID const,CSinksList *>>>::_Buyheadnode();
                  }
                  else
                  {
                    v24 = 0;
                  }
                  g_pRulesMap = v24;
                  if ( v24 )
                    return 1;
                }
              }
            }
          }
        }
        else
        {
          g_pAccountDefaults = 0;
        }
      }
    }
    else
    {
      g_pFaxArchiving = 0;
    }
  }
  LastError = 8;
LABEL_74:
  SetLastError(LastError);
  return 0;
}

```

## disassembly

```asm
0x140025b04  mov     [rsp-28h+arg_10], rbx
0x140025b09  push    rbp
0x140025b0a  push    rsi
0x140025b0b  push    rdi
0x140025b0c  push    r14
0x140025b0e  push    r15
0x140025b10  mov     rbp, rsp
0x140025b13  sub     rsp, 40h
0x140025b17  lea     rsi, WPP_GLOBAL_Control
0x140025b1e  lea     r15, WPP_3d3bb31224953be0bbd934d07ab03620_Traceguids
0x140025b25  mov     rbx, cs:WPP_GLOBAL_Control
0x140025b2c  cmp     rbx, rsi
0x140025b2f  jz      short loc_140025B55
0x140025b31  test    byte ptr [rbx+1Ch], 4
0x140025b35  jz      short loc_140025B55
0x140025b37  cmp     byte ptr [rbx+19h], 5
0x140025b3b  jb      short loc_140025B55
0x140025b3d  mov     edx, 0Dh
0x140025b42  mov     r8, r15
0x140025b45  mov     rcx, [rbx+10h]
0x140025b49  call    WPP_SF_
0x140025b4e  mov     rbx, cs:WPP_GLOBAL_Control
0x140025b55  xor     r14d, r14d
0x140025b58  mov     cs:?g_pFaxPerfCounters@@3PEAU_FAX_PERF_COUNTERS@@EA, r14; _FAX_PERF_COUNTERS * g_pFaxPerfCounters
0x140025b5f  mov     cs:qword_1400A7838, r14
0x140025b66  mov     cs:dword_1400A7840, r14d
0x140025b6d  mov     cs:dword_1400A7844, r14d
0x140025b74  mov     cs:Data, r14d
0x140025b7b  lea     edi, [r14+50h]
0x140025b7f  mov     r8d, edi; Size
0x140025b82  xor     edx, edx; Val
0x140025b84  lea     rcx, ?g_ReceiptsConfig@@3U_FAX_SERVER_RECEIPTS_CONFIGW@@A; void *
0x140025b8b  call    memset_0
0x140025b90  mov     cs:?g_ReceiptsConfig@@3U_FAX_SERVER_RECEIPTS_CONFIGW@@A, edi; _FAX_SERVER_RECEIPTS_CONFIGW g_ReceiptsConfig
0x140025b96  xorps   xmm0, xmm0
0x140025b99  xor     eax, eax
0x140025b9b  movups  cs:?g_ActivityLoggingConfig@@3U_FAX_SERVER_ACTIVITY_LOGGING_CONFIG@@A, xmm0; _FAX_SERVER_ACTIVITY_LOGGING_CONFIG g_ActivityLoggingConfig
0x140025ba2  movups  cs:fDesiredAccess, xmm0
0x140025ba9  mov     cs:qword_1400A7630, rax
0x140025bb0  mov     dword ptr cs:?g_ActivityLoggingConfig@@3U_FAX_SERVER_ACTIVITY_LOGGING_CONFIG@@A, 28h ; '('; _FAX_SERVER_ACTIVITY_LOGGING_CONFIG g_ActivityLoggingConfig
0x140025bba  movdqu  cs:?g_ServerActivity@@3U_FAX_SERVER_ACTIVITY@@A+4, xmm0; _FAX_SERVER_ACTIVITY g_ServerActivity
0x140025bc2  xorps   xmm1, xmm1
0x140025bc5  movdqu  cs:xmmword_1400A3BA0+4, xmm1
0x140025bcd  mov     dword ptr cs:?g_ServerActivity@@3U_FAX_SERVER_ACTIVITY@@A, 24h ; '$'; _FAX_SERVER_ACTIVITY g_ServerActivity
0x140025bd7  mov     cs:?g_hDispatchEventsCompPort@@3PEAXEA, r14; void * g_hDispatchEventsCompPort
0x140025bde  mov     cs:?g_hSendEventsCompPort@@3PEAXEA, r14; void * g_hSendEventsCompPort
0x140025be5  mov     cs:?g_dwlClientID@@3_KA, r14; unsigned __int64 g_dwlClientID
0x140025bec  mov     cs:?g_FaxQuotaWarn@@3U_FAX_QUOTA_WARN@@A, r14; _FAX_QUOTA_WARN g_FaxQuotaWarn
0x140025bf3  mov     cs:?g_hArchiveQuotaWarningEvent@@3PEAXEA, r14; void * g_hArchiveQuotaWarningEvent
0x140025bfa  mov     cs:?g_dwConnectionCount@@3KA, r14d; ulong g_dwConnectionCount
0x140025c01  or      rax, 0FFFFFFFFFFFFFFFFh
0x140025c05  mov     cs:?g_hInboxActivityLogFile@@3PEAXEA, rax; void * g_hInboxActivityLogFile
0x140025c0c  mov     cs:?g_hOutboxActivityLogFile@@3PEAXEA, rax; void * g_hOutboxActivityLogFile
0x140025c13  mov     cs:?g_fLogStringTableInit@@3HA, r14d; int g_fLogStringTableInit
0x140025c1a  mov     cs:?g_dwQueueCount@@3KA, r14d; ulong g_dwQueueCount
0x140025c21  mov     cs:?g_hJobQueueEvent@@3PEAXEA, r14; void * g_hJobQueueEvent
0x140025c28  mov     cs:?g_ScanQueueAfterTimeout@@3HA, r14d; int g_ScanQueueAfterTimeout
0x140025c2f  mov     cs:?g_dwReceiveDevicesCount@@3KA, r14d; ulong g_dwReceiveDevicesCount
0x140025c36  mov     cs:?g_bDelaySuicideAttempt@@3HA, r14d; int g_bDelaySuicideAttempt
0x140025c3d  mov     cs:?g_bServiceCanSuicide@@3HA, 1; int g_bServiceCanSuicide
0x140025c47  mov     cs:?g_dwCountRoutingMethods@@3KA, r14d; ulong g_dwCountRoutingMethods
0x140025c4e  mov     cs:?g_pLineCountryList@@3PEAUlinecountrylist_tag@@EA, r14; linecountrylist_tag * g_pLineCountryList
0x140025c55  mov     cs:?g_dwLastUniqueId@@3_KA, r14; unsigned __int64 g_dwLastUniqueId
0x140025c5c  mov     cs:?g_bServiceIsDown@@3HA, r14d; int g_bServiceIsDown
0x140025c63  mov     cs:?g_TapiCompletionPort@@3PEAXEA, r14; void * g_TapiCompletionPort
0x140025c6a  mov     cs:?g_hLineApp@@3KA, r14d; ulong g_hLineApp
0x140025c71  mov     cs:ServiceStatus.dwServiceType, 30h ; '0'
0x140025c7b  lea     edi, [rax+3]
0x140025c7e  mov     cs:ServiceStatus.dwCurrentState, edi
0x140025c84  movups  xmmword ptr cs:ServiceStatus.dwWin32ExitCode, xmm0
0x140025c8b  mov     cs:?g_hRPCListeningThread@@3PEAXEA, r14; void * g_hRPCListeningThread
0x140025c92  mov     cs:?g_lServiceThreadsCount@@3JA, r14d; long g_lServiceThreadsCount
0x140025c99  mov     cs:?g_hThreadCountEvent@@3PEAXEA, r14; void * g_hThreadCountEvent
0x140025ca0  mov     ecx, r14d
0x140025ca3  lea     rdx, __ImageBase
0x140025caa  mov     rax, rcx
0x140025cad  shl     rax, 5
0x140025cb1  mov     [rax+rdx+0A3688h], r14
0x140025cb9  inc     rcx
0x140025cbc  cmp     rcx, 0Eh
0x140025cc0  jnz     short loc_140025CAA
0x140025cc2  mov     rcx, r14
0x140025cc5  mov     rax, rcx
0x140025cc8  shl     rax, 5
0x140025ccc  mov     [rax+rdx+0A3048h], r14
0x140025cd4  inc     rcx
0x140025cd7  cmp     rcx, 32h ; '2'
0x140025cdb  jnz     short loc_140025CC5
0x140025cdd  mov     rcx, r14
0x140025ce0  mov     rax, rcx
0x140025ce3  add     rax, rax
0x140025ce6  mov     rva qword_1400A3BC8[rdx+rax*8], r14
0x140025cee  inc     rcx
0x140025cf1  cmp     rcx, 3Bh ; ';'
0x140025cf5  jnz     short loc_140025CE0
0x140025cf7  mov     cs:?g_StatusCompletionPortHandle@@3PEAXEA, r14; void * g_StatusCompletionPortHandle
0x140025cfe  mov     cs:?g_pFaxSD@@3PEAXEA, r14; void * g_pFaxSD
0x140025d05  mov     cs:?g_dwDeviceCount@@3KA, r14d; ulong g_dwDeviceCount
0x140025d0c  mov     cs:?g_dwDeviceEnabledCount@@3KA, r14d; ulong g_dwDeviceEnabledCount
0x140025d13  cmp     rbx, rsi
0x140025d16  jz      short loc_140025D37
0x140025d18  test    [rbx+1Ch], dil
0x140025d1c  jz      short loc_140025D37
0x140025d1e  cmp     byte ptr [rbx+19h], 5
0x140025d22  jb      short loc_140025D37
0x140025d24  lea     edx, [rcx-2Ah]
0x140025d27  lea     r8, WPP_62ed8e7de8ef3265f87aee086930cd18_Traceguids
0x140025d2e  mov     rcx, [rbx+10h]
0x140025d32  call    WPP_SF_
0x140025d37  mov     dword ptr [rbp+arg_0], r14d
0x140025d3b  lea     rdx, [rbp+arg_0]
0x140025d3f  lea     rcx, aMicrosoftWindo_1; "Microsoft-Windows-Fax-Common-DeviceLimi"...
0x140025d46  call    GetLicensingPolicyValue
0x140025d4b  test    eax, eax
0x140025d4d  js      short loc_140025D54
0x140025d4f  mov     ebx, dword ptr [rbp+arg_0]
0x140025d52  jmp     short loc_140025D84
0x140025d54  mov     ebx, 1
0x140025d59  mov     rcx, cs:WPP_GLOBAL_Control
0x140025d60  cmp     rcx, rsi
0x140025d63  jz      short loc_140025D84
0x140025d65  test    [rcx+1Ch], dil
0x140025d69  jz      short loc_140025D84
0x140025d6b  cmp     byte ptr [rcx+19h], 3
0x140025d6f  jb      short loc_140025D84
0x140025d71  lea     edx, [rbx+11h]
0x140025d74  lea     r8, WPP_62ed8e7de8ef3265f87aee086930cd18_Traceguids
0x140025d7b  mov     rcx, [rcx+10h]
0x140025d7f  call    WPP_SF_
0x140025d84  mov     cs:?g_dwDeviceEnabledLimit@@3KA, ebx; ulong g_dwDeviceEnabledLimit
0x140025d8a  mov     cs:?g_hTapiWorkerThread@@3PEAXEA, r14; void * g_hTapiWorkerThread
0x140025d91  mov     cs:?g_hJobQueueThread@@3PEAXEA, r14; void * g_hJobQueueThread
0x140025d98  call    GetResInst
0x140025d9d  mov     cs:?g_hResource@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hResource
0x140025da4  test    rax, rax
0x140025da7  jnz     short loc_140025DBC
0x140025da9  call    cs:__imp_GetLastError
0x140025db0  nop     dword ptr [rax+rax+00h]
0x140025db5  mov     ebx, eax
0x140025db7  jmp     loc_14002633C
0x140025dbc  xor     r9d, r9d; lpName
0x140025dbf  xor     r8d, r8d; bInitialState
0x140025dc2  lea     edx, [r9+1]; bManualReset
0x140025dc6  xor     ecx, ecx; lpEventAttributes
0x140025dc8  call    cs:__imp_CreateEventW
0x140025dcf  nop     dword ptr [rax+rax+00h]
0x140025dd4  mov     cs:?g_hServiceShutDownEvent@@3PEAXEA, rax; void * g_hServiceShutDownEvent
0x140025ddb  test    rax, rax
0x140025dde  jnz     short loc_140025E2B
0x140025de0  call    cs:__imp_GetLastError
0x140025de7  nop     dword ptr [rax+rax+00h]
0x140025dec  mov     ebx, eax
0x140025dee  mov     rcx, cs:WPP_GLOBAL_Control
0x140025df5  cmp     rcx, rsi
0x140025df8  jz      loc_14002633C
0x140025dfe  test    byte ptr [rcx+1Ch], 4
0x140025e02  jz      loc_14002633C
0x140025e08  cmp     [rcx+19h], dil
0x140025e0c  jb      loc_14002633C
0x140025e12  mov     edx, 0Eh
0x140025e17  mov     r9d, eax
0x140025e1a  mov     r8, r15
0x140025e1d  mov     rcx, [rcx+10h]
0x140025e21  call    WPP_SF_d
0x140025e26  jmp     loc_14002633C
0x140025e2b  xor     r9d, r9d; lpName
0x140025e2e  xor     r8d, r8d; bInitialState
0x140025e31  lea     edx, [r9+1]; bManualReset
0x140025e35  xor     ecx, ecx; lpEventAttributes
0x140025e37  call    cs:__imp_CreateEventW
0x140025e3e  nop     dword ptr [rax+rax+00h]
0x140025e43  mov     cs:?g_hSCMServiceShutDownEvent@@3PEAXEA, rax; void * g_hSCMServiceShutDownEvent
0x140025e4a  test    rax, rax
0x140025e4d  jnz     short loc_140025E88
0x140025e4f  call    cs:__imp_GetLastError
0x140025e56  nop     dword ptr [rax+rax+00h]
0x140025e5b  mov     ebx, eax
0x140025e5d  mov     rcx, cs:WPP_GLOBAL_Control
0x140025e64  cmp     rcx, rsi
0x140025e67  jz      loc_14002633C
0x140025e6d  test    byte ptr [rcx+1Ch], 4
0x140025e71  jz      loc_14002633C
0x140025e77  cmp     [rcx+19h], dil
0x140025e7b  jb      loc_14002633C
0x140025e81  mov     edx, 0Fh
0x140025e86  jmp     short loc_140025E17
0x140025e88  xor     r9d, r9d; lpName
0x140025e8b  mov     r8d, edi; lMaximumCount
0x140025e8e  xor     edx, edx; lInitialCount
0x140025e90  xor     ecx, ecx; lpSemaphoreAttributes
0x140025e92  call    cs:__imp_CreateSemaphoreW
0x140025e99  nop     dword ptr [rax+rax+00h]
0x140025e9e  mov     cs:?g_hServiceIsDownSemaphore@@3PEAXEA, rax; void * g_hServiceIsDownSemaphore
0x140025ea5  test    rax, rax
0x140025ea8  jnz     short loc_140025EE6
0x140025eaa  call    cs:__imp_GetLastError
0x140025eb1  nop     dword ptr [rax+rax+00h]
0x140025eb6  mov     ebx, eax
0x140025eb8  mov     rcx, cs:WPP_GLOBAL_Control
0x140025ebf  cmp     rcx, rsi
0x140025ec2  jz      loc_14002633C
0x140025ec8  test    byte ptr [rcx+1Ch], 4
0x140025ecc  jz      loc_14002633C
0x140025ed2  cmp     [rcx+19h], dil
0x140025ed6  jb      loc_14002633C
0x140025edc  mov     edx, 10h
0x140025ee1  jmp     loc_140025E17
0x140025ee6  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140025eed  call    cs:__imp_InitializeCriticalSection
0x140025ef4  nop     dword ptr [rax+rax+00h]
0x140025ef9  lea     rcx, ?g_CsInboundActivityLogging@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140025f00  call    cs:__imp_InitializeCriticalSection
0x140025f07  nop     dword ptr [rax+rax+00h]
0x140025f0c  lea     rcx, ?g_CsOutboundActivityLogging@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140025f13  call    cs:__imp_InitializeCriticalSection
0x140025f1a  nop     dword ptr [rax+rax+00h]
0x140025f1f  lea     rcx, ?g_CsJob@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140025f26  call    cs:__imp_InitializeCriticalSection
0x140025f2d  nop     dword ptr [rax+rax+00h]
0x140025f32  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140025f39  call    cs:__imp_InitializeCriticalSection
0x140025f40  nop     dword ptr [rax+rax+00h]
0x140025f45  lea     rcx, ?g_CsPerfCounters@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140025f4c  call    cs:__imp_InitializeCriticalSection
0x140025f53  nop     dword ptr [rax+rax+00h]
0x140025f58  lea     rcx, ?g_CsSecurity@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140025f5f  call    cs:__imp_InitializeCriticalSection
0x140025f66  nop     dword ptr [rax+rax+00h]
0x140025f6b  lea     rcx, ?g_csUniqueQueueFile@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140025f72  call    cs:__imp_InitializeCriticalSection
0x140025f79  nop     dword ptr [rax+rax+00h]
0x140025f7e  lea     rcx, ?g_CsLine@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140025f85  call    cs:__imp_InitializeCriticalSection
0x140025f8c  nop     dword ptr [rax+rax+00h]
0x140025f91  lea     rcx, ?g_CsRouting@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140025f98  call    cs:__imp_InitializeCriticalSection
0x140025f9f  nop     dword ptr [rax+rax+00h]
0x140025fa4  lea     rcx, ?g_CsServiceThreads@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140025fab  call    cs:__imp_InitializeCriticalSection
0x140025fb2  nop     dword ptr [rax+rax+00h]
0x140025fb7  lea     rcx, ?g_CsHandleTable@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140025fbe  call    cs:__imp_InitializeCriticalSection
0x140025fc5  nop     dword ptr [rax+rax+00h]
0x140025fca  lea     rcx, ?g_CsActivity@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140025fd1  call    cs:__imp_InitializeCriticalSection
0x140025fd8  nop     dword ptr [rax+rax+00h]
0x140025fdd  lea     rcx, ?g_CsClients@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140025fe4  call    cs:__imp_InitializeCriticalSection
0x140025feb  nop     dword ptr [rax+rax+00h]
0x140025ff0  lea     rax, ?g_DeviceProvidersListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_DeviceProvidersListHead
0x140025ff7  mov     cs:qword_1400A7358, rax
0x140025ffe  mov     cs:?g_DeviceProvidersListHead@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY g_DeviceProvidersListHead
0x140026005  lea     rax, ?g_HandleTableListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_HandleTableListHead
0x14002600c  mov     cs:qword_1400A7468, rax
0x140026013  mov     cs:?g_HandleTableListHead@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY g_HandleTableListHead
0x14002601a  lea     rax, ?g_JobListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_JobListHead
0x140026021  mov     cs:qword_1400A74C8, rax
0x140026028  mov     cs:?g_JobListHead@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY g_JobListHead
0x14002602f  lea     rax, ?g_QueueListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_QueueListHead
0x140026036  mov     cs:?g_QueueListHead@@3U_LIST_ENTRY@@A.Blink, rax; _LIST_ENTRY g_QueueListHead ...
0x14002603d  mov     cs:?g_QueueListHead@@3U_LIST_ENTRY@@A.Flink, rax; _LIST_ENTRY g_QueueListHead ...
0x140026044  lea     rax, ?g_lstRoutingExtensions@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_lstRoutingExtensions
0x14002604b  mov     cs:qword_1400A7550, rax
0x140026052  mov     cs:?g_lstRoutingExtensions@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY g_lstRoutingExtensions
0x140026059  lea     rax, ?g_lstRoutingMethods@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_lstRoutingMethods
0x140026060  mov     cs:qword_1400A7588, rax
0x140026067  mov     cs:?g_lstRoutingMethods@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY g_lstRoutingMethods
0x14002606e  lea     rax, ?g_TapiLinesListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_TapiLinesListHead
0x140026075  mov     cs:qword_1400A7740, rax
0x14002607c  mov     cs:?g_TapiLinesListHead@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY g_TapiLinesListHead
0x140026083  lea     rax, ?g_RemovedTapiLinesListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_RemovedTapiLinesListHead
0x14002608a  mov     cs:qword_1400A7788, rax
0x140026091  mov     cs:?g_RemovedTapiLinesListHead@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY g_RemovedTapiLinesListHead
0x140026098  mov     cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA, r14; CFaxConfiguration * g_pFaxConfig
0x14002609f  mov     cs:?g_pFaxArchiving@@3PEAVCFaxArchiving@@EA, r14; CFaxArchiving * g_pFaxArchiving
0x1400260a6  mov     cs:?g_pClientsMap@@3PEAVCClientsMap@@EA, r14; CClientsMap * g_pClientsMap
0x1400260ad  mov     cs:?g_pNotificationMap@@3PEAVCNotificationMap@@EA, r14; CNotificationMap * g_pNotificationMap
0x1400260b4  mov     cs:?g_pTAPIDevicesIdsMap@@3PEAVCMapDeviceId@@EA, r14; CMapDeviceId * g_pTAPIDevicesIdsMap
0x1400260bb  mov     cs:?g_pGroupsMap@@3PEAVCOutboundRoutingGroupsMap@@EA, r14; COutboundRoutingGroupsMap * g_pGroupsMap
0x1400260c2  mov     cs:?g_pRulesMap@@3PEAVCOutboundRulesMap@@EA, r14; COutboundRulesMap * g_pRulesMap
0x1400260c9  mov     cs:?g_pAccountList@@3PEAVCFaxAccountList@@EA, r14; CFaxAccountList * g_pAccountList
0x1400260d0  mov     cs:?g_pAccountDefaults@@3PEAVCFaxAccount@@EA, r14; CFaxAccount * g_pAccountDefaults
0x1400260d7  lea     r15, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1400260de  mov     rdx, r15; struct std::nothrow_t *
0x1400260e1  mov     ecx, 88h; unsigned __int64
0x1400260e6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400260eb  mov     rbx, rax
0x1400260ee  mov     [rbp+arg_0], rax
0x1400260f2  test    rax, rax
0x1400260f5  jz      short loc_14002612F
0x1400260f7  lea     rax, ??_7CFaxConfiguration@@6B@; const CFaxConfiguration::`vftable'
0x1400260fe  mov     [rbx], rax
0x140026101  mov     [rbx+30h], r14
0x140026105  mov     [rbx+38h], r14
0x140026109  mov     [rbx+60h], r14
0x14002610d  mov     [rbx+80h], r14d
0x140026114  lea     rcx, aSoftwareMicros_8; "Software\\Microsoft\\Fax"
0x14002611b  call    StringDup
0x140026120  mov     [rbx+78h], rax
0x140026124  test    rax, rax
  ... truncated ...
```
