# ServiceStart(void)

- ea: `0x14004ae64`
- end: `0x14004bc5d`
- name: `?ServiceStart@@YAKXZ`
- size: `3577`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `1`
- callee_count: `30`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1400246b0`

## callees

- `0x140002c73`
- `0x140004be4`
- `0x140004c78`
- `0x140004ca8`
- `0x140026388`
- `0x140026a24`
- `0x14002c380`
- `0x14004a944`
- `0x14004ae64`
- `0x1400530d0`
- `0x140053414`
- `0x140059f9c`
- `0x14005d6b8`
- `0x1400698ec`
- `0x14006998c`
- `0x1400699d0`
- `0x14006af2c`
- `0x140073b50`
- `0x14007551c`
- `0x140075c70`
- `0x140075e90`
- `0x14008119c`
- `0x140081b74`
- `0x140081de4`
- `0x140085288`
- `0x14008534c`
- `0x1400854a8`
- `0x140085718`
- `0x1400859f8`
- `0x140086ec0`

## import_xrefs

- `ADVAPI32!RegisterEventSourceW` at `0x14004b206`
- `ADVAPI32!RegisterEventSourceW` at `0x14004b206`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x14004b05d`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x14004b05d`
- `KERNEL32!GetLastError` at `0x14004b296`
- `KERNEL32!GetLastError` at `0x14004b350`
- `KERNEL32!GetLastError` at `0x14004b3ba`
- `KERNEL32!GetLastError` at `0x14004b41b`
- `KERNEL32!GetLastError` at `0x14004b51e`
- `KERNEL32!GetLastError` at `0x14004b58f`
- `KERNEL32!GetLastError` at `0x14004b5ee`
- `KERNEL32!GetLastError` at `0x14004b6d7`
- `KERNEL32!GetLastError` at `0x14004b762`
- `KERNEL32!GetLastError` at `0x14004b9b3`
- `KERNEL32!GetLastError` at `0x14004ba62`
- `KERNEL32!GetLastError` at `0x14004bace`
- `KERNEL32!GetLastError` at `0x14004bbc6`
- `KERNEL32!GetLastError` at `0x14004b296`
- `KERNEL32!GetLastError` at `0x14004b350`
- `KERNEL32!GetLastError` at `0x14004b3ba`
- `KERNEL32!GetLastError` at `0x14004b41b`
- `KERNEL32!GetLastError` at `0x14004b51e`
- `KERNEL32!GetLastError` at `0x14004b58f`
- `KERNEL32!GetLastError` at `0x14004b5ee`
- `KERNEL32!GetLastError` at `0x14004b6d7`
- `KERNEL32!GetLastError` at `0x14004b762`
- `KERNEL32!GetLastError` at `0x14004b9b3`
- `KERNEL32!GetLastError` at `0x14004ba62`
- `KERNEL32!GetLastError` at `0x14004bace`
- `KERNEL32!GetLastError` at `0x14004bbc6`
- `KERNEL32!CloseHandle` at `0x14004ba8e`
- `KERNEL32!CloseHandle` at `0x14004bae7`
- `KERNEL32!CloseHandle` at `0x14004ba8e`
- `KERNEL32!CloseHandle` at `0x14004bae7`
- `KERNEL32!EnterCriticalSection` at `0x14004b119`
- `KERNEL32!EnterCriticalSection` at `0x14004b229`
- `KERNEL32!EnterCriticalSection` at `0x14004b61c`
- `KERNEL32!EnterCriticalSection` at `0x14004b838`
- `KERNEL32!EnterCriticalSection` at `0x14004b84b`
- `KERNEL32!EnterCriticalSection` at `0x14004b119`
- `KERNEL32!EnterCriticalSection` at `0x14004b229`
- `KERNEL32!EnterCriticalSection` at `0x14004b61c`
- `KERNEL32!EnterCriticalSection` at `0x14004b838`
- `KERNEL32!EnterCriticalSection` at `0x14004b84b`
- `KERNEL32!LeaveCriticalSection` at `0x14004b16b`
- `KERNEL32!LeaveCriticalSection` at `0x14004b1f1`
- `KERNEL32!LeaveCriticalSection` at `0x14004b27b`
- `KERNEL32!LeaveCriticalSection` at `0x14004b2de`
- `KERNEL32!LeaveCriticalSection` at `0x14004b654`
- `KERNEL32!LeaveCriticalSection` at `0x14004b865`
- `KERNEL32!LeaveCriticalSection` at `0x14004b878`
- `KERNEL32!LeaveCriticalSection` at `0x14004b16b`
- `KERNEL32!LeaveCriticalSection` at `0x14004b1f1`
- `KERNEL32!LeaveCriticalSection` at `0x14004b27b`
- `KERNEL32!LeaveCriticalSection` at `0x14004b2de`
- `KERNEL32!LeaveCriticalSection` at `0x14004b654`
- `KERNEL32!LeaveCriticalSection` at `0x14004b865`
- `KERNEL32!LeaveCriticalSection` at `0x14004b878`
- `KERNEL32!WaitForSingleObject` at `0x14004b9f4`
- `KERNEL32!WaitForSingleObject` at `0x14004b9f4`
- `KERNEL32!CreateEventW` at `0x14004b3a2`
- `KERNEL32!CreateEventW` at `0x14004b3a2`
- `KERNEL32!GetExitCodeThread` at `0x14004baa6`
- `KERNEL32!GetExitCodeThread` at `0x14004baa6`
- `KERNEL32!CreateThread` at `0x14004b97b`
- `KERNEL32!CreateThread` at `0x14004bb92`
- `KERNEL32!CreateThread` at `0x14004b97b`
- `KERNEL32!CreateThread` at `0x14004bb92`

## pseudocode

```c
// Hidden C++ exception states: #wind=72 #try_helpers=1
__int64 __fastcall ServiceStart(__int64 a1, unsigned int a2)
{
  unsigned int v2; // edx
  unsigned int v3; // eax
  unsigned int v4; // edx
  CMapDeviceId *v5; // rcx
  __int64 v6; // rdx
  unsigned int FaxRegistry; // eax
  unsigned int *v8; // rbx
  void *v9; // rax
  unsigned int v10; // esi
  __int64 v11; // rdi
  unsigned __int16 *v12; // rax
  _DWORD *v13; // rdx
  unsigned int v14; // edx
  unsigned int i; // edi
  DWORD LastError; // eax
  DWORD v17; // ebx
  DWORD started; // eax
  CMapDeviceId *v20; // rcx
  __int64 v21; // rdx
  unsigned int v22; // edx
  unsigned int v23; // edx
  _OWORD *v24; // rax
  DWORD v25; // eax
  int FaxServiceInstance; // eax
  CMapDeviceId *v27; // rcx
  __int64 v28; // rdx
  unsigned int *v29; // rdx
  DWORD v30; // eax
  DWORD v31; // eax
  DWORD v32; // eax
  unsigned int v33; // edx
  DWORD Configuration; // eax
  unsigned int v35; // edx
  CMapDeviceId *v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // r9
  struct _REG_FAX_SERVICE *v39; // rcx
  unsigned int v40; // edx
  DWORD v41; // eax
  DWORD v42; // ebx
  int v43; // eax
  unsigned __int16 *v44; // rdx
  unsigned int v45; // eax
  unsigned int v46; // edx
  unsigned int v47; // ebx
  int v48; // eax
  unsigned __int16 *v49; // rdx
  unsigned int v50; // eax
  unsigned int v51; // edx
  __int64 v52; // r9
  CNotificationMap *v53; // rcx
  unsigned int v54; // edx
  unsigned int v55; // edx
  HANDLE v56; // rdi
  DWORD v57; // eax
  unsigned int v58; // edx
  DWORD v59; // eax
  __int64 v60; // rdx
  void *v61; // rdx
  unsigned __int16 *v62; // rcx
  DWORD dwCreationFlags[2]; // [rsp+20h] [rbp-79h]
  LPDWORD lpThreadId; // [rsp+28h] [rbp-71h]
  LPVOID lpParameter; // [rsp+30h] [rbp-69h] BYREF
  DWORD ExitCode; // [rsp+38h] [rbp-61h] BYREF
  DWORD ThreadId; // [rsp+3Ch] [rbp-5Dh] BYREF
  const wchar_t *v68; // [rsp+40h] [rbp-59h] BYREF
  int v69; // [rsp+48h] [rbp-51h]
  int v70; // [rsp+4Ch] [rbp-4Dh]
  const wchar_t *v71; // [rsp+50h] [rbp-49h]
  int v72; // [rsp+58h] [rbp-41h]
  int v73; // [rsp+5Ch] [rbp-3Dh]
  const wchar_t *v74; // [rsp+60h] [rbp-39h]
  int v75; // [rsp+68h] [rbp-31h]
  int v76; // [rsp+6Ch] [rbp-2Dh]
  const wchar_t *v77; // [rsp+70h] [rbp-29h]
  int v78; // [rsp+78h] [rbp-21h]
  int v79; // [rsp+7Ch] [rbp-1Dh]
  DWORD v80; // [rsp+80h] [rbp-19h]
  unsigned __int16 v81[14]; // [rsp+84h] [rbp-15h] BYREF

  ThreadId = 0;
  ExitCode = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids);
  }
  ReportServiceStatus(2u, a2, 0xEA60u);
  if ( !(unsigned int)IsFaxShared() )
  {
    LODWORD(lpParameter) = 0;
    v3 = IsLocalFaxPrinterShared(&lpParameter);
    if ( v3 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_26;
      }
      v6 = 22;
    }
    else
    {
      if ( !(_DWORD)lpParameter )
        goto LABEL_26;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids);
      }
      v3 = SetLocalFaxPrinterSharing();
      if ( !v3 )
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids);
        }
        goto LABEL_26;
      }
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_26:
        ReportServiceStatus(2u, v4, 0xEA60u);
        goto LABEL_27;
      }
      v6 = 21;
    }
    WPP_SF_d(*((_QWORD *)v5 + 2), v6, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v3);
    goto LABEL_26;
  }
LABEL_27:
  ReportServiceStatus(2u, v2, 0xEA60u);
  v69 = 1;
  v68 = L"Initialization/Termination";
  v71 = L"Outbound";
  v74 = L"Inbound";
  v77 = L"Unknown";
  v70 = 2;
  v72 = 2;
  v73 = 2;
  v75 = 3;
  v76 = 2;
  v78 = 4;
  v79 = 2;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_ac5a08ad8a3d3e294c0851b9f863ab66_Traceguids);
  }
  if ( InitializeCriticalSectionAndSpinCount(&stru_1400A7850, 0x80000000) )
    byte_1400A78A8 = 1;
  lpParameter = 0;
  FaxRegistry = GetFaxRegistry(&lpParameter);
  if ( FaxRegistry )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_ac5a08ad8a3d3e294c0851b9f863ab66_Traceguids, FaxRegistry);
    }
    goto LABEL_57;
  }
  v8 = (unsigned int *)lpParameter;
  if ( !(unsigned int)CreateFaxEventSource(lpParameter, &v68) )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_ac5a08ad8a3d3e294c0851b9f863ab66_Traceguids);
    }
LABEL_56:
    FreeFaxRegistry(v8);
LABEL_57:
    LastError = GetLastError();
    v17 = LastError;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, LastError);
    }
    return v17;
  }
  EnterCriticalSection(&stru_1400A7850);
  v9 = (void *)pMemAlloc(16LL * v8[14]);
  gs_pFaxCategory = v9;
  if ( !v9 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_ac5a08ad8a3d3e294c0851b9f863ab66_Traceguids);
    }
    LeaveCriticalSection(&stru_1400A7850);
    goto LABEL_56;
  }
  memset_0(v9, 0, 16LL * v8[14]);
  v10 = 0;
  dword_1400A787C = v8[14];
  if ( dword_1400A787C )
  {
    while ( 1 )
    {
      v11 = 2LL * v10;
      v12 = StringDup(*(unsigned __int16 **)(*((_QWORD *)v8 + 6) + 16LL * v10));
      v13 = gs_pFaxCategory;
      *((_QWORD *)gs_pFaxCategory + 2 * v10) = v12;
      if ( !v12 )
        break;
      ++v10;
      v13[2 * v11 + 2] = *(_DWORD *)(*((_QWORD *)v8 + 6) + 8 * v11 + 8);
      v13[2 * v11 + 3] = *(_DWORD *)(*((_QWORD *)v8 + 6) + 8 * v11 + 12);
      if ( v10 >= v8[14] )
        goto LABEL_52;
    }
    LeaveCriticalSection(&stru_1400A7850);
    goto LABEL_53;
  }
LABEL_52:
  LeaveCriticalSection(&stru_1400A7850);
  hEventLog = RegisterEventSourceW(0, L"Microsoft Fax");
  if ( !hEventLog )
  {
LABEL_53:
    EnterCriticalSection(&stru_1400A7850);
    for ( i = 0; i < v8[14]; ++i )
      pMemFree(*((LPVOID *)gs_pFaxCategory + 2 * i));
    pMemFree(gs_pFaxCategory);
    gs_pFaxCategory = 0;
    dword_1400A787C = 0;
    LeaveCriticalSection(&stru_1400A7850);
    goto LABEL_56;
  }
  ReportServiceStatus(2u, v14, 0xEA60u);
  started = EnableProcessPrivilege();
  v17 = started;
  if ( started )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_187;
    }
    v21 = 24;
LABEL_186:
    WPP_SF_d(*((_QWORD *)v20 + 2), v21, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, started);
LABEL_187:
    v80 = v17;
    v81[0] = 0;
    StringCchPrintfW(v81, 0xCu, L"%ld", v17, *(_QWORD *)dwCreationFlags, lpThreadId);
    v52 = 3221257513LL;
LABEL_188:
    FaxLog(1, 1, 1, v52);
    return v17;
  }
  if ( !(unsigned int)InitializeStringTable() )
  {
    started = GetLastError();
    v17 = started;
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_187;
    }
    v21 = 25;
    goto LABEL_186;
  }
  ReportServiceStatus(2u, v22, 0xEA60u);
  g_hThreadCountEvent = CreateEventW(0, 1, 1, 0);
  if ( !g_hThreadCountEvent )
  {
    started = GetLastError();
    v17 = started;
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_187;
    }
    v21 = 26;
    goto LABEL_186;
  }
  ReportServiceStatus(2u, v23, 0xEA60u);
  v24 = (_OWORD *)pMemAlloc(0x3Cu);
  g_pFaxPerfCounters = v24;
  if ( !v24 )
  {
    v25 = GetLastError();
    v17 = v25;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v25);
    }
    goto LABEL_83;
  }
  *v24 = 0;
  v24[1] = 0;
  v24[2] = 0;
  *(_OWORD *)((char *)v24 + 44) = 0;
  FaxServiceInstance = PerfInitialize();
  if ( FaxServiceInstance < 0 )
  {
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_83;
    }
    v28 = 28;
LABEL_89:
    WPP_SF_d(
      *((_QWORD *)v27 + 2),
      v28,
      WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids,
      (unsigned int)FaxServiceInstance);
LABEL_83:
    FaxLog(1, 1, 0, 3221257586LL);
    return v17;
  }
  FaxServiceInstance = PerfGetFaxServiceInstance();
  if ( FaxServiceInstance < 0 )
  {
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_83;
    }
    v28 = 29;
    goto LABEL_89;
  }
  if ( PerfSetFaxInboundRefValue(
         (char *)g_pFaxPerfCounters + 16,
         v29,
         (unsigned int *)g_pFaxPerfCounters + 1,
         (unsigned int *)g_pFaxPerfCounters + 3,
         (unsigned int *)g_pFaxPerfCounters + 2)
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v30 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v30);
  }
  if ( PerfSetFaxOutboundRefValue(
         (char *)g_pFaxPerfCounters + 36,
         (char *)g_pFaxPerfCounters + 40,
         (char *)g_pFaxPerfCounters + 20,
         (char *)g_pFaxPerfCounters + 24,
         (char *)g_pFaxPerfCounters + 32,
         (char *)g_pFaxPerfCounters + 28)
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v31 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v31);
  }
  if ( PerfSetFaxServiceRefValue(
         (char *)g_pFaxPerfCounters + 44,
         (char *)g_pFaxPerfCounters + 48,
         (char *)g_pFaxPerfCounters + 56,
         (char *)g_pFaxPerfCounters + 52)
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v32 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v32);
  }
  EnterCriticalSection(&g_CsPerfCounters);
  g_dwOutboundSeconds = 60 * *((_DWORD *)g_pFaxPerfCounters + 8);
  g_dwTotalSeconds = 60 * *((_DWORD *)g_pFaxPerfCounters + 14);
  g_dwInboundSeconds = 60 * *((_DWORD *)g_pFaxPerfCounters + 3);
  LeaveCriticalSection(&g_CsPerfCounters);
  ReportServiceStatus(2u, v33, 0xEA60u);
  Configuration = LoadConfiguration((struct _REG_FAX_SERVICE **)&lpParameter);
  v17 = Configuration;
  if ( Configuration )
  {
    v36 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v17;
    }
    v37 = 33;
    goto LABEL_115;
  }
  ReportServiceStatus(2u, v35, 0xEA60u);
  if ( !(unsigned int)InitializeFaxQueue(v39) )
  {
    v41 = GetLastError();
    v42 = v41;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v41);
    }
    v80 = v42;
    v81[0] = 0;
    v43 = StringCchPrintfW(v81, 0xCu, L"%ld", v42);
    v44 = v81;
    if ( v43 < 0 )
      v44 = 0;
    lpThreadId = (LPDWORD)v44;
    *(_QWORD *)dwCreationFlags = *((_QWORD *)g_pFaxConfig + 12);
    FaxLog(1, 1, 2, 3221257576LL);
    started = GetLastError();
    v17 = started;
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_187;
    }
    v21 = 35;
    goto LABEL_186;
  }
  ReportServiceStatus(2u, v40, 0xEA60u);
  v45 = InitializeLogging();
  v47 = v45;
  if ( v45 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v45);
    }
    v80 = v47;
    v81[0] = 0;
    v48 = StringCchPrintfW(v81, 0xCu, L"%ld", v47);
    v49 = v81;
    if ( v48 < 0 )
      v49 = 0;
    lpThreadId = (LPDWORD)v49;
    *(_QWORD *)dwCreationFlags = *(_QWORD *)&fDesiredAccess;
    FaxLog(1, 1, 2, 3221257577LL);
    EnterCriticalSection(&g_CsInboundActivityLogging);
    EnterCriticalSection(&g_CsOutboundActivityLogging);
    *(_QWORD *)((char *)&g_ActivityLoggingConfig + 4) = 0;
    LeaveCriticalSection(&g_CsOutboundActivityLogging);
    LeaveCriticalSection(&g_CsInboundActivityLogging);
  }
  ReportServiceStatus(2u, v46, 0xEA60u);
  v50 = InitializeServerEvents();
  v17 = v50;
  if ( v50 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v50);
    }
    v80 = v17;
    v81[0] = 0;
    StringCchPrintfW(v81, 0xCu, L"%ld", v17, *(_QWORD *)dwCreationFlags, lpThreadId);
    v52 = 3221257516LL;
    goto LABEL_188;
  }
  ReportServiceStatus(2u, v51, 0xEA60u);
  started = CNotificationMap::Init(v53);
  v17 = started;
  if ( started )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_187;
    }
    v21 = 38;
    goto LABEL_186;
  }
  ReportServiceStatus(2u, v54, 0xEA60u);
  v56 = CreateThread(0, 0, FaxInitThread, lpParameter, 0, &ThreadId);
  if ( !v56 )
  {
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v17;
    }
    Configuration = GetLastError();
    v36 = WPP_GLOBAL_Control;
    v37 = 39;
    v17 = Configuration;
LABEL_115:
    v38 = Configuration;
LABEL_116:
    WPP_SF_d(*((_QWORD *)v36 + 2), v37, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v38);
    return v17;
  }
  ReportServiceStatus(2u, v55, 0x4E20u);
  while ( 1 )
  {
    v57 = WaitForSingleObject(v56, 0x2710u);
    v17 = v57;
    if ( !v57 )
      break;
    if ( v57 != 258 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v59 = GetLastError();
        v60 = 42;
        goto LABEL_164;
      }
      goto LABEL_165;
    }
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids);
    }
    ReportServiceStatus(2u, v58, 0x7530u);
  }
  if ( !GetExitCodeThread(v56, &ExitCode) )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v59 = GetLastError();
      v60 = 40;
LABEL_164:
      v17 = v59;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v60, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids, v59);
    }
LABEL_165:
    CloseHandle(v56);
    return v17;
  }
  v17 = ExitCode;
  CloseHandle(v56);
  if ( v17 )
  {
    v36 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v17;
    }
    v37 = 43;
    v38 = v17;
    goto LABEL_116;
  }
  FaxLog(1, 3, 0, 1073773825);
  started = StartFaxRpcServer(v62, v61);
  v17 = started;
  if ( started )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_187;
    }
    v21 = 44;
    goto LABEL_186;
  }
  g_hRPCListeningThread = CreateThread(0, 0, FaxRPCListeningThread, 0, 0, &ThreadId);
  if ( !g_hRPCListeningThread )
  {
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_187;
    }
    started = GetLastError();
    v20 = WPP_GLOBAL_Control;
    v21 = 45;
    v17 = started;
    goto LABEL_186;
  }
  return 0;
}

```

## disassembly

```asm
0x14004ae64  push    rbp
0x14004ae66  push    rbx
0x14004ae67  push    rsi
0x14004ae68  push    rdi
0x14004ae69  push    r12
0x14004ae6b  push    r13
0x14004ae6d  push    r14
0x14004ae6f  push    r15
0x14004ae71  lea     rbp, [rsp-1Fh]
0x14004ae76  sub     rsp, 0B8h
0x14004ae7d  mov     rax, cs:__security_cookie
0x14004ae84  xor     rax, rsp
0x14004ae87  mov     [rbp+57h+var_50], rax
0x14004ae8b  xor     r15d, r15d
0x14004ae8e  mov     [rbp+57h+ThreadId], r15d
0x14004ae92  mov     [rbp+57h+ExitCode], r15d
0x14004ae96  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ae9d  lea     r12, WPP_GLOBAL_Control
0x14004aea4  lea     rdi, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids
0x14004aeab  mov     sil, 5
0x14004aeae  lea     r13d, [r15+4]
0x14004aeb2  cmp     rcx, r12
0x14004aeb5  jz      short loc_14004AED3
0x14004aeb7  test    [rcx+1Ch], r13b
0x14004aebb  jz      short loc_14004AED3
0x14004aebd  cmp     [rcx+19h], sil
0x14004aec1  jb      short loc_14004AED3
0x14004aec3  mov     rcx, [rcx+10h]
0x14004aec7  lea     edx, [r15+11h]
0x14004aecb  mov     r8, rdi
0x14004aece  call    WPP_SF_
0x14004aed3  mov     ebx, 0EA60h
0x14004aed8  mov     r14d, 2
0x14004aede  mov     r8d, ebx; unsigned int
0x14004aee1  mov     ecx, r14d; unsigned int
0x14004aee4  call    ?ReportServiceStatus@@YAHKKK@Z; ReportServiceStatus(ulong,ulong,ulong)
0x14004aee9  call    IsFaxShared
0x14004aeee  test    eax, eax
0x14004aef0  jnz     loc_14004AFC4
0x14004aef6  lea     rcx, [rbp+57h+lpParameter]
0x14004aefa  mov     dword ptr [rbp+57h+lpParameter], r15d
0x14004aefe  call    IsLocalFaxPrinterShared
0x14004af03  test    eax, eax
0x14004af05  jnz     loc_14004AF8D
0x14004af0b  cmp     dword ptr [rbp+57h+lpParameter], r15d
0x14004af0f  jz      loc_14004AFB9
0x14004af15  mov     rcx, cs:WPP_GLOBAL_Control
0x14004af1c  cmp     rcx, r12
0x14004af1f  jz      short loc_14004AF3C
0x14004af21  test    [rcx+1Ch], r13b
0x14004af25  jz      short loc_14004AF3C
0x14004af27  cmp     [rcx+19h], sil
0x14004af2b  jb      short loc_14004AF3C
0x14004af2d  mov     rcx, [rcx+10h]
0x14004af31  lea     edx, [rax+13h]
0x14004af34  mov     r8, rdi
0x14004af37  call    WPP_SF_
0x14004af3c  call    SetLocalFaxPrinterSharing
0x14004af41  test    eax, eax
0x14004af43  jnz     short loc_14004AF6E
0x14004af45  mov     rcx, cs:WPP_GLOBAL_Control
0x14004af4c  cmp     rcx, r12
0x14004af4f  jz      short loc_14004AFB9
0x14004af51  test    [rcx+1Ch], r13b
0x14004af55  jz      short loc_14004AFB9
0x14004af57  cmp     [rcx+19h], sil
0x14004af5b  jb      short loc_14004AFB9
0x14004af5d  mov     rcx, [rcx+10h]
0x14004af61  lea     edx, [rax+14h]
0x14004af64  mov     r8, rdi
0x14004af67  call    WPP_SF_
0x14004af6c  jmp     short loc_14004AFB9
0x14004af6e  mov     rcx, cs:WPP_GLOBAL_Control
0x14004af75  cmp     rcx, r12
0x14004af78  jz      short loc_14004AFB9
0x14004af7a  test    [rcx+1Ch], r13b
0x14004af7e  jz      short loc_14004AFB9
0x14004af80  cmp     [rcx+19h], r14b
0x14004af84  jb      short loc_14004AFB9
0x14004af86  mov     edx, 15h
0x14004af8b  jmp     short loc_14004AFAA
0x14004af8d  mov     rcx, cs:WPP_GLOBAL_Control
0x14004af94  cmp     rcx, r12
0x14004af97  jz      short loc_14004AFB9
0x14004af99  test    [rcx+1Ch], r13b
0x14004af9d  jz      short loc_14004AFB9
0x14004af9f  cmp     [rcx+19h], r14b
0x14004afa3  jb      short loc_14004AFB9
0x14004afa5  mov     edx, 16h
0x14004afaa  mov     rcx, [rcx+10h]
0x14004afae  mov     r9d, eax
0x14004afb1  mov     r8, rdi
0x14004afb4  call    WPP_SF_d
0x14004afb9  mov     r8d, ebx; unsigned int
0x14004afbc  mov     ecx, r14d; unsigned int
0x14004afbf  call    ?ReportServiceStatus@@YAHKKK@Z; ReportServiceStatus(ulong,ulong,ulong)
0x14004afc4  mov     r8d, ebx; unsigned int
0x14004afc7  mov     ecx, r14d; unsigned int
0x14004afca  call    ?ReportServiceStatus@@YAHKKK@Z; ReportServiceStatus(ulong,ulong,ulong)
0x14004afcf  lea     rax, aInitialization; "Initialization/Termination"
0x14004afd6  mov     [rbp+57h+var_A8], 1
0x14004afdd  mov     [rbp+57h+var_B0], rax
0x14004afe1  lea     rax, aOutbound; "Outbound"
0x14004afe8  mov     [rbp+57h+var_A0], rax
0x14004afec  lea     rax, aInbound; "Inbound"
0x14004aff3  mov     [rbp+57h+var_90], rax
0x14004aff7  lea     rax, aUnknown_0; "Unknown"
0x14004affe  mov     [rbp+57h+var_80], rax
0x14004b002  mov     [rbp+57h+var_A4], r14d
0x14004b006  mov     [rbp+57h+var_98], r14d
0x14004b00a  mov     [rbp+57h+var_94], r14d
0x14004b00e  mov     [rbp+57h+var_88], 3
0x14004b015  mov     [rbp+57h+var_84], r14d
0x14004b019  mov     [rbp+57h+var_78], r13d
0x14004b01d  mov     [rbp+57h+var_74], r14d
0x14004b021  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b028  cmp     rcx, r12
0x14004b02b  jz      short loc_14004B04E
0x14004b02d  test    [rcx+1Ch], r14b
0x14004b031  jz      short loc_14004B04E
0x14004b033  cmp     [rcx+19h], sil
0x14004b037  jb      short loc_14004B04E
0x14004b039  mov     rcx, [rcx+10h]
0x14004b03d  lea     r8, WPP_ac5a08ad8a3d3e294c0851b9f863ab66_Traceguids
0x14004b044  mov     edx, 0Ch
0x14004b049  call    WPP_SF_
0x14004b04e  lea     rsi, stru_1400A7850
0x14004b055  mov     edx, 80000000h; dwSpinCount
0x14004b05a  mov     rcx, rsi; lpCriticalSection
0x14004b05d  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x14004b064  nop     dword ptr [rax+rax+00h]
0x14004b069  test    eax, eax
0x14004b06b  jz      short loc_14004B074
0x14004b06d  mov     cs:byte_1400A78A8, 1
0x14004b074  lea     rcx, [rbp+57h+lpParameter]
0x14004b078  mov     [rbp+57h+lpParameter], r15
0x14004b07c  call    GetFaxRegistry
0x14004b081  test    eax, eax
0x14004b083  jz      short loc_14004B0C6
0x14004b085  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b08c  cmp     rcx, r12
0x14004b08f  jz      loc_14004B296
0x14004b095  test    [rcx+1Ch], r14b
0x14004b099  jz      loc_14004B296
0x14004b09f  cmp     [rcx+19h], r14b
0x14004b0a3  jb      loc_14004B296
0x14004b0a9  mov     rcx, [rcx+10h]
0x14004b0ad  lea     r8, WPP_ac5a08ad8a3d3e294c0851b9f863ab66_Traceguids
0x14004b0b4  mov     edx, 0Eh
0x14004b0b9  mov     r9d, eax
0x14004b0bc  call    WPP_SF_d
0x14004b0c1  jmp     loc_14004B296
0x14004b0c6  mov     rbx, [rbp+57h+lpParameter]
0x14004b0ca  lea     rdx, [rbp+57h+var_B0]
0x14004b0ce  mov     rcx, rbx
0x14004b0d1  call    CreateFaxEventSource
0x14004b0d6  test    eax, eax
0x14004b0d8  jnz     short loc_14004B116
0x14004b0da  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b0e1  cmp     rcx, r12
0x14004b0e4  jz      loc_14004B28E
0x14004b0ea  test    [rcx+1Ch], r14b
0x14004b0ee  jz      loc_14004B28E
0x14004b0f4  cmp     [rcx+19h], r14b
0x14004b0f8  jb      loc_14004B28E
0x14004b0fe  mov     rcx, [rcx+10h]
0x14004b102  lea     edx, [rax+0Fh]
0x14004b105  lea     r8, WPP_ac5a08ad8a3d3e294c0851b9f863ab66_Traceguids
0x14004b10c  call    WPP_SF_
0x14004b111  jmp     loc_14004B28E
0x14004b116  mov     rcx, rsi; lpCriticalSection
0x14004b119  call    cs:__imp_EnterCriticalSection
0x14004b120  nop     dword ptr [rax+rax+00h]
0x14004b125  mov     ecx, [rbx+38h]
0x14004b128  shl     rcx, 4; dwBytes
0x14004b12c  call    pMemAlloc
0x14004b131  mov     cs:?gs_pFaxCategory@@3PEAU_FAX_LOG_CATEGORYW@@EA, rax; _FAX_LOG_CATEGORYW * gs_pFaxCategory
0x14004b138  test    rax, rax
0x14004b13b  jnz     short loc_14004B17C
0x14004b13d  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b144  cmp     rcx, r12
0x14004b147  jz      short loc_14004B168
0x14004b149  test    [rcx+1Ch], r14b
0x14004b14d  jz      short loc_14004B168
0x14004b14f  cmp     [rcx+19h], r14b
0x14004b153  jb      short loc_14004B168
0x14004b155  mov     rcx, [rcx+10h]
0x14004b159  lea     edx, [rax+10h]
0x14004b15c  lea     r8, WPP_ac5a08ad8a3d3e294c0851b9f863ab66_Traceguids
0x14004b163  call    WPP_SF_
0x14004b168  mov     rcx, rsi; lpCriticalSection
0x14004b16b  call    cs:__imp_LeaveCriticalSection
0x14004b172  nop     dword ptr [rax+rax+00h]
0x14004b177  jmp     loc_14004B28E
0x14004b17c  mov     r8d, [rbx+38h]
0x14004b180  xor     edx, edx; Val
0x14004b182  shl     r8, 4; Size
0x14004b186  mov     rcx, rax; void *
0x14004b189  call    memset_0
0x14004b18e  mov     eax, [rbx+38h]
0x14004b191  mov     esi, r15d
0x14004b194  mov     cs:dword_1400A787C, eax
0x14004b19a  test    eax, eax
0x14004b19c  jz      short loc_14004B1EA
0x14004b19e  mov     rcx, [rbx+30h]
0x14004b1a2  mov     edi, esi
0x14004b1a4  add     rdi, rdi
0x14004b1a7  mov     rcx, [rcx+rdi*8]; unsigned __int16 *
0x14004b1ab  call    StringDup
0x14004b1b0  mov     rdx, cs:?gs_pFaxCategory@@3PEAU_FAX_LOG_CATEGORYW@@EA; _FAX_LOG_CATEGORYW * gs_pFaxCategory
0x14004b1b7  mov     [rdx+rdi*8], rax
0x14004b1bb  test    rax, rax
0x14004b1be  jz      loc_14004B2D7
0x14004b1c4  mov     rax, [rbx+30h]
0x14004b1c8  inc     esi
0x14004b1ca  mov     ecx, [rax+rdi*8+8]
0x14004b1ce  mov     [rdx+rdi*8+8], ecx
0x14004b1d2  mov     rax, [rbx+30h]
0x14004b1d6  mov     ecx, [rax+rdi*8+0Ch]
0x14004b1da  mov     [rdx+rdi*8+0Ch], ecx
0x14004b1de  cmp     esi, [rbx+38h]
0x14004b1e1  jb      short loc_14004B19E
0x14004b1e3  lea     rdi, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids
0x14004b1ea  lea     rcx, stru_1400A7850; lpCriticalSection
0x14004b1f1  call    cs:__imp_LeaveCriticalSection
0x14004b1f8  nop     dword ptr [rax+rax+00h]
0x14004b1fd  lea     rdx, SourceName; "Microsoft Fax"
0x14004b204  xor     ecx, ecx; lpUNCServerName
0x14004b206  call    cs:__imp_RegisterEventSourceW
0x14004b20d  nop     dword ptr [rax+rax+00h]
0x14004b212  mov     cs:hEventLog, rax
0x14004b219  test    rax, rax
0x14004b21c  jnz     loc_14004B2EF
0x14004b222  lea     rcx, stru_1400A7850; lpCriticalSection
0x14004b229  call    cs:__imp_EnterCriticalSection
0x14004b230  nop     dword ptr [rax+rax+00h]
0x14004b235  mov     edi, r15d
0x14004b238  cmp     [rbx+38h], r15d
0x14004b23c  jbe     short loc_14004B25A
0x14004b23e  mov     rcx, cs:?gs_pFaxCategory@@3PEAU_FAX_LOG_CATEGORYW@@EA; _FAX_LOG_CATEGORYW * gs_pFaxCategory
0x14004b245  mov     eax, edi
0x14004b247  add     rax, rax
0x14004b24a  mov     rcx, [rcx+rax*8]; lpMem
0x14004b24e  call    pMemFree
0x14004b253  inc     edi
0x14004b255  cmp     edi, [rbx+38h]
0x14004b258  jb      short loc_14004B23E
0x14004b25a  mov     rcx, cs:?gs_pFaxCategory@@3PEAU_FAX_LOG_CATEGORYW@@EA; lpMem
0x14004b261  call    pMemFree
0x14004b266  lea     rcx, stru_1400A7850; lpCriticalSection
0x14004b26d  mov     cs:?gs_pFaxCategory@@3PEAU_FAX_LOG_CATEGORYW@@EA, r15; _FAX_LOG_CATEGORYW * gs_pFaxCategory
0x14004b274  mov     cs:dword_1400A787C, r15d
0x14004b27b  call    cs:__imp_LeaveCriticalSection
0x14004b282  nop     dword ptr [rax+rax+00h]
0x14004b287  lea     rdi, WPP_575c1ee0a50b364bf8a30468b758ba83_Traceguids
0x14004b28e  mov     rcx, rbx; lpMem
0x14004b291  call    FreeFaxRegistry
0x14004b296  call    cs:__imp_GetLastError
0x14004b29d  nop     dword ptr [rax+rax+00h]
0x14004b2a2  mov     ebx, eax
0x14004b2a4  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b2ab  cmp     rcx, r12
0x14004b2ae  jz      short loc_14004B2D0
0x14004b2b0  test    [rcx+1Ch], r13b
0x14004b2b4  jz      short loc_14004B2D0
0x14004b2b6  cmp     [rcx+19h], r14b
0x14004b2ba  jb      short loc_14004B2D0
0x14004b2bc  mov     rcx, [rcx+10h]
0x14004b2c0  mov     edx, 17h
0x14004b2c5  mov     r9d, eax
0x14004b2c8  mov     r8, rdi
0x14004b2cb  call    WPP_SF_d
0x14004b2d0  mov     eax, ebx
0x14004b2d2  jmp     loc_14004BC3C
0x14004b2d7  lea     rcx, stru_1400A7850; lpCriticalSection
0x14004b2de  call    cs:__imp_LeaveCriticalSection
0x14004b2e5  nop     dword ptr [rax+rax+00h]
0x14004b2ea  jmp     loc_14004B222
0x14004b2ef  mov     esi, 0EA60h
0x14004b2f4  mov     ecx, r14d; unsigned int
0x14004b2f7  mov     r8d, esi; unsigned int
0x14004b2fa  call    ?ReportServiceStatus@@YAHKKK@Z; ReportServiceStatus(ulong,ulong,ulong)
0x14004b2ff  call    EnableProcessPrivilege
0x14004b304  mov     ebx, eax
0x14004b306  test    eax, eax
0x14004b308  jz      short loc_14004B347
0x14004b30a  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b311  cmp     rcx, r12
0x14004b314  jz      loc_14004BBEF
0x14004b31a  test    [rcx+1Ch], r13b
0x14004b31e  jz      loc_14004BBEF
0x14004b324  cmp     [rcx+19h], r14b
0x14004b328  jb      loc_14004BBEF
0x14004b32e  mov     edx, 18h
0x14004b333  mov     rcx, [rcx+10h]
0x14004b337  mov     r9d, eax
0x14004b33a  mov     r8, rdi
0x14004b33d  call    WPP_SF_d
0x14004b342  jmp     loc_14004BBEF
0x14004b347  call    ?InitializeStringTable@@YAHXZ; InitializeStringTable(void)
  ... truncated ...
```
