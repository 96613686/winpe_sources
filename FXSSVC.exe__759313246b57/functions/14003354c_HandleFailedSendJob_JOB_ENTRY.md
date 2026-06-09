# HandleFailedSendJob(_JOB_ENTRY *)

- ea: `0x14003354c`
- end: `0x140034174`
- name: `?HandleFailedSendJob@@YAHPEAU_JOB_ENTRY@@@Z`
- size: `3112`
- prototype: `__int64 __fastcall(struct _JOB_ENTRY *lpMem)`
- caller_count: `1`
- callee_count: `28`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400311d0`

## callees

- `0x140002c73`
- `0x140004c78`
- `0x140004ca8`
- `0x140004e48`
- `0x140004f64`
- `0x140004fe4`
- `0x140023a0c`
- `0x14002cd50`
- `0x14002f49c`
- `0x140030a90`
- `0x14003354c`
- `0x14003437c`
- `0x140034c0c`
- `0x140036164`
- `0x140036b8c`
- `0x140038d44`
- `0x1400399f0`
- `0x14003b04c`
- `0x14003c4ac`
- `0x14003de98`
- `0x140040c14`
- `0x1400522a4`
- `0x140058d78`
- `0x14005900c`
- `0x14006998c`
- `0x140073444`
- `0x140085718`
- `0x140086ec0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140033811`
- `KERNEL32!GetLastError` at `0x1400338d9`
- `KERNEL32!GetLastError` at `0x1400339a9`
- `KERNEL32!GetLastError` at `0x140033a3e`
- `KERNEL32!GetLastError` at `0x140033abf`
- `KERNEL32!GetLastError` at `0x140033c2d`
- `KERNEL32!GetLastError` at `0x140033d16`
- `KERNEL32!GetLastError` at `0x140033e6c`
- `KERNEL32!GetLastError` at `0x140033f54`
- `KERNEL32!GetLastError` at `0x140033fbc`
- `KERNEL32!GetLastError` at `0x14003404d`
- `KERNEL32!GetLastError` at `0x140034119`
- `KERNEL32!GetLastError` at `0x140033811`
- `KERNEL32!GetLastError` at `0x1400338d9`
- `KERNEL32!GetLastError` at `0x1400339a9`
- `KERNEL32!GetLastError` at `0x140033a3e`
- `KERNEL32!GetLastError` at `0x140033abf`
- `KERNEL32!GetLastError` at `0x140033c2d`
- `KERNEL32!GetLastError` at `0x140033d16`
- `KERNEL32!GetLastError` at `0x140033e6c`
- `KERNEL32!GetLastError` at `0x140033f54`
- `KERNEL32!GetLastError` at `0x140033fbc`
- `KERNEL32!GetLastError` at `0x14003404d`
- `KERNEL32!GetLastError` at `0x140034119`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400336d3`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400336d3`
- `KERNEL32!DeleteFileW` at `0x1400340f1`
- `KERNEL32!DeleteFileW` at `0x1400340f1`
- `KERNEL32!EnterCriticalSection` at `0x1400335c5`
- `KERNEL32!EnterCriticalSection` at `0x1400335d8`
- `KERNEL32!EnterCriticalSection` at `0x14003382e`
- `KERNEL32!EnterCriticalSection` at `0x140033d5f`
- `KERNEL32!EnterCriticalSection` at `0x140034080`
- `KERNEL32!EnterCriticalSection` at `0x1400335c5`
- `KERNEL32!EnterCriticalSection` at `0x1400335d8`
- `KERNEL32!EnterCriticalSection` at `0x14003382e`
- `KERNEL32!EnterCriticalSection` at `0x140033d5f`
- `KERNEL32!EnterCriticalSection` at `0x140034080`
- `KERNEL32!LeaveCriticalSection` at `0x140033853`
- `KERNEL32!LeaveCriticalSection` at `0x140033dd4`
- `KERNEL32!LeaveCriticalSection` at `0x140033ffb`
- `KERNEL32!LeaveCriticalSection` at `0x14003400e`
- `KERNEL32!LeaveCriticalSection` at `0x1400340a2`
- `KERNEL32!LeaveCriticalSection` at `0x140033853`
- `KERNEL32!LeaveCriticalSection` at `0x140033dd4`
- `KERNEL32!LeaveCriticalSection` at `0x140033ffb`
- `KERNEL32!LeaveCriticalSection` at `0x14003400e`
- `KERNEL32!LeaveCriticalSection` at `0x1400340a2`
- `KERNEL32!SetEvent` at `0x140033f94`
- `KERNEL32!SetEvent` at `0x140033f94`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  __int64 v29; // rcx
  char v30; // al
  CMapDeviceId *v31; // rcx
  __int64 v32; // rdx
  int QueueEvent; // eax
  int v34; // r9d
  DWORD v35; // eax
  bool v36; // zf
  unsigned int v37; // esi
  __int64 v38; // rcx
  unsigned int v39; // eax
  unsigned int v40; // ebx
  DWORD v41; // eax
  __int64 v42; // r8
  DWORD v43; // eax
  char v44; // al
  DWORD v46; // [rsp+20h] [rbp-288h]
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
      v46 = *(_DWORD *)(v2 + 592);
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 197, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
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
      v30 = GetLastError();
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        198,
        (unsigned int)&WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
        *(_QWORD *)(v2 + 72),
        v30);
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
        v46 = GetLastError();
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 196, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
      }
    }
    IncreaseJobRefCount((struct _JOB_QUEUE *)v2, 1);
    v29 = *(_QWORD *)(v2 + 40);
    *(_QWORD *)(v2 + 1160) = *(_QWORD *)(v29 + 40);
    *(_QWORD *)(v2 + 1168) = *(_QWORD *)(v29 + 48);
  }
  FaxLogSend((const struct _JOB_QUEUE *)v2, v12);
  if ( !v12 )
  {
    EnterCriticalSection(&g_CsOutboundActivityLogging);
    if ( g_hOutboxActivityLogFile == (HANDLE)-1LL )
    {
      v31 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_128;
      }
      v32 = 199;
    }
    else
    {
      if ( (unsigned int)LogOutboundActivity((struct _JOB_QUEUE *)v2) )
        goto LABEL_128;
      v31 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_128;
      }
      v32 = 200;
    }
    WPP_SF_(*((_QWORD *)v31 + 2), v32, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
LABEL_128:
    LeaveCriticalSection(&g_CsOutboundActivityLogging);
  }
  QueueEvent = CreateQueueEvent(2, v2);
  if ( QueueEvent
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LOWORD(v46) = QueueEvent;
    WPP_SF_lh(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      201,
      &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
      *(unsigned int *)(v2 + 16),
      v46);
  }
  *(_DWORD *)(*((_QWORD *)lpMem + 2) + 72LL) = 537919488;
  UpdateDeviceJobsCounter(*((struct _LINE_INFO **)lpMem + 2), 1, -1, v34);
  if ( !(unsigned int)EndJob(lpMem, 1)
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v35 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 202, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, v35);
  }
  v36 = *(_DWORD *)(v2 + 1844) == 512;
  *(_QWORD *)(v2 + 40) = 0;
  if ( v36 )
  {
    v37 = *(_DWORD *)(v2 + 32);
    if ( *(_DWORD *)(v2 + 36) == 2 )
      v38 = *(_QWORD *)(v2 + 584);
    else
      v38 = v2;
    v39 = AllocateAndCopySid(*(PSID *)(v38 + 408));
    v40 = v39;
    if ( v39
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 203, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, v39);
    }
    DecreaseJobRefCount((struct _JOB_QUEUE *)v2, 1, 1, 0);
    if ( !v40 )
    {
      if ( !CreateFaxEvent(0, 0x17u, v37, 0)
        && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v41 = GetLastError();
        WPP_SF_Dll(*((_QWORD *)WPP_GLOBAL_Control + 2), 204, v42, 23, *(_DWORD *)(v2 + 32), v41);
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
      v43 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 205, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, v43);
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
      GetLastError();
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 206, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
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
      v44 = GetLastError();
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        208,
        (unsigned int)&WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
        (unsigned int)FileName,
        v44);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x14003354c  push    rbx
0x14003354e  push    rbp
0x14003354f  push    rsi
0x140033550  push    rdi
0x140033551  push    r12
0x140033553  push    r13
0x140033555  push    r14
0x140033557  push    r15
0x140033559  sub     rsp, 268h
0x140033560  mov     rax, cs:__security_cookie
0x140033567  xor     rax, rsp
0x14003356a  mov     [rsp+2A8h+var_58], rax
0x140033572  mov     r14, rcx
0x140033575  mov     rcx, cs:WPP_GLOBAL_Control
0x14003357c  lea     rbp, WPP_GLOBAL_Control
0x140033583  mov     r13b, 4
0x140033586  cmp     rcx, rbp
0x140033589  jz      short loc_1400335AC
0x14003358b  test    [rcx+1Ch], r13b
0x14003358f  jz      short loc_1400335AC
0x140033591  cmp     byte ptr [rcx+19h], 5
0x140033595  jb      short loc_1400335AC
0x140033597  mov     rcx, [rcx+10h]
0x14003359b  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x1400335a2  mov     edx, 0B9h
0x1400335a7  call    WPP_SF_
0x1400335ac  xor     edx, edx; Val
0x1400335ae  lea     rcx, [rsp+2A8h+FileName]; void *
0x1400335b3  mov     r8d, 208h; Size
0x1400335b9  call    memset_0
0x1400335be  lea     rcx, ?g_CsJob@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400335c5  call    cs:__imp_EnterCriticalSection
0x1400335cc  nop     dword ptr [rax+rax+00h]
0x1400335d1  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400335d8  call    cs:__imp_EnterCriticalSection
0x1400335df  nop     dword ptr [rax+rax+00h]
0x1400335e4  mov     rdi, [r14+450h]
0x1400335eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400335f2  cmp     rcx, rbp
0x1400335f5  jz      short loc_14003361C
0x1400335f7  test    [rcx+1Ch], r13b
0x1400335fb  jz      short loc_14003361C
0x1400335fd  cmp     byte ptr [rcx+19h], 5
0x140033601  jb      short loc_14003361C
0x140033603  mov     r9d, [rdi+20h]
0x140033607  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14003360e  mov     rcx, [rcx+10h]
0x140033612  mov     edx, 0BAh
0x140033617  call    WPP_SF_d
0x14003361c  mov     rax, [rdi+48h]
0x140033620  xor     r12d, r12d
0x140033623  mov     r15d, 7FFFFFFEh
0x140033629  test    rax, rax
0x14003362c  jz      loc_1400336CA
0x140033632  mov     ecx, r15d
0x140033635  lea     rdx, [rsp+2A8h+FileName]
0x14003363a  mov     ebx, 104h
0x14003363f  test    rcx, rcx
0x140033642  jz      short loc_140033663
0x140033644  movzx   r8d, word ptr [rax]
0x140033648  test    r8w, r8w
0x14003364c  jz      short loc_140033663
0x14003364e  mov     [rdx], r8w
0x140033652  add     rax, 2
0x140033656  add     rdx, 2
0x14003365a  dec     rcx
0x14003365d  sub     rbx, 1
0x140033661  jnz     short loc_14003363F
0x140033663  lea     rcx, [rdx-2]
0x140033667  mov     rax, rbx
0x14003366a  neg     rax
0x14003366d  sbb     esi, esi
0x14003366f  not     esi
0x140033671  and     esi, 8007007Ah
0x140033677  test    rbx, rbx
0x14003367a  cmovnz  rcx, rdx
0x14003367e  mov     [rcx], r12w
0x140033682  mov     rcx, [rdi+48h]; lpMem
0x140033686  call    pMemFree
0x14003368b  mov     [rdi+48h], r12
0x14003368f  test    rbx, rbx
0x140033692  jnz     short loc_1400336CA
0x140033694  mov     rcx, cs:WPP_GLOBAL_Control
0x14003369b  cmp     rcx, rbp
0x14003369e  jz      short loc_1400336C4
0x1400336a0  test    [rcx+1Ch], r13b
0x1400336a4  jz      short loc_1400336C4
0x1400336a6  cmp     byte ptr [rcx+19h], 2
0x1400336aa  jb      short loc_1400336C4
0x1400336ac  mov     rcx, [rcx+10h]
0x1400336b0  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x1400336b7  mov     edx, 0BBh
0x1400336bc  mov     r9d, esi
0x1400336bf  call    WPP_SF_d
0x1400336c4  mov     [rsp+2A8h+FileName], r12w
0x1400336ca  lea     rcx, [r14+30h]; lpSystemTimeAsFileTime
0x1400336ce  mov     esi, 1
0x1400336d3  call    cs:__imp_GetSystemTimeAsFileTime
0x1400336da  nop     dword ptr [rax+rax+00h]
0x1400336df  mov     rax, [r14+30h]
0x1400336e3  sub     rax, [r14+28h]
0x1400336e7  mov     ecx, [r14+468h]
0x1400336ee  mov     [r14+38h], rax
0x1400336f2  cmp     ecx, 8
0x1400336f5  jnz     short loc_140033752
0x1400336f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400336fe  cmp     rcx, rbp
0x140033701  jz      short loc_14003372F
0x140033703  test    [rcx+1Ch], r13b
0x140033707  jz      short loc_14003372F
0x140033709  cmp     byte ptr [rcx+19h], 5
0x14003370d  jb      short loc_14003372F
0x14003370f  mov     r9d, [rdi+20h]
0x140033713  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14003371a  mov     rcx, [rcx+10h]
0x14003371e  mov     edx, 0BCh
0x140033723  call    WPP_SF_d
0x140033728  mov     rcx, cs:WPP_GLOBAL_Control
0x14003372f  lea     rbx, WPP_GLOBAL_Control
0x140033736  cmp     [r14+44h], r12d
0x14003373a  jnz     short loc_140033748
0x14003373c  mov     [r14+40h], esi
0x140033740  mov     ebp, r12d
0x140033743  jmp     loc_140033AEB
0x140033748  mov     ebp, esi
0x14003374a  mov     esi, r12d
0x14003374d  jmp     loc_140033AF2
0x140033752  cmp     ecx, 0Bh
0x140033755  jnz     loc_140033AD5
0x14003375b  mov     eax, [r14+46Ch]
0x140033762  cmp     eax, ecx
0x140033764  ja      loc_140033909
0x14003376a  jz      loc_1400339BF
0x140033770  sub     eax, esi
0x140033772  jz      loc_1400339BF
0x140033778  sub     eax, 6
0x14003377b  jz      loc_140033827
0x140033781  sub     eax, esi
0x140033783  jz      loc_1400339BF
0x140033789  sub     eax, esi
0x14003378b  jz      loc_1400339BF
0x140033791  cmp     eax, esi
0x140033793  jnz     loc_14003392A
0x140033799  mov     rax, cs:?g_pFaxPerfCounters@@3PEAU_FAX_PERF_COUNTERS@@EA; _FAX_PERF_COUNTERS * g_pFaxPerfCounters
0x1400337a0  mov     ebp, r12d
0x1400337a3  test    rax, rax
0x1400337a6  jz      loc_140033AE4
0x1400337ac  lock inc dword ptr [rax+24h]
0x1400337b0  mov     rcx, cs:?g_pFaxPerfCounters@@3PEAU_FAX_PERF_COUNTERS@@EA; _FAX_PERF_COUNTERS * g_pFaxPerfCounters
0x1400337b7  lea     rax, [rcx+1Ch]
0x1400337bb  lea     r10, [rcx+20h]
0x1400337bf  mov     [rsp+2A8h+var_280], rax; PVOID
0x1400337c4  lea     r9, [rcx+18h]; PVOID
0x1400337c8  mov     [rsp+2A8h+var_288], r10; PVOID
0x1400337cd  lea     r8, [rcx+14h]; PVOID
0x1400337d1  lea     rdx, [rcx+28h]; PVOID
0x1400337d5  add     rcx, 24h ; '$'; Address
0x1400337d9  call    ?PerfSetFaxOutboundRefValue@@YAKPEAK00000@Z; PerfSetFaxOutboundRefValue(ulong *,ulong *,ulong *,ulong *,ulong *,ulong *)
0x1400337de  test    eax, eax
0x1400337e0  jz      loc_140033AE4
0x1400337e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400337ed  lea     rbx, WPP_GLOBAL_Control
0x1400337f4  cmp     rcx, rbx
0x1400337f7  jz      loc_140033AF2
0x1400337fd  test    [rcx+1Ch], r13b
0x140033801  jz      loc_140033AF2
0x140033807  cmp     byte ptr [rcx+19h], 2
0x14003380b  jb      loc_140033AF2
0x140033811  call    cs:__imp_GetLastError
0x140033818  nop     dword ptr [rax+rax+00h]
0x14003381d  mov     edx, 0C0h
0x140033822  jmp     loc_1400338EA
0x140033827  lea     rcx, ?g_CsLine@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003382e  call    cs:__imp_EnterCriticalSection
0x140033835  nop     dword ptr [rax+rax+00h]
0x14003383a  mov     rdx, [r14+10h]
0x14003383e  test    [rdx+4Ch], r13b
0x140033842  jnz     short loc_14003384C
0x140033844  cmp     [rdx+20h], r12d
0x140033848  cmovz   esi, r12d
0x14003384c  lea     rcx, ?g_CsLine@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140033853  call    cs:__imp_LeaveCriticalSection
0x14003385a  nop     dword ptr [rax+rax+00h]
0x14003385f  mov     rax, cs:?g_pFaxPerfCounters@@3PEAU_FAX_PERF_COUNTERS@@EA; _FAX_PERF_COUNTERS * g_pFaxPerfCounters
0x140033866  mov     ebp, 1
0x14003386b  test    rax, rax
0x14003386e  jz      loc_140033AE4
0x140033874  lock inc dword ptr [rax+24h]
0x140033878  mov     rcx, cs:?g_pFaxPerfCounters@@3PEAU_FAX_PERF_COUNTERS@@EA; _FAX_PERF_COUNTERS * g_pFaxPerfCounters
0x14003387f  lea     rax, [rcx+1Ch]
0x140033883  lea     r10, [rcx+20h]
0x140033887  mov     [rsp+2A8h+var_280], rax; PVOID
0x14003388c  lea     r9, [rcx+18h]; PVOID
0x140033890  mov     [rsp+2A8h+var_288], r10; PVOID
0x140033895  lea     r8, [rcx+14h]; PVOID
0x140033899  lea     rdx, [rcx+28h]; PVOID
0x14003389d  add     rcx, 24h ; '$'; Address
0x1400338a1  call    ?PerfSetFaxOutboundRefValue@@YAKPEAK00000@Z; PerfSetFaxOutboundRefValue(ulong *,ulong *,ulong *,ulong *,ulong *,ulong *)
0x1400338a6  test    eax, eax
0x1400338a8  jz      loc_140033AE4
0x1400338ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400338b5  lea     rbx, WPP_GLOBAL_Control
0x1400338bc  cmp     rcx, rbx
0x1400338bf  jz      loc_140033AF2
0x1400338c5  test    [rcx+1Ch], r13b
0x1400338c9  jz      loc_140033AF2
0x1400338cf  cmp     byte ptr [rcx+19h], 2
0x1400338d3  jb      loc_140033AF2
0x1400338d9  call    cs:__imp_GetLastError
0x1400338e0  nop     dword ptr [rax+rax+00h]
0x1400338e5  mov     edx, 0BDh
0x1400338ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400338f1  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x1400338f8  mov     r9d, eax
0x1400338fb  mov     rcx, [rcx+10h]
0x1400338ff  call    WPP_SF_d
0x140033904  jmp     loc_140033AEB
0x140033909  sub     eax, 0Ch
0x14003390c  jz      loc_140033A54
0x140033912  sub     eax, esi
0x140033914  jz      loc_1400339BF
0x14003391a  sub     eax, esi
0x14003391c  jz      loc_140033799
0x140033922  cmp     eax, esi
0x140033924  jz      loc_1400339BF
0x14003392a  mov     rcx, rdi
0x14003392d  call    CheckForJobRetry
0x140033932  mov     ebp, eax
0x140033934  mov     rax, cs:?g_pFaxPerfCounters@@3PEAU_FAX_PERF_COUNTERS@@EA; _FAX_PERF_COUNTERS * g_pFaxPerfCounters
0x14003393b  test    rax, rax
0x14003393e  jz      loc_140033AE4
0x140033944  lock inc dword ptr [rax+28h]
0x140033948  mov     rcx, cs:?g_pFaxPerfCounters@@3PEAU_FAX_PERF_COUNTERS@@EA; _FAX_PERF_COUNTERS * g_pFaxPerfCounters
0x14003394f  lea     rax, [rcx+1Ch]
0x140033953  lea     r10, [rcx+20h]
0x140033957  mov     [rsp+2A8h+var_280], rax; PVOID
0x14003395c  lea     r9, [rcx+18h]; PVOID
0x140033960  mov     [rsp+2A8h+var_288], r10; PVOID
0x140033965  lea     r8, [rcx+14h]; PVOID
0x140033969  lea     rdx, [rcx+28h]; PVOID
0x14003396d  add     rcx, 24h ; '$'; Address
0x140033971  call    ?PerfSetFaxOutboundRefValue@@YAKPEAK00000@Z; PerfSetFaxOutboundRefValue(ulong *,ulong *,ulong *,ulong *,ulong *,ulong *)
0x140033976  test    eax, eax
0x140033978  jz      loc_140033AE4
0x14003397e  mov     rcx, cs:WPP_GLOBAL_Control
0x140033985  lea     rbx, WPP_GLOBAL_Control
0x14003398c  cmp     rcx, rbx
0x14003398f  jz      loc_140033AF2
0x140033995  test    [rcx+1Ch], r13b
0x140033999  jz      loc_140033AF2
0x14003399f  cmp     byte ptr [rcx+19h], 2
0x1400339a3  jb      loc_140033AF2
0x1400339a9  call    cs:__imp_GetLastError
0x1400339b0  nop     dword ptr [rax+rax+00h]
0x1400339b5  mov     edx, 0C1h
0x1400339ba  jmp     loc_1400338EA
0x1400339bf  mov     rcx, rdi
0x1400339c2  call    CheckForJobRetry
0x1400339c7  mov     ebp, eax
0x1400339c9  mov     rax, cs:?g_pFaxPerfCounters@@3PEAU_FAX_PERF_COUNTERS@@EA; _FAX_PERF_COUNTERS * g_pFaxPerfCounters
0x1400339d0  test    rax, rax
0x1400339d3  jz      loc_140033AE4
0x1400339d9  lock inc dword ptr [rax+24h]
0x1400339dd  mov     rcx, cs:?g_pFaxPerfCounters@@3PEAU_FAX_PERF_COUNTERS@@EA; _FAX_PERF_COUNTERS * g_pFaxPerfCounters
0x1400339e4  lea     rax, [rcx+1Ch]
0x1400339e8  lea     r10, [rcx+20h]
0x1400339ec  mov     [rsp+2A8h+var_280], rax; PVOID
0x1400339f1  lea     r9, [rcx+18h]; PVOID
0x1400339f5  mov     [rsp+2A8h+var_288], r10; PVOID
0x1400339fa  lea     r8, [rcx+14h]; PVOID
0x1400339fe  lea     rdx, [rcx+28h]; PVOID
0x140033a02  add     rcx, 24h ; '$'; Address
0x140033a06  call    ?PerfSetFaxOutboundRefValue@@YAKPEAK00000@Z; PerfSetFaxOutboundRefValue(ulong *,ulong *,ulong *,ulong *,ulong *,ulong *)
0x140033a0b  test    eax, eax
0x140033a0d  jz      loc_140033AE4
0x140033a13  mov     rcx, cs:WPP_GLOBAL_Control
0x140033a1a  lea     rbx, WPP_GLOBAL_Control
0x140033a21  cmp     rcx, rbx
0x140033a24  jz      loc_140033AF2
0x140033a2a  test    [rcx+1Ch], r13b
0x140033a2e  jz      loc_140033AF2
0x140033a34  cmp     byte ptr [rcx+19h], 2
0x140033a38  jb      loc_140033AF2
0x140033a3e  call    cs:__imp_GetLastError
0x140033a45  nop     dword ptr [rax+rax+00h]
0x140033a4a  mov     edx, 0BEh
0x140033a4f  jmp     loc_1400338EA
0x140033a54  mov     rcx, rdi
0x140033a57  call    CheckForJobRetry
0x140033a5c  mov     ebp, eax
0x140033a5e  mov     rax, cs:?g_pFaxPerfCounters@@3PEAU_FAX_PERF_COUNTERS@@EA; _FAX_PERF_COUNTERS * g_pFaxPerfCounters
0x140033a65  test    rax, rax
0x140033a68  jz      short loc_140033AE4
0x140033a6a  lock inc dword ptr [rax+28h]
0x140033a6e  mov     rcx, cs:?g_pFaxPerfCounters@@3PEAU_FAX_PERF_COUNTERS@@EA; _FAX_PERF_COUNTERS * g_pFaxPerfCounters
0x140033a75  lea     rax, [rcx+1Ch]
0x140033a79  lea     r10, [rcx+20h]
0x140033a7d  mov     [rsp+2A8h+var_280], rax; PVOID
0x140033a82  lea     r9, [rcx+18h]; PVOID
0x140033a86  mov     [rsp+2A8h+var_288], r10; PVOID
  ... truncated ...
```
