# FaxStatusThread(void *)

- ea: `0x140030520`
- end: `0x140030e81`
- name: `?FaxStatusThread@@YAKPEAX@Z`
- size: `2401`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callees

- `0x140002c43`
- `0x140003468`
- `0x140004b30`
- `0x140004b58`
- `0x140004e68`
- `0x140022a4c`
- `0x140030520`
- `0x140034fc4`
- `0x140035554`
- `0x14004eedc`
- `0x1400502b0`
- `0x1400505e8`
- `0x14005086c`
- `0x14005584c`
- `0x140055acc`
- `0x140067168`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14003062c`
- `KERNEL32!GetLastError` at `0x140030676`
- `KERNEL32!GetLastError` at `0x1400306e8`
- `KERNEL32!GetLastError` at `0x14003077a`
- `KERNEL32!GetLastError` at `0x140030835`
- `KERNEL32!GetLastError` at `0x1400308e5`
- `KERNEL32!GetLastError` at `0x1400309b8`
- `KERNEL32!GetLastError` at `0x140030a85`
- `KERNEL32!GetLastError` at `0x140030ae0`
- `KERNEL32!GetLastError` at `0x140030b3b`
- `KERNEL32!GetLastError` at `0x140030bfa`
- `KERNEL32!GetLastError` at `0x140030c99`
- `KERNEL32!GetLastError` at `0x140030d73`
- `KERNEL32!GetLastError` at `0x140030e04`
- `KERNEL32!GetLastError` at `0x140030e46`
- `KERNEL32!GetLastError` at `0x14003062c`
- `KERNEL32!GetLastError` at `0x140030676`
- `KERNEL32!GetLastError` at `0x1400306e8`
- `KERNEL32!GetLastError` at `0x14003077a`
- `KERNEL32!GetLastError` at `0x140030835`
- `KERNEL32!GetLastError` at `0x1400308e5`
- `KERNEL32!GetLastError` at `0x1400309b8`
- `KERNEL32!GetLastError` at `0x140030a85`
- `KERNEL32!GetLastError` at `0x140030ae0`
- `KERNEL32!GetLastError` at `0x140030b3b`
- `KERNEL32!GetLastError` at `0x140030bfa`
- `KERNEL32!GetLastError` at `0x140030c99`
- `KERNEL32!GetLastError` at `0x140030d73`
- `KERNEL32!GetLastError` at `0x140030e04`
- `KERNEL32!GetLastError` at `0x140030e46`
- `KERNEL32!LocalFree` at `0x140030609`
- `KERNEL32!LocalFree` at `0x140030609`
- `KERNEL32!EnterCriticalSection` at `0x140030791`
- `KERNEL32!EnterCriticalSection` at `0x140030cd8`
- `KERNEL32!EnterCriticalSection` at `0x140030791`
- `KERNEL32!EnterCriticalSection` at `0x140030cd8`
- `KERNEL32!LeaveCriticalSection` at `0x140030d31`
- `KERNEL32!LeaveCriticalSection` at `0x140030d9f`
- `KERNEL32!LeaveCriticalSection` at `0x140030d31`
- `KERNEL32!LeaveCriticalSection` at `0x140030d9f`
- `KERNEL32!PostQueuedCompletionStatus` at `0x140030de2`
- `KERNEL32!PostQueuedCompletionStatus` at `0x140030de2`
- `KERNEL32!GetQueuedCompletionStatus` at `0x1400305a4`
- `KERNEL32!GetQueuedCompletionStatus` at `0x1400305a4`
- `msvcrt!_wcsicmp` at `0x140030b8e`
- `msvcrt!_wcsicmp` at `0x140030b8e`
- `USER32!LoadStringW` at `0x140030bbc`
- `USER32!LoadStringW` at `0x140030bbc`

## pseudocode

```c
__int64 __fastcall FaxStatusThread(void *a1)
{
  _QWORD *v1; // r14
  BOOL QueuedCompletionStatus; // eax
  __int64 v3; // rdx
  LPOVERLAPPED v4; // r8
  DWORD LastError; // eax
  __int64 v6; // rdx
  DWORD v7; // eax
  __int64 v8; // rdx
  int v9; // r8d
  __int64 v10; // rsi
  DWORD v11; // eax
  __int64 v12; // rdx
  bool v13; // zf
  __int64 v14; // rdx
  LPOVERLAPPED v15; // r10
  __int64 v16; // rdx
  int InternalHigh_high; // ecx
  unsigned __int16 *Pointer; // rcx
  __int64 v19; // rax
  DWORD v20; // eax
  unsigned __int16 *hEvent; // rcx
  __int64 v22; // rax
  DWORD v23; // eax
  unsigned __int16 *Internal; // rcx
  __int64 v25; // rax
  DWORD v26; // eax
  HINSTANCE v27; // rcx
  int v28; // edi
  __int64 v29; // rbx
  DWORD v30; // eax
  int v31; // r8d
  DWORD v32; // eax
  __int64 v33; // r8
  __int64 v34; // r9
  DWORD v35; // eax
  int QueueEvent; // eax
  __int64 v37; // rdx
  DWORD v38; // eax
  DWORD v39; // eax
  DWORD dwMilliseconds; // [rsp+20h] [rbp-40h]
  unsigned int v42; // [rsp+40h] [rbp-20h] BYREF
  LPOVERLAPPED Overlapped; // [rsp+48h] [rbp-18h] BYREF
  unsigned __int64 CompletionKey; // [rsp+50h] [rbp-10h] BYREF
  int v45; // [rsp+A8h] [rbp+48h] BYREF
  unsigned int v46; // [rsp+B0h] [rbp+50h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+B8h] [rbp+58h] BYREF

  Overlapped = 0;
  v1 = 0;
  NumberOfBytesTransferred = 0;
  CompletionKey = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
  }
  while ( 1 )
  {
    QueuedCompletionStatus = GetQueuedCompletionStatus(
                               g_StatusCompletionPortHandle,
                               &NumberOfBytesTransferred,
                               &CompletionKey,
                               &Overlapped,
                               0xFFFFFFFF);
    v4 = Overlapped;
    if ( !QueuedCompletionStatus && !Overlapped )
      goto LABEL_21;
    v1 = (_QWORD *)CompletionKey;
    if ( CompletionKey == 0xFFFFFFFF )
      break;
    if ( *(_DWORD *)(CompletionKey + 16) != 1162758476 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          115,
          &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
          (unsigned int)CompletionKey);
        v4 = Overlapped;
      }
      if ( LocalFree(v4)
        && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        v6 = 116;
LABEL_18:
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, LastError);
        goto LABEL_19;
      }
      goto LABEL_19;
    }
    if ( QueuedCompletionStatus )
    {
      if ( LODWORD(Overlapped->Internal) != 56 )
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            119,
            &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
            (unsigned int)Overlapped);
          v4 = Overlapped;
        }
        if ( !(unsigned int)SecureHeapFree(*(_QWORD *)(v1[5] + 2152LL), v3, v4, v1[5] + 64LL, 1)
          && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          LastError = GetLastError();
          v6 = 120;
          goto LABEL_18;
        }
        goto LABEL_19;
      }
      EnterCriticalSection(&g_CsJob);
      v10 = v1[6];
      if ( v10 )
      {
        v13 = *(_DWORD *)(v10 + 1736) == 1;
        v46 = 0;
        v45 = 0;
        if ( v13 )
        {
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            WPP_SF_dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              123,
              &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
              *(unsigned int *)(*(_QWORD *)(v10 + 1104) + 32LL),
              *(_DWORD *)(*(_QWORD *)(v10 + 1104) + 1844LL));
          }
          if ( !(unsigned int)SecureHeapFree(*(_QWORD *)(v1[5] + 2152LL), v8, Overlapped, v1[5] + 64LL, 1)
            && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v11 = GetLastError();
            v12 = 124;
            goto LABEL_121;
          }
        }
        else
        {
          LegacyJobStatusToStatus(HIDWORD(Overlapped->Internal), &v46, &v42, &v45);
          if ( v46 == 10 || v46 <= 7 || v46 >= 0xE )
          {
            FreeFSPIJobStatus((struct _FSPI_JOB_STATUS *)(v10 + 1120), v14);
            memset_0((void *)(v10 + 1124), 0, 0x54u);
            v16 = *(_QWORD *)(v10 + 16);
            *(_DWORD *)(v10 + 1120) = 88;
            *(_DWORD *)(v16 + 72) = HIDWORD(Overlapped->Internal);
            LegacyJobStatusToStatus(
              HIDWORD(Overlapped->Internal),
              (unsigned int *)(v10 + 1128),
              (unsigned int *)(v10 + 1132),
              &v45);
            if ( v45 )
              *(_DWORD *)(v10 + 1124) |= 0x10000000u;
            *(_DWORD *)(v10 + 1136) = Overlapped->InternalHigh;
            InternalHigh_high = HIDWORD(Overlapped->InternalHigh);
            *(_DWORD *)(v10 + 1124) |= 1u;
            *(_DWORD *)(v10 + 1168) = InternalHigh_high;
            Pointer = (unsigned __int16 *)Overlapped->Pointer;
            if ( Pointer )
            {
              v19 = StringDup(Pointer);
              *(_QWORD *)(v10 + 1144) = v19;
              if ( !v19
                && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v20 = GetLastError();
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  127,
                  &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
                  v20);
              }
            }
            hEvent = (unsigned __int16 *)Overlapped->hEvent;
            if ( hEvent )
            {
              v22 = StringDup(hEvent);
              *(_QWORD *)(v10 + 1152) = v22;
              if ( !v22
                && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v23 = GetLastError();
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  128,
                  &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
                  v23);
              }
            }
            Internal = (unsigned __int16 *)Overlapped[1].Internal;
            if ( Internal )
            {
              v25 = StringDup(Internal);
              *(_QWORD *)(v10 + 1160) = v25;
              if ( !v25
                && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v26 = GetLastError();
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  129,
                  &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
                  v26);
              }
            }
            *(_WORD *)(v10 + 1216) = 0;
            if ( *(_DWORD *)(v10 + 1136) )
            {
              v27 = _wcsicmp(
                      (const wchar_t *)(*(_QWORD *)(*(_QWORD *)(v10 + 16) + 40LL) + 1624LL),
                      L"{2172FD8F-11F6-11d3-90BF-006094EB630B}")
                  ? *(HINSTANCE *)(*(_QWORD *)(*(_QWORD *)(v10 + 16) + 40LL) + 56LL)
                  : (HINSTANCE)g_hResource;
              if ( !LoadStringW(v27, *(_DWORD *)(v10 + 1136), (LPWSTR)(v10 + 1216), 256) )
              {
                if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v28 = *(_DWORD *)(v10 + 1136);
                  v29 = *(_QWORD *)(*(_QWORD *)(v10 + 16) + 40LL) + 584LL;
                  v30 = GetLastError();
                  WPP_SF_llS(*((_QWORD *)WPP_GLOBAL_Control + 2), 130, v31, v30, v28, v29);
                }
                *(_DWORD *)(v10 + 1124) &= ~0x10000000u;
                *(_DWORD *)(v10 + 1136) = 0;
                *(_DWORD *)(v10 + 1132) = 0;
              }
            }
            v32 = MapFSPIJobStatusToEventId((const struct _FSPI_JOB_STATUS *)(v10 + 1120));
            v33 = *(_QWORD *)(v10 + 1104);
            if ( *(_DWORD *)(v33 + 36) == 2 )
              v34 = *(_QWORD *)(v33 + 584);
            else
              v34 = *(_QWORD *)(v10 + 1104);
            if ( !(unsigned int)CreateFaxEvent(
                                  *(_DWORD *)(*(_QWORD *)(v10 + 16) + 24LL),
                                  v32,
                                  *(_DWORD *)(v33 + 32),
                                  *(void **)(v34 + 408))
              && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v35 = GetLastError();
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 131, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, v35);
            }
            EnterCriticalSection(&g_CsQueue);
            QueueEvent = CreateQueueEvent(2u, *(_QWORD *)(v10 + 1104));
            if ( QueueEvent
              && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              LOWORD(dwMilliseconds) = QueueEvent;
              WPP_SF_lh(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                132,
                &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
                *(unsigned int *)(*(_QWORD *)(v10 + 1104) + 16LL),
                dwMilliseconds);
            }
            LeaveCriticalSection(&g_CsQueue);
            if ( !(unsigned int)SecureHeapFree(*(_QWORD *)(v1[5] + 2152LL), v37, Overlapped, v1[5] + 64LL, 1)
              && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v11 = GetLastError();
              v12 = 133;
              goto LABEL_121;
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
            {
              WPP_SF_dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                125,
                &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
                *(unsigned int *)(*(_QWORD *)(v10 + 1104) + 32LL),
                v46);
              v15 = Overlapped;
            }
            if ( !(unsigned int)SecureHeapFree(*(_QWORD *)(v1[5] + 2152LL), v14, v15, v1[5] + 64LL, 1)
              && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v11 = GetLastError();
              v12 = 126;
              goto LABEL_121;
            }
          }
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_SDSq(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (_DWORD)Overlapped,
            v9,
            v1[5] + 1104,
            HIDWORD(Overlapped->Internal),
            v1[7],
            (char)Overlapped);
        }
        if ( !(unsigned int)SecureHeapFree(*(_QWORD *)(v1[5] + 2152LL), v8, Overlapped, v1[5] + 64LL, 1)
          && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v11 = GetLastError();
          v12 = 122;
LABEL_121:
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, v11);
        }
      }
      Overlapped = 0;
      LeaveCriticalSection(&g_CsJob);
    }
    else
    {
LABEL_21:
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v7 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 117, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, v7);
        v4 = Overlapped;
      }
      if ( v4 )
      {
        if ( !(unsigned int)SecureHeapFree(*(_QWORD *)(v1[5] + 2152LL), v3, v4, v1[5] + 64LL, 1)
          && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          LastError = GetLastError();
          v6 = 118;
          goto LABEL_18;
        }
LABEL_19:
        Overlapped = 0;
      }
    }
  }
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 113, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
  }
  if ( !PostQueuedCompletionStatus(g_StatusCompletionPortHandle, 0, 0xFFFFFFFF, 0)
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v38 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 114, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, v38);
  }
  if ( !(unsigned int)DecreaseServiceThreadsCount()
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v39 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 134, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, v39);
  }
  return 0;
}

```

## disassembly

```asm
0x140030520  mov     [rsp-38h+arg_0], rbx
0x140030525  push    rbp
0x140030526  push    rsi
0x140030527  push    rdi
0x140030528  push    r12
0x14003052a  push    r13
0x14003052c  push    r14
0x14003052e  push    r15
0x140030530  mov     rbp, rsp
0x140030533  sub     rsp, 60h
0x140030537  xor     r13d, r13d
0x14003053a  mov     [rbp+Overlapped], r13
0x14003053e  mov     r14d, r13d
0x140030541  mov     [rbp+NumberOfBytesTransferred], r13d
0x140030545  mov     [rbp+CompletionKey], r13
0x140030549  mov     rcx, cs:WPP_GLOBAL_Control
0x140030550  lea     rbx, WPP_GLOBAL_Control
0x140030557  lea     r12, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14003055e  mov     dil, 4
0x140030561  cmp     rcx, rbx
0x140030564  jz      short loc_140030582
0x140030566  test    [rcx+1Ch], dil
0x14003056a  jz      short loc_140030582
0x14003056c  cmp     byte ptr [rcx+19h], 5
0x140030570  jb      short loc_140030582
0x140030572  mov     rcx, [rcx+10h]
0x140030576  lea     edx, [r13+70h]
0x14003057a  mov     r8, r12
0x14003057d  call    WPP_SF_
0x140030582  mov     r15d, 2
0x140030588  mov     esi, 0FFFFFFFFh
0x14003058d  mov     rcx, cs:?g_StatusCompletionPortHandle@@3PEAXEA; CompletionPort
0x140030594  lea     r9, [rbp+Overlapped]; lpOverlapped
0x140030598  lea     r8, [rbp+CompletionKey]; lpCompletionKey
0x14003059c  mov     [rsp+60h+dwMilliseconds], esi; dwMilliseconds
0x1400305a0  lea     rdx, [rbp+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x1400305a4  call    cs:__imp_GetQueuedCompletionStatus
0x1400305aa  mov     r8, [rbp+Overlapped]
0x1400305ae  test    eax, eax
0x1400305b0  jnz     short loc_1400305BB
0x1400305b2  test    r8, r8
0x1400305b5  jz      loc_14003065E
0x1400305bb  mov     r14, [rbp+CompletionKey]
0x1400305bf  cmp     r14, rsi
0x1400305c2  jz      loc_140030DAA
0x1400305c8  cmp     dword ptr [r14+10h], 454E494Ch
0x1400305d0  jz      loc_140030656
0x1400305d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400305dd  cmp     rcx, rbx
0x1400305e0  jz      short loc_140030606
0x1400305e2  test    [rcx+1Ch], dil
0x1400305e6  jz      short loc_140030606
0x1400305e8  cmp     byte ptr [rcx+19h], 3
0x1400305ec  jb      short loc_140030606
0x1400305ee  mov     rcx, [rcx+10h]
0x1400305f2  mov     edx, 73h ; 's'
0x1400305f7  mov     r9d, r14d
0x1400305fa  mov     r8, r12
0x1400305fd  call    WPP_SF_d
0x140030602  mov     r8, [rbp+Overlapped]
0x140030606  mov     rcx, r8; hMem
0x140030609  call    cs:__imp_LocalFree
0x14003060f  test    rax, rax
0x140030612  jz      short loc_14003064D
0x140030614  mov     rax, cs:WPP_GLOBAL_Control
0x14003061b  cmp     rax, rbx
0x14003061e  jz      short loc_14003064D
0x140030620  test    [rax+1Ch], dil
0x140030624  jz      short loc_14003064D
0x140030626  cmp     [rax+19h], r15b
0x14003062a  jb      short loc_14003064D
0x14003062c  call    cs:__imp_GetLastError
0x140030632  mov     edx, 74h ; 't'
0x140030637  mov     rcx, cs:WPP_GLOBAL_Control
0x14003063e  mov     r9d, eax
0x140030641  mov     r8, r12
0x140030644  mov     rcx, [rcx+10h]
0x140030648  call    WPP_SF_d
0x14003064d  mov     [rbp+Overlapped], r13
0x140030651  jmp     loc_14003058D
0x140030656  test    eax, eax
0x140030658  jnz     loc_1400306F8
0x14003065e  mov     rax, cs:WPP_GLOBAL_Control
0x140030665  cmp     rax, rbx
0x140030668  jz      short loc_14003069B
0x14003066a  test    [rax+1Ch], dil
0x14003066e  jz      short loc_14003069B
0x140030670  cmp     [rax+19h], r15b
0x140030674  jb      short loc_14003069B
0x140030676  call    cs:__imp_GetLastError
0x14003067c  mov     rcx, cs:WPP_GLOBAL_Control
0x140030683  mov     edx, 75h ; 'u'
0x140030688  mov     r9d, eax
0x14003068b  mov     r8, r12
0x14003068e  mov     rcx, [rcx+10h]
0x140030692  call    WPP_SF_d
0x140030697  mov     r8, [rbp+Overlapped]
0x14003069b  test    r8, r8
0x14003069e  jz      loc_14003058D
0x1400306a4  mov     rcx, [r14+28h]
0x1400306a8  mov     [rsp+60h+dwMilliseconds], 1
0x1400306b0  lea     r9, [rcx+40h]
0x1400306b4  mov     rcx, [rcx+868h]
0x1400306bb  call    ?SecureHeapFree@@YAHPEAXK0PEBGW4EXCEPTION_SOURCE_TYPE@@@Z; SecureHeapFree(void *,ulong,void *,ushort const *,EXCEPTION_SOURCE_TYPE)
0x1400306c0  test    eax, eax
0x1400306c2  jnz     short loc_14003064D
0x1400306c4  mov     rax, cs:WPP_GLOBAL_Control
0x1400306cb  cmp     rax, rbx
0x1400306ce  jz      loc_14003064D
0x1400306d4  test    [rax+1Ch], dil
0x1400306d8  jz      loc_14003064D
0x1400306de  cmp     [rax+19h], r15b
0x1400306e2  jb      loc_14003064D
0x1400306e8  call    cs:__imp_GetLastError
0x1400306ee  mov     edx, 76h ; 'v'
0x1400306f3  jmp     loc_140030637
0x1400306f8  cmp     dword ptr [r8], 38h ; '8'
0x1400306fc  jz      loc_14003078A
0x140030702  mov     rcx, cs:WPP_GLOBAL_Control
0x140030709  cmp     rcx, rbx
0x14003070c  jz      short loc_140030732
0x14003070e  test    [rcx+1Ch], dil
0x140030712  jz      short loc_140030732
0x140030714  cmp     byte ptr [rcx+19h], 3
0x140030718  jb      short loc_140030732
0x14003071a  mov     rcx, [rcx+10h]
0x14003071e  mov     r9d, r8d
0x140030721  mov     r8, r12
0x140030724  mov     edx, 77h ; 'w'
0x140030729  call    WPP_SF_d
0x14003072e  mov     r8, [rbp+Overlapped]
0x140030732  mov     rcx, [r14+28h]
0x140030736  mov     [rsp+60h+dwMilliseconds], 1
0x14003073e  lea     r9, [rcx+40h]
0x140030742  mov     rcx, [rcx+868h]
0x140030749  call    ?SecureHeapFree@@YAHPEAXK0PEBGW4EXCEPTION_SOURCE_TYPE@@@Z; SecureHeapFree(void *,ulong,void *,ushort const *,EXCEPTION_SOURCE_TYPE)
0x14003074e  test    eax, eax
0x140030750  jnz     loc_14003064D
0x140030756  mov     rax, cs:WPP_GLOBAL_Control
0x14003075d  cmp     rax, rbx
0x140030760  jz      loc_14003064D
0x140030766  test    [rax+1Ch], dil
0x14003076a  jz      loc_14003064D
0x140030770  cmp     [rax+19h], r15b
0x140030774  jb      loc_14003064D
0x14003077a  call    cs:__imp_GetLastError
0x140030780  mov     edx, 78h ; 'x'
0x140030785  jmp     loc_140030637
0x14003078a  lea     rcx, ?g_CsJob@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140030791  call    cs:__imp_EnterCriticalSection
0x140030797  mov     rsi, [r14+30h]
0x14003079b  test    rsi, rsi
0x14003079e  jnz     loc_140030845
0x1400307a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400307ab  cmp     rcx, rbx
0x1400307ae  jz      short loc_1400307E9
0x1400307b0  test    [rcx+1Ch], dil
0x1400307b4  jz      short loc_1400307E9
0x1400307b6  cmp     byte ptr [rcx+19h], 3
0x1400307ba  jb      short loc_1400307E9
0x1400307bc  mov     rdx, [rbp+Overlapped]
0x1400307c0  mov     rax, [r14+38h]
0x1400307c4  mov     r9, [r14+28h]
0x1400307c8  mov     rcx, [rcx+10h]
0x1400307cc  add     r9, 450h
0x1400307d3  mov     [rsp+60h+var_30], rdx
0x1400307d8  mov     [rsp+60h+var_38], rax
0x1400307dd  mov     eax, [rdx+4]
0x1400307e0  mov     [rsp+60h+dwMilliseconds], eax
0x1400307e4  call    WPP_SF_SDSq
0x1400307e9  mov     rcx, [r14+28h]
0x1400307ed  mov     r8, [rbp+Overlapped]
0x1400307f1  mov     [rsp+60h+dwMilliseconds], 1
0x1400307f9  lea     r9, [rcx+40h]
0x1400307fd  mov     rcx, [rcx+868h]
0x140030804  call    ?SecureHeapFree@@YAHPEAXK0PEBGW4EXCEPTION_SOURCE_TYPE@@@Z; SecureHeapFree(void *,ulong,void *,ushort const *,EXCEPTION_SOURCE_TYPE)
0x140030809  test    eax, eax
0x14003080b  jnz     loc_140030D94
0x140030811  mov     rax, cs:WPP_GLOBAL_Control
0x140030818  cmp     rax, rbx
0x14003081b  jz      loc_140030D94
0x140030821  test    [rax+1Ch], dil
0x140030825  jz      loc_140030D94
0x14003082b  cmp     [rax+19h], r15b
0x14003082f  jb      loc_140030D94
0x140030835  call    cs:__imp_GetLastError
0x14003083b  mov     edx, 7Ah ; 'z'
0x140030840  jmp     loc_140030D7E
0x140030845  cmp     dword ptr [rsi+6C8h], 1
0x14003084c  mov     [rbp+arg_10], r13d
0x140030850  mov     [rbp+arg_8], r13d
0x140030854  jnz     loc_1400308F5
0x14003085a  mov     rcx, cs:WPP_GLOBAL_Control
0x140030861  cmp     rcx, rbx
0x140030864  jz      short loc_140030899
0x140030866  test    [rcx+1Ch], dil
0x14003086a  jz      short loc_140030899
0x14003086c  cmp     byte ptr [rcx+19h], 3
0x140030870  jb      short loc_140030899
0x140030872  mov     r9, [rsi+450h]
0x140030879  mov     edx, 7Bh ; '{'
0x14003087e  mov     rcx, [rcx+10h]
0x140030882  mov     r8, r12
0x140030885  mov     eax, [r9+734h]
0x14003088c  mov     r9d, [r9+20h]
0x140030890  mov     [rsp+60h+dwMilliseconds], eax
0x140030894  call    WPP_SF_dd
0x140030899  mov     rcx, [r14+28h]
0x14003089d  mov     r8, [rbp+Overlapped]
0x1400308a1  mov     [rsp+60h+dwMilliseconds], 1
0x1400308a9  lea     r9, [rcx+40h]
0x1400308ad  mov     rcx, [rcx+868h]
0x1400308b4  call    ?SecureHeapFree@@YAHPEAXK0PEBGW4EXCEPTION_SOURCE_TYPE@@@Z; SecureHeapFree(void *,ulong,void *,ushort const *,EXCEPTION_SOURCE_TYPE)
0x1400308b9  test    eax, eax
0x1400308bb  jnz     loc_140030D94
0x1400308c1  mov     rax, cs:WPP_GLOBAL_Control
0x1400308c8  cmp     rax, rbx
0x1400308cb  jz      loc_140030D94
0x1400308d1  test    [rax+1Ch], dil
0x1400308d5  jz      loc_140030D94
0x1400308db  cmp     [rax+19h], r15b
0x1400308df  jb      loc_140030D94
0x1400308e5  call    cs:__imp_GetLastError
0x1400308eb  mov     edx, 7Ch ; '|'
0x1400308f0  jmp     loc_140030D7E
0x1400308f5  mov     r10, [rbp+Overlapped]
0x1400308f9  lea     r9, [rbp+arg_8]; int *
0x1400308fd  lea     r8, [rbp+var_20]; unsigned int *
0x140030901  lea     rdx, [rbp+arg_10]; unsigned int *
0x140030905  mov     ecx, [r10+4]; unsigned int
0x140030909  call    ?LegacyJobStatusToStatus@@YAKKPEAK0PEAH@Z; LegacyJobStatusToStatus(ulong,ulong *,ulong *,int *)
0x14003090e  mov     r8d, [rbp+arg_10]
0x140030912  cmp     r8d, 0Ah
0x140030916  jz      loc_1400309C8
0x14003091c  cmp     r8d, 7
0x140030920  jbe     loc_1400309C8
0x140030926  cmp     r8d, 0Eh
0x14003092a  jnb     loc_1400309C8
0x140030930  mov     rcx, cs:WPP_GLOBAL_Control
0x140030937  cmp     rcx, rbx
0x14003093a  jz      short loc_14003096D
0x14003093c  test    [rcx+1Ch], dil
0x140030940  jz      short loc_14003096D
0x140030942  cmp     byte ptr [rcx+19h], 3
0x140030946  jb      short loc_14003096D
0x140030948  mov     r9, [rsi+450h]
0x14003094f  mov     edx, 7Dh ; '}'
0x140030954  mov     rcx, [rcx+10h]
0x140030958  mov     [rsp+60h+dwMilliseconds], r8d
0x14003095d  mov     r8, r12
0x140030960  mov     r9d, [r9+20h]
0x140030964  call    WPP_SF_dd
0x140030969  mov     r10, [rbp+Overlapped]
0x14003096d  mov     rcx, [r14+28h]
0x140030971  mov     r8, r10
0x140030974  mov     [rsp+60h+dwMilliseconds], 1
0x14003097c  lea     r9, [rcx+40h]
0x140030980  mov     rcx, [rcx+868h]
0x140030987  call    ?SecureHeapFree@@YAHPEAXK0PEBGW4EXCEPTION_SOURCE_TYPE@@@Z; SecureHeapFree(void *,ulong,void *,ushort const *,EXCEPTION_SOURCE_TYPE)
0x14003098c  test    eax, eax
0x14003098e  jnz     loc_140030D94
0x140030994  mov     rax, cs:WPP_GLOBAL_Control
0x14003099b  cmp     rax, rbx
0x14003099e  jz      loc_140030D94
0x1400309a4  test    [rax+1Ch], dil
0x1400309a8  jz      loc_140030D94
0x1400309ae  cmp     [rax+19h], r15b
0x1400309b2  jb      loc_140030D94
0x1400309b8  call    cs:__imp_GetLastError
0x1400309be  mov     edx, 7Eh ; '~'
0x1400309c3  jmp     loc_140030D7E
0x1400309c8  lea     r12, [rsi+460h]
0x1400309cf  mov     rcx, r12; struct _FSPI_JOB_STATUS *
0x1400309d2  call    ?FreeFSPIJobStatus@@YAHPEAU_FSPI_JOB_STATUS@@H@Z; FreeFSPIJobStatus(_FSPI_JOB_STATUS *,int)
0x1400309d7  xor     edx, edx; Val
0x1400309d9  lea     rcx, [rsi+464h]; void *
0x1400309e0  lea     r8d, [rdx+54h]; Size
0x1400309e4  call    memset_0
0x1400309e9  mov     rdx, [rsi+10h]
0x1400309ed  lea     r15, [rsi+46Ch]
0x1400309f4  mov     dword ptr [r12], 58h ; 'X'
0x1400309fc  lea     r9, [rbp+arg_8]; int *
0x140030a00  mov     rax, [rbp+Overlapped]
0x140030a04  mov     r8, r15; unsigned int *
0x140030a07  mov     ecx, [rax+4]
0x140030a0a  mov     [rdx+48h], ecx
0x140030a0d  lea     rdx, [rsi+468h]; unsigned int *
0x140030a14  mov     rcx, [rbp+Overlapped]
0x140030a18  mov     ecx, [rcx+4]; unsigned int
0x140030a1b  call    ?LegacyJobStatusToStatus@@YAKKPEAK0PEAH@Z; LegacyJobStatusToStatus(ulong,ulong *,ulong *,int *)
0x140030a20  cmp     [rbp+arg_8], r13d
0x140030a24  jz      short loc_140030A2E
0x140030a26  bts     dword ptr [rsi+464h], 1Ch
0x140030a2e  mov     rax, [rbp+Overlapped]
0x140030a32  mov     ecx, [rax+8]
0x140030a35  mov     [rsi+470h], ecx
0x140030a3b  mov     rax, [rbp+Overlapped]
0x140030a3f  mov     ecx, [rax+0Ch]
0x140030a42  or      dword ptr [rsi+464h], 1
0x140030a49  mov     [rsi+490h], ecx
  ... truncated ...
```
