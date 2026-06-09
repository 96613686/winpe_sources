# JobQueueThread(void *)

- ea: `0x140039350`
- end: `0x140039ea7`
- name: `?JobQueueThread@@YAKPEAX@Z`
- size: `2903`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `24`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x140004e68`
- `0x140022a4c`
- `0x14003392c`
- `0x140033acc`
- `0x1400354bc`
- `0x1400391f4`
- `0x140039350`
- `0x14003a3d8`
- `0x14003bf04`
- `0x14003df00`
- `0x14003e14c`
- `0x14003e488`
- `0x14004a8e0`
- `0x14004eedc`
- `0x140055acc`
- `0x140065df8`
- `0x140070684`
- `0x1400708c4`
- `0x140073750`
- `0x140073aa0`
- `0x140081866`
- `0x1400818b0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140039408`
- `ADVAPI32!RegCloseKey` at `0x140039408`
- `KERNEL32!ReleaseSemaphore` at `0x140039c3b`
- `KERNEL32!ReleaseSemaphore` at `0x140039e3e`
- `KERNEL32!ReleaseSemaphore` at `0x140039c3b`
- `KERNEL32!ReleaseSemaphore` at `0x140039e3e`
- `KERNEL32!GetLastError` at `0x140039484`
- `KERNEL32!GetLastError` at `0x14003954b`
- `KERNEL32!GetLastError` at `0x1400395d1`
- `KERNEL32!GetLastError` at `0x14003963b`
- `KERNEL32!GetLastError` at `0x1400396d9`
- `KERNEL32!GetLastError` at `0x1400398dd`
- `KERNEL32!GetLastError` at `0x1400399a5`
- `KERNEL32!GetLastError` at `0x140039a38`
- `KERNEL32!GetLastError` at `0x140039b0f`
- `KERNEL32!GetLastError` at `0x140039be0`
- `KERNEL32!GetLastError` at `0x140039c5d`
- `KERNEL32!GetLastError` at `0x140039d58`
- `KERNEL32!GetLastError` at `0x140039e02`
- `KERNEL32!GetLastError` at `0x140039e60`
- `KERNEL32!GetLastError` at `0x140039484`
- `KERNEL32!GetLastError` at `0x14003954b`
- `KERNEL32!GetLastError` at `0x1400395d1`
- `KERNEL32!GetLastError` at `0x14003963b`
- `KERNEL32!GetLastError` at `0x1400396d9`
- `KERNEL32!GetLastError` at `0x1400398dd`
- `KERNEL32!GetLastError` at `0x1400399a5`
- `KERNEL32!GetLastError` at `0x140039a38`
- `KERNEL32!GetLastError` at `0x140039b0f`
- `KERNEL32!GetLastError` at `0x140039be0`
- `KERNEL32!GetLastError` at `0x140039c5d`
- `KERNEL32!GetLastError` at `0x140039d58`
- `KERNEL32!GetLastError` at `0x140039e02`
- `KERNEL32!GetLastError` at `0x140039e60`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400397b7`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400397b7`
- `KERNEL32!EnterCriticalSection` at `0x140039450`
- `KERNEL32!EnterCriticalSection` at `0x14003945d`
- `KERNEL32!EnterCriticalSection` at `0x140039705`
- `KERNEL32!EnterCriticalSection` at `0x140039786`
- `KERNEL32!EnterCriticalSection` at `0x1400397a0`
- `KERNEL32!EnterCriticalSection` at `0x1400397ad`
- `KERNEL32!EnterCriticalSection` at `0x140039849`
- `KERNEL32!EnterCriticalSection` at `0x140039450`
- `KERNEL32!EnterCriticalSection` at `0x14003945d`
- `KERNEL32!EnterCriticalSection` at `0x140039705`
- `KERNEL32!EnterCriticalSection` at `0x140039786`
- `KERNEL32!EnterCriticalSection` at `0x1400397a0`
- `KERNEL32!EnterCriticalSection` at `0x1400397ad`
- `KERNEL32!EnterCriticalSection` at `0x140039849`
- `KERNEL32!LeaveCriticalSection` at `0x1400394c4`
- `KERNEL32!LeaveCriticalSection` at `0x1400394d1`
- `KERNEL32!LeaveCriticalSection` at `0x14003971b`
- `KERNEL32!LeaveCriticalSection` at `0x14003972d`
- `KERNEL32!LeaveCriticalSection` at `0x140039793`
- `KERNEL32!LeaveCriticalSection` at `0x140039860`
- `KERNEL32!LeaveCriticalSection` at `0x140039d84`
- `KERNEL32!LeaveCriticalSection` at `0x140039d91`
- `KERNEL32!LeaveCriticalSection` at `0x1400394c4`
- `KERNEL32!LeaveCriticalSection` at `0x1400394d1`
- `KERNEL32!LeaveCriticalSection` at `0x14003971b`
- `KERNEL32!LeaveCriticalSection` at `0x14003972d`
- `KERNEL32!LeaveCriticalSection` at `0x140039793`
- `KERNEL32!LeaveCriticalSection` at `0x140039860`
- `KERNEL32!LeaveCriticalSection` at `0x140039d84`
- `KERNEL32!LeaveCriticalSection` at `0x140039d91`
- `KERNEL32!WaitForMultipleObjects` at `0x14003960c`
- `KERNEL32!WaitForMultipleObjects` at `0x14003960c`
- `KERNEL32!GetSystemTime` at `0x14003995e`
- `KERNEL32!GetSystemTime` at `0x14003995e`
- `KERNEL32!SystemTimeToFileTime` at `0x140039a03`
- `KERNEL32!SystemTimeToFileTime` at `0x140039a03`

## pseudocode

```c
__int64 __fastcall JobQueueThread(void *a1)
{
  HKEY v1; // rax
  HKEY v2; // rbx
  DWORD LastError; // eax
  DWORD v4; // eax
  CMapDeviceId *v5; // rcx
  DWORD v6; // eax
  DWORD v7; // eax
  CMapDeviceId *v8; // rcx
  DWORD v9; // eax
  CMapDeviceId *v10; // rcx
  DWORD v11; // eax
  struct _LIST_ENTRY *Flink; // r12
  CMapDeviceId *v13; // rcx
  struct _LIST_ENTRY *v14; // r14
  struct _LIST_ENTRY *v15; // r15
  unsigned int *v16; // rdi
  struct _LIST_ENTRY *v17; // r13
  struct _FILETIME *v18; // rsi
  int Flink_high; // r8d
  int v20; // edx
  int v21; // ebx
  unsigned __int64 v22; // rax
  DWORD v23; // eax
  DWORD v24; // eax
  __int64 v25; // rdx
  struct _LIST_ENTRY *Blink; // rax
  struct _LIST_ENTRY *v27; // rcx
  unsigned int **v28; // rax
  CMapDeviceId *v29; // rcx
  struct _LINE_INFO *TapiLineForFaxOperation; // rbx
  DWORD v31; // eax
  char v32; // al
  DWORD v33; // eax
  __int128 *v34; // rbx
  __int128 *v35; // rdx
  __int64 v36; // rdi
  __int128 **v37; // rax
  int QueueEvent; // eax
  DWORD v39; // eax
  __int64 v40; // rdx
  DWORD v41; // eax
  DWORD v42; // eax
  __int64 v44; // [rsp+20h] [rbp-59h]
  DWORD dwMilliseconds; // [rsp+30h] [rbp-49h] BYREF
  __int128 v46; // [rsp+38h] [rbp-41h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp-31h] BYREF
  struct _SYSTEMTIME Buf1; // [rsp+50h] [rbp-29h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+60h] [rbp-19h] BYREF
  HANDLE Handles[2]; // [rsp+70h] [rbp-9h] BYREF
  HANDLE v51; // [rsp+80h] [rbp+7h]

  SystemTimeAsFileTime = 0;
  v51 = 0;
  *(_OWORD *)Handles = 0;
  dwMilliseconds = 600;
  v46 = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 151, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids);
  }
  v1 = (HKEY)OpenRegistryKey(-2147483646, L"Software\\Microsoft\\Fax", 0, 131099);
  v2 = v1;
  if ( v1 )
  {
    GetRegistryDwordDefault(v1, L"JobQueueTimeout", (BYTE *)&dwMilliseconds);
    RegCloseKey(v2);
  }
  dwMilliseconds *= 1000;
  *((_QWORD *)&v46 + 1) = &v46;
  *(_QWORD *)&v46 = &v46;
  Handles[0] = g_hQueueTimer;
  Handles[1] = g_hJobQueueEvent;
  v51 = g_hServiceShutDownEvent;
  EnterCriticalSection(&g_CsJob);
  EnterCriticalSection(&g_CsQueue);
  if ( !(unsigned int)RestoreFaxQueue() )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 152, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, LastError);
    }
    FaxLog(1, 1, 0, 3221257507LL, v44);
  }
  LeaveCriticalSection(&g_CsQueue);
  LeaveCriticalSection(&g_CsJob);
  if ( !g_bDelaySuicideAttempt && (unsigned int)ServiceShouldDie() )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 153, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids);
    }
    if ( (unsigned int)WaitForServiceRPCServer() )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 155, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids);
      }
      if ( !(unsigned int)StopService(v5, L"Fax", 1)
        && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v6 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 156, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v6);
      }
    }
    else if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v4 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 154, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v4);
    }
  }
  while ( 1 )
  {
    v7 = WaitForMultipleObjects(3u, Handles, 0, dwMilliseconds);
    if ( v7 == -1 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_57;
      }
      v9 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 157, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v9);
      goto LABEL_56;
    }
    if ( v7 == 258 )
    {
      if ( (unsigned int)ServiceShouldDie() )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 158, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids);
        }
        if ( !(unsigned int)StopService(v10, L"Fax", 1)
          && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v11 = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 159, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v11);
        }
      }
      EnterCriticalSection(&g_CsQueue);
      if ( !g_ScanQueueAfterTimeout )
      {
        LeaveCriticalSection(&g_CsQueue);
        continue;
      }
      g_ScanQueueAfterTimeout = 0;
      LeaveCriticalSection(&g_CsQueue);
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
      {
        goto LABEL_57;
      }
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 160, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids);
      goto LABEL_56;
    }
    if ( v7 == 2 )
      break;
LABEL_56:
    v8 = WPP_GLOBAL_Control;
LABEL_57:
    if ( g_bServiceIsDown == 1 )
    {
      if ( v8 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 4) != 0 && *((_BYTE *)v8 + 25) >= 3u )
      {
        v40 = 162;
LABEL_158:
        WPP_SF_(*((_QWORD *)v8 + 2), v40, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids);
        goto LABEL_159;
      }
      goto LABEL_159;
    }
    EnterCriticalSection(&g_CsConfig);
    LeaveCriticalSection(&g_CsConfig);
    EnterCriticalSection(&g_CsJob);
    EnterCriticalSection(&g_CsQueue);
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    Flink = g_QueueListHead.Flink;
    if ( g_QueueListHead.Flink == &g_QueueListHead )
      goto LABEL_137;
    v13 = WPP_GLOBAL_Control;
    while ( g_bServiceIsDown != 1 )
    {
      v14 = Flink;
      v15 = Flink;
      v16 = (unsigned int *)Flink;
      v17 = Flink;
      v18 = (struct _FILETIME *)Flink;
      Flink = Flink->Flink;
      Flink_high = HIDWORD(v14[115].Flink);
      if ( (Flink_high & 0x10) != 0 || HIDWORD(v14[2].Flink) == 4 )
        goto LABEL_80;
      v20 = HIDWORD(v14[2].Flink) == 2 ? HIDWORD(v14[36].Blink[115].Flink) : HIDWORD(v14[115].Flink);
      if ( v20 == 4 || (Flink_high & 0x80u) != 0 )
        goto LABEL_80;
      EnterCriticalSection(&g_CsConfig);
      v21 = *((_DWORD *)g_pFaxConfig + 2);
      LeaveCriticalSection(&g_CsConfig);
      if ( (v21 & 4) != 0 || (v16[461] & 0x782) != 0 || v16[9] == 32 )
        goto LABEL_117;
      v22 = (unsigned __int64)v18[3];
      if ( v16[9] == 8 )
      {
        if ( v22 && *(_QWORD *)&SystemTimeAsFileTime < v22 )
          goto LABEL_117;
        if ( !(unsigned int)StartRoutingJob((struct _JOB_QUEUE *)v16) )
        {
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_80;
          }
          v23 = GetLastError();
          WPP_SF_dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            167,
            &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
            v16[8],
            v23);
          goto LABEL_117;
        }
      }
      else
      {
        if ( v22 && *(_QWORD *)&SystemTimeAsFileTime < v22 )
          goto LABEL_117;
        if ( HIDWORD(v17[5].Flink) != 2 )
          goto LABEL_98;
        SystemTime = 0;
        Buf1 = 0;
        GetSystemTime(&SystemTime);
        Buf1 = SystemTime;
        if ( !(unsigned int)SetDiscountTime(&Buf1) )
        {
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_80;
          }
          v24 = GetLastError();
          v25 = 168;
LABEL_90:
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v25, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v24);
LABEL_117:
          v13 = WPP_GLOBAL_Control;
          goto LABEL_80;
        }
        if ( !memcmp_0(&Buf1, &SystemTime, 0x10u) )
        {
LABEL_98:
          v29 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                170,
                &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
                v16[8],
                v16[461]);
              v29 = WPP_GLOBAL_Control;
            }
            if ( v29 != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)v29 + 28) & 4) != 0
              && *((_BYTE *)v29 + 25) >= 5u )
            {
              WPP_SF_(*((_QWORD *)v29 + 2), 51, &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids);
            }
          }
          TapiLineForFaxOperation = GetTapiLineForFaxOperation(0xFFFFFFFF, 2u, (const unsigned __int16 *)v17[29].Flink);
          if ( TapiLineForFaxOperation )
          {
            _JOB_QUEUE::PutStatus((_JOB_QUEUE *)v16, v16[461] & 0xFFFFFFDF);
            if ( !(unsigned int)StartSendJob((struct _JOB_QUEUE *)v16, TapiLineForFaxOperation) )
            {
              v13 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_80;
              }
              v32 = GetLastError();
              WPP_SF_lSl(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                173,
                (unsigned int)&WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
                v16[8],
                *((_QWORD *)TapiLineForFaxOperation + 7),
                v32);
            }
          }
          else
          {
            v31 = GetLastError();
            if ( v31 == 1168 )
            {
              if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  171,
                  &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
                  v16[8]);
              }
            }
            else if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                   && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                   && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                172,
                &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
                v16[8],
                v31);
            }
            _JOB_QUEUE::PutStatus((_JOB_QUEUE *)v15, v16[461] | 0x20);
          }
          goto LABEL_117;
        }
        _JOB_QUEUE::PutStatus((_JOB_QUEUE *)v16, v16[461] & 0xFFFFFFDF);
        if ( !SystemTimeToFileTime(&Buf1, v18 + 3) )
        {
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_80;
          }
          v24 = GetLastError();
          v25 = 169;
          goto LABEL_90;
        }
        Blink = v15->Blink;
        v27 = v15->Flink;
        Blink->Flink = v15->Flink;
        v27->Blink = Blink;
        v15->Flink = 0;
        v15->Blink = 0;
        v28 = (unsigned int **)*((_QWORD *)&v46 + 1);
        v15->Flink = (struct _LIST_ENTRY *)&v46;
        v15->Blink = (struct _LIST_ENTRY *)v28;
        *v28 = v16;
        *((_QWORD *)&v46 + 1) = v14;
      }
      v13 = WPP_GLOBAL_Control;
LABEL_80:
      if ( Flink == &g_QueueListHead )
        goto LABEL_137;
    }
    if ( dword_1400A1890 )
      goto LABEL_133;
    if ( ReleaseSemaphore(g_hServiceIsDownSemaphore, 1, 0) )
    {
      dword_1400A1890 = 1;
LABEL_132:
      v13 = WPP_GLOBAL_Control;
LABEL_133:
      if ( v13 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 4) != 0 && *((_BYTE *)v13 + 25) >= 3u )
        WPP_SF_(*((_QWORD *)v13 + 2), 164, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids);
    }
    else
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v33 = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 163, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v33);
          goto LABEL_132;
        }
        goto LABEL_133;
      }
    }
LABEL_137:
    v34 = (__int128 *)v46;
    while ( v34 != &v46 )
    {
      v35 = v34;
      v36 = (__int64)v34;
      v34 = *(__int128 **)v34;
      v37 = (__int128 **)*((_QWORD *)v35 + 1);
      *v37 = v34;
      *((_QWORD *)v34 + 1) = v37;
      *(_QWORD *)v35 = 0;
      *((_QWORD *)v35 + 1) = 0;
      InsertQueueEntryByPriorityAndSchedule(v36);
      QueueEvent = CreateQueueEvent(2u, v36);
      if ( QueueEvent
        && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LOWORD(v44) = QueueEvent;
        WPP_SF_lh(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          174,
          &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
          *(unsigned int *)(v36 + 16),
          v44);
      }
    }
    if ( !(unsigned int)StartJobQueueTimer()
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v39 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 175, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v39);
    }
    LeaveCriticalSection(&g_CsQueue);
    LeaveCriticalSection(&g_CsJob);
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    v40 = 161;
    goto LABEL_158;
  }
LABEL_159:
  if ( !(unsigned int)DecreaseServiceThreadsCount()
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v41 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 176, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v41);
  }
  if ( !dword_1400A1890
    && !ReleaseSemaphore(g_hServiceIsDownSemaphore, 1, 0)
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v42 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 177, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v42);
  }
  return 0;
}

```

## disassembly

```asm
0x140039350  push    rbp
0x140039352  push    rbx
0x140039353  push    rsi
0x140039354  push    rdi
0x140039355  push    r12
0x140039357  push    r13
0x140039359  push    r14
0x14003935b  push    r15
0x14003935d  lea     rbp, [rsp-1Fh]
0x140039362  sub     rsp, 98h
0x140039369  mov     rax, cs:__security_cookie
0x140039370  xor     rax, rsp
0x140039373  mov     [rbp+57h+var_48], rax
0x140039377  xor     r14d, r14d
0x14003937a  xorps   xmm0, xmm0
0x14003937d  xor     eax, eax
0x14003937f  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r14
0x140039383  mov     edi, 258h
0x140039388  mov     [rbp+57h+var_50], rax
0x14003938c  movups  xmmword ptr [rbp+57h+Handles], xmm0
0x140039390  mov     [rbp+57h+dwMilliseconds], edi
0x140039393  movups  [rbp+57h+var_98], xmm0
0x140039397  mov     rcx, cs:WPP_GLOBAL_Control
0x14003939e  lea     rsi, WPP_GLOBAL_Control
0x1400393a5  cmp     rcx, rsi
0x1400393a8  jz      short loc_1400393CB
0x1400393aa  test    byte ptr [rcx+1Ch], 4
0x1400393ae  jz      short loc_1400393CB
0x1400393b0  cmp     byte ptr [rcx+19h], 5
0x1400393b4  jb      short loc_1400393CB
0x1400393b6  mov     rcx, [rcx+10h]
0x1400393ba  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x1400393c1  mov     edx, 97h
0x1400393c6  call    WPP_SF_
0x1400393cb  mov     r9d, 2001Bh
0x1400393d1  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Fax"
0x1400393d8  xor     r8d, r8d
0x1400393db  mov     rcx, 0FFFFFFFF80000002h
0x1400393e2  call    OpenRegistryKey
0x1400393e7  mov     rbx, rax
0x1400393ea  test    rax, rax
0x1400393ed  jz      short loc_14003940E
0x1400393ef  mov     r9d, edi
0x1400393f2  lea     r8, [rbp+57h+dwMilliseconds]; lpData
0x1400393f6  lea     rdx, aJobqueuetimeou; "JobQueueTimeout"
0x1400393fd  mov     rcx, rax; hKey
0x140039400  call    GetRegistryDwordDefault
0x140039405  mov     rcx, rbx; hKey
0x140039408  call    cs:__imp_RegCloseKey
0x14003940e  imul    eax, [rbp+57h+dwMilliseconds], 3E8h
0x140039415  lea     rcx, ?g_CsJob@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003941c  mov     [rbp+57h+dwMilliseconds], eax
0x14003941f  lea     rax, [rbp+57h+var_98]
0x140039423  mov     qword ptr [rbp+57h+var_98+8], rax
0x140039427  lea     rax, [rbp+57h+var_98]
0x14003942b  mov     qword ptr [rbp+57h+var_98], rax
0x14003942f  mov     rax, cs:?g_hQueueTimer@@3PEAXEA; void * g_hQueueTimer
0x140039436  mov     [rbp+57h+Handles], rax
0x14003943a  mov     rax, cs:?g_hJobQueueEvent@@3PEAXEA; void * g_hJobQueueEvent
0x140039441  mov     [rbp+57h+Handles+8], rax
0x140039445  mov     rax, cs:?g_hServiceShutDownEvent@@3PEAXEA; void * g_hServiceShutDownEvent
0x14003944c  mov     [rbp+57h+var_50], rax
0x140039450  call    cs:__imp_EnterCriticalSection
0x140039456  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003945d  call    cs:__imp_EnterCriticalSection
0x140039463  call    ?RestoreFaxQueue@@YAHXZ; RestoreFaxQueue(void)
0x140039468  test    eax, eax
0x14003946a  jnz     short loc_1400394BD
0x14003946c  mov     rax, cs:WPP_GLOBAL_Control
0x140039473  cmp     rax, rsi
0x140039476  jz      short loc_1400394A9
0x140039478  test    byte ptr [rax+1Ch], 4
0x14003947c  jz      short loc_1400394A9
0x14003947e  cmp     byte ptr [rax+19h], 2
0x140039482  jb      short loc_1400394A9
0x140039484  call    cs:__imp_GetLastError
0x14003948a  mov     rcx, cs:WPP_GLOBAL_Control
0x140039491  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x140039498  mov     edx, 98h
0x14003949d  mov     r9d, eax
0x1400394a0  mov     rcx, [rcx+10h]
0x1400394a4  call    WPP_SF_d
0x1400394a9  xor     r8d, r8d
0x1400394ac  mov     r9d, 0C0007D23h
0x1400394b2  lea     edx, [r8+1]
0x1400394b6  mov     ecx, edx
0x1400394b8  call    FaxLog
0x1400394bd  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400394c4  call    cs:__imp_LeaveCriticalSection
0x1400394ca  lea     rcx, ?g_CsJob@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400394d1  call    cs:__imp_LeaveCriticalSection
0x1400394d7  cmp     cs:?g_bDelaySuicideAttempt@@3HA, r14d; int g_bDelaySuicideAttempt
0x1400394de  jnz     loc_1400395F6
0x1400394e4  call    ?ServiceShouldDie@@YAHXZ; ServiceShouldDie(void)
0x1400394e9  test    eax, eax
0x1400394eb  jz      loc_1400395F6
0x1400394f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400394f8  cmp     rcx, rsi
0x1400394fb  jz      short loc_14003951E
0x1400394fd  test    byte ptr [rcx+1Ch], 4
0x140039501  jz      short loc_14003951E
0x140039503  cmp     byte ptr [rcx+19h], 5
0x140039507  jb      short loc_14003951E
0x140039509  mov     rcx, [rcx+10h]
0x14003950d  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x140039514  mov     edx, 99h
0x140039519  call    WPP_SF_
0x14003951e  call    WaitForServiceRPCServer
0x140039523  test    eax, eax
0x140039525  jnz     short loc_140039575
0x140039527  mov     rax, cs:WPP_GLOBAL_Control
0x14003952e  cmp     rax, rsi
0x140039531  jz      loc_1400395F6
0x140039537  test    byte ptr [rax+1Ch], 4
0x14003953b  jz      loc_1400395F6
0x140039541  cmp     byte ptr [rax+19h], 2
0x140039545  jb      loc_1400395F6
0x14003954b  call    cs:__imp_GetLastError
0x140039551  mov     rcx, cs:WPP_GLOBAL_Control
0x140039558  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003955f  mov     edx, 9Ah
0x140039564  mov     r9d, eax
0x140039567  mov     rcx, [rcx+10h]
0x14003956b  call    WPP_SF_d
0x140039570  jmp     loc_1400395F6
0x140039575  mov     rcx, cs:WPP_GLOBAL_Control
0x14003957c  cmp     rcx, rsi
0x14003957f  jz      short loc_1400395A2
0x140039581  test    byte ptr [rcx+1Ch], 4
0x140039585  jz      short loc_1400395A2
0x140039587  cmp     byte ptr [rcx+19h], 5
0x14003958b  jb      short loc_1400395A2
0x14003958d  mov     rcx, [rcx+10h]
0x140039591  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x140039598  mov     edx, 9Bh
0x14003959d  call    WPP_SF_
0x1400395a2  xor     r9d, r9d
0x1400395a5  lea     rdx, SubsystemName; "Fax"
0x1400395ac  lea     r8d, [r9+1]
0x1400395b0  call    StopService
0x1400395b5  test    eax, eax
0x1400395b7  jnz     short loc_1400395F6
0x1400395b9  mov     rax, cs:WPP_GLOBAL_Control
0x1400395c0  cmp     rax, rsi
0x1400395c3  jz      short loc_1400395F6
0x1400395c5  test    byte ptr [rax+1Ch], 4
0x1400395c9  jz      short loc_1400395F6
0x1400395cb  cmp     byte ptr [rax+19h], 2
0x1400395cf  jb      short loc_1400395F6
0x1400395d1  call    cs:__imp_GetLastError
0x1400395d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400395de  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x1400395e5  mov     edx, 9Ch
0x1400395ea  mov     r9d, eax
0x1400395ed  mov     rcx, [rcx+10h]
0x1400395f1  call    WPP_SF_d
0x1400395f6  lea     rdi, ?g_QueueListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_QueueListHead
0x1400395fd  mov     r9d, [rbp+57h+dwMilliseconds]; dwMilliseconds
0x140039601  lea     rdx, [rbp+57h+Handles]; lpHandles
0x140039605  xor     r8d, r8d; bWaitAll
0x140039608  lea     ecx, [r8+3]; nCount
0x14003960c  call    cs:__imp_WaitForMultipleObjects
0x140039612  cmp     eax, 0FFFFFFFFh
0x140039615  jnz     short loc_140039665
0x140039617  mov     rcx, cs:WPP_GLOBAL_Control
0x14003961e  cmp     rcx, rsi
0x140039621  jz      loc_140039772
0x140039627  test    byte ptr [rcx+1Ch], 4
0x14003962b  jz      loc_140039772
0x140039631  cmp     byte ptr [rcx+19h], 2
0x140039635  jb      loc_140039772
0x14003963b  call    cs:__imp_GetLastError
0x140039641  mov     rcx, cs:WPP_GLOBAL_Control
0x140039648  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003964f  mov     edx, 9Dh
0x140039654  mov     r9d, eax
0x140039657  mov     rcx, [rcx+10h]
0x14003965b  call    WPP_SF_d
0x140039660  jmp     loc_14003976B
0x140039665  cmp     eax, 102h
0x14003966a  jnz     loc_140039762
0x140039670  call    ?ServiceShouldDie@@YAHXZ; ServiceShouldDie(void)
0x140039675  test    eax, eax
0x140039677  jz      loc_1400396FE
0x14003967d  mov     rcx, cs:WPP_GLOBAL_Control
0x140039684  cmp     rcx, rsi
0x140039687  jz      short loc_1400396AA
0x140039689  test    byte ptr [rcx+1Ch], 4
0x14003968d  jz      short loc_1400396AA
0x14003968f  cmp     byte ptr [rcx+19h], 5
0x140039693  jb      short loc_1400396AA
0x140039695  mov     rcx, [rcx+10h]
0x140039699  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x1400396a0  mov     edx, 9Eh
0x1400396a5  call    WPP_SF_
0x1400396aa  xor     r9d, r9d
0x1400396ad  lea     rdx, SubsystemName; "Fax"
0x1400396b4  lea     r8d, [r9+1]
0x1400396b8  call    StopService
0x1400396bd  test    eax, eax
0x1400396bf  jnz     short loc_1400396FE
0x1400396c1  mov     rax, cs:WPP_GLOBAL_Control
0x1400396c8  cmp     rax, rsi
0x1400396cb  jz      short loc_1400396FE
0x1400396cd  test    byte ptr [rax+1Ch], 4
0x1400396d1  jz      short loc_1400396FE
0x1400396d3  cmp     byte ptr [rax+19h], 2
0x1400396d7  jb      short loc_1400396FE
0x1400396d9  call    cs:__imp_GetLastError
0x1400396df  mov     rcx, cs:WPP_GLOBAL_Control
0x1400396e6  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x1400396ed  mov     edx, 9Fh
0x1400396f2  mov     r9d, eax
0x1400396f5  mov     rcx, [rcx+10h]
0x1400396f9  call    WPP_SF_d
0x1400396fe  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140039705  call    cs:__imp_EnterCriticalSection
0x14003970b  cmp     cs:?g_ScanQueueAfterTimeout@@3HA, r14d; int g_ScanQueueAfterTimeout
0x140039712  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140039719  jnz     short loc_140039726
0x14003971b  call    cs:__imp_LeaveCriticalSection
0x140039721  jmp     loc_1400395FD
0x140039726  mov     cs:?g_ScanQueueAfterTimeout@@3HA, r14d; int g_ScanQueueAfterTimeout
0x14003972d  call    cs:__imp_LeaveCriticalSection
0x140039733  mov     rcx, cs:WPP_GLOBAL_Control
0x14003973a  cmp     rcx, rsi
0x14003973d  jz      short loc_140039772
0x14003973f  test    byte ptr [rcx+1Ch], 4
0x140039743  jz      short loc_140039772
0x140039745  cmp     byte ptr [rcx+19h], 3
0x140039749  jb      short loc_140039772
0x14003974b  mov     rcx, [rcx+10h]
0x14003974f  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x140039756  mov     edx, 0A0h
0x14003975b  call    WPP_SF_
0x140039760  jmp     short loc_14003976B
0x140039762  cmp     eax, 2
0x140039765  jz      loc_140039DB4
0x14003976b  mov     rcx, cs:WPP_GLOBAL_Control
0x140039772  cmp     cs:?g_bServiceIsDown@@3HA, 1; int g_bServiceIsDown
0x140039779  jz      loc_140039D9C
0x14003977f  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140039786  call    cs:__imp_EnterCriticalSection
0x14003978c  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140039793  call    cs:__imp_LeaveCriticalSection
0x140039799  lea     rcx, ?g_CsJob@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400397a0  call    cs:__imp_EnterCriticalSection
0x1400397a6  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400397ad  call    cs:__imp_EnterCriticalSection
0x1400397b3  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400397b7  call    cs:__imp_GetSystemTimeAsFileTime
0x1400397bd  mov     r12, cs:?g_QueueListHead@@3U_LIST_ENTRY@@A.Flink; _LIST_ENTRY g_QueueListHead ...
0x1400397c4  cmp     r12, rdi
0x1400397c7  jz      loc_140039CBB
0x1400397cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400397d4  lea     rax, ?g_QueueListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_QueueListHead
0x1400397db  cmp     cs:?g_bServiceIsDown@@3HA, 1; int g_bServiceIsDown
0x1400397e2  jz      loc_140039C21
0x1400397e8  mov     r14, r12
0x1400397eb  mov     r15, r12
0x1400397ee  mov     rdi, r12
0x1400397f1  mov     r13, r12
0x1400397f4  mov     rsi, r12
0x1400397f7  mov     r12, [r12]
0x1400397fb  mov     r8d, [r14+734h]
0x140039802  test    r8b, 10h
0x140039806  jnz     loc_14003991A
0x14003980c  cmp     dword ptr [r14+24h], 4
0x140039811  jz      loc_14003991A
0x140039817  cmp     dword ptr [r14+24h], 2
0x14003981c  jnz     short loc_14003982D
0x14003981e  mov     rax, [r14+248h]
0x140039825  mov     edx, [rax+734h]
0x14003982b  jmp     short loc_140039830
0x14003982d  mov     edx, r8d
0x140039830  cmp     edx, 4
0x140039833  jz      loc_140039913
0x140039839  test    r8b, r8b
0x14003983c  js      loc_140039913
0x140039842  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140039849  call    cs:__imp_EnterCriticalSection
0x14003984f  mov     rax, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x140039856  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003985d  mov     ebx, [rax+8]
0x140039860  call    cs:__imp_LeaveCriticalSection
0x140039866  test    bl, 4
0x140039869  jnz     loc_140039C15
0x14003986f  test    dword ptr [rdi+734h], 782h
0x140039879  jnz     loc_140039C15
0x14003987f  cmp     dword ptr [rdi+24h], 20h ; ' '
0x140039883  jz      loc_140039C15
0x140039889  cmp     dword ptr [rdi+24h], 8
0x14003988d  mov     rax, [rsi+18h]
0x140039891  jnz     loc_140039932
0x140039897  test    rax, rax
0x14003989a  jz      short loc_1400398A6
0x14003989c  cmp     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], rax
0x1400398a0  jb      loc_140039C15
0x1400398a6  mov     rcx, rdi; this
0x1400398a9  call    ?StartRoutingJob@@YAHPEAU_JOB_QUEUE@@@Z; StartRoutingJob(_JOB_QUEUE *)
  ... truncated ...
```
