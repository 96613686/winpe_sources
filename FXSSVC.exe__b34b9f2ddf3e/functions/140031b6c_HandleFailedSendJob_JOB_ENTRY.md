# HandleFailedSendJob(_JOB_ENTRY *)

- ea: `0x140031b6c`
- end: `0x1400326f5`
- name: `?HandleFailedSendJob@@YAHPEAU_JOB_ENTRY@@@Z`
- size: `2953`
- prototype: `__int64 __fastcall(struct _JOB_ENTRY *lpMem)`
- caller_count: `1`
- callee_count: `28`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14002f9f0`

## callees

- `0x140002c43`
- `0x140004b30`
- `0x140004b58`
- `0x140004ce4`
- `0x140004df0`
- `0x140004e68`
- `0x140022a4c`
- `0x14002b8c0`
- `0x14002de58`
- `0x14002f32c`
- `0x140031b6c`
- `0x1400328e8`
- `0x1400330ec`
- `0x140034564`
- `0x140034ef8`
- `0x140036eb4`
- `0x140037b14`
- `0x14003909c`
- `0x14003a3d8`
- `0x14003bc8c`
- `0x14003e7ac`
- `0x14004efe0`
- `0x14005584c`
- `0x140055acc`
- `0x140065dbc`
- `0x14006ef88`
- `0x140080278`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140031e1f`
- `KERNEL32!GetLastError` at `0x140031ed5`
- `KERNEL32!GetLastError` at `0x140031f9f`
- `KERNEL32!GetLastError` at `0x14003202e`
- `KERNEL32!GetLastError` at `0x1400320a9`
- `KERNEL32!GetLastError` at `0x140032211`
- `KERNEL32!GetLastError` at `0x1400322f4`
- `KERNEL32!GetLastError` at `0x140032434`
- `KERNEL32!GetLastError` at `0x140032516`
- `KERNEL32!GetLastError` at `0x140032572`
- `KERNEL32!GetLastError` at `0x1400325ed`
- `KERNEL32!GetLastError` at `0x1400326a1`
- `KERNEL32!GetLastError` at `0x140031e1f`
- `KERNEL32!GetLastError` at `0x140031ed5`
- `KERNEL32!GetLastError` at `0x140031f9f`
- `KERNEL32!GetLastError` at `0x14003202e`
- `KERNEL32!GetLastError` at `0x1400320a9`
- `KERNEL32!GetLastError` at `0x140032211`
- `KERNEL32!GetLastError` at `0x1400322f4`
- `KERNEL32!GetLastError` at `0x140032434`
- `KERNEL32!GetLastError` at `0x140032516`
- `KERNEL32!GetLastError` at `0x140032572`
- `KERNEL32!GetLastError` at `0x1400325ed`
- `KERNEL32!GetLastError` at `0x1400326a1`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140031ce7`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140031ce7`
- `KERNEL32!DeleteFileW` at `0x14003267f`
- `KERNEL32!DeleteFileW` at `0x14003267f`
- `KERNEL32!EnterCriticalSection` at `0x140031be5`
- `KERNEL32!EnterCriticalSection` at `0x140031bf2`
- `KERNEL32!EnterCriticalSection` at `0x140031e36`
- `KERNEL32!EnterCriticalSection` at `0x140032333`
- `KERNEL32!EnterCriticalSection` at `0x14003261a`
- `KERNEL32!EnterCriticalSection` at `0x140031be5`
- `KERNEL32!EnterCriticalSection` at `0x140031bf2`
- `KERNEL32!EnterCriticalSection` at `0x140031e36`
- `KERNEL32!EnterCriticalSection` at `0x140032333`
- `KERNEL32!EnterCriticalSection` at `0x14003261a`
- `KERNEL32!LeaveCriticalSection` at `0x140031e55`
- `KERNEL32!LeaveCriticalSection` at `0x1400323a2`
- `KERNEL32!LeaveCriticalSection` at `0x1400325ab`
- `KERNEL32!LeaveCriticalSection` at `0x1400325b8`
- `KERNEL32!LeaveCriticalSection` at `0x140032636`
- `KERNEL32!LeaveCriticalSection` at `0x140031e55`
- `KERNEL32!LeaveCriticalSection` at `0x1400323a2`
- `KERNEL32!LeaveCriticalSection` at `0x1400325ab`
- `KERNEL32!LeaveCriticalSection` at `0x1400325b8`
- `KERNEL32!LeaveCriticalSection` at `0x140032636`
- `KERNEL32!SetEvent` at `0x140032550`
- `KERNEL32!SetEvent` at `0x140032550`

## pseudocode

```c
__int64 __fastcall HandleFailedSendJob(struct _JOB_ENTRY *lpMem)
{
  __int64 v2; // rdi
  WCHAR *v3; // rax
  __int64 v4; // r15
  __int64 v5; // rcx
  WCHAR *v6; // rdx
  __int64 v7; // rbx
  WCHAR *v8; // rcx
  BOOL v9; // esi
  int v10; // ecx
  CMapDeviceId *v11; // rcx
  int v12; // ebp
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  DWORD LastError; // eax
  __int64 v19; // rdx
  __int64 v20; // rdx
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  __int64 v24; // rcx
  __int64 v25; // rdx
  _WORD *v26; // rcx
  _WORD *v27; // rax
  _WORD *v28; // rcx
  DWORD v29; // eax
  __int64 v30; // rcx
  char v31; // al
  CMapDeviceId *v32; // rcx
  __int64 v33; // rdx
  int QueueEvent; // eax
  int v35; // r9d
  DWORD v36; // eax
  bool v37; // zf
  DWORD v38; // esi
  __int64 v39; // rcx
  unsigned int v40; // eax
  unsigned int v41; // ebx
  DWORD v42; // eax
  __int64 v43; // r8
  DWORD v44; // eax
  DWORD v45; // eax
  char v46; // al
  int v48; // [rsp+20h] [rbp-288h]
  WCHAR FileName[264]; // [rsp+40h] [rbp-268h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 185, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
  }
  memset_0(FileName, 0, 0x208u);
  EnterCriticalSection(&g_CsJob);
  EnterCriticalSection(&g_CsQueue);
  v2 = *((_QWORD *)lpMem + 138);
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      186,
      &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
      *(unsigned int *)(v2 + 32));
  }
  v3 = *(WCHAR **)(v2 + 72);
  v4 = 2147483646;
  if ( v3 )
  {
    v5 = 2147483646;
    v6 = FileName;
    v7 = 260;
    do
    {
      if ( !v5 )
        break;
      if ( !*v3 )
        break;
      *v6++ = *v3++;
      --v5;
      --v7;
    }
    while ( v7 );
    v8 = v6 - 1;
    if ( v7 )
      v8 = v6;
    *v8 = 0;
    pMemFree(*(LPVOID *)(v2 + 72));
    *(_QWORD *)(v2 + 72) = 0;
    if ( !v7 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          187,
          &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
          v7 == 0 ? 0x8007007A : 0);
      }
      FileName[0] = 0;
    }
  }
  v9 = 1;
  GetSystemTimeAsFileTime((LPFILETIME)lpMem + 6);
  v10 = *((_DWORD *)lpMem + 282);
  *((_QWORD *)lpMem + 7) = *((_QWORD *)lpMem + 6) - *((_QWORD *)lpMem + 5);
  if ( v10 == 8 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        188,
        &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
        *(unsigned int *)(v2 + 32));
      v11 = WPP_GLOBAL_Control;
    }
    if ( *((_DWORD *)lpMem + 17) )
    {
      v12 = 1;
      v9 = 0;
      goto LABEL_78;
    }
    *((_DWORD *)lpMem + 16) = 1;
    v12 = 0;
    goto LABEL_77;
  }
  if ( v10 != 11 )
  {
    v12 = 0;
    if ( v10 == 13 )
      v12 = 0;
    goto LABEL_77;
  }
  v13 = *((_DWORD *)lpMem + 283);
  if ( v13 > 0xB )
  {
    v21 = v13 - 12;
    if ( !v21 )
    {
      v12 = CheckForJobRetry(v2);
      if ( !g_pFaxPerfCounters )
        goto LABEL_77;
      _InterlockedIncrement((volatile signed __int32 *)g_pFaxPerfCounters + 10);
      if ( !PerfSetFaxOutboundRefValue(
              (char *)g_pFaxPerfCounters + 36,
              (char *)g_pFaxPerfCounters + 40,
              (char *)g_pFaxPerfCounters + 20,
              (char *)g_pFaxPerfCounters + 24,
              (char *)g_pFaxPerfCounters + 32,
              (char *)g_pFaxPerfCounters + 28) )
        goto LABEL_77;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        v19 = 191;
        goto LABEL_52;
      }
      goto LABEL_78;
    }
    v22 = v21 - 1;
    if ( v22 )
    {
      v23 = v22 - 1;
      if ( !v23 )
        goto LABEL_38;
      if ( v23 != 1 )
      {
LABEL_57:
        v12 = CheckForJobRetry(v2);
        if ( !g_pFaxPerfCounters )
          goto LABEL_77;
        _InterlockedIncrement((volatile signed __int32 *)g_pFaxPerfCounters + 10);
        if ( !PerfSetFaxOutboundRefValue(
                (char *)g_pFaxPerfCounters + 36,
                (char *)g_pFaxPerfCounters + 40,
                (char *)g_pFaxPerfCounters + 20,
                (char *)g_pFaxPerfCounters + 24,
                (char *)g_pFaxPerfCounters + 32,
                (char *)g_pFaxPerfCounters + 28) )
          goto LABEL_77;
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          LastError = GetLastError();
          v19 = 193;
          goto LABEL_52;
        }
        goto LABEL_78;
      }
    }
LABEL_63:
    v12 = CheckForJobRetry(v2);
    if ( !g_pFaxPerfCounters )
      goto LABEL_77;
    _InterlockedIncrement((volatile signed __int32 *)g_pFaxPerfCounters + 9);
    if ( !PerfSetFaxOutboundRefValue(
            (char *)g_pFaxPerfCounters + 36,
            (char *)g_pFaxPerfCounters + 40,
            (char *)g_pFaxPerfCounters + 20,
            (char *)g_pFaxPerfCounters + 24,
            (char *)g_pFaxPerfCounters + 32,
            (char *)g_pFaxPerfCounters + 28) )
      goto LABEL_77;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      v19 = 190;
      goto LABEL_52;
    }
    goto LABEL_78;
  }
  if ( v13 == 11 )
    goto LABEL_63;
  v14 = v13 - 1;
  if ( !v14 )
    goto LABEL_63;
  v15 = v14 - 6;
  if ( v15 )
  {
    v16 = v15 - 1;
    if ( v16 )
    {
      v17 = v16 - 1;
      if ( v17 )
      {
        if ( v17 == 1 )
        {
LABEL_38:
          v12 = 0;
          if ( !g_pFaxPerfCounters )
            goto LABEL_77;
          _InterlockedIncrement((volatile signed __int32 *)g_pFaxPerfCounters + 9);
          if ( !PerfSetFaxOutboundRefValue(
                  (char *)g_pFaxPerfCounters + 36,
                  (char *)g_pFaxPerfCounters + 40,
                  (char *)g_pFaxPerfCounters + 20,
                  (char *)g_pFaxPerfCounters + 24,
                  (char *)g_pFaxPerfCounters + 32,
                  (char *)g_pFaxPerfCounters + 28) )
            goto LABEL_77;
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            LastError = GetLastError();
            v19 = 192;
LABEL_52:
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v19,
              &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
              LastError);
LABEL_77:
            v11 = WPP_GLOBAL_Control;
            goto LABEL_78;
          }
          goto LABEL_78;
        }
        goto LABEL_57;
      }
    }
    goto LABEL_63;
  }
  EnterCriticalSection(&g_CsLine);
  v20 = *((_QWORD *)lpMem + 2);
  if ( (*(_BYTE *)(v20 + 76) & 4) == 0 )
    v9 = *(_DWORD *)(v20 + 32) != 0;
  LeaveCriticalSection(&g_CsLine);
  v12 = 1;
  if ( !g_pFaxPerfCounters )
    goto LABEL_77;
  _InterlockedIncrement((volatile signed __int32 *)g_pFaxPerfCounters + 9);
  if ( !PerfSetFaxOutboundRefValue(
          (char *)g_pFaxPerfCounters + 36,
          (char *)g_pFaxPerfCounters + 40,
          (char *)g_pFaxPerfCounters + 20,
          (char *)g_pFaxPerfCounters + 24,
          (char *)g_pFaxPerfCounters + 32,
          (char *)g_pFaxPerfCounters + 28) )
    goto LABEL_77;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LastError = GetLastError();
    v19 = 189;
    goto LABEL_52;
  }
LABEL_78:
  if ( *((_DWORD *)lpMem + 16) )
  {
    if ( v11 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 4) != 0 && *((_BYTE *)v11 + 25) >= 5u )
      WPP_SF_d(*((_QWORD *)v11 + 2), 194, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, *(unsigned int *)(v2 + 32));
    _JOB_QUEUE::PutStatus((_JOB_QUEUE *)v2, 0x200u);
    if ( !(unsigned int)UpdatePersistentJobStatus((struct _JOB_QUEUE *const)v2)
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        195,
        &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
        *(unsigned int *)(v2 + 1844));
    }
    v12 = 0;
    ++*(_DWORD *)(*(_QWORD *)(v2 + 584) + 380LL);
  }
  v24 = *(_QWORD *)(v2 + 40);
  v25 = 256;
  *(_DWORD *)(v2 + 1688) = *((_DWORD *)lpMem + 283);
  v26 = (_WORD *)(v24 + 1216);
  v27 = (_WORD *)(v2 + 1176);
  do
  {
    if ( !v4 )
      break;
    if ( !*v26 )
      break;
    *v27++ = *v26++;
    --v4;
    --v25;
  }
  while ( v25 );
  v28 = v27 - 1;
  if ( v25 )
    v28 = v27;
  *v28 = 0;
  if ( v12 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        197,
        &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
        *(unsigned int *)(v2 + 32),
        *(_DWORD *)(v2 + 592));
    }
    _JOB_QUEUE::PutStatus((_JOB_QUEUE *)v2, 0x40u);
    if ( v9 )
    {
      RescheduleJobQueueEntry((struct _JOB_QUEUE *)v2);
    }
    else if ( !(unsigned int)CommitQueueEntry((struct _JOB_QUEUE *)v2, 1)
           && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v31 = GetLastError();
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        198,
        (unsigned int)&WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
        *(_QWORD *)(v2 + 72),
        v31);
    }
  }
  else
  {
    if ( !*((_DWORD *)lpMem + 16) )
    {
      if ( !*(_DWORD *)(v2 + 1688) )
      {
        *(_DWORD *)(v2 + 1688) = 12;
        *(_WORD *)(v2 + 1176) = 0;
      }
      if ( !(unsigned int)MarkJobAsExpired((struct _JOB_QUEUE *)v2)
        && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v29 = GetLastError();
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          196,
          &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
          *(unsigned int *)(v2 + 32),
          v29);
      }
    }
    IncreaseJobRefCount((struct _JOB_QUEUE *)v2, 1);
    v30 = *(_QWORD *)(v2 + 40);
    *(_QWORD *)(v2 + 1160) = *(_QWORD *)(v30 + 40);
    *(_QWORD *)(v2 + 1168) = *(_QWORD *)(v30 + 48);
  }
  FaxLogSend((const struct _JOB_QUEUE *)v2, v12);
  if ( !v12 )
  {
    EnterCriticalSection(&g_CsOutboundActivityLogging);
    if ( g_hOutboxActivityLogFile == (HANDLE)-1LL )
    {
      v32 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_128;
      }
      v33 = 199;
    }
    else
    {
      if ( (unsigned int)LogOutboundActivity((struct _JOB_QUEUE *)v2) )
        goto LABEL_128;
      v32 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_128;
      }
      v33 = 200;
    }
    WPP_SF_(*((_QWORD *)v32 + 2), v33, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
LABEL_128:
    LeaveCriticalSection(&g_CsOutboundActivityLogging);
  }
  QueueEvent = CreateQueueEvent(2u, v2);
  if ( QueueEvent
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LOWORD(v48) = QueueEvent;
    WPP_SF_lh(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      201,
      &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
      *(unsigned int *)(v2 + 16),
      v48);
  }
  *(_DWORD *)(*((_QWORD *)lpMem + 2) + 72LL) = 537919488;
  UpdateDeviceJobsCounter(*((struct _LINE_INFO **)lpMem + 2), 1, -1, v35);
  if ( !(unsigned int)EndJob(lpMem, 1)
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v36 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 202, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, v36);
  }
  v37 = *(_DWORD *)(v2 + 1844) == 512;
  *(_QWORD *)(v2 + 40) = 0;
  if ( v37 )
  {
    v38 = *(_DWORD *)(v2 + 32);
    if ( *(_DWORD *)(v2 + 36) == 2 )
      v39 = *(_QWORD *)(v2 + 584);
    else
      v39 = v2;
    v40 = AllocateAndCopySid(*(PSID *)(v39 + 408));
    v41 = v40;
    if ( v40
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 203, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, v40);
    }
    DecreaseJobRefCount((struct _JOB_QUEUE *)v2, 1, 1, 0);
    if ( !v41 )
    {
      if ( !(unsigned int)CreateFaxEvent(0, 0x17u, v38, 0)
        && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v42 = GetLastError();
        WPP_SF_Dll(*((_QWORD *)WPP_GLOBAL_Control + 2), 204, v43, 23, *(_DWORD *)(v2 + 32), v42);
      }
      pMemFree(0);
    }
  }
  if ( !SetEvent(g_hJobQueueEvent) )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v44 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 205, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, v44);
    }
    g_ScanQueueAfterTimeout = 1;
  }
  LeaveCriticalSection(&g_CsQueue);
  LeaveCriticalSection(&g_CsJob);
  if ( !v12 )
  {
    if ( !(unsigned int)SendJobReceipt(0, (struct _JOB_QUEUE *)v2, FileName)
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v45 = GetLastError();
      WPP_SF_dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        206,
        &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
        *(unsigned int *)(v2 + 32),
        v45);
    }
    EnterCriticalSection(&g_CsQueue);
    DecreaseJobRefCount((struct _JOB_QUEUE *)v2, 1, 1, 1);
    LeaveCriticalSection(&g_CsQueue);
  }
  if ( FileName[0] )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 207, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, FileName);
    }
    if ( !DeleteFileW(FileName)
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v46 = GetLastError();
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        208,
        (unsigned int)&WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
        (unsigned int)FileName,
        v46);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x140031b6c  push    rbx
0x140031b6e  push    rbp
0x140031b6f  push    rsi
0x140031b70  push    rdi
0x140031b71  push    r12
0x140031b73  push    r13
0x140031b75  push    r14
0x140031b77  push    r15
0x140031b79  sub     rsp, 268h
0x140031b80  mov     rax, cs:__security_cookie
0x140031b87  xor     rax, rsp
0x140031b8a  mov     [rsp+2A8h+var_58], rax
0x140031b92  mov     r14, rcx
0x140031b95  mov     rcx, cs:WPP_GLOBAL_Control
0x140031b9c  lea     rbp, WPP_GLOBAL_Control
0x140031ba3  mov     r13b, 4
0x140031ba6  cmp     rcx, rbp
0x140031ba9  jz      short loc_140031BCC
0x140031bab  test    [rcx+1Ch], r13b
0x140031baf  jz      short loc_140031BCC
0x140031bb1  cmp     byte ptr [rcx+19h], 5
0x140031bb5  jb      short loc_140031BCC
0x140031bb7  mov     rcx, [rcx+10h]
0x140031bbb  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x140031bc2  mov     edx, 0B9h
0x140031bc7  call    WPP_SF_
0x140031bcc  xor     edx, edx; Val
0x140031bce  lea     rcx, [rsp+2A8h+FileName]; void *
0x140031bd3  mov     r8d, 208h; Size
0x140031bd9  call    memset_0
0x140031bde  lea     rcx, ?g_CsJob@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140031be5  call    cs:__imp_EnterCriticalSection
0x140031beb  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140031bf2  call    cs:__imp_EnterCriticalSection
0x140031bf8  mov     rdi, [r14+450h]
0x140031bff  mov     rcx, cs:WPP_GLOBAL_Control
0x140031c06  cmp     rcx, rbp
0x140031c09  jz      short loc_140031C30
0x140031c0b  test    [rcx+1Ch], r13b
0x140031c0f  jz      short loc_140031C30
0x140031c11  cmp     byte ptr [rcx+19h], 5
0x140031c15  jb      short loc_140031C30
0x140031c17  mov     r9d, [rdi+20h]
0x140031c1b  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x140031c22  mov     rcx, [rcx+10h]
0x140031c26  mov     edx, 0BAh
0x140031c2b  call    WPP_SF_d
0x140031c30  mov     rax, [rdi+48h]
0x140031c34  xor     r12d, r12d
0x140031c37  mov     r15d, 7FFFFFFEh
0x140031c3d  test    rax, rax
0x140031c40  jz      loc_140031CDE
0x140031c46  mov     ecx, r15d
0x140031c49  lea     rdx, [rsp+2A8h+FileName]
0x140031c4e  mov     ebx, 104h
0x140031c53  test    rcx, rcx
0x140031c56  jz      short loc_140031C77
0x140031c58  movzx   r8d, word ptr [rax]
0x140031c5c  test    r8w, r8w
0x140031c60  jz      short loc_140031C77
0x140031c62  mov     [rdx], r8w
0x140031c66  add     rax, 2
0x140031c6a  add     rdx, 2
0x140031c6e  dec     rcx
0x140031c71  sub     rbx, 1
0x140031c75  jnz     short loc_140031C53
0x140031c77  lea     rcx, [rdx-2]
0x140031c7b  mov     rax, rbx
0x140031c7e  neg     rax
0x140031c81  sbb     esi, esi
0x140031c83  not     esi
0x140031c85  and     esi, 8007007Ah
0x140031c8b  test    rbx, rbx
0x140031c8e  cmovnz  rcx, rdx
0x140031c92  mov     [rcx], r12w
0x140031c96  mov     rcx, [rdi+48h]; lpMem
0x140031c9a  call    pMemFree
0x140031c9f  mov     [rdi+48h], r12
0x140031ca3  test    rbx, rbx
0x140031ca6  jnz     short loc_140031CDE
0x140031ca8  mov     rcx, cs:WPP_GLOBAL_Control
0x140031caf  cmp     rcx, rbp
0x140031cb2  jz      short loc_140031CD8
0x140031cb4  test    [rcx+1Ch], r13b
0x140031cb8  jz      short loc_140031CD8
0x140031cba  cmp     byte ptr [rcx+19h], 2
0x140031cbe  jb      short loc_140031CD8
0x140031cc0  mov     rcx, [rcx+10h]
0x140031cc4  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x140031ccb  mov     edx, 0BBh
0x140031cd0  mov     r9d, esi
0x140031cd3  call    WPP_SF_d
0x140031cd8  mov     [rsp+2A8h+FileName], r12w
0x140031cde  lea     rcx, [r14+30h]; lpSystemTimeAsFileTime
0x140031ce2  mov     esi, 1
0x140031ce7  call    cs:__imp_GetSystemTimeAsFileTime
0x140031ced  mov     rax, [r14+30h]
0x140031cf1  sub     rax, [r14+28h]
0x140031cf5  mov     ecx, [r14+468h]
0x140031cfc  mov     [r14+38h], rax
0x140031d00  cmp     ecx, 8
0x140031d03  jnz     short loc_140031D60
0x140031d05  mov     rcx, cs:WPP_GLOBAL_Control
0x140031d0c  cmp     rcx, rbp
0x140031d0f  jz      short loc_140031D3D
0x140031d11  test    [rcx+1Ch], r13b
0x140031d15  jz      short loc_140031D3D
0x140031d17  cmp     byte ptr [rcx+19h], 5
0x140031d1b  jb      short loc_140031D3D
0x140031d1d  mov     r9d, [rdi+20h]
0x140031d21  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x140031d28  mov     rcx, [rcx+10h]
0x140031d2c  mov     edx, 0BCh
0x140031d31  call    WPP_SF_d
0x140031d36  mov     rcx, cs:WPP_GLOBAL_Control
0x140031d3d  lea     rbx, WPP_GLOBAL_Control
0x140031d44  cmp     [r14+44h], r12d
0x140031d48  jnz     short loc_140031D56
0x140031d4a  mov     [r14+40h], esi
0x140031d4e  mov     ebp, r12d
0x140031d51  jmp     loc_1400320CF
0x140031d56  mov     ebp, esi
0x140031d58  mov     esi, r12d
0x140031d5b  jmp     loc_1400320D6
0x140031d60  cmp     ecx, 0Bh
0x140031d63  jnz     loc_1400320B9
0x140031d69  mov     eax, [r14+46Ch]
0x140031d70  cmp     eax, ecx
0x140031d72  ja      loc_140031EFF
0x140031d78  jz      loc_140031FAF
0x140031d7e  sub     eax, esi
0x140031d80  jz      loc_140031FAF
0x140031d86  sub     eax, 6
0x140031d89  jz      loc_140031E2F
0x140031d8f  sub     eax, esi
0x140031d91  jz      loc_140031FAF
0x140031d97  sub     eax, esi
0x140031d99  jz      loc_140031FAF
0x140031d9f  cmp     eax, esi
0x140031da1  jnz     loc_140031F20
0x140031da7  mov     rax, cs:?g_pFaxPerfCounters@@3PEAU_FAX_PERF_COUNTERS@@EA; _FAX_PERF_COUNTERS * g_pFaxPerfCounters
0x140031dae  mov     ebp, r12d
0x140031db1  test    rax, rax
0x140031db4  jz      loc_1400320C8
0x140031dba  lock inc dword ptr [rax+24h]
0x140031dbe  mov     rcx, cs:?g_pFaxPerfCounters@@3PEAU_FAX_PERF_COUNTERS@@EA; _FAX_PERF_COUNTERS * g_pFaxPerfCounters
0x140031dc5  lea     rax, [rcx+1Ch]
0x140031dc9  lea     r10, [rcx+20h]
0x140031dcd  mov     [rsp+2A8h+var_280], rax; PVOID
0x140031dd2  lea     r9, [rcx+18h]; PVOID
0x140031dd6  mov     [rsp+2A8h+var_288], r10; PVOID
0x140031ddb  lea     r8, [rcx+14h]; PVOID
0x140031ddf  lea     rdx, [rcx+28h]; PVOID
0x140031de3  add     rcx, 24h ; '$'; Address
0x140031de7  call    ?PerfSetFaxOutboundRefValue@@YAKPEAK00000@Z; PerfSetFaxOutboundRefValue(ulong *,ulong *,ulong *,ulong *,ulong *,ulong *)
0x140031dec  test    eax, eax
0x140031dee  jz      loc_1400320C8
0x140031df4  mov     rcx, cs:WPP_GLOBAL_Control
0x140031dfb  lea     rbx, WPP_GLOBAL_Control
0x140031e02  cmp     rcx, rbx
0x140031e05  jz      loc_1400320D6
0x140031e0b  test    [rcx+1Ch], r13b
0x140031e0f  jz      loc_1400320D6
0x140031e15  cmp     byte ptr [rcx+19h], 2
0x140031e19  jb      loc_1400320D6
0x140031e1f  call    cs:__imp_GetLastError
0x140031e25  mov     edx, 0C0h
0x140031e2a  jmp     loc_140031EE0
0x140031e2f  lea     rcx, ?g_CsLine@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140031e36  call    cs:__imp_EnterCriticalSection
0x140031e3c  mov     rdx, [r14+10h]
0x140031e40  test    [rdx+4Ch], r13b
0x140031e44  jnz     short loc_140031E4E
0x140031e46  cmp     [rdx+20h], r12d
0x140031e4a  cmovz   esi, r12d
0x140031e4e  lea     rcx, ?g_CsLine@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140031e55  call    cs:__imp_LeaveCriticalSection
0x140031e5b  mov     rax, cs:?g_pFaxPerfCounters@@3PEAU_FAX_PERF_COUNTERS@@EA; _FAX_PERF_COUNTERS * g_pFaxPerfCounters
0x140031e62  mov     ebp, 1
0x140031e67  test    rax, rax
0x140031e6a  jz      loc_1400320C8
0x140031e70  lock inc dword ptr [rax+24h]
0x140031e74  mov     rcx, cs:?g_pFaxPerfCounters@@3PEAU_FAX_PERF_COUNTERS@@EA; _FAX_PERF_COUNTERS * g_pFaxPerfCounters
0x140031e7b  lea     rax, [rcx+1Ch]
0x140031e7f  lea     r10, [rcx+20h]
0x140031e83  mov     [rsp+2A8h+var_280], rax; PVOID
0x140031e88  lea     r9, [rcx+18h]; PVOID
0x140031e8c  mov     [rsp+2A8h+var_288], r10; PVOID
0x140031e91  lea     r8, [rcx+14h]; PVOID
0x140031e95  lea     rdx, [rcx+28h]; PVOID
0x140031e99  add     rcx, 24h ; '$'; Address
0x140031e9d  call    ?PerfSetFaxOutboundRefValue@@YAKPEAK00000@Z; PerfSetFaxOutboundRefValue(ulong *,ulong *,ulong *,ulong *,ulong *,ulong *)
0x140031ea2  test    eax, eax
0x140031ea4  jz      loc_1400320C8
0x140031eaa  mov     rcx, cs:WPP_GLOBAL_Control
0x140031eb1  lea     rbx, WPP_GLOBAL_Control
0x140031eb8  cmp     rcx, rbx
0x140031ebb  jz      loc_1400320D6
0x140031ec1  test    [rcx+1Ch], r13b
0x140031ec5  jz      loc_1400320D6
0x140031ecb  cmp     byte ptr [rcx+19h], 2
0x140031ecf  jb      loc_1400320D6
0x140031ed5  call    cs:__imp_GetLastError
0x140031edb  mov     edx, 0BDh
0x140031ee0  mov     rcx, cs:WPP_GLOBAL_Control
0x140031ee7  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x140031eee  mov     r9d, eax
0x140031ef1  mov     rcx, [rcx+10h]
0x140031ef5  call    WPP_SF_d
0x140031efa  jmp     loc_1400320CF
0x140031eff  sub     eax, 0Ch
0x140031f02  jz      loc_14003203E
0x140031f08  sub     eax, esi
0x140031f0a  jz      loc_140031FAF
0x140031f10  sub     eax, esi
0x140031f12  jz      loc_140031DA7
0x140031f18  cmp     eax, esi
0x140031f1a  jz      loc_140031FAF
0x140031f20  mov     rcx, rdi
0x140031f23  call    CheckForJobRetry
0x140031f28  mov     ebp, eax
0x140031f2a  mov     rax, cs:?g_pFaxPerfCounters@@3PEAU_FAX_PERF_COUNTERS@@EA; _FAX_PERF_COUNTERS * g_pFaxPerfCounters
0x140031f31  test    rax, rax
0x140031f34  jz      loc_1400320C8
0x140031f3a  lock inc dword ptr [rax+28h]
0x140031f3e  mov     rcx, cs:?g_pFaxPerfCounters@@3PEAU_FAX_PERF_COUNTERS@@EA; _FAX_PERF_COUNTERS * g_pFaxPerfCounters
0x140031f45  lea     rax, [rcx+1Ch]
0x140031f49  lea     r10, [rcx+20h]
0x140031f4d  mov     [rsp+2A8h+var_280], rax; PVOID
0x140031f52  lea     r9, [rcx+18h]; PVOID
0x140031f56  mov     [rsp+2A8h+var_288], r10; PVOID
0x140031f5b  lea     r8, [rcx+14h]; PVOID
0x140031f5f  lea     rdx, [rcx+28h]; PVOID
0x140031f63  add     rcx, 24h ; '$'; Address
0x140031f67  call    ?PerfSetFaxOutboundRefValue@@YAKPEAK00000@Z; PerfSetFaxOutboundRefValue(ulong *,ulong *,ulong *,ulong *,ulong *,ulong *)
0x140031f6c  test    eax, eax
0x140031f6e  jz      loc_1400320C8
0x140031f74  mov     rcx, cs:WPP_GLOBAL_Control
0x140031f7b  lea     rbx, WPP_GLOBAL_Control
0x140031f82  cmp     rcx, rbx
0x140031f85  jz      loc_1400320D6
0x140031f8b  test    [rcx+1Ch], r13b
0x140031f8f  jz      loc_1400320D6
0x140031f95  cmp     byte ptr [rcx+19h], 2
0x140031f99  jb      loc_1400320D6
0x140031f9f  call    cs:__imp_GetLastError
0x140031fa5  mov     edx, 0C1h
0x140031faa  jmp     loc_140031EE0
0x140031faf  mov     rcx, rdi
0x140031fb2  call    CheckForJobRetry
0x140031fb7  mov     ebp, eax
0x140031fb9  mov     rax, cs:?g_pFaxPerfCounters@@3PEAU_FAX_PERF_COUNTERS@@EA; _FAX_PERF_COUNTERS * g_pFaxPerfCounters
0x140031fc0  test    rax, rax
0x140031fc3  jz      loc_1400320C8
0x140031fc9  lock inc dword ptr [rax+24h]
0x140031fcd  mov     rcx, cs:?g_pFaxPerfCounters@@3PEAU_FAX_PERF_COUNTERS@@EA; _FAX_PERF_COUNTERS * g_pFaxPerfCounters
0x140031fd4  lea     rax, [rcx+1Ch]
0x140031fd8  lea     r10, [rcx+20h]
0x140031fdc  mov     [rsp+2A8h+var_280], rax; PVOID
0x140031fe1  lea     r9, [rcx+18h]; PVOID
0x140031fe5  mov     [rsp+2A8h+var_288], r10; PVOID
0x140031fea  lea     r8, [rcx+14h]; PVOID
0x140031fee  lea     rdx, [rcx+28h]; PVOID
0x140031ff2  add     rcx, 24h ; '$'; Address
0x140031ff6  call    ?PerfSetFaxOutboundRefValue@@YAKPEAK00000@Z; PerfSetFaxOutboundRefValue(ulong *,ulong *,ulong *,ulong *,ulong *,ulong *)
0x140031ffb  test    eax, eax
0x140031ffd  jz      loc_1400320C8
0x140032003  mov     rcx, cs:WPP_GLOBAL_Control
0x14003200a  lea     rbx, WPP_GLOBAL_Control
0x140032011  cmp     rcx, rbx
0x140032014  jz      loc_1400320D6
0x14003201a  test    [rcx+1Ch], r13b
0x14003201e  jz      loc_1400320D6
0x140032024  cmp     byte ptr [rcx+19h], 2
0x140032028  jb      loc_1400320D6
0x14003202e  call    cs:__imp_GetLastError
0x140032034  mov     edx, 0BEh
0x140032039  jmp     loc_140031EE0
0x14003203e  mov     rcx, rdi
0x140032041  call    CheckForJobRetry
0x140032046  mov     ebp, eax
0x140032048  mov     rax, cs:?g_pFaxPerfCounters@@3PEAU_FAX_PERF_COUNTERS@@EA; _FAX_PERF_COUNTERS * g_pFaxPerfCounters
0x14003204f  test    rax, rax
0x140032052  jz      short loc_1400320C8
0x140032054  lock inc dword ptr [rax+28h]
0x140032058  mov     rcx, cs:?g_pFaxPerfCounters@@3PEAU_FAX_PERF_COUNTERS@@EA; _FAX_PERF_COUNTERS * g_pFaxPerfCounters
0x14003205f  lea     rax, [rcx+1Ch]
0x140032063  lea     r10, [rcx+20h]
0x140032067  mov     [rsp+2A8h+var_280], rax; PVOID
0x14003206c  lea     r9, [rcx+18h]; PVOID
0x140032070  mov     [rsp+2A8h+var_288], r10; PVOID
0x140032075  lea     r8, [rcx+14h]; PVOID
0x140032079  lea     rdx, [rcx+28h]; PVOID
0x14003207d  add     rcx, 24h ; '$'; Address
0x140032081  call    ?PerfSetFaxOutboundRefValue@@YAKPEAK00000@Z; PerfSetFaxOutboundRefValue(ulong *,ulong *,ulong *,ulong *,ulong *,ulong *)
0x140032086  test    eax, eax
0x140032088  jz      short loc_1400320C8
0x14003208a  mov     rcx, cs:WPP_GLOBAL_Control
0x140032091  lea     rbx, WPP_GLOBAL_Control
0x140032098  cmp     rcx, rbx
  ... truncated ...
```
