# JobQueueThread(void *)

- ea: `0x14003b300`
- end: `0x14003bf33`
- name: `?JobQueueThread@@YAKPEAX@Z`
- size: `3123`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `0`
- callee_count: `24`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x140004fe4`
- `0x140023a0c`
- `0x1400354cc`
- `0x140035688`
- `0x140037184`
- `0x14003b1a4`
- `0x14003b300`
- `0x14003c4ac`
- `0x14003e168`
- `0x1400402a0`
- `0x140040500`
- `0x1400408a8`
- `0x14004d830`
- `0x140052184`
- `0x14005900c`
- `0x1400699d0`
- `0x140074cb4`
- `0x140074f18`
- `0x1400781f0`
- `0x140078570`
- `0x140086e76`
- `0x140086ec0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14003b3b8`
- `ADVAPI32!RegCloseKey` at `0x14003b3b8`
- `KERNEL32!ReleaseSemaphore` at `0x14003bc96`
- `KERNEL32!ReleaseSemaphore` at `0x14003bebd`
- `KERNEL32!ReleaseSemaphore` at `0x14003bc96`
- `KERNEL32!ReleaseSemaphore` at `0x14003bebd`
- `KERNEL32!GetLastError` at `0x14003b446`
- `KERNEL32!GetLastError` at `0x14003b51f`
- `KERNEL32!GetLastError` at `0x14003b5ab`
- `KERNEL32!GetLastError` at `0x14003b621`
- `KERNEL32!GetLastError` at `0x14003b6c5`
- `KERNEL32!GetLastError` at `0x14003b90b`
- `KERNEL32!GetLastError` at `0x14003b9df`
- `KERNEL32!GetLastError` at `0x14003ba7e`
- `KERNEL32!GetLastError` at `0x14003bb5b`
- `KERNEL32!GetLastError` at `0x14003bc32`
- `KERNEL32!GetLastError` at `0x14003bcbe`
- `KERNEL32!GetLastError` at `0x14003bdbf`
- `KERNEL32!GetLastError` at `0x14003be7b`
- `KERNEL32!GetLastError` at `0x14003bee5`
- `KERNEL32!GetLastError` at `0x14003b446`
- `KERNEL32!GetLastError` at `0x14003b51f`
- `KERNEL32!GetLastError` at `0x14003b5ab`
- `KERNEL32!GetLastError` at `0x14003b621`
- `KERNEL32!GetLastError` at `0x14003b6c5`
- `KERNEL32!GetLastError` at `0x14003b90b`
- `KERNEL32!GetLastError` at `0x14003b9df`
- `KERNEL32!GetLastError` at `0x14003ba7e`
- `KERNEL32!GetLastError` at `0x14003bb5b`
- `KERNEL32!GetLastError` at `0x14003bc32`
- `KERNEL32!GetLastError` at `0x14003bcbe`
- `KERNEL32!GetLastError` at `0x14003bdbf`
- `KERNEL32!GetLastError` at `0x14003be7b`
- `KERNEL32!GetLastError` at `0x14003bee5`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14003b7d3`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14003b7d3`
- `KERNEL32!EnterCriticalSection` at `0x14003b406`
- `KERNEL32!EnterCriticalSection` at `0x14003b419`
- `KERNEL32!EnterCriticalSection` at `0x14003b6f7`
- `KERNEL32!EnterCriticalSection` at `0x14003b78a`
- `KERNEL32!EnterCriticalSection` at `0x14003b7b0`
- `KERNEL32!EnterCriticalSection` at `0x14003b7c3`
- `KERNEL32!EnterCriticalSection` at `0x14003b86b`
- `KERNEL32!EnterCriticalSection` at `0x14003b406`
- `KERNEL32!EnterCriticalSection` at `0x14003b419`
- `KERNEL32!EnterCriticalSection` at `0x14003b6f7`
- `KERNEL32!EnterCriticalSection` at `0x14003b78a`
- `KERNEL32!EnterCriticalSection` at `0x14003b7b0`
- `KERNEL32!EnterCriticalSection` at `0x14003b7c3`
- `KERNEL32!EnterCriticalSection` at `0x14003b86b`
- `KERNEL32!LeaveCriticalSection` at `0x14003b48c`
- `KERNEL32!LeaveCriticalSection` at `0x14003b49f`
- `KERNEL32!LeaveCriticalSection` at `0x14003b713`
- `KERNEL32!LeaveCriticalSection` at `0x14003b72b`
- `KERNEL32!LeaveCriticalSection` at `0x14003b79d`
- `KERNEL32!LeaveCriticalSection` at `0x14003b888`
- `KERNEL32!LeaveCriticalSection` at `0x14003bdf1`
- `KERNEL32!LeaveCriticalSection` at `0x14003be04`
- `KERNEL32!LeaveCriticalSection` at `0x14003b48c`
- `KERNEL32!LeaveCriticalSection` at `0x14003b49f`
- `KERNEL32!LeaveCriticalSection` at `0x14003b713`
- `KERNEL32!LeaveCriticalSection` at `0x14003b72b`
- `KERNEL32!LeaveCriticalSection` at `0x14003b79d`
- `KERNEL32!LeaveCriticalSection` at `0x14003b888`
- `KERNEL32!LeaveCriticalSection` at `0x14003bdf1`
- `KERNEL32!LeaveCriticalSection` at `0x14003be04`
- `KERNEL32!WaitForMultipleObjects` at `0x14003b5ec`
- `KERNEL32!WaitForMultipleObjects` at `0x14003b5ec`
- `KERNEL32!GetSystemTime` at `0x14003b992`
- `KERNEL32!GetSystemTime` at `0x14003b992`
- `KERNEL32!SystemTimeToFileTime` at `0x14003ba43`
- `KERNEL32!SystemTimeToFileTime` at `0x14003ba43`

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
  struct _LIST_ENTRY *v16; // rdi
  struct _LIST_ENTRY *v17; // r13
  struct _FILETIME *v18; // rsi
  int Flink_high; // r8d
  int v20; // edx
  int v21; // ebx
  unsigned __int64 v22; // rax
  DWORD v23; // eax
  __int64 v24; // rdx
  struct _LIST_ENTRY *Blink; // rax
  struct _LIST_ENTRY *v26; // rcx
  struct _LIST_ENTRY *v27; // rax
  CMapDeviceId *v28; // rcx
  struct _LINE_INFO *TapiLineForFaxOperation; // rbx
  DWORD v30; // eax
  char v31; // al
  DWORD v32; // eax
  __int128 *v33; // rbx
  __int128 *v34; // rdx
  __int128 *v35; // rdi
  __int128 **v36; // rax
  int QueueEvent; // eax
  DWORD v38; // eax
  __int64 v39; // rdx
  DWORD v40; // eax
  DWORD v41; // eax
  DWORD v43; // [rsp+20h] [rbp-59h]
  DWORD dwMilliseconds; // [rsp+30h] [rbp-49h] BYREF
  __int128 v45; // [rsp+38h] [rbp-41h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp-31h] BYREF
  struct _SYSTEMTIME Buf1; // [rsp+50h] [rbp-29h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+60h] [rbp-19h] BYREF
  HANDLE Handles[2]; // [rsp+70h] [rbp-9h] BYREF
  HANDLE v50; // [rsp+80h] [rbp+7h]

  SystemTimeAsFileTime = 0;
  v50 = 0;
  *(_OWORD *)Handles = 0;
  dwMilliseconds = 600;
  v45 = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 151, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids);
  }
  v1 = OpenRegistryKey(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Fax", 0, 0x2001Bu);
  v2 = v1;
  if ( v1 )
  {
    GetRegistryDwordDefault(v1, L"JobQueueTimeout", (BYTE *)&dwMilliseconds, 600);
    RegCloseKey(v2);
  }
  dwMilliseconds *= 1000;
  *((_QWORD *)&v45 + 1) = &v45;
  *(_QWORD *)&v45 = &v45;
  Handles[0] = g_hQueueTimer;
  Handles[1] = g_hJobQueueEvent;
  v50 = g_hServiceShutDownEvent;
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
    FaxLog(1u, 1u, 0, 0xC0007D23, v43);
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
      if ( !(unsigned int)StopService((__int64)v5, L"Fax", 1, 0)
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
        if ( !(unsigned int)StopService((__int64)v10, L"Fax", 1, 0)
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
        v39 = 162;
LABEL_158:
        WPP_SF_(*((_QWORD *)v8 + 2), v39, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids);
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
      v16 = Flink;
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
      if ( (v21 & 4) != 0 || (HIDWORD(v16[115].Flink) & 0x782) != 0 || HIDWORD(v16[2].Flink) == 32 )
        goto LABEL_117;
      v22 = (unsigned __int64)v18[3];
      if ( HIDWORD(v16[2].Flink) == 8 )
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
          v43 = GetLastError();
          WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 167, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids);
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
          v23 = GetLastError();
          v24 = 168;
LABEL_90:
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v24, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v23);
LABEL_117:
          v13 = WPP_GLOBAL_Control;
          goto LABEL_80;
        }
        if ( !memcmp_0(&Buf1, &SystemTime, 0x10u) )
        {
LABEL_98:
          v28 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              v43 = HIDWORD(v16[115].Flink);
              WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 170, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids);
              v28 = WPP_GLOBAL_Control;
            }
            if ( v28 != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)v28 + 28) & 4) != 0
              && *((_BYTE *)v28 + 25) >= 5u )
            {
              WPP_SF_(*((_QWORD *)v28 + 2), 51, &WPP_ee733597ac3932bb7d4fe030915e01c4_Traceguids);
            }
          }
          TapiLineForFaxOperation = GetTapiLineForFaxOperation(0xFFFFFFFF, 2u, (const unsigned __int16 *)v17[29].Flink);
          if ( TapiLineForFaxOperation )
          {
            _JOB_QUEUE::PutStatus((_JOB_QUEUE *)v16, HIDWORD(v16[115].Flink) & 0xFFFFFFDF);
            if ( !(unsigned int)StartSendJob((struct _JOB_QUEUE *)v16, TapiLineForFaxOperation) )
            {
              v13 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_80;
              }
              v31 = GetLastError();
              WPP_SF_lSl(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                173,
                (unsigned int)&WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
                v16[2].Flink,
                *((_QWORD *)TapiLineForFaxOperation + 7),
                v31);
            }
          }
          else
          {
            v30 = GetLastError();
            if ( v30 == 1168 )
            {
              if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  171,
                  &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
                  LODWORD(v16[2].Flink));
              }
            }
            else if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                   && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                   && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              HIWORD(v43) = HIWORD(v30);
              WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 172, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids);
            }
            _JOB_QUEUE::PutStatus((_JOB_QUEUE *)v15, HIDWORD(v16[115].Flink) | 0x20);
          }
          goto LABEL_117;
        }
        _JOB_QUEUE::PutStatus((_JOB_QUEUE *)v16, HIDWORD(v16[115].Flink) & 0xFFFFFFDF);
        if ( !SystemTimeToFileTime(&Buf1, v18 + 3) )
        {
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_80;
          }
          v23 = GetLastError();
          v24 = 169;
          goto LABEL_90;
        }
        Blink = v15->Blink;
        v26 = v15->Flink;
        Blink->Flink = v15->Flink;
        v26->Blink = Blink;
        v15->Flink = 0;
        v15->Blink = 0;
        v27 = (struct _LIST_ENTRY *)*((_QWORD *)&v45 + 1);
        v15->Flink = (struct _LIST_ENTRY *)&v45;
        v15->Blink = v27;
        v27->Flink = v16;
        *((_QWORD *)&v45 + 1) = v14;
      }
      v13 = WPP_GLOBAL_Control;
LABEL_80:
      if ( Flink == &g_QueueListHead )
        goto LABEL_137;
    }
    if ( dword_1400A7890 )
      goto LABEL_133;
    if ( ReleaseSemaphore(g_hServiceIsDownSemaphore, 1, 0) )
    {
      dword_1400A7890 = 1;
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
          v32 = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 163, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v32);
          goto LABEL_132;
        }
        goto LABEL_133;
      }
    }
LABEL_137:
    v33 = (__int128 *)v45;
    while ( v33 != &v45 )
    {
      v34 = v33;
      v35 = v33;
      v33 = *(__int128 **)v33;
      v36 = (__int128 **)*((_QWORD *)v34 + 1);
      *v36 = v33;
      *((_QWORD *)v33 + 1) = v36;
      *(_QWORD *)v34 = 0;
      *((_QWORD *)v34 + 1) = 0;
      InsertQueueEntryByPriorityAndSchedule(v35);
      QueueEvent = CreateQueueEvent(2, v35);
      if ( QueueEvent
        && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LOWORD(v43) = QueueEvent;
        WPP_SF_lh(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          174,
          &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
          *((unsigned int *)v35 + 4),
          v43);
      }
    }
    if ( !(unsigned int)StartJobQueueTimer()
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v38 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 175, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v38);
    }
    LeaveCriticalSection(&g_CsQueue);
    LeaveCriticalSection(&g_CsJob);
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    v39 = 161;
    goto LABEL_158;
  }
LABEL_159:
  if ( !(unsigned int)DecreaseServiceThreadsCount()
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v40 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 176, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v40);
  }
  if ( !dword_1400A7890
    && !ReleaseSemaphore(g_hServiceIsDownSemaphore, 1, 0)
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v41 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 177, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v41);
  }
  return 0;
}

```

## disassembly

```asm
0x14003b300  push    rbp
0x14003b302  push    rbx
0x14003b303  push    rsi
0x14003b304  push    rdi
0x14003b305  push    r12
0x14003b307  push    r13
0x14003b309  push    r14
0x14003b30b  push    r15
0x14003b30d  lea     rbp, [rsp-1Fh]
0x14003b312  sub     rsp, 98h
0x14003b319  mov     rax, cs:__security_cookie
0x14003b320  xor     rax, rsp
0x14003b323  mov     [rbp+57h+var_48], rax
0x14003b327  xor     r14d, r14d
0x14003b32a  xorps   xmm0, xmm0
0x14003b32d  xor     eax, eax
0x14003b32f  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r14
0x14003b333  mov     edi, 258h
0x14003b338  mov     [rbp+57h+var_50], rax
0x14003b33c  movups  xmmword ptr [rbp+57h+Handles], xmm0
0x14003b340  mov     [rbp+57h+dwMilliseconds], edi
0x14003b343  movups  [rbp+57h+var_98], xmm0
0x14003b347  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b34e  lea     rsi, WPP_GLOBAL_Control
0x14003b355  cmp     rcx, rsi
0x14003b358  jz      short loc_14003B37B
0x14003b35a  test    byte ptr [rcx+1Ch], 4
0x14003b35e  jz      short loc_14003B37B
0x14003b360  cmp     byte ptr [rcx+19h], 5
0x14003b364  jb      short loc_14003B37B
0x14003b366  mov     rcx, [rcx+10h]
0x14003b36a  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003b371  mov     edx, 97h
0x14003b376  call    WPP_SF_
0x14003b37b  mov     r9d, 2001Bh
0x14003b381  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Fax"
0x14003b388  xor     r8d, r8d
0x14003b38b  mov     rcx, 0FFFFFFFF80000002h
0x14003b392  call    OpenRegistryKey
0x14003b397  mov     rbx, rax
0x14003b39a  test    rax, rax
0x14003b39d  jz      short loc_14003B3C4
0x14003b39f  mov     r9d, edi
0x14003b3a2  lea     r8, [rbp+57h+dwMilliseconds]; lpData
0x14003b3a6  lea     rdx, aJobqueuetimeou; "JobQueueTimeout"
0x14003b3ad  mov     rcx, rax; hKey
0x14003b3b0  call    GetRegistryDwordDefault
0x14003b3b5  mov     rcx, rbx; hKey
0x14003b3b8  call    cs:__imp_RegCloseKey
0x14003b3bf  nop     dword ptr [rax+rax+00h]
0x14003b3c4  imul    eax, [rbp+57h+dwMilliseconds], 3E8h
0x14003b3cb  lea     rcx, ?g_CsJob@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003b3d2  mov     [rbp+57h+dwMilliseconds], eax
0x14003b3d5  lea     rax, [rbp+57h+var_98]
0x14003b3d9  mov     qword ptr [rbp+57h+var_98+8], rax
0x14003b3dd  lea     rax, [rbp+57h+var_98]
0x14003b3e1  mov     qword ptr [rbp+57h+var_98], rax
0x14003b3e5  mov     rax, cs:?g_hQueueTimer@@3PEAXEA; void * g_hQueueTimer
0x14003b3ec  mov     [rbp+57h+Handles], rax
0x14003b3f0  mov     rax, cs:?g_hJobQueueEvent@@3PEAXEA; void * g_hJobQueueEvent
0x14003b3f7  mov     [rbp+57h+Handles+8], rax
0x14003b3fb  mov     rax, cs:?g_hServiceShutDownEvent@@3PEAXEA; void * g_hServiceShutDownEvent
0x14003b402  mov     [rbp+57h+var_50], rax
0x14003b406  call    cs:__imp_EnterCriticalSection
0x14003b40d  nop     dword ptr [rax+rax+00h]
0x14003b412  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003b419  call    cs:__imp_EnterCriticalSection
0x14003b420  nop     dword ptr [rax+rax+00h]
0x14003b425  call    ?RestoreFaxQueue@@YAHXZ; RestoreFaxQueue(void)
0x14003b42a  test    eax, eax
0x14003b42c  jnz     short loc_14003B485
0x14003b42e  mov     rax, cs:WPP_GLOBAL_Control
0x14003b435  cmp     rax, rsi
0x14003b438  jz      short loc_14003B471
0x14003b43a  test    byte ptr [rax+1Ch], 4
0x14003b43e  jz      short loc_14003B471
0x14003b440  cmp     byte ptr [rax+19h], 2
0x14003b444  jb      short loc_14003B471
0x14003b446  call    cs:__imp_GetLastError
0x14003b44d  nop     dword ptr [rax+rax+00h]
0x14003b452  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b459  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003b460  mov     edx, 98h
0x14003b465  mov     r9d, eax
0x14003b468  mov     rcx, [rcx+10h]
0x14003b46c  call    WPP_SF_d
0x14003b471  xor     r8d, r8d
0x14003b474  mov     r9d, 0C0007D23h
0x14003b47a  lea     edx, [r8+1]
0x14003b47e  mov     ecx, edx
0x14003b480  call    FaxLog
0x14003b485  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003b48c  call    cs:__imp_LeaveCriticalSection
0x14003b493  nop     dword ptr [rax+rax+00h]
0x14003b498  lea     rcx, ?g_CsJob@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003b49f  call    cs:__imp_LeaveCriticalSection
0x14003b4a6  nop     dword ptr [rax+rax+00h]
0x14003b4ab  cmp     cs:?g_bDelaySuicideAttempt@@3HA, r14d; int g_bDelaySuicideAttempt
0x14003b4b2  jnz     loc_14003B5D6
0x14003b4b8  call    ?ServiceShouldDie@@YAHXZ; ServiceShouldDie(void)
0x14003b4bd  test    eax, eax
0x14003b4bf  jz      loc_14003B5D6
0x14003b4c5  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b4cc  cmp     rcx, rsi
0x14003b4cf  jz      short loc_14003B4F2
0x14003b4d1  test    byte ptr [rcx+1Ch], 4
0x14003b4d5  jz      short loc_14003B4F2
0x14003b4d7  cmp     byte ptr [rcx+19h], 5
0x14003b4db  jb      short loc_14003B4F2
0x14003b4dd  mov     rcx, [rcx+10h]
0x14003b4e1  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003b4e8  mov     edx, 99h
0x14003b4ed  call    WPP_SF_
0x14003b4f2  call    WaitForServiceRPCServer
0x14003b4f7  test    eax, eax
0x14003b4f9  jnz     short loc_14003B54F
0x14003b4fb  mov     rax, cs:WPP_GLOBAL_Control
0x14003b502  cmp     rax, rsi
0x14003b505  jz      loc_14003B5D6
0x14003b50b  test    byte ptr [rax+1Ch], 4
0x14003b50f  jz      loc_14003B5D6
0x14003b515  cmp     byte ptr [rax+19h], 2
0x14003b519  jb      loc_14003B5D6
0x14003b51f  call    cs:__imp_GetLastError
0x14003b526  nop     dword ptr [rax+rax+00h]
0x14003b52b  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b532  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003b539  mov     edx, 9Ah
0x14003b53e  mov     r9d, eax
0x14003b541  mov     rcx, [rcx+10h]
0x14003b545  call    WPP_SF_d
0x14003b54a  jmp     loc_14003B5D6
0x14003b54f  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b556  cmp     rcx, rsi
0x14003b559  jz      short loc_14003B57C
0x14003b55b  test    byte ptr [rcx+1Ch], 4
0x14003b55f  jz      short loc_14003B57C
0x14003b561  cmp     byte ptr [rcx+19h], 5
0x14003b565  jb      short loc_14003B57C
0x14003b567  mov     rcx, [rcx+10h]
0x14003b56b  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003b572  mov     edx, 9Bh
0x14003b577  call    WPP_SF_
0x14003b57c  xor     r9d, r9d
0x14003b57f  lea     rdx, SubsystemName; "Fax"
0x14003b586  lea     r8d, [r9+1]
0x14003b58a  call    StopService
0x14003b58f  test    eax, eax
0x14003b591  jnz     short loc_14003B5D6
0x14003b593  mov     rax, cs:WPP_GLOBAL_Control
0x14003b59a  cmp     rax, rsi
0x14003b59d  jz      short loc_14003B5D6
0x14003b59f  test    byte ptr [rax+1Ch], 4
0x14003b5a3  jz      short loc_14003B5D6
0x14003b5a5  cmp     byte ptr [rax+19h], 2
0x14003b5a9  jb      short loc_14003B5D6
0x14003b5ab  call    cs:__imp_GetLastError
0x14003b5b2  nop     dword ptr [rax+rax+00h]
0x14003b5b7  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b5be  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003b5c5  mov     edx, 9Ch
0x14003b5ca  mov     r9d, eax
0x14003b5cd  mov     rcx, [rcx+10h]
0x14003b5d1  call    WPP_SF_d
0x14003b5d6  lea     rdi, ?g_QueueListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_QueueListHead
0x14003b5dd  mov     r9d, [rbp+57h+dwMilliseconds]; dwMilliseconds
0x14003b5e1  lea     rdx, [rbp+57h+Handles]; lpHandles
0x14003b5e5  xor     r8d, r8d; bWaitAll
0x14003b5e8  lea     ecx, [r8+3]; nCount
0x14003b5ec  call    cs:__imp_WaitForMultipleObjects
0x14003b5f3  nop     dword ptr [rax+rax+00h]
0x14003b5f8  cmp     eax, 0FFFFFFFFh
0x14003b5fb  jnz     short loc_14003B651
0x14003b5fd  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b604  cmp     rcx, rsi
0x14003b607  jz      loc_14003B776
0x14003b60d  test    byte ptr [rcx+1Ch], 4
0x14003b611  jz      loc_14003B776
0x14003b617  cmp     byte ptr [rcx+19h], 2
0x14003b61b  jb      loc_14003B776
0x14003b621  call    cs:__imp_GetLastError
0x14003b628  nop     dword ptr [rax+rax+00h]
0x14003b62d  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b634  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003b63b  mov     edx, 9Dh
0x14003b640  mov     r9d, eax
0x14003b643  mov     rcx, [rcx+10h]
0x14003b647  call    WPP_SF_d
0x14003b64c  jmp     loc_14003B76F
0x14003b651  cmp     eax, 102h
0x14003b656  jnz     loc_14003B766
0x14003b65c  call    ?ServiceShouldDie@@YAHXZ; ServiceShouldDie(void)
0x14003b661  test    eax, eax
0x14003b663  jz      loc_14003B6F0
0x14003b669  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b670  cmp     rcx, rsi
0x14003b673  jz      short loc_14003B696
0x14003b675  test    byte ptr [rcx+1Ch], 4
0x14003b679  jz      short loc_14003B696
0x14003b67b  cmp     byte ptr [rcx+19h], 5
0x14003b67f  jb      short loc_14003B696
0x14003b681  mov     rcx, [rcx+10h]
0x14003b685  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003b68c  mov     edx, 9Eh
0x14003b691  call    WPP_SF_
0x14003b696  xor     r9d, r9d
0x14003b699  lea     rdx, SubsystemName; "Fax"
0x14003b6a0  lea     r8d, [r9+1]
0x14003b6a4  call    StopService
0x14003b6a9  test    eax, eax
0x14003b6ab  jnz     short loc_14003B6F0
0x14003b6ad  mov     rax, cs:WPP_GLOBAL_Control
0x14003b6b4  cmp     rax, rsi
0x14003b6b7  jz      short loc_14003B6F0
0x14003b6b9  test    byte ptr [rax+1Ch], 4
0x14003b6bd  jz      short loc_14003B6F0
0x14003b6bf  cmp     byte ptr [rax+19h], 2
0x14003b6c3  jb      short loc_14003B6F0
0x14003b6c5  call    cs:__imp_GetLastError
0x14003b6cc  nop     dword ptr [rax+rax+00h]
0x14003b6d1  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b6d8  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003b6df  mov     edx, 9Fh
0x14003b6e4  mov     r9d, eax
0x14003b6e7  mov     rcx, [rcx+10h]
0x14003b6eb  call    WPP_SF_d
0x14003b6f0  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003b6f7  call    cs:__imp_EnterCriticalSection
0x14003b6fe  nop     dword ptr [rax+rax+00h]
0x14003b703  cmp     cs:?g_ScanQueueAfterTimeout@@3HA, r14d; int g_ScanQueueAfterTimeout
0x14003b70a  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003b711  jnz     short loc_14003B724
0x14003b713  call    cs:__imp_LeaveCriticalSection
0x14003b71a  nop     dword ptr [rax+rax+00h]
0x14003b71f  jmp     loc_14003B5DD
0x14003b724  mov     cs:?g_ScanQueueAfterTimeout@@3HA, r14d; int g_ScanQueueAfterTimeout
0x14003b72b  call    cs:__imp_LeaveCriticalSection
0x14003b732  nop     dword ptr [rax+rax+00h]
0x14003b737  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b73e  cmp     rcx, rsi
0x14003b741  jz      short loc_14003B776
0x14003b743  test    byte ptr [rcx+1Ch], 4
0x14003b747  jz      short loc_14003B776
0x14003b749  cmp     byte ptr [rcx+19h], 3
0x14003b74d  jb      short loc_14003B776
0x14003b74f  mov     rcx, [rcx+10h]
0x14003b753  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003b75a  mov     edx, 0A0h
0x14003b75f  call    WPP_SF_
0x14003b764  jmp     short loc_14003B76F
0x14003b766  cmp     eax, 2
0x14003b769  jz      loc_14003BE2D
0x14003b76f  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b776  cmp     cs:?g_bServiceIsDown@@3HA, 1; int g_bServiceIsDown
0x14003b77d  jz      loc_14003BE15
0x14003b783  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003b78a  call    cs:__imp_EnterCriticalSection
0x14003b791  nop     dword ptr [rax+rax+00h]
0x14003b796  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003b79d  call    cs:__imp_LeaveCriticalSection
0x14003b7a4  nop     dword ptr [rax+rax+00h]
0x14003b7a9  lea     rcx, ?g_CsJob@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003b7b0  call    cs:__imp_EnterCriticalSection
0x14003b7b7  nop     dword ptr [rax+rax+00h]
0x14003b7bc  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003b7c3  call    cs:__imp_EnterCriticalSection
0x14003b7ca  nop     dword ptr [rax+rax+00h]
0x14003b7cf  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14003b7d3  call    cs:__imp_GetSystemTimeAsFileTime
0x14003b7da  nop     dword ptr [rax+rax+00h]
0x14003b7df  mov     r12, cs:?g_QueueListHead@@3U_LIST_ENTRY@@A.Flink; _LIST_ENTRY g_QueueListHead ...
0x14003b7e6  cmp     r12, rdi
0x14003b7e9  jz      loc_14003BD22
0x14003b7ef  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b7f6  lea     rax, ?g_QueueListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_QueueListHead
0x14003b7fd  cmp     cs:?g_bServiceIsDown@@3HA, 1; int g_bServiceIsDown
0x14003b804  jz      loc_14003BC7C
0x14003b80a  mov     r14, r12
0x14003b80d  mov     r15, r12
0x14003b810  mov     rdi, r12
0x14003b813  mov     r13, r12
0x14003b816  mov     rsi, r12
0x14003b819  mov     r12, [r12]
0x14003b81d  mov     r8d, [r14+734h]
0x14003b824  test    r8b, 10h
0x14003b828  jnz     loc_14003B94E
0x14003b82e  cmp     dword ptr [r14+24h], 4
0x14003b833  jz      loc_14003B94E
0x14003b839  cmp     dword ptr [r14+24h], 2
0x14003b83e  jnz     short loc_14003B84F
0x14003b840  mov     rax, [r14+248h]
0x14003b847  mov     edx, [rax+734h]
0x14003b84d  jmp     short loc_14003B852
0x14003b84f  mov     edx, r8d
0x14003b852  cmp     edx, 4
0x14003b855  jz      loc_14003B947
0x14003b85b  test    r8b, r8b
0x14003b85e  js      loc_14003B947
0x14003b864  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003b86b  call    cs:__imp_EnterCriticalSection
  ... truncated ...
```
