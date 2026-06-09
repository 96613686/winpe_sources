# UbpmConstraintsCheck

- ea: `0x180008b30`
- end: `0x180009a20`
- name: `UbpmConstraintsCheck`
- size: `3824`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180007000`

## callees

- `0x1800038d0`
- `0x180008b30`
- `0x18000a8f4`
- `0x18000a9ac`
- `0x18000ab30`
- `0x18000ad48`
- `0x180019220`
- `0x18001af64`
- `0x18001b618`
- `0x1800265d0`
- `0x18002aeac`
- `0x18002ba28`
- `0x180030914`
- `0x180032fdc`
- `0x1800346d0`
- `0x180035184`
- `0x180037440`
- `0x180038520`
- `0x180038944`
- `0x180038a20`
- `0x180038af4`
- `0x180040260`

## import_xrefs

- `ntdll!RtlFindLeastSignificantBit` at `0x180008c0d`
- `ntdll!RtlFindLeastSignificantBit` at `0x180009389`
- `ntdll!RtlFindLeastSignificantBit` at `0x180008c0d`
- `ntdll!RtlFindLeastSignificantBit` at `0x180009389`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009332`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800097d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000985b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800098ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009332`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800097d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000985b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800098ca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008ee4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800095b3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008ee4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800095b3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008eb0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009545`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008eb0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009545`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008efc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800095cb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008efc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800095cb`
- `RPCRT4!UuidEqual` at `0x180008fad`
- `RPCRT4!UuidEqual` at `0x18000919c`
- `RPCRT4!UuidEqual` at `0x180008fad`
- `RPCRT4!UuidEqual` at `0x18000919c`
- `RPCRT4!UuidIsNil` at `0x180008f64`
- `RPCRT4!UuidIsNil` at `0x180008f64`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800090b8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800090b8`
- `ext-ms-win-session-winsta-l1-1-0!WinStationQueryInformationW` at `0x180008e42`
- `ext-ms-win-session-winsta-l1-1-0!WinStationQueryInformationW` at `0x180008e42`

## string_xrefs

- `0x180009091`: `NT TASK`

## pseudocode

```c
__int64 __fastcall UbpmConstraintsCheck(UUID **a1, _DWORD *a2, __int16 *a3, unsigned __int16 *a4, _BYTE *a5)
{
  UUID *v7; // rax
  const WCHAR *v9; // rbx
  __int64 v10; // rax
  unsigned __int16 v11; // r15
  unsigned __int16 v12; // si
  unsigned __int16 v13; // dx
  __int64 v14; // r10
  unsigned int v15; // r9d
  unsigned __int16 v16; // r8
  UUID *v17; // rcx
  char v18; // r14
  int v19; // eax
  int v20; // esi
  PVOID *v21; // r10
  unsigned int v22; // r14d
  UUID *v23; // rcx
  UUID *v25; // rbx
  _QWORD *v26; // rcx
  __int16 v27; // r8
  int v28; // edx
  int v29; // ecx
  __int64 *v30; // r11
  _DWORD *v31; // rdx
  _DWORD *v32; // rcx
  __int64 v33; // rdx
  void *v34; // r9
  UUID *v35; // rcx
  __int64 v36; // r9
  unsigned __int64 v37; // rax
  UUID *v38; // rsi
  UUID *v39; // rdx
  UUID *v40; // rcx
  _DWORD *v41; // rcx
  int v42; // eax
  __int64 *v43; // r8
  int *v44; // rcx
  void *v45; // rcx
  UUID *v46; // rcx
  void *v47; // rcx
  char v48; // al
  unsigned __int16 LeastSignificantBit; // cx
  __int64 v50; // rdx
  __int64 *v51; // r11
  _DWORD *v52; // rax
  struct _GUID *v53; // rcx
  UUID *v54; // rdx
  __int64 v55; // rax
  void *v56; // rcx
  __int64 *v57; // r10
  int *v58; // rax
  int v59; // r8d
  int v60; // r11d
  DWORD LastError; // eax
  char v62; // al
  char v63; // al
  const struct _GUID *phkResult; // [rsp+20h] [rbp-51h]
  LPDWORD lpcbData; // [rsp+28h] [rbp-49h]
  const struct _GUID *v66; // [rsp+30h] [rbp-41h]
  BYTE Data[4]; // [rsp+40h] [rbp-31h] BYREF
  DWORD Type; // [rsp+44h] [rbp-2Dh] BYREF
  int v69; // [rsp+48h] [rbp-29h] BYREF
  RPC_STATUS Status; // [rsp+4Ch] [rbp-25h] BYREF
  DWORD cbData; // [rsp+50h] [rbp-21h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-19h] BYREF
  int v73; // [rsp+60h] [rbp-11h] BYREF
  _DWORD *v74; // [rsp+68h] [rbp-9h]
  struct _GUID v75; // [rsp+70h] [rbp-1h] BYREF

  *a3 = 0;
  v75 = 0;
  Status = 0;
  *a5 = 0;
  v7 = *a1;
  v74 = a2;
  v9 = *(const WCHAR **)(*(_QWORD *)v7[1].Data4 + 8LL);
  if ( v9 )
  {
    v10 = -1;
    do
      ++v10;
    while ( v9[v10] );
    if ( (unsigned int)v10 > 8 && CompareStringW(0x7Fu, 1u, v9, 7, L"NT TASK", 7) == 2 )
      v9 += 7;
  }
  v11 = 0;
  v12 = -1;
  v13 = 0;
  v14 = *(_QWORD *)(*a1)[1].Data4;
  v15 = *(_DWORD *)(v14 + 32);
  while ( v13 < v15 )
  {
    v16 = v13 + 1;
    if ( (UUID *)(*(_QWORD *)(v14 + 40) + 40LL * v13) == a1[1] )
    {
      v12 = v13;
      while ( v16 < v15 )
      {
        v17 = a1[8];
        if ( _bittest64((const __int64 *)&v17, v16) )
        {
          v11 = v16;
          goto LABEL_10;
        }
        ++v16;
      }
      break;
    }
    ++v13;
  }
LABEL_10:
  *a4 = v12;
  v18 = v12;
  if ( RtlFindLeastSignificantBit((ULONGLONG)a1[8]) != v12 )
  {
    if ( (*(_BYTE *)(*(_QWORD *)(*a1)[1].Data4 + 16LL) & 2) != 0
      && !(unsigned __int8)UbpmpRemoveQueuedSerialActions(a1[6], 0, 0, v12 + 1) )
    {
      v22 = 4320;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v57 = (__int64 *)a1[1];
        v58 = (int *)v57[4];
        if ( v58 )
          v59 = *v58;
        else
          LOBYTE(v59) = 0;
        WPP_SF_SSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          (unsigned int)WPP_029c709143543b8b7778781675a35e95_Traceguids,
          *(_QWORD *)(*(_QWORD *)(*a1)[1].Data4 + 8LL),
          *v57,
          v59);
      }
      return v22;
    }
    v20 = 1;
    goto LABEL_13;
  }
  v19 = *((_DWORD *)a1 + 14);
  if ( (v19 & 0x10000) == 0 )
  {
    v20 = 0;
LABEL_13:
    v21 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_17;
  }
  v43 = (__int64 *)a1[1];
  v44 = (int *)v43[4];
  if ( v44 && (*v44 & 1) == 0 )
  {
    v22 = 4320;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_SSd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        (unsigned int)WPP_029c709143543b8b7778781675a35e95_Traceguids,
        *(_QWORD *)(*(_QWORD *)(*a1)[1].Data4 + 8LL),
        *v43,
        *v44);
    return v22;
  }
  if ( (v19 & 1) == 0 )
  {
    v22 = UbpmpSignalImmediateTrigger(a1, a5);
    if ( v22 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_SSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          (unsigned int)WPP_029c709143543b8b7778781675a35e95_Traceguids,
          *(_QWORD *)(*(_QWORD *)(*a1)[1].Data4 + 8LL),
          *(_QWORD *)&a1[1]->Data1,
          v22);
      return v22;
    }
    goto LABEL_69;
  }
  v21 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    if ( v44 )
      v60 = *v44;
    else
      LOBYTE(v60) = 0;
    WPP_SF_SSd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      (unsigned int)WPP_029c709143543b8b7778781675a35e95_Traceguids,
      *(_QWORD *)(*(_QWORD *)(*a1)[1].Data4 + 8LL),
      *v43,
      v60);
    v21 = (PVOID *)WPP_GLOBAL_Control;
  }
  v20 = 1;
LABEL_17:
  if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 0x10) != 0 )
  {
    WPP_SF_Sidd(
      (unsigned int)v21[2],
      18,
      (unsigned int)WPP_029c709143543b8b7778781675a35e95_Traceguids,
      *(_QWORD *)(*(_QWORD *)(*a1)[1].Data4 + 8LL),
      (char)a1[8],
      v18,
      v20);
    v21 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !v20 )
  {
    if ( !(unsigned int)UbpmSystemUserOOBEInProgress()
      || UbpmUtilsSearchMultiString(*(PCNZWCH *)(*(_QWORD *)(*a1)[1].Data4 + 8LL), g_OOBEExemptedTasks)
      || !(unsigned int)UbpmSystemMachineOOBEInProgress()
      && !*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*a1)[1].Data4 + 40LL) + 24LL) + 32LL) )
    {
      v21 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_19;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_SSLL(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        (unsigned int)WPP_029c709143543b8b7778781675a35e95_Traceguids,
        *(_QWORD *)(*(_QWORD *)(*a1)[1].Data4 + 8LL),
        *(_QWORD *)&a1[1]->Data1,
        **(_DWORD **)&a1[1][2].Data1,
        *((_DWORD *)a1 + 14));
    UbpmpQueueActionInstance(2, a1);
    v22 = 0;
    *a5 = 1;
LABEL_69:
    ReportTaskEvent(v45, &TASK_INSTANCE_QUEUED, v9, a1[6]);
    return v22;
  }
LABEL_19:
  v22 = 0;
  if ( *(_QWORD *)(*(_QWORD *)(*a1)[1].Data4 + 48LL) )
  {
    v22 = UbpmMaintenanceConstraintsCheck(a1, a5);
    if ( v22 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_SSLL(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          (unsigned int)WPP_029c709143543b8b7778781675a35e95_Traceguids,
          *(_QWORD *)(*(_QWORD *)(*a1)[1].Data4 + 8LL),
          *(_QWORD *)&a1[1]->Data1,
          **(_DWORD **)&a1[1][2].Data1,
          *((_DWORD *)a1 + 14));
      return v22;
    }
    v21 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v20 )
    goto LABEL_21;
  v29 = *((_DWORD *)a1 + 14);
  if ( (v29 & 0x80000) != 0 )
  {
    v51 = (__int64 *)a1[1];
    v52 = (_DWORD *)v51[4];
    if ( v52 )
    {
      if ( (*v52 & 0x140) == 0x100 )
      {
        v22 = 4320;
        if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 2) != 0 )
          WPP_SF_SSLL(
            (unsigned int)v21[2],
            21,
            (unsigned int)WPP_029c709143543b8b7778781675a35e95_Traceguids,
            *(_QWORD *)(*(_QWORD *)(*a1)[1].Data4 + 8LL),
            *v51,
            *v52,
            v29);
        return v22;
      }
    }
  }
  v30 = (__int64 *)a1[1];
  v31 = (_DWORD *)v30[4];
  if ( v31 )
  {
    if ( ((*v31 & 0x40) != 0 || (v29 & 0x100000) != 0)
      && ((_DWORD)a1[7] & 0x80000) != 0
      && (*v31 & 0x40) != 0
      && (*v31 & 0x180) == 0x180
      && !LOBYTE((*a1)[19].Data1) )
    {
      v22 = 4320;
      if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 2) != 0 )
        WPP_SF_SSLL(
          (unsigned int)v21[2],
          22,
          (unsigned int)WPP_029c709143543b8b7778781675a35e95_Traceguids,
          *(_QWORD *)(*(_QWORD *)(*a1)[1].Data4 + 8LL),
          *v30,
          *v31,
          v29);
      return v22;
    }
    if ( (*(_BYTE *)v31 & 2) != 0 )
    {
      if ( UbpmPowerSource() )
      {
        v22 = 4320;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          LastError = GetLastError();
          WPP_SF_SSLd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            LastError,
            (unsigned int)a1[1],
            *(_QWORD *)(*(_QWORD *)(*a1)[1].Data4 + 8LL),
            *(_QWORD *)&a1[1]->Data1,
            **(_DWORD **)&a1[1][2].Data1,
            LastError);
        }
        ReportTaskEvent(v47, &NO_START_ON_BATTERIES, v9);
        return v22;
      }
      v21 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  v32 = *(_DWORD **)&a1[1][2].Data1;
  if ( v32 && (*v32 & 0x20400) != 0 )
  {
    if ( (unsigned __int8)IsWinStationQueryInformationWPresent() )
    {
      v33 = *((unsigned int *)a1 + 9);
      lpcbData = (LPDWORD)&v73;
      v69 = 0;
      v73 = 0;
      if ( !(unsigned __int8)WinStationQueryInformationW(0, v33, 39, &v69, 4) )
      {
        v22 = 4320;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v48 = GetLastError();
          WPP_SF_SSLdd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            24,
            *(_QWORD *)&a1[1][2].Data1,
            *(_QWORD *)(*(_QWORD *)(*a1)[1].Data4 + 8LL),
            *(_QWORD *)&a1[1]->Data1,
            **(_DWORD **)&a1[1][2].Data1,
            *((_DWORD *)a1 + 9),
            v48);
        }
        return v22;
      }
      if ( (**(_DWORD **)&a1[1][2].Data1 & 0x400) != 0 )
      {
        hKey = 0;
        Type = 0;
        cbData = 4;
        *(_DWORD *)Data = 0;
        if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control", 0, 0x20019u, &hKey) )
        {
          if ( !RegQueryValueExW(hKey, L"EmulateRailSession", 0, &Type, Data, &cbData) && Type != 4 )
            *(_DWORD *)Data = 0;
          RegCloseKey(hKey);
        }
        if ( *(_DWORD *)Data || v69 == 5 )
        {
          v22 = 4320;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v62 = GetLastError();
            WPP_SF_SSLdd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              25,
              *(_QWORD *)&a1[1][2].Data1,
              *(_QWORD *)(*(_QWORD *)(*a1)[1].Data4 + 8LL),
              *(_QWORD *)&a1[1]->Data1,
              **(_DWORD **)&a1[1][2].Data1,
              *((_DWORD *)a1 + 9),
              v62);
          }
          ReportTaskEvent(v56, &NO_START_ON_RAIL_SESSION, v9);
          return v22;
        }
      }
      if ( (**(_DWORD **)&a1[1][2].Data1 & 0x20000) != 0 )
      {
        hKey = 0;
        Type = 0;
        cbData = 4;
        *(_DWORD *)Data = 0;
        if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control", 0, 0x20019u, &hKey) )
        {
          if ( !RegQueryValueExW(hKey, L"EmulateWorkerSession", 0, &Type, Data, &cbData) && Type != 4 )
            *(_DWORD *)Data = 0;
          RegCloseKey(hKey);
        }
        if ( *(_DWORD *)Data || v69 == 8 )
        {
          v22 = 4320;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v63 = GetLastError();
            WPP_SF_SSLdd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              26,
              *(_QWORD *)&a1[1][2].Data1,
              *(_QWORD *)(*(_QWORD *)(*a1)[1].Data4 + 8LL),
              *(_QWORD *)&a1[1]->Data1,
              **(_DWORD **)&a1[1][2].Data1,
              *((_DWORD *)a1 + 9),
              v63);
          }
          EventManager::EvtReport(g_hTaskEventManager, &NO_START_ON_WORKER_SESSION, v9, v34, phkResult);
          return v22;
        }
      }
    }
    v21 = (PVOID *)WPP_GLOBAL_Control;
  }
  v35 = *a1;
  v36 = *(_QWORD *)(*a1)[1].Data4;
  v37 = -*(_QWORD *)(v36 + 84);
  if ( !*(_QWORD *)(v36 + 84) )
    v37 = _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0] - *(_QWORD *)(v36 + 92);
  if ( v37 && !*v74 )
  {
    if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 2) != 0 )
      WPP_SF_SSLL(
        (unsigned int)v21[2],
        27,
        (unsigned int)WPP_029c709143543b8b7778781675a35e95_Traceguids,
        *(_QWORD *)(v36 + 8),
        *(_QWORD *)&a1[1]->Data1,
        **(_DWORD **)&a1[1][2].Data1,
        *((_DWORD *)a1 + 14));
    v22 = 1222;
    ReportTaskEvent(v35, &JOB_NO_START_WO_NETWORK, v9, a1[6]);
    return v22;
  }
  if ( (*(_BYTE *)(v36 + 16) & 0x24) != 0 )
    goto LABEL_21;
  if ( UuidIsNil(v35 + 17, &Status) )
    goto LABEL_57;
  v53 = *a1;
  v54 = a1[6];
  v55 = *(_QWORD *)&(*a1)[17].Data1 - *(_QWORD *)&v54->Data1;
  if ( !v55 )
    v55 = *(_QWORD *)v53[17].Data4 - *(_QWORD *)v54->Data4;
  if ( !v55 )
  {
LABEL_57:
    v38 = *(UUID **)&(*a1)[14].Data1;
    while ( v38 != &(*a1)[14] )
    {
      v39 = a1[6];
      v40 = v38;
      v38 = *(UUID **)&v38->Data1;
      v40 = (UUID *)((char *)v40 + 52);
      v75 = *v40;
      if ( !UuidEqual(v40, v39, &Status) )
        goto LABEL_60;
    }
LABEL_21:
    if ( (*(_BYTE *)(*(_QWORD *)(*a1)[1].Data4 + 16LL) & 8) != 0 && !v11 )
    {
      *a3 = 1;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          29,
          WPP_029c709143543b8b7778781675a35e95_Traceguids,
          *(_QWORD *)(*(_QWORD *)(*a1)[1].Data4 + 8LL));
    }
    (*a1)[17] = 0;
    v23 = *a1;
    if ( (*(_BYTE *)(*(_QWORD *)(*a1)[1].Data4 + 16LL) & 2) != 0 )
    {
      v25 = *(UUID **)&v23[14].Data1;
      while ( v25 != &(*a1)[14] )
      {
        v46 = v25;
        v25 = *(UUID **)&v25->Data1;
        if ( UuidEqual((UUID *)((char *)v46 + 52), a1[6], &Status) )
        {
          v22 = 4320;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_SSd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              30,
              (unsigned int)WPP_029c709143543b8b7778781675a35e95_Traceguids,
              *(_QWORD *)(*(_QWORD *)(*a1)[1].Data4 + 8LL),
              *(_QWORD *)&a1[1]->Data1,
              *(_DWORD *)(*(_QWORD *)(*a1)[1].Data4 + 16LL));
          return v22;
        }
      }
      if ( v11 )
      {
        *a3 = v11 + 1;
        (*a1)[17] = *a1[6];
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v27 = *a3;
          v28 = 31;
          goto LABEL_171;
        }
      }
    }
    else if ( v11 )
    {
      v23[17] = *a1[6];
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        LOBYTE(v27) = v11;
        v28 = 32;
LABEL_171:
        WPP_SF_Sd(
          v26[2],
          v28,
          (unsigned int)WPP_029c709143543b8b7778781675a35e95_Traceguids,
          *(_QWORD *)(*(_QWORD *)(*a1)[1].Data4 + 8LL),
          v27);
      }
    }
    return v22;
  }
  v75 = v53[17];
LABEL_60:
  v22 = 4320;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_SSd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      28,
      (unsigned int)WPP_029c709143543b8b7778781675a35e95_Traceguids,
      *(_QWORD *)(*(_QWORD *)(*a1)[1].Data4 + 8LL),
      *(_QWORD *)&a1[1]->Data1,
      *(_DWORD *)(*(_QWORD *)(*a1)[1].Data4 + 16LL));
  v41 = *(_DWORD **)(*a1)[1].Data4;
  v42 = v41[4];
  if ( (v42 & 8) != 0 )
  {
    LeastSignificantBit = RtlFindLeastSignificantBit((ULONGLONG)a1[8]);
    v50 = *(_QWORD *)(*a1)[1].Data4;
    if ( (unsigned int)LeastSignificantBit < *(_DWORD *)(v50 + 32)
      && (UUID *)(*(_QWORD *)(v50 + 40) + 40LL * LeastSignificantBit) == a1[1] )
    {
      UbpmpQueueActionInstance(0, a1);
      *a5 = 1;
      v22 = 0;
      EventManager::EvtReport(g_hTaskEventManager, &NEW_INSTANCE_QUEUED, v9, a1[6], &v75, lpcbData, v66);
    }
  }
  else if ( (v42 & 0x10) != 0 )
  {
    ReportTaskEvent(v41, &NEW_INSTANCE_IGNORED, v9, &v75);
  }
  return v22;
}

```

## disassembly

```asm
0x180008b30  mov     [rsp-8+arg_8], rbx
0x180008b35  push    rbp
0x180008b36  push    rsi
0x180008b37  push    rdi
0x180008b38  push    r12
0x180008b3a  push    r13
0x180008b3c  push    r14
0x180008b3e  push    r15
0x180008b40  lea     rbp, [rsp-1Fh]
0x180008b45  sub     rsp, 90h
0x180008b4c  mov     rax, cs:__security_cookie
0x180008b53  xor     rax, rsp
0x180008b56  mov     [rbp+4Fh+var_40], rax
0x180008b5a  mov     r12, [rbp+4Fh+arg_20]
0x180008b5e  xor     eax, eax
0x180008b60  mov     [r8], ax
0x180008b64  xorps   xmm0, xmm0
0x180008b67  movups  xmmword ptr [rbp+4Fh+var_50.Data1], xmm0
0x180008b6b  mov     [rbp+4Fh+Status], 0
0x180008b72  mov     rdi, rcx
0x180008b75  mov     [r12], al
0x180008b79  mov     r14, r9
0x180008b7c  mov     rax, [rcx]
0x180008b7f  mov     r13, r8
0x180008b82  mov     [rbp+4Fh+var_58], rdx
0x180008b86  mov     rcx, [rax+18h]
0x180008b8a  mov     rbx, [rcx+8]
0x180008b8e  test    rbx, rbx
0x180008b91  jz      short loc_180008BB3
0x180008b93  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180008b9a  nop     word ptr [rax+rax+00h]
0x180008ba0  inc     rax
0x180008ba3  cmp     word ptr [rbx+rax*2], 0
0x180008ba8  jnz     short loc_180008BA0
0x180008baa  cmp     eax, 8
0x180008bad  ja      loc_180009091
0x180008bb3  mov     rax, [rdi]
0x180008bb6  xor     r15d, r15d
0x180008bb9  mov     esi, 0FFFFh
0x180008bbe  xor     edx, edx
0x180008bc0  mov     r10, [rax+18h]
0x180008bc4  mov     r9d, [r10+20h]
0x180008bc8  movzx   eax, dx
0x180008bcb  cmp     eax, r9d
0x180008bce  jnb     short loc_180008C01
0x180008bd0  movzx   eax, dx
0x180008bd3  lea     r8d, [rdx+1]
0x180008bd7  lea     rcx, [rax+rax*4]
0x180008bdb  mov     rax, [r10+28h]
0x180008bdf  lea     rcx, [rax+rcx*8]
0x180008be3  cmp     rcx, [rdi+8]
0x180008be7  jnz     loc_1800095DC
0x180008bed  mov     rcx, [rdi+40h]
0x180008bf1  movzx   esi, dx
0x180008bf4  movzx   eax, r8w
0x180008bf8  cmp     eax, r9d
0x180008bfb  jb      loc_1800095E5
0x180008c01  mov     [r14], si
0x180008c05  mov     rcx, [rdi+40h]; Value
0x180008c09  movzx   r14d, si
0x180008c0d  call    cs:__imp_RtlFindLeastSignificantBit
0x180008c14  nop     dword ptr [rax+rax+00h]
0x180008c19  movsx   ecx, al
0x180008c1c  lea     rdx, WPP_GLOBAL_Control
0x180008c23  cmp     ecx, r14d
0x180008c26  jnz     loc_1800095FD
0x180008c2c  mov     eax, [rdi+38h]
0x180008c2f  bt      eax, 10h
0x180008c33  jb      loc_180009012
0x180008c39  xor     esi, esi
0x180008c3b  mov     r10, cs:WPP_GLOBAL_Control
0x180008c42  jmp     short loc_180008C60
0x180008c44  mov     r10, cs:WPP_GLOBAL_Control
0x180008c4b  cmp     r10, rdx
0x180008c4e  jz      short loc_180008C5B
0x180008c50  test    byte ptr [r10+1Ch], 4
0x180008c55  jnz     loc_1800096AA
0x180008c5b  mov     esi, 1
0x180008c60  cmp     r10, rdx
0x180008c63  jnz     loc_180008D4E
0x180008c69  test    esi, esi
0x180008c6b  jz      loc_180008D97
0x180008c71  mov     rax, [rdi]
0x180008c74  xor     r14d, r14d
0x180008c77  mov     rcx, [rax+18h]
0x180008c7b  cmp     [rcx+30h], r14
0x180008c7f  jnz     loc_1800092E9
0x180008c85  test    esi, esi
0x180008c87  jz      loc_180008DB0
0x180008c8d  mov     rax, [rdi]
0x180008c90  mov     rcx, [rax+18h]
0x180008c94  test    byte ptr [rcx+10h], 8
0x180008c98  jnz     loc_1800090D6
0x180008c9e  lea     rsi, WPP_GLOBAL_Control
0x180008ca5  mov     rax, [rdi]
0x180008ca8  xorps   xmm0, xmm0
0x180008cab  movups  xmmword ptr [rax+110h], xmm0
0x180008cb2  mov     rcx, [rdi]
0x180008cb5  mov     rax, [rcx+18h]
0x180008cb9  test    byte ptr [rax+10h], 2
0x180008cbd  jnz     short loc_180008CF4
0x180008cbf  test    r15w, r15w
0x180008cc3  jnz     loc_1800099CA
0x180008cc9  mov     eax, r14d
0x180008ccc  mov     rcx, [rbp+4Fh+var_40]
0x180008cd0  xor     rcx, rsp; StackCookie
0x180008cd3  call    __security_check_cookie
0x180008cd8  mov     rbx, [rsp+0C0h+arg_8]
0x180008ce0  add     rsp, 90h
0x180008ce7  pop     r15
0x180008ce9  pop     r14
0x180008ceb  pop     r13
0x180008ced  pop     r12
0x180008cef  pop     rdi
0x180008cf0  pop     rsi
0x180008cf1  pop     rbp
0x180008cf2  retn
0x180008cf4  mov     rbx, [rcx+0E0h]
0x180008cfb  mov     rax, [rdi]
0x180008cfe  add     rax, 0E0h
0x180008d04  cmp     rbx, rax
0x180008d07  jnz     loc_18000918A
0x180008d0d  test    r15w, r15w
0x180008d11  jz      short loc_180008CC9
0x180008d13  inc     r15w
0x180008d17  mov     [r13+0], r15w
0x180008d1c  mov     rax, [rdi+30h]
0x180008d20  mov     rcx, [rdi]
0x180008d23  movups  xmm0, xmmword ptr [rax]
0x180008d26  movups  xmmword ptr [rcx+110h], xmm0
0x180008d2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180008d34  cmp     rcx, rsi
0x180008d37  jz      short loc_180008CC9
0x180008d39  test    byte ptr [rcx+1Ch], 4
0x180008d3d  jz      short loc_180008CC9
0x180008d3f  movzx   r8d, word ptr [r13+0]
0x180008d44  mov     edx, 1Fh
0x180008d49  jmp     loc_1800099FB
0x180008d4e  test    byte ptr [r10+1Ch], 10h
0x180008d53  jz      loc_180008C69
0x180008d59  mov     rax, [rdi]
0x180008d5c  lea     r8, WPP_029c709143543b8b7778781675a35e95_Traceguids
0x180008d63  mov     rcx, [r10+10h]
0x180008d67  mov     edx, 12h
0x180008d6c  mov     dword ptr [rsp+0C0h+var_90], esi
0x180008d70  mov     dword ptr [rsp+0C0h+lpcbData], r14d
0x180008d75  mov     r9, [rax+18h]
0x180008d79  mov     rax, [rdi+40h]
0x180008d7d  mov     [rsp+0C0h+phkResult], rax
0x180008d82  mov     r9, [r9+8]
0x180008d86  call    WPP_SF_Sidd
0x180008d8b  mov     r10, cs:WPP_GLOBAL_Control
0x180008d92  jmp     loc_180008C69
0x180008d97  call    ?UbpmSystemUserOOBEInProgress@@YAHXZ; UbpmSystemUserOOBEInProgress(void)
0x180008d9c  test    eax, eax
0x180008d9e  jnz     loc_18000912D
0x180008da4  mov     r10, cs:WPP_GLOBAL_Control
0x180008dab  jmp     loc_180008C71
0x180008db0  mov     ecx, [rdi+38h]
0x180008db3  mov     r8d, ecx
0x180008db6  and     r8d, 80000h
0x180008dbd  jnz     loc_1800093FE
0x180008dc3  mov     r11, [rdi+8]
0x180008dc7  mov     rdx, [r11+20h]
0x180008dcb  test    rdx, rdx
0x180008dce  jz      short loc_180008DF0
0x180008dd0  mov     esi, [rdx]
0x180008dd2  mov     eax, esi
0x180008dd4  and     eax, 40h
0x180008dd7  jnz     loc_180009262
0x180008ddd  bt      ecx, 14h
0x180008de1  jb      loc_180009262
0x180008de7  test    byte ptr [rdx], 2
0x180008dea  jnz     loc_180009249
0x180008df0  mov     rax, [rdi+8]
0x180008df4  mov     rcx, [rax+20h]
0x180008df8  test    rcx, rcx
0x180008dfb  jz      loc_180008F22
0x180008e01  test    dword ptr [rcx], 20400h
0x180008e07  jz      loc_180008F22
0x180008e0d  call    IsWinStationQueryInformationWPresent
0x180008e12  test    al, al
0x180008e14  jz      loc_180008F1B
0x180008e1a  mov     edx, [rdi+24h]
0x180008e1d  lea     rax, [rbp+4Fh+var_60]
0x180008e21  xor     esi, esi
0x180008e23  mov     [rsp+0C0h+lpcbData], rax
0x180008e28  lea     r9, [rbp+4Fh+var_78]
0x180008e2c  mov     dword ptr [rsp+0C0h+phkResult], 4
0x180008e34  mov     r8d, 27h ; '''
0x180008e3a  mov     [rbp+4Fh+var_78], esi
0x180008e3d  xor     ecx, ecx
0x180008e3f  mov     [rbp+4Fh+var_60], esi
0x180008e42  call    cs:__imp_WinStationQueryInformationW
0x180008e49  nop     dword ptr [rax+rax+00h]
0x180008e4e  test    al, al
0x180008e50  jz      loc_18000930B
0x180008e56  mov     rax, [rdi+8]
0x180008e5a  mov     rcx, [rax+20h]
0x180008e5e  test    dword ptr [rcx], 400h
0x180008e64  jnz     loc_180009514
0x180008e6a  mov     rax, [rdi+8]
0x180008e6e  mov     r8, [rax+20h]
0x180008e72  test    dword ptr [r8], 20000h
0x180008e79  jz      loc_180008F1B
0x180008e7f  lea     rax, [rbp+4Fh+hKey]
0x180008e83  mov     [rbp+4Fh+hKey], rsi
0x180008e87  mov     r9d, 20019h; samDesired
0x180008e8d  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180008e92  xor     r8d, r8d; ulOptions
0x180008e95  mov     [rbp+4Fh+Type], esi
0x180008e98  lea     rdx, SubKey; "System\\CurrentControlSet\\Control"
0x180008e9f  mov     [rbp+4Fh+cbData], 4
0x180008ea6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180008ead  mov     dword ptr [rbp+4Fh+Data], esi
0x180008eb0  call    cs:__imp_RegOpenKeyExW
0x180008eb7  nop     dword ptr [rax+rax+00h]
0x180008ebc  test    eax, eax
0x180008ebe  jnz     short loc_180008F08
0x180008ec0  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180008ec4  lea     rax, [rbp+4Fh+cbData]
0x180008ec8  mov     [rsp+0C0h+lpcbData], rax; void *
0x180008ecd  lea     r9, [rbp+4Fh+Type]; lpType
0x180008ed1  lea     rax, [rbp+4Fh+Data]
0x180008ed5  xor     r8d, r8d; lpReserved
0x180008ed8  lea     rdx, aEmulateworkers; "EmulateWorkerSession"
0x180008edf  mov     [rsp+0C0h+phkResult], rax; struct _GUID *
0x180008ee4  call    cs:__imp_RegQueryValueExW
0x180008eeb  nop     dword ptr [rax+rax+00h]
0x180008ef0  test    eax, eax
0x180008ef2  jz      loc_1800098AE
0x180008ef8  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180008efc  call    cs:__imp_RegCloseKey
0x180008f03  nop     dword ptr [rax+rax+00h]
0x180008f08  cmp     dword ptr [rbp+4Fh+Data], esi
0x180008f0b  jnz     loc_180009059
0x180008f11  cmp     [rbp+4Fh+var_78], 8
0x180008f15  jz      loc_180009059
0x180008f1b  mov     r10, cs:WPP_GLOBAL_Control
0x180008f22  mov     rcx, [rdi]
0x180008f25  xorps   xmm0, xmm0
0x180008f28  movq    rax, xmm0
0x180008f2d  mov     r9, [rcx+18h]
0x180008f31  sub     rax, [r9+54h]
0x180008f35  jnz     short loc_180008F45
0x180008f37  psrldq  xmm0, 8
0x180008f3c  movq    rax, xmm0
0x180008f41  sub     rax, [r9+5Ch]
0x180008f45  test    rax, rax
0x180008f48  jnz     loc_18000991D
0x180008f4e  test    byte ptr [r9+10h], 24h
0x180008f53  jnz     loc_180008C8D
0x180008f59  add     rcx, 110h; Uuid
0x180008f60  lea     rdx, [rbp+4Fh+Status]; Status
0x180008f64  call    cs:__imp_UuidIsNil
0x180008f6b  nop     dword ptr [rax+rax+00h]
0x180008f70  test    eax, eax
0x180008f72  jz      loc_180009479
0x180008f78  mov     rax, [rdi]
0x180008f7b  mov     rsi, [rax+0E0h]
0x180008f82  mov     rax, [rdi]
0x180008f85  add     rax, 0E0h
0x180008f8b  cmp     rsi, rax
0x180008f8e  jz      loc_180008C8D
0x180008f94  mov     rdx, [rdi+30h]; Uuid2
0x180008f98  lea     r8, [rbp+4Fh+Status]; Status
0x180008f9c  mov     rcx, rsi
0x180008f9f  mov     rsi, [rsi]
0x180008fa2  add     rcx, 34h ; '4'; Uuid1
0x180008fa6  movups  xmm0, xmmword ptr [rcx]
0x180008fa9  movups  xmmword ptr [rbp+4Fh+var_50.Data1], xmm0
0x180008fad  call    cs:__imp_UuidEqual
0x180008fb4  nop     dword ptr [rax+rax+00h]
0x180008fb9  test    eax, eax
0x180008fbb  jnz     short loc_180008F82
0x180008fbd  mov     r14d, 10E0h
0x180008fc3  mov     rcx, cs:WPP_GLOBAL_Control
0x180008fca  lea     rdx, WPP_GLOBAL_Control
0x180008fd1  cmp     rcx, rdx
0x180008fd4  jz      short loc_180008FE0
0x180008fd6  test    byte ptr [rcx+1Ch], 2
0x180008fda  jnz     loc_180009991
0x180008fe0  mov     rax, [rdi]
0x180008fe3  mov     rcx, [rax+18h]; void *
0x180008fe7  mov     eax, [rcx+10h]
0x180008fea  test    al, 8
0x180008fec  jnz     loc_180009385
0x180008ff2  test    al, 10h
0x180008ff4  jz      loc_180008CC9
0x180008ffa  lea     r9, [rbp+4Fh+var_50]; struct _GUID *
0x180008ffe  mov     r8, rbx; unsigned __int16 *
0x180009001  lea     rdx, NEW_INSTANCE_IGNORED; struct _EVENT_DESCRIPTOR *
0x180009008  call    ?ReportTaskEvent@@YAKPEAXPEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@@Z; ReportTaskEvent(void *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *)
0x18000900d  jmp     loc_180008CC9
0x180009012  mov     r8, [rdi+8]
0x180009016  mov     rcx, [r8+20h]
0x18000901a  test    rcx, rcx
0x18000901d  jnz     loc_180009209
0x180009023  test    al, 1
0x180009025  jnz     loc_180008C44
  ... truncated ...
```
