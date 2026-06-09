# s_UbpmRpcTaskHostReportTaskStatus

- ea: `0x180011a90`
- end: `0x180012565`
- name: `s_UbpmRpcTaskHostReportTaskStatus`
- size: `2773`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, void *, int)`
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, loader_planting, service_task, installer_update`

## callees

- `0x180003da0`
- `0x180004c30`
- `0x1800053a0`
- `0x180005614`
- `0x180006820`
- `0x180007e9c`
- `0x180007ec0`
- `0x180011a90`
- `0x180012570`
- `0x180012950`
- `0x180012b1c`
- `0x18001b07c`
- `0x18001bb54`
- `0x18001c87c`
- `0x18001cbe0`
- `0x180024740`
- `0x180032f78`
- `0x18003f434`
- `0x18003f6e4`
- `0x18003f83c`
- `0x18003f8b0`
- `0x18003f93c`
- `0x18004022e`
- `0x180040260`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180011d81`
- `ntdll!RtlFreeHeap` at `0x180011da8`
- `ntdll!RtlFreeHeap` at `0x180011dcf`
- `ntdll!RtlFreeHeap` at `0x180011df3`
- `ntdll!RtlFreeHeap` at `0x180011e17`
- `ntdll!RtlFreeHeap` at `0x180011e35`
- `ntdll!RtlFreeHeap` at `0x180011ffd`
- `ntdll!RtlFreeHeap` at `0x180011d81`
- `ntdll!RtlFreeHeap` at `0x180011da8`
- `ntdll!RtlFreeHeap` at `0x180011dcf`
- `ntdll!RtlFreeHeap` at `0x180011df3`
- `ntdll!RtlFreeHeap` at `0x180011e17`
- `ntdll!RtlFreeHeap` at `0x180011e35`
- `ntdll!RtlFreeHeap` at `0x180011ffd`
- `ntdll!RtlReleaseSRWLockShared` at `0x180011b59`
- `ntdll!RtlReleaseSRWLockShared` at `0x18001239c`
- `ntdll!RtlReleaseSRWLockShared` at `0x18001242e`
- `ntdll!RtlReleaseSRWLockShared` at `0x180011b59`
- `ntdll!RtlReleaseSRWLockShared` at `0x18001239c`
- `ntdll!RtlReleaseSRWLockShared` at `0x18001242e`
- `ntdll!RtlAcquireSRWLockShared` at `0x180011b2c`
- `ntdll!RtlAcquireSRWLockShared` at `0x180011b2c`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180011b6a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180011b8c`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001221a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180011b6a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180011b8c`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001221a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180011e4c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180011e62`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180012257`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800123ba`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800123d0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800124db`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800124ef`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180011e4c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180011e62`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180012257`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800123ba`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800123d0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800124db`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800124ef`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180011ea4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180011ee9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180011f80`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180011fbc`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180011ea4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180011ee9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180011f80`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180011fbc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011b76`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011b98`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012226`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011b76`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011b98`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012226`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180011ebf`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180011f02`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180011f9b`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180011fd6`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180011ebf`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180011f02`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180011f9b`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180011fd6`
- `RPCRT4!UuidEqual` at `0x180011bf1`
- `RPCRT4!UuidEqual` at `0x180011bf1`

## string_xrefs

- `0x1800121aa`: `ReportTaskEvent(0x%x) --> ret=%d`
- `0x1800121ff`: `ReportTaskEvent(0x%x) --> ret=%d`

## pseudocode

```c
__int64 __fastcall s_UbpmRpcTaskHostReportTaskStatus(unsigned int *a1, __int64 a2, UUID *a3, int a4, void *a5, int a6)
{
  __int64 v9; // rsi
  unsigned int *i; // rax
  unsigned int *v12; // r13
  __int64 v13; // r8
  int v14; // ebx
  int v15; // r9d
  unsigned __int16 v16; // r15
  unsigned __int16 *v17; // rdx
  unsigned __int16 *v18; // r9
  __int64 v19; // r8
  __int64 v20; // r11
  __int64 v21; // rcx
  __int64 v22; // r10
  unsigned __int16 *v23; // rcx
  unsigned __int16 *v24; // rcx
  unsigned __int16 *v25; // rdx
  unsigned __int16 *v26; // rcx
  __int16 v27; // ax
  __int16 v28; // ax
  unsigned int *v29; // rdx
  __int64 v30; // rax
  unsigned int **v31; // rcx
  void *v32; // r8
  void *v33; // r8
  void *v34; // r8
  void *v35; // r8
  void *v36; // r8
  DWORD v37; // ebx
  unsigned int v38; // eax
  __int64 v39; // rdx
  __int64 v40; // r8
  DWORD v41; // ebx
  unsigned int v42; // edi
  int v43; // r15d
  DWORD v44; // ebx
  DWORD v45; // ebx
  int v47; // eax
  __int64 v48; // r8
  const unsigned __int16 *v49; // r9
  int v50; // eax
  __int64 v51; // r8
  __int64 v52; // rcx
  unsigned int v53; // eax
  __int64 v54; // r8
  __int64 v55; // rdx
  __int64 v56; // r8
  __int64 v57; // r8
  void *v58; // [rsp+28h] [rbp-D8h]
  const struct _GUID *pSid; // [rsp+30h] [rbp-D0h]
  void *v60; // [rsp+38h] [rbp-C8h]
  const struct _GUID *v61; // [rsp+40h] [rbp-C0h]
  size_t Size; // [rsp+48h] [rbp-B8h]
  int v63; // [rsp+80h] [rbp-80h]
  unsigned int v64[3]; // [rsp+84h] [rbp-7Ch] BYREF
  RPC_STATUS Status; // [rsp+90h] [rbp-70h] BYREF
  unsigned int *v66; // [rsp+98h] [rbp-68h]
  __int64 v67; // [rsp+A0h] [rbp-60h]
  unsigned int *v68; // [rsp+A8h] [rbp-58h] BYREF
  struct _GUID v69; // [rsp+B0h] [rbp-50h] BYREF
  UUID Uuid2; // [rsp+C0h] [rbp-40h] BYREF
  __int128 TlsValue; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v72; // [rsp+E0h] [rbp-20h]
  __int128 v73; // [rsp+F0h] [rbp-10h]
  __int128 v74; // [rsp+100h] [rbp+0h]
  __int128 v75; // [rsp+110h] [rbp+10h]
  __int128 v76; // [rsp+120h] [rbp+20h]
  __int128 v77; // [rsp+130h] [rbp+30h]
  __int128 v78; // [rsp+140h] [rbp+40h]
  __int64 v79; // [rsp+150h] [rbp+50h]
  unsigned __int16 v80[256]; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int16 v81[256]; // [rsp+360h] [rbp+260h] BYREF

  v68 = a1;
  v9 = 0;
  v67 = 0;
  memset_0(v80, 0, sizeof(v80));
  memset_0(v81, 0, sizeof(v81));
  Status = 0;
  *(_QWORD *)&v64[1] = 0;
  Uuid2 = 0;
  v69 = 0;
  if ( a4 != 1 || !a2 )
    return 87;
  RtlAcquireSRWLockShared(&g_TaskHostContextListLock);
  if ( *a1 != 1665679957 )
  {
    RtlReleaseSRWLockShared(&g_TaskHostContextListLock);
    return 5;
  }
  if ( (a1[26] & 4) != 0 )
  {
    RtlReleaseSRWLockShared(&g_TaskHostContextListLock);
    v42 = 1067;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, a1[8]);
    return v42;
  }
  RtlReleaseSRWLockShared(&g_TaskHostContextListLock);
  RtlAcquireSRWLockExclusive(a1 + 20);
  a1[22] = GetCurrentThreadId();
  RtlAcquireSRWLockExclusive(a1 + 16);
  a1[18] = GetCurrentThreadId();
  v64[0] = a1[8];
  for ( i = (unsigned int *)*((_QWORD *)a1 + 25); ; i = *(unsigned int **)i )
  {
    v66 = i;
    if ( i == a1 + 50 )
    {
      a1[18] = 0;
      RtlReleaseSRWLockExclusive(a1 + 16);
      a1[22] = 0;
      RtlReleaseSRWLockExclusive(a1 + 20);
      v42 = 87;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_qddi(*((_QWORD *)WPP_GLOBAL_Control + 2), v55, v56, a1, a1[8], *((unsigned __int16 *)a1 + 98), a2);
      goto LABEL_57;
    }
    v12 = i - 4;
    if ( i[10] == a6 )
    {
      if ( *((_QWORD *)v12 + 12) )
        break;
    }
LABEL_105:
    ;
  }
  if ( !UuidEqual((UUID *)v12 + 2, a3, &Status) )
  {
    i = v66;
    goto LABEL_105;
  }
  if ( (v12[26] & 1) == 0 )
  {
    v14 = 0;
    v63 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v61 = (const struct _GUID *)*((_QWORD *)v12 + 16);
      LODWORD(v60) = *((unsigned __int16 *)a1 + 98);
      WPP_SF_qqiddi(*((_QWORD *)WPP_GLOBAL_Control + 2), *((unsigned __int16 *)a1 + 98), v13, a1, v12, a2, a1[8]);
    }
    Uuid2 = *(UUID *)(v12 + 15);
    *((_BYTE *)v12 + 104) |= 1u;
    v15 = v12[31];
    v69 = *(struct _GUID *)(v12 + 27);
    v16 = *((_WORD *)v12 + 53);
    if ( v16 )
    {
      LODWORD(Size) = v12[37];
      UbpmRunNextSerializedAction(
        (int)&Uuid2,
        v16,
        (int)&v69,
        v15,
        *((_QWORD *)v12 + 16),
        a1[48],
        *((PSID *)a1 + 23),
        *((_QWORD *)v12 + 17),
        v12[36],
        Size,
        *((void **)v12 + 19),
        *((_BYTE *)v12 + 160),
        *((unsigned __int16 ***)v12 + 21),
        v12[44],
        *((_BYTE *)v12 + 180),
        *((unsigned __int16 ***)v12 + 23));
    }
    v17 = (unsigned __int16 *)*((_QWORD *)v12 + 10);
    v18 = v80;
    v19 = 2147483646;
    v20 = 256;
    v21 = 2147483646;
    v22 = 256;
    do
    {
      if ( !v21 )
        break;
      if ( !*v17 )
        break;
      *v18++ = *v17++;
      --v21;
      --v22;
    }
    while ( v22 );
    v23 = v18 - 1;
    if ( v22 )
      v23 = v18;
    *v23 = 0;
    v24 = (unsigned __int16 *)*((_QWORD *)v12 + 11);
    if ( v24 )
    {
      v25 = v81;
      do
      {
        if ( !v19 )
          break;
        if ( !*v24 )
          break;
        *v25++ = *v24++;
        --v19;
        --v20;
      }
      while ( v20 );
      v26 = v25 - 1;
      if ( v20 )
        v26 = v25;
      *v26 = 0;
    }
    if ( v16 <= 1u )
    {
      LODWORD(v52) = (_DWORD)::pSid;
      if ( *((_QWORD *)a1 + 23) )
        v52 = *((_QWORD *)a1 + 23);
      UbpmUtilsGetAccountNamesFromSid(v52, 1, 0, 0, (__int64)&v64[1]);
    }
    v27 = *((_WORD *)a1 + 98);
    if ( !v27 || (v28 = v27 - 1, (*((_WORD *)a1 + 98) = v28) == 0) )
    {
      if ( *((unsigned int **)a1 + 27) == a1 + 54 )
        v14 = 1;
      v63 = v14;
    }
    if ( _InterlockedExchangeAdd64((volatile signed __int64 *)v12 + 1, 0xFFFFFFFFFFFFFFFFuLL) == 1 )
    {
      v29 = v66;
      v30 = *(_QWORD *)v66;
      if ( *(unsigned int **)(*(_QWORD *)v66 + 8LL) != v66 || (v31 = (unsigned int **)*((_QWORD *)v66 + 1), *v31 != v66) )
        __fastfail(3u);
      *v31 = (unsigned int *)v30;
      *(_QWORD *)(v30 + 8) = v31;
      *((_QWORD *)v29 + 1) = v29;
      *(_QWORD *)v29 = v29;
      UbpmUtilsSystemPowerOff(*((HANDLE *)v12 + 24));
      v32 = (void *)*((_QWORD *)v12 + 21);
      if ( v32 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v32);
      v33 = (void *)*((_QWORD *)v12 + 23);
      if ( v33 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v33);
      v34 = (void *)*((_QWORD *)v12 + 19);
      if ( v34 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v34);
      v35 = (void *)*((_QWORD *)v12 + 10);
      if ( v35 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v35);
      v36 = (void *)*((_QWORD *)v12 + 11);
      if ( v36 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v36);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
      v12 = 0;
    }
    a1[18] = 0;
    RtlReleaseSRWLockExclusive(a1 + 16);
    a1[22] = 0;
    RtlReleaseSRWLockExclusive(a1 + 20);
    v37 = UbpmpLockTrackerId;
    v79 = 0;
    TlsValue = 0;
    v72 = 0;
    v73 = 0;
    v74 = 0;
    v75 = 0;
    v76 = 0;
    v77 = 0;
    v78 = 0;
    if ( UbpmpLockTrackerId != -1 )
    {
      if ( TlsGetValue(UbpmpLockTrackerId) )
        __int2c();
      TlsSetValue(v37, &TlsValue);
    }
    v38 = UbpmpOpenTriggerConsumer(&Uuid2, 0);
    v41 = UbpmpLockTrackerId;
    v42 = v38;
    if ( UbpmpLockTrackerId != -1 )
    {
      if ( *(_QWORD *)TlsGetValue(UbpmpLockTrackerId) )
        __int2c();
      TlsSetValue(v41, 0);
    }
    v9 = v67;
    if ( v42 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_qqdd(*((_QWORD *)WPP_GLOBAL_Control + 2), v39, v40, a1, v12, a1[8], *((unsigned __int16 *)a1 + 98));
      v43 = v63;
      v42 = 0;
    }
    else
    {
      UbpmpExecutionTimeLimitCallback(v67, 0, 0);
      if ( (int)a5 < 0 )
      {
        ReportTaskEvent(g_hTaskEventManager, &ACTION_FAILURE, v80, &v69, v81, (unsigned int)a5, v64[0]);
        if ( v16 <= 1u )
          ReportTaskEvent(
            g_hTaskEventManager,
            &JOB_FAILURE,
            v80,
            &v69,
            *(const unsigned __int16 **)&v64[1],
            (unsigned int)a5);
        UbpmScheduleRestartOnFailure(v9, 0);
      }
      else
      {
        v47 = EventManager::EvtReport(g_hTaskEventManager, &ACTION_SUCCESS, v80, &v69, v81, (char)a5, v64[0], v60, v61);
        v48 = (unsigned __int16)v47;
        if ( v47 >= 0 )
          v48 = 0;
        TaskEventTrace(L"ReportTaskEvent(0x%x) --> ret=%d", &ACTION_SUCCESS, v48);
        if ( v16 <= 1u )
        {
          v49 = L"(NONE)";
          if ( *(_QWORD *)&v64[1] )
            v49 = *(const unsigned __int16 **)&v64[1];
          v50 = EventManager::EvtReport(g_hTaskEventManager, &JOB_SUCCESS, v80, v49, &v69, v58, pSid);
          v51 = (unsigned __int16)v50;
          if ( v50 >= 0 )
            v51 = 0;
          TaskEventTrace(L"ReportTaskEvent(0x%x) --> ret=%d", &JOB_SUCCESS, v51);
        }
      }
      v43 = v63;
      RtlAcquireSRWLockExclusive(v9 + 208);
      *(_DWORD *)(v9 + 216) = GetCurrentThreadId();
      UbpmpTriggerConsumerReportResult(v9, (unsigned int)a5, 0);
      *(_DWORD *)(v9 + 216) = 0;
      RtlReleaseSRWLockExclusive(v9 + 208);
    }
    if ( v43 == 1 )
    {
      _InterlockedIncrement64((volatile signed __int64 *)a1 + 12);
      v53 = UbpmUtilsSubmitThreadPoolWork((void (*)(void *, unsigned __int8, void *))UbpmpStopHostCallback, a1, 1, 0, 0);
      if ( v53 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_dqd(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, v54, a1[8], a1, v53);
        UbpmpDecrementRefAndDelete(&v68, 1);
      }
    }
LABEL_57:
    if ( v9 )
    {
      v44 = UbpmpLockTrackerId;
      v79 = 0;
      TlsValue = 0;
      v72 = 0;
      v73 = 0;
      v74 = 0;
      v75 = 0;
      v76 = 0;
      v77 = 0;
      v78 = 0;
      if ( UbpmpLockTrackerId != -1 )
      {
        if ( TlsGetValue(UbpmpLockTrackerId) )
          __int2c();
        TlsSetValue(v44, &TlsValue);
      }
      UbpmpCloseTriggerConsumer(v9);
      v45 = UbpmpLockTrackerId;
      if ( UbpmpLockTrackerId != -1 )
      {
        if ( *(_QWORD *)TlsGetValue(UbpmpLockTrackerId) )
          __int2c();
        TlsSetValue(v45, 0);
      }
    }
    if ( *(_QWORD *)&v64[1] )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *(PVOID *)&v64[1]);
    return v42;
  }
  a1[18] = 0;
  RtlReleaseSRWLockExclusive(a1 + 16);
  a1[22] = 0;
  RtlReleaseSRWLockExclusive(a1 + 20);
  v42 = 4320;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_qqidd(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, v57, a1, v12, a2, a1[8], *((unsigned __int16 *)a1 + 98));
  return v42;
}

```

## disassembly

```asm
0x180011a90  mov     [rsp-8+arg_8], rbx
0x180011a95  push    rbp
0x180011a96  push    rsi
0x180011a97  push    rdi
0x180011a98  push    r12
0x180011a9a  push    r13
0x180011a9c  push    r14
0x180011a9e  push    r15
0x180011aa0  lea     rbp, [rsp-470h]
0x180011aa8  sub     rsp, 570h
0x180011aaf  mov     rax, cs:__security_cookie
0x180011ab6  xor     rax, rsp
0x180011ab9  mov     [rbp+4A0h+var_40], rax
0x180011ac0  mov     r15, r8
0x180011ac3  mov     [rbp+4A0h+var_4F8], rcx
0x180011ac7  mov     r14, rdx
0x180011aca  mov     r12, rcx
0x180011acd  xor     esi, esi
0x180011acf  lea     rcx, [rbp+4A0h+var_440]; void *
0x180011ad3  xor     edx, edx; Val
0x180011ad5  mov     [rbp+4A0h+var_500], rsi
0x180011ad9  mov     r8d, 200h; Size
0x180011adf  mov     ebx, r9d
0x180011ae2  call    memset_0
0x180011ae7  xor     edx, edx; Val
0x180011ae9  lea     rcx, [rbp+4A0h+var_240]; void *
0x180011af0  mov     r8d, 200h; Size
0x180011af6  call    memset_0
0x180011afb  xor     r13d, r13d
0x180011afe  mov     [rbp+4A0h+Status], esi
0x180011b01  mov     qword ptr [rbp+4A0h+var_51C+4], r13
0x180011b05  xorps   xmm0, xmm0
0x180011b08  xorps   xmm1, xmm1
0x180011b0b  movups  xmmword ptr [rbp+4A0h+Uuid2.Data1], xmm0
0x180011b0f  movups  xmmword ptr [rbp+4A0h+var_4F0.Data1], xmm1
0x180011b13  cmp     ebx, 1
0x180011b16  jnz     loc_180012392
0x180011b1c  test    r14, r14
0x180011b1f  jz      loc_180012392
0x180011b25  lea     rcx, g_TaskHostContextListLock
0x180011b2c  call    cs:__imp_RtlAcquireSRWLockShared
0x180011b33  nop     dword ptr [rax+rax+00h]
0x180011b38  cmp     dword ptr [r12], 63484255h
0x180011b40  lea     rcx, g_TaskHostContextListLock
0x180011b47  jnz     loc_18001239C
0x180011b4d  test    byte ptr [r12+68h], 4
0x180011b53  jnz     loc_18001242E
0x180011b59  call    cs:__imp_RtlReleaseSRWLockShared
0x180011b60  nop     dword ptr [rax+rax+00h]
0x180011b65  lea     rcx, [r12+50h]
0x180011b6a  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180011b71  nop     dword ptr [rax+rax+00h]
0x180011b76  call    cs:__imp_GetCurrentThreadId
0x180011b7d  nop     dword ptr [rax+rax+00h]
0x180011b82  lea     rcx, [r12+40h]
0x180011b87  mov     [r12+58h], eax
0x180011b8c  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180011b93  nop     dword ptr [rax+rax+00h]
0x180011b98  call    cs:__imp_GetCurrentThreadId
0x180011b9f  nop     dword ptr [rax+rax+00h]
0x180011ba4  mov     edi, [rbp+4A0h+arg_28]
0x180011baa  lea     rbx, [r12+0C8h]
0x180011bb2  mov     [r12+48h], eax
0x180011bb7  mov     eax, [r12+20h]
0x180011bbc  mov     dword ptr [rbp+4A0h+var_51C], eax
0x180011bbf  mov     rax, [rbx]
0x180011bc2  mov     [rbp+4A0h+var_508], rax
0x180011bc6  cmp     rax, rbx
0x180011bc9  jz      loc_1800123B2
0x180011bcf  cmp     [rax+28h], edi
0x180011bd2  lea     r13, [rax-10h]
0x180011bd6  jnz     loc_180012487
0x180011bdc  cmp     [r13+60h], rsi
0x180011be0  jz      loc_180012487
0x180011be6  lea     rcx, [r13+20h]; Uuid1
0x180011bea  mov     rdx, r15; Uuid2
0x180011bed  lea     r8, [rbp+4A0h+Status]; Status
0x180011bf1  call    cs:__imp_UuidEqual
0x180011bf8  nop     dword ptr [rax+rax+00h]
0x180011bfd  test    eax, eax
0x180011bff  jz      loc_180012483
0x180011c05  test    byte ptr [r13+68h], 1
0x180011c0a  jnz     loc_1800124D3
0x180011c10  xor     edi, edi
0x180011c12  mov     ebx, edi
0x180011c14  mov     [rbp+4A0h+var_520], ebx
0x180011c17  mov     rcx, cs:WPP_GLOBAL_Control
0x180011c1e  lea     rax, WPP_GLOBAL_Control
0x180011c25  cmp     rcx, rax
0x180011c28  jnz     loc_1800120F1
0x180011c2e  movups  xmm0, xmmword ptr [r13+3Ch]
0x180011c33  movups  xmmword ptr [rbp+4A0h+Uuid2.Data1], xmm0
0x180011c37  or      byte ptr [r13+68h], 1
0x180011c3c  movups  xmm0, xmmword ptr [r13+6Ch]
0x180011c41  mov     r9d, [r13+7Ch]; int
0x180011c45  movups  xmmword ptr [rbp+4A0h+var_4F0.Data1], xmm0
0x180011c49  movzx   r15d, word ptr [r13+6Ah]
0x180011c4e  test    r15w, r15w
0x180011c52  jnz     loc_18001204D
0x180011c58  mov     rdx, [r13+50h]
0x180011c5c  lea     r9, [rbp+4A0h+var_440]
0x180011c60  mov     r8d, 7FFFFFFEh
0x180011c66  mov     r11d, 100h
0x180011c6c  mov     ecx, r8d
0x180011c6f  mov     r10d, r11d
0x180011c72  test    rcx, rcx
0x180011c75  jz      short loc_180011C94
0x180011c77  movzx   eax, word ptr [rdx]
0x180011c7a  test    ax, ax
0x180011c7d  jz      short loc_180011C94
0x180011c7f  mov     [r9], ax
0x180011c83  add     rdx, 2
0x180011c87  add     r9, 2
0x180011c8b  dec     rcx
0x180011c8e  sub     r10, 1
0x180011c92  jnz     short loc_180011C72
0x180011c94  test    r10, r10
0x180011c97  lea     rcx, [r9-2]
0x180011c9b  cmovnz  rcx, r9
0x180011c9f  mov     [rcx], di
0x180011ca2  mov     rcx, [r13+58h]
0x180011ca6  test    rcx, rcx
0x180011ca9  jz      short loc_180011CE1
0x180011cab  lea     rdx, [rbp+4A0h+var_240]
0x180011cb2  test    r8, r8
0x180011cb5  jz      short loc_180011CD3
0x180011cb7  movzx   eax, word ptr [rcx]
0x180011cba  test    ax, ax
0x180011cbd  jz      short loc_180011CD3
0x180011cbf  mov     [rdx], ax
0x180011cc2  add     rcx, 2
0x180011cc6  add     rdx, 2
0x180011cca  dec     r8
0x180011ccd  sub     r11, 1
0x180011cd1  jnz     short loc_180011CB2
0x180011cd3  test    r11, r11
0x180011cd6  lea     rcx, [rdx-2]
0x180011cda  cmovnz  rcx, rdx
0x180011cde  mov     [rcx], di
0x180011ce1  mov     r14d, 1
0x180011ce7  cmp     r15w, r14w
0x180011ceb  jbe     loc_180012275
0x180011cf1  movzx   eax, word ptr [r12+0C4h]
0x180011cfa  test    ax, ax
0x180011cfd  jz      loc_180012036
0x180011d03  dec     ax
0x180011d06  mov     [r12+0C4h], ax
0x180011d0f  test    ax, ax
0x180011d12  jz      loc_180012036
0x180011d18  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180011d1f  lock xadd [r13+8], rax
0x180011d25  cmp     rax, r14
0x180011d28  jnz     loc_180011E44
0x180011d2e  mov     rdx, [rbp+4A0h+var_508]
0x180011d32  mov     rax, [rdx]
0x180011d35  cmp     [rax+8], rdx
0x180011d39  jnz     loc_180012138
0x180011d3f  mov     rcx, [rdx+8]
0x180011d43  cmp     [rcx], rdx
0x180011d46  jnz     loc_180012138
0x180011d4c  mov     [rcx], rax
0x180011d4f  mov     [rax+8], rcx
0x180011d53  mov     [rdx+8], rdx
0x180011d57  mov     [rdx], rdx
0x180011d5a  mov     rcx, [r13+0C0h]; hObject
0x180011d61  call    ?UbpmUtilsSystemPowerOff@@YAKPEAX@Z; UbpmUtilsSystemPowerOff(void *)
0x180011d66  mov     r8, [r13+0A8h]; P
0x180011d6d  test    r8, r8
0x180011d70  jz      short loc_180011D8D
0x180011d72  mov     rcx, gs:60h
0x180011d7b  xor     edx, edx; Flags
0x180011d7d  mov     rcx, [rcx+30h]; HeapHandle
0x180011d81  call    cs:__imp_RtlFreeHeap
0x180011d88  nop     dword ptr [rax+rax+00h]
0x180011d8d  mov     r8, [r13+0B8h]; P
0x180011d94  test    r8, r8
0x180011d97  jz      short loc_180011DB4
0x180011d99  mov     rcx, gs:60h
0x180011da2  xor     edx, edx; Flags
0x180011da4  mov     rcx, [rcx+30h]; HeapHandle
0x180011da8  call    cs:__imp_RtlFreeHeap
0x180011daf  nop     dword ptr [rax+rax+00h]
0x180011db4  mov     r8, [r13+98h]; P
0x180011dbb  test    r8, r8
0x180011dbe  jz      short loc_180011DDB
0x180011dc0  mov     rcx, gs:60h
0x180011dc9  xor     edx, edx; Flags
0x180011dcb  mov     rcx, [rcx+30h]; HeapHandle
0x180011dcf  call    cs:__imp_RtlFreeHeap
0x180011dd6  nop     dword ptr [rax+rax+00h]
0x180011ddb  mov     r8, [r13+50h]; P
0x180011ddf  test    r8, r8
0x180011de2  jz      short loc_180011DFF
0x180011de4  mov     rcx, gs:60h
0x180011ded  xor     edx, edx; Flags
0x180011def  mov     rcx, [rcx+30h]; HeapHandle
0x180011df3  call    cs:__imp_RtlFreeHeap
0x180011dfa  nop     dword ptr [rax+rax+00h]
0x180011dff  mov     r8, [r13+58h]; P
0x180011e03  test    r8, r8
0x180011e06  jz      short loc_180011E23
0x180011e08  mov     rcx, gs:60h
0x180011e11  xor     edx, edx; Flags
0x180011e13  mov     rcx, [rcx+30h]; HeapHandle
0x180011e17  call    cs:__imp_RtlFreeHeap
0x180011e1e  nop     dword ptr [rax+rax+00h]
0x180011e23  mov     rcx, gs:60h
0x180011e2c  mov     r8, r13; P
0x180011e2f  xor     edx, edx; Flags
0x180011e31  mov     rcx, [rcx+30h]; HeapHandle
0x180011e35  call    cs:__imp_RtlFreeHeap
0x180011e3c  nop     dword ptr [rax+rax+00h]
0x180011e41  mov     r13, rdi
0x180011e44  lea     rcx, [r12+40h]
0x180011e49  mov     [rcx+8], edi
0x180011e4c  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180011e53  nop     dword ptr [rax+rax+00h]
0x180011e58  lea     rcx, [r12+50h]
0x180011e5d  mov     [r12+58h], edi
0x180011e62  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180011e69  nop     dword ptr [rax+rax+00h]
0x180011e6e  mov     ebx, cs:UbpmpLockTrackerId
0x180011e74  xorps   xmm0, xmm0
0x180011e77  xor     eax, eax
0x180011e79  mov     [rbp+4A0h+var_450], rax
0x180011e7d  movups  [rbp+4A0h+TlsValue], xmm0
0x180011e81  movups  [rbp+4A0h+var_4C0], xmm0
0x180011e85  movups  [rbp+4A0h+var_4B0], xmm0
0x180011e89  movups  [rbp+4A0h+var_4A0], xmm0
0x180011e8d  movups  [rbp+4A0h+var_490], xmm0
0x180011e91  movups  [rbp+4A0h+var_480], xmm0
0x180011e95  movups  [rbp+4A0h+var_470], xmm0
0x180011e99  movups  [rbp+4A0h+var_460], xmm0
0x180011e9d  cmp     ebx, 0FFFFFFFFh
0x180011ea0  jz      short loc_180011ECB
0x180011ea2  mov     ecx, ebx; dwTlsIndex
0x180011ea4  call    cs:__imp_TlsGetValue
0x180011eab  nop     dword ptr [rax+rax+00h]
0x180011eb0  test    rax, rax
0x180011eb3  jnz     loc_18001248F
0x180011eb9  lea     rdx, [rbp+4A0h+TlsValue]; lpTlsValue
0x180011ebd  mov     ecx, ebx; dwTlsIndex
0x180011ebf  call    cs:__imp_TlsSetValue
0x180011ec6  nop     dword ptr [rax+rax+00h]
0x180011ecb  lea     r8, [rbp+4A0h+var_500]
0x180011ecf  xor     edx, edx; String2
0x180011ed1  lea     rcx, [rbp+4A0h+Uuid2]; Uuid2
0x180011ed5  call    UbpmpOpenTriggerConsumer
0x180011eda  mov     ebx, cs:UbpmpLockTrackerId
0x180011ee0  mov     edi, eax
0x180011ee2  cmp     ebx, 0FFFFFFFFh
0x180011ee5  jz      short loc_180011F0E
0x180011ee7  mov     ecx, ebx; dwTlsIndex
0x180011ee9  call    cs:__imp_TlsGetValue
0x180011ef0  nop     dword ptr [rax+rax+00h]
0x180011ef5  cmp     [rax], rsi
0x180011ef8  jnz     loc_180012496
0x180011efe  xor     edx, edx; lpTlsValue
0x180011f00  mov     ecx, ebx; dwTlsIndex
0x180011f02  call    cs:__imp_TlsSetValue
0x180011f09  nop     dword ptr [rax+rax+00h]
0x180011f0e  mov     rsi, [rbp+4A0h+var_500]
0x180011f12  test    edi, edi
0x180011f14  jz      loc_18001213F
0x180011f1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180011f21  lea     rbx, WPP_GLOBAL_Control
0x180011f28  cmp     rcx, rbx
0x180011f2b  jnz     loc_18001249D
0x180011f31  mov     r15d, [rbp+4A0h+var_520]
0x180011f35  xor     edi, edi
0x180011f37  cmp     r15d, 1
0x180011f3b  jz      loc_1800122A7
0x180011f41  test    rsi, rsi
0x180011f44  jz      loc_180011FE2
0x180011f4a  mov     ebx, cs:UbpmpLockTrackerId
0x180011f50  xorps   xmm0, xmm0
0x180011f53  xor     eax, eax
0x180011f55  mov     [rbp+4A0h+var_450], rax
0x180011f59  movups  [rbp+4A0h+TlsValue], xmm0
0x180011f5d  movups  [rbp+4A0h+var_4C0], xmm0
0x180011f61  movups  [rbp+4A0h+var_4B0], xmm0
0x180011f65  movups  [rbp+4A0h+var_4A0], xmm0
0x180011f69  movups  [rbp+4A0h+var_490], xmm0
0x180011f6d  movups  [rbp+4A0h+var_480], xmm0
0x180011f71  movups  [rbp+4A0h+var_470], xmm0
0x180011f75  movups  [rbp+4A0h+var_460], xmm0
0x180011f79  cmp     ebx, 0FFFFFFFFh
0x180011f7c  jz      short loc_180011FA7
0x180011f7e  mov     ecx, ebx; dwTlsIndex
0x180011f80  call    cs:__imp_TlsGetValue
0x180011f87  nop     dword ptr [rax+rax+00h]
0x180011f8c  test    rax, rax
0x180011f8f  jnz     loc_180012557
0x180011f95  lea     rdx, [rbp+4A0h+TlsValue]; lpTlsValue
0x180011f99  mov     ecx, ebx; dwTlsIndex
0x180011f9b  call    cs:__imp_TlsSetValue
0x180011fa2  nop     dword ptr [rax+rax+00h]
0x180011fa7  mov     rcx, rsi
0x180011faa  call    UbpmpCloseTriggerConsumer
0x180011faf  mov     ebx, cs:UbpmpLockTrackerId
  ... truncated ...
```
