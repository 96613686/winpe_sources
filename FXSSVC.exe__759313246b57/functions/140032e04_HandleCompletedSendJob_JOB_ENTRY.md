# HandleCompletedSendJob(_JOB_ENTRY *)

- ea: `0x140032e04`
- end: `0x140033546`
- name: `?HandleCompletedSendJob@@YAHPEAU_JOB_ENTRY@@@Z`
- size: `1858`
- prototype: `__int64 __fastcall(struct _JOB_ENTRY *)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400311d0`

## callees

- `0x140004be4`
- `0x140004c78`
- `0x140004ca8`
- `0x140004fe4`
- `0x140023a0c`
- `0x14002cd50`
- `0x14002e534`
- `0x1400306e0`
- `0x140030a90`
- `0x140032e04`
- `0x140034c0c`
- `0x140036164`
- `0x140036744`
- `0x1400399f0`
- `0x14003b04c`
- `0x14003c4ac`
- `0x140040c14`
- `0x1400522a4`
- `0x14005900c`
- `0x1400699d0`
- `0x140086ec0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140032ef2`
- `KERNEL32!GetLastError` at `0x140033123`
- `KERNEL32!GetLastError` at `0x140033235`
- `KERNEL32!GetLastError` at `0x1400333d1`
- `KERNEL32!GetLastError` at `0x140033440`
- `KERNEL32!GetLastError` at `0x1400334ae`
- `KERNEL32!GetLastError` at `0x140032ef2`
- `KERNEL32!GetLastError` at `0x140033123`
- `KERNEL32!GetLastError` at `0x140033235`
- `KERNEL32!GetLastError` at `0x1400333d1`
- `KERNEL32!GetLastError` at `0x140033440`
- `KERNEL32!GetLastError` at `0x1400334ae`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140032e82`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140032e82`
- `KERNEL32!EnterCriticalSection` at `0x140032e6b`
- `KERNEL32!EnterCriticalSection` at `0x140032fa2`
- `KERNEL32!EnterCriticalSection` at `0x14003302b`
- `KERNEL32!EnterCriticalSection` at `0x140033166`
- `KERNEL32!EnterCriticalSection` at `0x14003326c`
- `KERNEL32!EnterCriticalSection` at `0x1400334f2`
- `KERNEL32!EnterCriticalSection` at `0x140032e6b`
- `KERNEL32!EnterCriticalSection` at `0x140032fa2`
- `KERNEL32!EnterCriticalSection` at `0x14003302b`
- `KERNEL32!EnterCriticalSection` at `0x140033166`
- `KERNEL32!EnterCriticalSection` at `0x14003326c`
- `KERNEL32!EnterCriticalSection` at `0x1400334f2`
- `KERNEL32!LeaveCriticalSection` at `0x140032fbf`
- `KERNEL32!LeaveCriticalSection` at `0x140033084`
- `KERNEL32!LeaveCriticalSection` at `0x1400331f2`
- `KERNEL32!LeaveCriticalSection` at `0x14003347c`
- `KERNEL32!LeaveCriticalSection` at `0x14003348f`
- `KERNEL32!LeaveCriticalSection` at `0x140033512`
- `KERNEL32!LeaveCriticalSection` at `0x140032fbf`
- `KERNEL32!LeaveCriticalSection` at `0x140033084`
- `KERNEL32!LeaveCriticalSection` at `0x1400331f2`
- `KERNEL32!LeaveCriticalSection` at `0x14003347c`
- `KERNEL32!LeaveCriticalSection` at `0x14003348f`
- `KERNEL32!LeaveCriticalSection` at `0x140033512`
- `KERNEL32!SetEvent` at `0x140033418`
- `KERNEL32!SetEvent` at `0x140033418`
- `ole32!CoUninitialize` at `0x140033153`
- `ole32!CoUninitialize` at `0x140033153`
- `ole32!CoInitializeEx` at `0x140032fd7`
- `ole32!CoInitializeEx` at `0x140032fd7`

## pseudocode

```c
__int64 __fastcall HandleCompletedSendJob(struct _JOB_ENTRY *a1)
{
  __int64 v2; // rdi
  DWORD LastError; // eax
  DWORD v4; // ebx
  __int64 v5; // rbp
  int v6; // ebx
  HRESULT v7; // eax
  unsigned int v8; // esi
  __int64 v9; // rdx
  __int64 v10; // rbx
  _WORD *v11; // r8
  char *v12; // rax
  char *v13; // r8
  CMapDeviceId *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rbx
  __int64 v17; // rcx
  int v18; // eax
  _WORD *v19; // rcx
  _WORD *v20; // rax
  _WORD *v21; // rcx
  int QueueEvent; // eax
  _QWORD *v23; // rcx
  int v24; // r9d
  DWORD v25; // eax
  DWORD v26; // eax
  DWORD v28; // [rsp+20h] [rbp-2A8h]
  unsigned __int16 v29[14]; // [rsp+44h] [rbp-284h] BYREF
  char v30; // [rsp+60h] [rbp-268h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 172, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
  }
  EnterCriticalSection(&g_CsJob);
  v2 = *((_QWORD *)a1 + 138);
  GetSystemTimeAsFileTime((LPFILETIME)a1 + 6);
  *((_QWORD *)a1 + 7) = *((_QWORD *)a1 + 6) - *((_QWORD *)a1 + 5);
  if ( !*(_QWORD *)(v2 + 72) )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        173,
        &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
        *(unsigned int *)(v2 + 32));
    }
    if ( !(unsigned int)CreateTiffFileForJob((struct _JOB_QUEUE *)v2) )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v28 = LastError;
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 174, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
      }
      v29[0] = 0;
      StringCchPrintfW(v29, 0xCu, L"%ld", v4, v28);
      FaxLog(2u, 1u, 1u, 0xC0007D4C, *((_QWORD *)g_pFaxConfig + 12));
    }
  }
  v5 = 2147483646;
  if ( *(_QWORD *)(v2 + 72) )
  {
    EnterCriticalSection(&g_CsConfig);
    v6 = *((_DWORD *)g_pFaxConfig + 11);
    LeaveCriticalSection(&g_CsConfig);
    if ( v6 )
    {
      v7 = CoInitializeEx(0, 0);
      v8 = v7;
      if ( v7 >= 0 )
      {
        if ( !ArchiveOutboundJob((const struct _JOB_QUEUE *)v2)
          && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v28 = GetLastError();
          WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 176, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
        }
        CoUninitialize();
      }
      else
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            175,
            &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
            (unsigned int)v7);
        }
        EnterCriticalSection(&g_CsConfig);
        v9 = 2147483646;
        v10 = 260;
        v11 = (_WORD *)*((_QWORD *)g_pFaxConfig + 6);
        v12 = &v30;
        do
        {
          if ( !v9 )
            break;
          if ( !*v11 )
            break;
          *(_WORD *)v12 = *v11++;
          v12 += 2;
          --v9;
          --v10;
        }
        while ( v10 );
        v13 = v12 - 2;
        if ( v10 )
          v13 = v12;
        *(_WORD *)v13 = 0;
        LeaveCriticalSection(&g_CsConfig);
        if ( v10 )
        {
          v29[0] = 0;
          StringCchPrintfW(v29, 0xCu, L"%ld", v8);
          FaxLog(2u, 1u, 3u, 0xC0007D14, *(_QWORD *)(v2 + 72));
        }
      }
    }
  }
  EnterCriticalSection(&g_CsOutboundActivityLogging);
  if ( g_hOutboxActivityLogFile == (HANDLE)-1LL )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = 177;
LABEL_42:
      WPP_SF_(*((_QWORD *)v14 + 2), v15, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
    }
  }
  else if ( !(unsigned int)LogOutboundActivity((struct _JOB_QUEUE *)v2) )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = 178;
      goto LABEL_42;
    }
  }
  LeaveCriticalSection(&g_CsOutboundActivityLogging);
  FaxLogSend((const struct _JOB_QUEUE *)v2, 0);
  if ( g_pFaxPerfCounters
    && !(unsigned int)UpdatePerfCounters(v2)
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v28 = GetLastError();
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 179, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
  }
  EnterCriticalSection(&g_CsQueue);
  v16 = 256;
  _JOB_QUEUE::PutStatus((_JOB_QUEUE *)v2, 0x100u);
  v17 = *(_QWORD *)(v2 + 40);
  v18 = *(_DWORD *)(v17 + 1132);
  v19 = (_WORD *)(v17 + 1216);
  *(_DWORD *)(v2 + 1688) = v18;
  v20 = (_WORD *)(v2 + 1176);
  do
  {
    if ( !v5 )
      break;
    if ( !*v19 )
      break;
    *v20++ = *v19++;
    --v5;
    --v16;
  }
  while ( v16 );
  v21 = v20 - 1;
  if ( v16 )
    v21 = v20;
  *v21 = 0;
  if ( !(unsigned int)UpdatePersistentJobStatus((struct _JOB_QUEUE *const)v2)
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      180,
      &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
      *(unsigned int *)(v2 + 1844));
  }
  ++*(_DWORD *)(*(_QWORD *)(v2 + 584) + 376LL);
  QueueEvent = CreateQueueEvent(2, v2);
  if ( QueueEvent
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LOWORD(v28) = QueueEvent;
    WPP_SF_lh(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      181,
      &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
      *(unsigned int *)(v2 + 16),
      v28);
  }
  IncreaseJobRefCount((struct _JOB_QUEUE *)v2, 1);
  v23 = *(_QWORD **)(v2 + 40);
  *(_QWORD *)(v2 + 1160) = v23[5];
  *(_QWORD *)(v2 + 1168) = v23[6];
  *(_DWORD *)(v23[2] + 72LL) = 537919488;
  UpdateDeviceJobsCounter(*(struct _LINE_INFO **)(*(_QWORD *)(v2 + 40) + 16LL), 1, -1, v24);
  if ( !(unsigned int)EndJob(*(struct _JOB_ENTRY **)(v2 + 40), 1)
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v25 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 182, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, v25);
  }
  *(_QWORD *)(v2 + 40) = 0;
  DecreaseJobRefCount((struct _JOB_QUEUE *)v2, 1, 1, 0);
  if ( !SetEvent(g_hJobQueueEvent) )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v26 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 183, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, v26);
    }
    g_ScanQueueAfterTimeout = 1;
  }
  LeaveCriticalSection(&g_CsQueue);
  LeaveCriticalSection(&g_CsJob);
  if ( !(unsigned int)SendJobReceipt(1, (struct _JOB_QUEUE *)v2, *(unsigned __int16 **)(v2 + 72)) )
  {
    GetLastError();
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 184, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
    }
  }
  EnterCriticalSection(&g_CsQueue);
  DecreaseJobRefCount((struct _JOB_QUEUE *)v2, 1, 1, 1);
  LeaveCriticalSection(&g_CsQueue);
  return 1;
}

```

## disassembly

```asm
0x140032e04  push    rbx
0x140032e06  push    rbp
0x140032e07  push    rsi
0x140032e08  push    rdi
0x140032e09  push    r12
0x140032e0b  push    r13
0x140032e0d  push    r14
0x140032e0f  push    r15
0x140032e11  sub     rsp, 288h
0x140032e18  mov     rax, cs:__security_cookie
0x140032e1f  xor     rax, rsp
0x140032e22  mov     [rsp+2C8h+var_58], rax
0x140032e2a  mov     rsi, rcx
0x140032e2d  mov     rcx, cs:WPP_GLOBAL_Control
0x140032e34  lea     rbp, WPP_GLOBAL_Control
0x140032e3b  mov     r13b, 4
0x140032e3e  cmp     rcx, rbp
0x140032e41  jz      short loc_140032E64
0x140032e43  test    [rcx+1Ch], r13b
0x140032e47  jz      short loc_140032E64
0x140032e49  cmp     byte ptr [rcx+19h], 5
0x140032e4d  jb      short loc_140032E64
0x140032e4f  mov     rcx, [rcx+10h]
0x140032e53  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x140032e5a  mov     edx, 0ACh
0x140032e5f  call    WPP_SF_
0x140032e64  lea     rcx, ?g_CsJob@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140032e6b  call    cs:__imp_EnterCriticalSection
0x140032e72  nop     dword ptr [rax+rax+00h]
0x140032e77  mov     rdi, [rsi+450h]
0x140032e7e  lea     rcx, [rsi+30h]; lpSystemTimeAsFileTime
0x140032e82  call    cs:__imp_GetSystemTimeAsFileTime
0x140032e89  nop     dword ptr [rax+rax+00h]
0x140032e8e  mov     rax, [rsi+30h]
0x140032e92  mov     r15d, 2
0x140032e98  sub     rax, [rsi+28h]
0x140032e9c  xor     r14d, r14d
0x140032e9f  mov     [rsi+38h], rax
0x140032ea3  lea     r12d, [r15-1]
0x140032ea7  cmp     [rdi+48h], r14
0x140032eab  jnz     loc_140032F8C
0x140032eb1  mov     rcx, cs:WPP_GLOBAL_Control
0x140032eb8  cmp     rcx, rbp
0x140032ebb  jz      short loc_140032EE2
0x140032ebd  test    [rcx+1Ch], r13b
0x140032ec1  jz      short loc_140032EE2
0x140032ec3  cmp     byte ptr [rcx+19h], 5
0x140032ec7  jb      short loc_140032EE2
0x140032ec9  mov     r9d, [rdi+20h]
0x140032ecd  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x140032ed4  mov     rcx, [rcx+10h]
0x140032ed8  mov     edx, 0ADh
0x140032edd  call    WPP_SF_d
0x140032ee2  mov     rcx, rdi; struct _JOB_QUEUE *
0x140032ee5  call    ?CreateTiffFileForJob@@YAHPEAU_JOB_QUEUE@@@Z; CreateTiffFileForJob(_JOB_QUEUE *)
0x140032eea  test    eax, eax
0x140032eec  jnz     loc_140032F8C
0x140032ef2  call    cs:__imp_GetLastError
0x140032ef9  nop     dword ptr [rax+rax+00h]
0x140032efe  mov     ebx, eax
0x140032f00  mov     rcx, cs:WPP_GLOBAL_Control
0x140032f07  cmp     rcx, rbp
0x140032f0a  jz      short loc_140032F35
0x140032f0c  test    [rcx+1Ch], r13b
0x140032f10  jz      short loc_140032F35
0x140032f12  cmp     [rcx+19h], r15b
0x140032f16  jb      short loc_140032F35
0x140032f18  mov     r9d, [rdi+20h]
0x140032f1c  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x140032f23  mov     rcx, [rcx+10h]
0x140032f27  mov     edx, 0AEh
0x140032f2c  mov     dword ptr [rsp+2C8h+var_2A8], eax
0x140032f30  call    WPP_SF_dd
0x140032f35  mov     r9d, ebx
0x140032f38  mov     [rsp+2C8h+var_288], ebx
0x140032f3c  lea     r8, aLd; "%ld"
0x140032f43  mov     [rsp+2C8h+var_284], r14w
0x140032f49  mov     edx, 0Ch; unsigned __int64
0x140032f4e  lea     rcx, [rsp+2C8h+var_284]; unsigned __int16 *
0x140032f53  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140032f58  test    eax, eax
0x140032f5a  lea     rdx, [rsp+2C8h+var_284]
0x140032f5f  mov     rax, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x140032f66  mov     r9d, 0C0007D4Ch
0x140032f6c  cmovs   rdx, r14
0x140032f70  mov     r8d, r12d
0x140032f73  mov     [rsp+2C8h+var_2A0], rdx
0x140032f78  mov     edx, r12d
0x140032f7b  mov     rcx, [rax+60h]
0x140032f7f  mov     [rsp+2C8h+var_2A8], rcx
0x140032f84  mov     ecx, r15d
0x140032f87  call    FaxLog
0x140032f8c  mov     ebp, 7FFFFFFEh
0x140032f91  cmp     [rdi+48h], r14
0x140032f95  jz      loc_14003315F
0x140032f9b  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140032fa2  call    cs:__imp_EnterCriticalSection
0x140032fa9  nop     dword ptr [rax+rax+00h]
0x140032fae  mov     rax, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x140032fb5  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140032fbc  mov     ebx, [rax+2Ch]
0x140032fbf  call    cs:__imp_LeaveCriticalSection
0x140032fc6  nop     dword ptr [rax+rax+00h]
0x140032fcb  test    ebx, ebx
0x140032fcd  jz      loc_14003315F
0x140032fd3  xor     edx, edx; dwCoInit
0x140032fd5  xor     ecx, ecx; pvReserved
0x140032fd7  call    cs:__imp_CoInitializeEx
0x140032fde  nop     dword ptr [rax+rax+00h]
0x140032fe3  mov     esi, eax
0x140032fe5  test    eax, eax
0x140032fe7  jns     loc_1400330F8
0x140032fed  mov     rcx, cs:WPP_GLOBAL_Control
0x140032ff4  lea     rdx, WPP_GLOBAL_Control
0x140032ffb  cmp     rcx, rdx
0x140032ffe  jz      short loc_140033024
0x140033000  test    [rcx+1Ch], r13b
0x140033004  jz      short loc_140033024
0x140033006  cmp     [rcx+19h], r15b
0x14003300a  jb      short loc_140033024
0x14003300c  mov     rcx, [rcx+10h]
0x140033010  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x140033017  mov     edx, 0AFh
0x14003301c  mov     r9d, eax
0x14003301f  call    WPP_SF_d
0x140033024  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003302b  call    cs:__imp_EnterCriticalSection
0x140033032  nop     dword ptr [rax+rax+00h]
0x140033037  mov     rax, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x14003303e  mov     rdx, rbp
0x140033041  mov     ebx, 104h
0x140033046  mov     r8, [rax+30h]
0x14003304a  lea     rax, [rsp+2C8h+var_268]
0x14003304f  test    rdx, rdx
0x140033052  jz      short loc_14003306E
0x140033054  movzx   ecx, word ptr [r8]
0x140033058  test    cx, cx
0x14003305b  jz      short loc_14003306E
0x14003305d  mov     [rax], cx
0x140033060  add     r8, r15
0x140033063  add     rax, r15
0x140033066  sub     rdx, r12
0x140033069  sub     rbx, r12
0x14003306c  jnz     short loc_14003304F
0x14003306e  lea     r8, [rax-2]
0x140033072  test    rbx, rbx
0x140033075  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003307c  cmovnz  r8, rax
0x140033080  mov     [r8], r14w
0x140033084  call    cs:__imp_LeaveCriticalSection
0x14003308b  nop     dword ptr [rax+rax+00h]
0x140033090  test    rbx, rbx
0x140033093  jz      loc_14003315F
0x140033099  mov     r9d, esi
0x14003309c  mov     [rsp+2C8h+var_288], esi
0x1400330a0  lea     r8, aLd; "%ld"
0x1400330a7  mov     [rsp+2C8h+var_284], r14w
0x1400330ad  mov     edx, 0Ch; unsigned __int64
0x1400330b2  lea     rcx, [rsp+2C8h+var_284]; unsigned __int16 *
0x1400330b7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400330bc  test    eax, eax
0x1400330be  lea     rdx, [rsp+2C8h+var_284]
0x1400330c3  lea     rax, [rsp+2C8h+var_268]
0x1400330c8  mov     r9d, 0C0007D14h
0x1400330ce  cmovs   rdx, r14
0x1400330d2  mov     r8d, 3
0x1400330d8  mov     [rsp+2C8h+var_298], rdx
0x1400330dd  mov     ecx, r15d
0x1400330e0  mov     [rsp+2C8h+var_2A0], rax
0x1400330e5  mov     edx, r12d
0x1400330e8  mov     rax, [rdi+48h]
0x1400330ec  mov     [rsp+2C8h+var_2A8], rax
0x1400330f1  call    FaxLog
0x1400330f6  jmp     short loc_14003315F
0x1400330f8  mov     rcx, rdi; struct _JOB_QUEUE *
0x1400330fb  call    ?ArchiveOutboundJob@@YAHPEBU_JOB_QUEUE@@@Z; ArchiveOutboundJob(_JOB_QUEUE const *)
0x140033100  test    eax, eax
0x140033102  jnz     short loc_140033153
0x140033104  mov     rax, cs:WPP_GLOBAL_Control
0x14003310b  lea     rdx, WPP_GLOBAL_Control
0x140033112  cmp     rax, rdx
0x140033115  jz      short loc_140033153
0x140033117  test    [rax+1Ch], r13b
0x14003311b  jz      short loc_140033153
0x14003311d  cmp     [rax+19h], r15b
0x140033121  jb      short loc_140033153
0x140033123  call    cs:__imp_GetLastError
0x14003312a  nop     dword ptr [rax+rax+00h]
0x14003312f  mov     rcx, cs:WPP_GLOBAL_Control
0x140033136  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14003313d  mov     r9d, [rdi+20h]
0x140033141  mov     edx, 0B0h
0x140033146  mov     dword ptr [rsp+2C8h+var_2A8], eax
0x14003314a  mov     rcx, [rcx+10h]
0x14003314e  call    WPP_SF_dd
0x140033153  call    cs:__imp_CoUninitialize
0x14003315a  nop     dword ptr [rax+rax+00h]
0x14003315f  lea     rcx, ?g_CsOutboundActivityLogging@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140033166  call    cs:__imp_EnterCriticalSection
0x14003316d  nop     dword ptr [rax+rax+00h]
0x140033172  cmp     cs:?g_hOutboxActivityLogFile@@3PEAXEA, 0FFFFFFFFFFFFFFFFh; void * g_hOutboxActivityLogFile
0x14003317a  jnz     short loc_1400331B2
0x14003317c  mov     rcx, cs:WPP_GLOBAL_Control
0x140033183  lea     rsi, WPP_GLOBAL_Control
0x14003318a  cmp     rcx, rsi
0x14003318d  jz      short loc_1400331EB
0x14003318f  test    [rcx+1Ch], r13b
0x140033193  jz      short loc_1400331EB
0x140033195  cmp     [rcx+19h], r15b
0x140033199  jb      short loc_1400331EB
0x14003319b  mov     edx, 0B1h
0x1400331a0  mov     rcx, [rcx+10h]
0x1400331a4  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x1400331ab  call    WPP_SF_
0x1400331b0  jmp     short loc_1400331EB
0x1400331b2  mov     rcx, rdi; struct _JOB_QUEUE *
0x1400331b5  call    ?LogOutboundActivity@@YAHPEAU_JOB_QUEUE@@@Z; LogOutboundActivity(_JOB_QUEUE *)
0x1400331ba  test    eax, eax
0x1400331bc  jnz     short loc_1400331E4
0x1400331be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400331c5  lea     rsi, WPP_GLOBAL_Control
0x1400331cc  cmp     rcx, rsi
0x1400331cf  jz      short loc_1400331EB
0x1400331d1  test    [rcx+1Ch], r13b
0x1400331d5  jz      short loc_1400331EB
0x1400331d7  cmp     [rcx+19h], r15b
0x1400331db  jb      short loc_1400331EB
0x1400331dd  mov     edx, 0B2h
0x1400331e2  jmp     short loc_1400331A0
0x1400331e4  lea     rsi, WPP_GLOBAL_Control
0x1400331eb  lea     rcx, ?g_CsOutboundActivityLogging@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400331f2  call    cs:__imp_LeaveCriticalSection
0x1400331f9  nop     dword ptr [rax+rax+00h]
0x1400331fe  xor     edx, edx; int
0x140033200  mov     rcx, rdi; struct _JOB_QUEUE *
0x140033203  call    ?FaxLogSend@@YAXPEBU_JOB_QUEUE@@H@Z; FaxLogSend(_JOB_QUEUE const *,int)
0x140033208  cmp     cs:?g_pFaxPerfCounters@@3PEAU_FAX_PERF_COUNTERS@@EA, r14; _FAX_PERF_COUNTERS * g_pFaxPerfCounters
0x14003320f  jz      short loc_140033265
0x140033211  mov     rcx, rdi
0x140033214  call    UpdatePerfCounters
0x140033219  test    eax, eax
0x14003321b  jnz     short loc_140033265
0x14003321d  mov     rax, cs:WPP_GLOBAL_Control
0x140033224  cmp     rax, rsi
0x140033227  jz      short loc_140033265
0x140033229  test    [rax+1Ch], r13b
0x14003322d  jz      short loc_140033265
0x14003322f  cmp     [rax+19h], r15b
0x140033233  jb      short loc_140033265
0x140033235  call    cs:__imp_GetLastError
0x14003323c  nop     dword ptr [rax+rax+00h]
0x140033241  mov     rcx, cs:WPP_GLOBAL_Control
0x140033248  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14003324f  mov     r9d, [rdi+20h]
0x140033253  mov     edx, 0B3h
0x140033258  mov     dword ptr [rsp+2C8h+var_2A8], eax
0x14003325c  mov     rcx, [rcx+10h]
0x140033260  call    WPP_SF_dd
0x140033265  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003326c  call    cs:__imp_EnterCriticalSection
0x140033273  nop     dword ptr [rax+rax+00h]
0x140033278  mov     ebx, 100h
0x14003327d  mov     rcx, rdi; this
0x140033280  mov     edx, ebx; unsigned int
0x140033282  call    ?PutStatus@_JOB_QUEUE@@QEAAXK@Z; _JOB_QUEUE::PutStatus(ulong)
0x140033287  mov     rcx, [rdi+28h]
0x14003328b  mov     eax, [rcx+46Ch]
0x140033291  add     rcx, 4C0h
0x140033298  mov     [rdi+698h], eax
0x14003329e  lea     rax, [rdi+498h]
0x1400332a5  test    rbp, rbp
0x1400332a8  jz      short loc_1400332C3
0x1400332aa  movzx   edx, word ptr [rcx]
0x1400332ad  test    dx, dx
0x1400332b0  jz      short loc_1400332C3
0x1400332b2  mov     [rax], dx
0x1400332b5  add     rcx, r15
0x1400332b8  add     rax, r15
0x1400332bb  sub     rbp, r12
0x1400332be  sub     rbx, r12
0x1400332c1  jnz     short loc_1400332A5
0x1400332c3  lea     rcx, [rax-2]
0x1400332c7  test    rbx, rbx
0x1400332ca  cmovnz  rcx, rax
0x1400332ce  mov     [rcx], r14w
0x1400332d2  mov     rcx, rdi; struct _JOB_QUEUE *
0x1400332d5  call    ?UpdatePersistentJobStatus@@YAHQEAU_JOB_QUEUE@@@Z; UpdatePersistentJobStatus(_JOB_QUEUE * const)
0x1400332da  test    eax, eax
0x1400332dc  jnz     short loc_140033312
0x1400332de  mov     rcx, cs:WPP_GLOBAL_Control
0x1400332e5  cmp     rcx, rsi
0x1400332e8  jz      short loc_140033312
0x1400332ea  test    [rcx+1Ch], r13b
0x1400332ee  jz      short loc_140033312
0x1400332f0  cmp     [rcx+19h], r15b
0x1400332f4  jb      short loc_140033312
0x1400332f6  mov     r9d, [rdi+734h]
0x1400332fd  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x140033304  mov     rcx, [rcx+10h]
0x140033308  mov     edx, 0B4h
  ... truncated ...
```
