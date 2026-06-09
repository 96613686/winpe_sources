# FaxStatusThread(void *)

- ea: `0x140031d80`
- end: `0x140032772`
- name: `?FaxStatusThread@@YAKPEAX@Z`
- size: `2546`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callees

- `0x140002c73`
- `0x1400034d4`
- `0x140004c78`
- `0x140004ca8`
- `0x140004fe4`
- `0x140023a0c`
- `0x140031d80`
- `0x140036c68`
- `0x140037224`
- `0x140052184`
- `0x1400535fc`
- `0x140053938`
- `0x140053bc8`
- `0x140058d78`
- `0x14005900c`
- `0x14006af2c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140031e98`
- `KERNEL32!GetLastError` at `0x140031ee8`
- `KERNEL32!GetLastError` at `0x140031f60`
- `KERNEL32!GetLastError` at `0x140031ff8`
- `KERNEL32!GetLastError` at `0x1400320bf`
- `KERNEL32!GetLastError` at `0x140032175`
- `KERNEL32!GetLastError` at `0x14003224e`
- `KERNEL32!GetLastError` at `0x140032321`
- `KERNEL32!GetLastError` at `0x140032382`
- `KERNEL32!GetLastError` at `0x1400323e3`
- `KERNEL32!GetLastError` at `0x1400324b4`
- `KERNEL32!GetLastError` at `0x140032559`
- `KERNEL32!GetLastError` at `0x140032645`
- `KERNEL32!GetLastError` at `0x1400326e8`
- `KERNEL32!GetLastError` at `0x140032730`
- `KERNEL32!GetLastError` at `0x140031e98`
- `KERNEL32!GetLastError` at `0x140031ee8`
- `KERNEL32!GetLastError` at `0x140031f60`
- `KERNEL32!GetLastError` at `0x140031ff8`
- `KERNEL32!GetLastError` at `0x1400320bf`
- `KERNEL32!GetLastError` at `0x140032175`
- `KERNEL32!GetLastError` at `0x14003224e`
- `KERNEL32!GetLastError` at `0x140032321`
- `KERNEL32!GetLastError` at `0x140032382`
- `KERNEL32!GetLastError` at `0x1400323e3`
- `KERNEL32!GetLastError` at `0x1400324b4`
- `KERNEL32!GetLastError` at `0x140032559`
- `KERNEL32!GetLastError` at `0x140032645`
- `KERNEL32!GetLastError` at `0x1400326e8`
- `KERNEL32!GetLastError` at `0x140032730`
- `KERNEL32!LocalFree` at `0x140031e6f`
- `KERNEL32!LocalFree` at `0x140031e6f`
- `KERNEL32!EnterCriticalSection` at `0x140032015`
- `KERNEL32!EnterCriticalSection` at `0x14003259e`
- `KERNEL32!EnterCriticalSection` at `0x140032015`
- `KERNEL32!EnterCriticalSection` at `0x14003259e`
- `KERNEL32!LeaveCriticalSection` at `0x1400325fd`
- `KERNEL32!LeaveCriticalSection` at `0x140032677`
- `KERNEL32!LeaveCriticalSection` at `0x1400325fd`
- `KERNEL32!LeaveCriticalSection` at `0x140032677`
- `KERNEL32!PostQueuedCompletionStatus` at `0x1400326c0`
- `KERNEL32!PostQueuedCompletionStatus` at `0x1400326c0`
- `KERNEL32!GetQueuedCompletionStatus` at `0x140031e04`
- `KERNEL32!GetQueuedCompletionStatus` at `0x140031e04`
- `msvcrt!_wcsicmp` at `0x14003243c`
- `msvcrt!_wcsicmp` at `0x14003243c`
- `USER32!LoadStringW` at `0x140032470`
- `USER32!LoadStringW` at `0x140032470`

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
  unsigned __int16 *v19; // rax
  DWORD v20; // eax
  unsigned __int16 *hEvent; // rcx
  unsigned __int16 *v22; // rax
  DWORD v23; // eax
  unsigned __int16 *Internal; // rcx
  unsigned __int16 *v25; // rax
  DWORD v26; // eax
  HINSTANCE v27; // rcx
  int v28; // edi
  __int64 v29; // rbx
  DWORD v30; // eax
  int v31; // r8d
  unsigned int v32; // eax
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
            WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 123, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
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
            if ( !CreateFaxEvent(
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
            QueueEvent = CreateQueueEvent(2, *(_QWORD *)(v10 + 1104));
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
              WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 125, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
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
0x140031d80  mov     [rsp-38h+arg_0], rbx
0x140031d85  push    rbp
0x140031d86  push    rsi
0x140031d87  push    rdi
0x140031d88  push    r12
0x140031d8a  push    r13
0x140031d8c  push    r14
0x140031d8e  push    r15
0x140031d90  mov     rbp, rsp
0x140031d93  sub     rsp, 60h
0x140031d97  xor     r13d, r13d
0x140031d9a  mov     [rbp+Overlapped], r13
0x140031d9e  mov     r14d, r13d
0x140031da1  mov     [rbp+NumberOfBytesTransferred], r13d
0x140031da5  mov     [rbp+CompletionKey], r13
0x140031da9  mov     rcx, cs:WPP_GLOBAL_Control
0x140031db0  lea     rbx, WPP_GLOBAL_Control
0x140031db7  lea     r12, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x140031dbe  mov     dil, 4
0x140031dc1  cmp     rcx, rbx
0x140031dc4  jz      short loc_140031DE2
0x140031dc6  test    [rcx+1Ch], dil
0x140031dca  jz      short loc_140031DE2
0x140031dcc  cmp     byte ptr [rcx+19h], 5
0x140031dd0  jb      short loc_140031DE2
0x140031dd2  mov     rcx, [rcx+10h]
0x140031dd6  lea     edx, [r13+70h]
0x140031dda  mov     r8, r12
0x140031ddd  call    WPP_SF_
0x140031de2  mov     r15d, 2
0x140031de8  mov     esi, 0FFFFFFFFh
0x140031ded  mov     rcx, cs:?g_StatusCompletionPortHandle@@3PEAXEA; CompletionPort
0x140031df4  lea     r9, [rbp+Overlapped]; lpOverlapped
0x140031df8  lea     r8, [rbp+CompletionKey]; lpCompletionKey
0x140031dfc  mov     [rsp+60h+dwMilliseconds], esi; dwMilliseconds
0x140031e00  lea     rdx, [rbp+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x140031e04  call    cs:__imp_GetQueuedCompletionStatus
0x140031e0b  nop     dword ptr [rax+rax+00h]
0x140031e10  mov     r8, [rbp+Overlapped]
0x140031e14  test    eax, eax
0x140031e16  jnz     short loc_140031E21
0x140031e18  test    r8, r8
0x140031e1b  jz      loc_140031ED0
0x140031e21  mov     r14, [rbp+CompletionKey]
0x140031e25  cmp     r14, rsi
0x140031e28  jz      loc_140032688
0x140031e2e  cmp     dword ptr [r14+10h], 454E494Ch
0x140031e36  jz      loc_140031EC8
0x140031e3c  mov     rcx, cs:WPP_GLOBAL_Control
0x140031e43  cmp     rcx, rbx
0x140031e46  jz      short loc_140031E6C
0x140031e48  test    [rcx+1Ch], dil
0x140031e4c  jz      short loc_140031E6C
0x140031e4e  cmp     byte ptr [rcx+19h], 3
0x140031e52  jb      short loc_140031E6C
0x140031e54  mov     rcx, [rcx+10h]
0x140031e58  mov     edx, 73h ; 's'
0x140031e5d  mov     r9d, r14d
0x140031e60  mov     r8, r12
0x140031e63  call    WPP_SF_d
0x140031e68  mov     r8, [rbp+Overlapped]
0x140031e6c  mov     rcx, r8; hMem
0x140031e6f  call    cs:__imp_LocalFree
0x140031e76  nop     dword ptr [rax+rax+00h]
0x140031e7b  test    rax, rax
0x140031e7e  jz      short loc_140031EBF
0x140031e80  mov     rax, cs:WPP_GLOBAL_Control
0x140031e87  cmp     rax, rbx
0x140031e8a  jz      short loc_140031EBF
0x140031e8c  test    [rax+1Ch], dil
0x140031e90  jz      short loc_140031EBF
0x140031e92  cmp     [rax+19h], r15b
0x140031e96  jb      short loc_140031EBF
0x140031e98  call    cs:__imp_GetLastError
0x140031e9f  nop     dword ptr [rax+rax+00h]
0x140031ea4  mov     edx, 74h ; 't'
0x140031ea9  mov     rcx, cs:WPP_GLOBAL_Control
0x140031eb0  mov     r9d, eax
0x140031eb3  mov     r8, r12
0x140031eb6  mov     rcx, [rcx+10h]
0x140031eba  call    WPP_SF_d
0x140031ebf  mov     [rbp+Overlapped], r13
0x140031ec3  jmp     loc_140031DED
0x140031ec8  test    eax, eax
0x140031eca  jnz     loc_140031F76
0x140031ed0  mov     rax, cs:WPP_GLOBAL_Control
0x140031ed7  cmp     rax, rbx
0x140031eda  jz      short loc_140031F13
0x140031edc  test    [rax+1Ch], dil
0x140031ee0  jz      short loc_140031F13
0x140031ee2  cmp     [rax+19h], r15b
0x140031ee6  jb      short loc_140031F13
0x140031ee8  call    cs:__imp_GetLastError
0x140031eef  nop     dword ptr [rax+rax+00h]
0x140031ef4  mov     rcx, cs:WPP_GLOBAL_Control
0x140031efb  mov     edx, 75h ; 'u'
0x140031f00  mov     r9d, eax
0x140031f03  mov     r8, r12
0x140031f06  mov     rcx, [rcx+10h]
0x140031f0a  call    WPP_SF_d
0x140031f0f  mov     r8, [rbp+Overlapped]
0x140031f13  test    r8, r8
0x140031f16  jz      loc_140031DED
0x140031f1c  mov     rcx, [r14+28h]
0x140031f20  mov     [rsp+60h+dwMilliseconds], 1
0x140031f28  lea     r9, [rcx+40h]
0x140031f2c  mov     rcx, [rcx+868h]
0x140031f33  call    ?SecureHeapFree@@YAHPEAXK0PEBGW4EXCEPTION_SOURCE_TYPE@@@Z; SecureHeapFree(void *,ulong,void *,ushort const *,EXCEPTION_SOURCE_TYPE)
0x140031f38  test    eax, eax
0x140031f3a  jnz     short loc_140031EBF
0x140031f3c  mov     rax, cs:WPP_GLOBAL_Control
0x140031f43  cmp     rax, rbx
0x140031f46  jz      loc_140031EBF
0x140031f4c  test    [rax+1Ch], dil
0x140031f50  jz      loc_140031EBF
0x140031f56  cmp     [rax+19h], r15b
0x140031f5a  jb      loc_140031EBF
0x140031f60  call    cs:__imp_GetLastError
0x140031f67  nop     dword ptr [rax+rax+00h]
0x140031f6c  mov     edx, 76h ; 'v'
0x140031f71  jmp     loc_140031EA9
0x140031f76  cmp     dword ptr [r8], 38h ; '8'
0x140031f7a  jz      loc_14003200E
0x140031f80  mov     rcx, cs:WPP_GLOBAL_Control
0x140031f87  cmp     rcx, rbx
0x140031f8a  jz      short loc_140031FB0
0x140031f8c  test    [rcx+1Ch], dil
0x140031f90  jz      short loc_140031FB0
0x140031f92  cmp     byte ptr [rcx+19h], 3
0x140031f96  jb      short loc_140031FB0
0x140031f98  mov     rcx, [rcx+10h]
0x140031f9c  mov     r9d, r8d
0x140031f9f  mov     r8, r12
0x140031fa2  mov     edx, 77h ; 'w'
0x140031fa7  call    WPP_SF_d
0x140031fac  mov     r8, [rbp+Overlapped]
0x140031fb0  mov     rcx, [r14+28h]
0x140031fb4  mov     [rsp+60h+dwMilliseconds], 1
0x140031fbc  lea     r9, [rcx+40h]
0x140031fc0  mov     rcx, [rcx+868h]
0x140031fc7  call    ?SecureHeapFree@@YAHPEAXK0PEBGW4EXCEPTION_SOURCE_TYPE@@@Z; SecureHeapFree(void *,ulong,void *,ushort const *,EXCEPTION_SOURCE_TYPE)
0x140031fcc  test    eax, eax
0x140031fce  jnz     loc_140031EBF
0x140031fd4  mov     rax, cs:WPP_GLOBAL_Control
0x140031fdb  cmp     rax, rbx
0x140031fde  jz      loc_140031EBF
0x140031fe4  test    [rax+1Ch], dil
0x140031fe8  jz      loc_140031EBF
0x140031fee  cmp     [rax+19h], r15b
0x140031ff2  jb      loc_140031EBF
0x140031ff8  call    cs:__imp_GetLastError
0x140031fff  nop     dword ptr [rax+rax+00h]
0x140032004  mov     edx, 78h ; 'x'
0x140032009  jmp     loc_140031EA9
0x14003200e  lea     rcx, ?g_CsJob@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140032015  call    cs:__imp_EnterCriticalSection
0x14003201c  nop     dword ptr [rax+rax+00h]
0x140032021  mov     rsi, [r14+30h]
0x140032025  test    rsi, rsi
0x140032028  jnz     loc_1400320D5
0x14003202e  mov     rcx, cs:WPP_GLOBAL_Control
0x140032035  cmp     rcx, rbx
0x140032038  jz      short loc_140032073
0x14003203a  test    [rcx+1Ch], dil
0x14003203e  jz      short loc_140032073
0x140032040  cmp     byte ptr [rcx+19h], 3
0x140032044  jb      short loc_140032073
0x140032046  mov     rdx, [rbp+Overlapped]
0x14003204a  mov     rax, [r14+38h]
0x14003204e  mov     r9, [r14+28h]
0x140032052  mov     rcx, [rcx+10h]
0x140032056  add     r9, 450h
0x14003205d  mov     [rsp+60h+var_30], rdx
0x140032062  mov     [rsp+60h+var_38], rax
0x140032067  mov     eax, [rdx+4]
0x14003206a  mov     [rsp+60h+dwMilliseconds], eax
0x14003206e  call    WPP_SF_SDSq
0x140032073  mov     rcx, [r14+28h]
0x140032077  mov     r8, [rbp+Overlapped]
0x14003207b  mov     [rsp+60h+dwMilliseconds], 1
0x140032083  lea     r9, [rcx+40h]
0x140032087  mov     rcx, [rcx+868h]
0x14003208e  call    ?SecureHeapFree@@YAHPEAXK0PEBGW4EXCEPTION_SOURCE_TYPE@@@Z; SecureHeapFree(void *,ulong,void *,ushort const *,EXCEPTION_SOURCE_TYPE)
0x140032093  test    eax, eax
0x140032095  jnz     loc_14003266C
0x14003209b  mov     rax, cs:WPP_GLOBAL_Control
0x1400320a2  cmp     rax, rbx
0x1400320a5  jz      loc_14003266C
0x1400320ab  test    [rax+1Ch], dil
0x1400320af  jz      loc_14003266C
0x1400320b5  cmp     [rax+19h], r15b
0x1400320b9  jb      loc_14003266C
0x1400320bf  call    cs:__imp_GetLastError
0x1400320c6  nop     dword ptr [rax+rax+00h]
0x1400320cb  mov     edx, 7Ah ; 'z'
0x1400320d0  jmp     loc_140032656
0x1400320d5  cmp     dword ptr [rsi+6C8h], 1
0x1400320dc  mov     [rbp+arg_10], r13d
0x1400320e0  mov     [rbp+arg_8], r13d
0x1400320e4  jnz     loc_14003218B
0x1400320ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400320f1  cmp     rcx, rbx
0x1400320f4  jz      short loc_140032129
0x1400320f6  test    [rcx+1Ch], dil
0x1400320fa  jz      short loc_140032129
0x1400320fc  cmp     byte ptr [rcx+19h], 3
0x140032100  jb      short loc_140032129
0x140032102  mov     r9, [rsi+450h]
0x140032109  mov     edx, 7Bh ; '{'
0x14003210e  mov     rcx, [rcx+10h]
0x140032112  mov     r8, r12
0x140032115  mov     eax, [r9+734h]
0x14003211c  mov     r9d, [r9+20h]
0x140032120  mov     [rsp+60h+dwMilliseconds], eax
0x140032124  call    WPP_SF_dd
0x140032129  mov     rcx, [r14+28h]
0x14003212d  mov     r8, [rbp+Overlapped]
0x140032131  mov     [rsp+60h+dwMilliseconds], 1
0x140032139  lea     r9, [rcx+40h]
0x14003213d  mov     rcx, [rcx+868h]
0x140032144  call    ?SecureHeapFree@@YAHPEAXK0PEBGW4EXCEPTION_SOURCE_TYPE@@@Z; SecureHeapFree(void *,ulong,void *,ushort const *,EXCEPTION_SOURCE_TYPE)
0x140032149  test    eax, eax
0x14003214b  jnz     loc_14003266C
0x140032151  mov     rax, cs:WPP_GLOBAL_Control
0x140032158  cmp     rax, rbx
0x14003215b  jz      loc_14003266C
0x140032161  test    [rax+1Ch], dil
0x140032165  jz      loc_14003266C
0x14003216b  cmp     [rax+19h], r15b
0x14003216f  jb      loc_14003266C
0x140032175  call    cs:__imp_GetLastError
0x14003217c  nop     dword ptr [rax+rax+00h]
0x140032181  mov     edx, 7Ch ; '|'
0x140032186  jmp     loc_140032656
0x14003218b  mov     r10, [rbp+Overlapped]
0x14003218f  lea     r9, [rbp+arg_8]; int *
0x140032193  lea     r8, [rbp+var_20]; unsigned int *
0x140032197  lea     rdx, [rbp+arg_10]; unsigned int *
0x14003219b  mov     ecx, [r10+4]; unsigned int
0x14003219f  call    ?LegacyJobStatusToStatus@@YAKKPEAK0PEAH@Z; LegacyJobStatusToStatus(ulong,ulong *,ulong *,int *)
0x1400321a4  mov     r8d, [rbp+arg_10]
0x1400321a8  cmp     r8d, 0Ah
0x1400321ac  jz      loc_140032264
0x1400321b2  cmp     r8d, 7
0x1400321b6  jbe     loc_140032264
0x1400321bc  cmp     r8d, 0Eh
0x1400321c0  jnb     loc_140032264
0x1400321c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400321cd  cmp     rcx, rbx
0x1400321d0  jz      short loc_140032203
0x1400321d2  test    [rcx+1Ch], dil
0x1400321d6  jz      short loc_140032203
0x1400321d8  cmp     byte ptr [rcx+19h], 3
0x1400321dc  jb      short loc_140032203
0x1400321de  mov     r9, [rsi+450h]
0x1400321e5  mov     edx, 7Dh ; '}'
0x1400321ea  mov     rcx, [rcx+10h]
0x1400321ee  mov     [rsp+60h+dwMilliseconds], r8d
0x1400321f3  mov     r8, r12
0x1400321f6  mov     r9d, [r9+20h]
0x1400321fa  call    WPP_SF_dd
0x1400321ff  mov     r10, [rbp+Overlapped]
0x140032203  mov     rcx, [r14+28h]
0x140032207  mov     r8, r10
0x14003220a  mov     [rsp+60h+dwMilliseconds], 1
0x140032212  lea     r9, [rcx+40h]
0x140032216  mov     rcx, [rcx+868h]
0x14003221d  call    ?SecureHeapFree@@YAHPEAXK0PEBGW4EXCEPTION_SOURCE_TYPE@@@Z; SecureHeapFree(void *,ulong,void *,ushort const *,EXCEPTION_SOURCE_TYPE)
0x140032222  test    eax, eax
0x140032224  jnz     loc_14003266C
0x14003222a  mov     rax, cs:WPP_GLOBAL_Control
0x140032231  cmp     rax, rbx
0x140032234  jz      loc_14003266C
0x14003223a  test    [rax+1Ch], dil
0x14003223e  jz      loc_14003266C
0x140032244  cmp     [rax+19h], r15b
0x140032248  jb      loc_14003266C
0x14003224e  call    cs:__imp_GetLastError
0x140032255  nop     dword ptr [rax+rax+00h]
0x14003225a  mov     edx, 7Eh ; '~'
0x14003225f  jmp     loc_140032656
0x140032264  lea     r12, [rsi+460h]
0x14003226b  mov     rcx, r12; struct _FSPI_JOB_STATUS *
0x14003226e  call    ?FreeFSPIJobStatus@@YAHPEAU_FSPI_JOB_STATUS@@H@Z; FreeFSPIJobStatus(_FSPI_JOB_STATUS *,int)
0x140032273  xor     edx, edx; Val
0x140032275  lea     rcx, [rsi+464h]; void *
0x14003227c  lea     r8d, [rdx+54h]; Size
0x140032280  call    memset_0
0x140032285  mov     rdx, [rsi+10h]
0x140032289  lea     r15, [rsi+46Ch]
0x140032290  mov     dword ptr [r12], 58h ; 'X'
0x140032298  lea     r9, [rbp+arg_8]; int *
0x14003229c  mov     rax, [rbp+Overlapped]
0x1400322a0  mov     r8, r15; unsigned int *
0x1400322a3  mov     ecx, [rax+4]
0x1400322a6  mov     [rdx+48h], ecx
0x1400322a9  lea     rdx, [rsi+468h]; unsigned int *
0x1400322b0  mov     rcx, [rbp+Overlapped]
0x1400322b4  mov     ecx, [rcx+4]; unsigned int
0x1400322b7  call    ?LegacyJobStatusToStatus@@YAKKPEAK0PEAH@Z; LegacyJobStatusToStatus(ulong,ulong *,ulong *,int *)
  ... truncated ...
```
