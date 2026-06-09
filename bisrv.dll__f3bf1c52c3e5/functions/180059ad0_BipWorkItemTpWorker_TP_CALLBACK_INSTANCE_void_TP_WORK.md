# BipWorkItemTpWorker(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x180059ad0`
- end: `0x18005a55b`
- name: `?BipWorkItemTpWorker@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `2699`
- prototype: `void(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *)`
- caller_count: `0`
- callee_count: `32`
- tags: `authz_impersonation, loader_planting, service_task, installer_update`

## callees

- `0x180005670`
- `0x180006300`
- `0x18000b7a8`
- `0x18000d7c0`
- `0x18000da50`
- `0x180011e98`
- `0x1800121b0`
- `0x180013190`
- `0x180013d20`
- `0x180015744`
- `0x180015864`
- `0x180015880`
- `0x180016258`
- `0x180016d24`
- `0x18002d0b0`
- `0x18002e0e0`
- `0x180030a50`
- `0x18003d104`
- `0x18004e12c`
- `0x18004f170`
- `0x180055090`
- `0x180056154`
- `0x180057dec`
- `0x180058370`
- `0x180058b20`
- `0x180059ad0`
- `0x18005b0d0`
- `0x18005b748`
- `0x18006a8d4`
- `0x180078394`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x180059d05`
- `ntdll!RtlReleaseSRWLockShared` at `0x180059ebc`
- `ntdll!RtlReleaseSRWLockShared` at `0x180059d05`
- `ntdll!RtlReleaseSRWLockShared` at `0x180059ebc`
- `ntdll!RtlAcquireSRWLockShared` at `0x180059cd9`
- `ntdll!RtlAcquireSRWLockShared` at `0x180059e91`
- `ntdll!RtlAcquireSRWLockShared` at `0x180059cd9`
- `ntdll!RtlAcquireSRWLockShared` at `0x180059e91`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180059d38`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180059ef6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005a009`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005a07a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005a1ef`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005a332`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180059d38`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180059ef6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005a009`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005a07a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005a1ef`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18005a332`
- `ntdll!RtlWakeAddressAll` at `0x18005a4d0`
- `ntdll!RtlWakeAddressAll` at `0x18005a4d0`
- `ntdll!RtlFreeHeap` at `0x18005a0b9`
- `ntdll!RtlFreeHeap` at `0x18005a22d`
- `ntdll!RtlFreeHeap` at `0x18005a380`
- `ntdll!RtlFreeHeap` at `0x18005a412`
- `ntdll!RtlFreeHeap` at `0x18005a490`
- `ntdll!RtlFreeHeap` at `0x18005a0b9`
- `ntdll!RtlFreeHeap` at `0x18005a22d`
- `ntdll!RtlFreeHeap` at `0x18005a380`
- `ntdll!RtlFreeHeap` at `0x18005a412`
- `ntdll!RtlFreeHeap` at `0x18005a490`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180059c36`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180059c36`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180059cbc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180059e6f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180059cbc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180059e6f`

## pseudocode

```c
void __fastcall BipWorkItemTpWorker(struct _TP_CALLBACK_INSTANCE *a1, char *a2, struct _TP_WORK *a3)
{
  __int128 v4; // xmm0
  char *v5; // r12
  struct _BI_LOCK *v6; // rsi
  _QWORD *v7; // rdi
  __int64 v8; // rdx
  int v9; // eax
  __int64 v10; // r15
  int v11; // ebx
  const unsigned __int16 *v12; // rcx
  unsigned int ActiveSessionId; // edi
  int v14; // ebx
  struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *v15; // rcx
  int v16; // ebx
  __int64 v17; // rcx
  __int64 v18; // rcx
  unsigned __int8 WorkItemDebugMode; // al
  unsigned __int8 v20; // al
  __int64 v21; // r15
  int v22; // ebx
  __int64 v23; // rcx
  unsigned int v24; // esi
  int v25; // ebx
  struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *v26; // rcx
  int v27; // ebx
  int ActivationType; // eax
  __int64 v29; // r12
  int v30; // r15d
  __int64 v31; // rdi
  struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *v32; // rcx
  __int64 FirstActivatedInstance; // rbx
  struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *v34; // rcx
  char *v35; // r8
  int v36; // ebx
  char *v37; // rcx
  __int64 v38; // rbx
  int v39; // eax
  int v40; // ebx
  __int64 v41; // rax
  __int64 v42; // r15
  __int64 v43; // rsi
  struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *v44; // rcx
  __int64 v45; // rbx
  int v46; // eax
  char *v47; // rdx
  __int64 v48; // rbx
  int v49; // edi
  __int64 i; // rbx
  __int64 v51; // r12
  int v52; // esi
  __int64 v53; // r15
  struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *v54; // rcx
  __int64 v55; // rbx
  int v56; // eax
  char *v57; // r8
  int v58; // edi
  __int64 v59; // rbx
  __int64 j; // rbx
  int v61; // eax
  bool v62; // sf
  __int64 v63; // rdx
  _QWORD *v64; // rbx
  __int64 v65; // rax
  _QWORD *v66; // rbx
  __int64 v67; // rdx
  __int64 v68; // r8
  __int64 v69; // r9
  __int64 v70; // [rsp+30h] [rbp-D0h] BYREF
  char *v71; // [rsp+38h] [rbp-C8h] BYREF
  const unsigned __int16 *v72; // [rsp+40h] [rbp-C0h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v74; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v75; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v76[600]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v77; // [rsp+2D8h] [rbp+1D8h]
  __int128 v78; // [rsp+2E0h] [rbp+1E0h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+2F0h] [rbp+1F0h] BYREF
  __int128 v80; // [rsp+300h] [rbp+200h]
  __int128 v81; // [rsp+310h] [rbp+210h]
  __int128 v82; // [rsp+320h] [rbp+220h]
  __int128 v83; // [rsp+330h] [rbp+230h]
  PVOID P[2]; // [rsp+340h] [rbp+240h]

  memset_0(v76, 0, 0x270u);
  v72 = (const unsigned __int16 *)*((_QWORD *)a2 + 10);
  v74 = 0;
  if ( (unsigned int)dword_1800C3098 > 5 && (qword_1800C30A8 & 2) != 0 && (qword_1800C30B0 & 2) == qword_1800C30B0 )
  {
    v4 = *((_OWORD *)a2 + 2);
    LODWORD(v71) = *((_DWORD *)a2 + 126);
    *((_QWORD *)&v82 + 1) = 16;
    *(_QWORD *)&v82 = &v75;
    *((_QWORD *)&v81 + 1) = 4;
    *(_QWORD *)&v81 = &v71;
    *(_DWORD *)&EventDescriptor.Level = 261;
    UserData.Ptr = (ULONGLONG)off_1800C30A0;
    v75 = v4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 2;
    UserData.Size = *(unsigned __int16 *)off_1800C30A0;
    *(_QWORD *)&v80 = &dword_1800B2D3C;
    UserData.Reserved = 2;
    *((_QWORD *)&v80 + 1) = 0x10000002ELL;
    LODWORD(v70) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
  }
  v5 = (char *)NtCurrentTeb()->ThreadLocalStoragePointer + 8 * (unsigned int)tls_index;
  v71 = v5;
LABEL_6:
  v6 = (struct _BI_LOCK *)(a2 + 56);
LABEL_7:
  v7 = a2 + 488;
  while ( 1 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        while ( 1 )
        {
          while ( 1 )
          {
            while ( 1 )
            {
              BipSyncAcquireLock(v6);
              v9 = *((_DWORD *)a2 + 126);
              if ( (v9 & 0x10) != 0 )
              {
                v10 = *(_QWORD *)v5;
                do
                {
                  LOBYTE(v8) = 1;
                  *((_DWORD *)a2 + 126) = v9 & 0xFFFFFFEF;
                  BipSyncReleaseLock(v6, v8);
                  BipAcquireGlobalLock();
                  v11 = 1 << dword_1800C46D8;
                  if ( *(_DWORD *)(v10 + 4) >= (unsigned int)(1 << dword_1800C46D8) && IsDebuggerPresent() )
                    BipSyncDebugPrintLockBug((struct _BI_LOCK *)BipSessionLock);
                  RtlAcquireSRWLockShared(BipSessionLock);
                  v12 = v72;
                  *(_DWORD *)(v10 + 4) |= v11;
                  ActiveSessionId = BipPackageGetActiveSessionId(v12);
                  v14 = ~(1 << dword_1800C46D8);
                  RtlReleaseSRWLockShared(BipSessionLock);
                  *(_DWORD *)(v10 + 4) &= v14;
                  BipLockWatchdogContextDisarmWatchdog(v15);
                  v16 = ~(1 << dword_1800C3CB0);
                  dword_1800C3CB4 = 0;
                  *(_DWORD *)(v10 + 8) &= v16;
                  RtlReleaseSRWLockExclusive(&BipGlobalLock);
                  v17 = *((unsigned int *)a2 + 100);
                  *(_DWORD *)(v10 + 4) &= v16;
                  if ( (unsigned __int8)BipUtilActTypeIsDebugSupported(v17) )
                    WorkItemDebugMode = BipSystemPsmGetWorkItemDebugMode(
                                          v18,
                                          ActiveSessionId,
                                          *((_QWORD *)v72 + 3),
                                          v72 + 208);
                  else
                    WorkItemDebugMode = 0;
                  BipWorkItemProcessBackgroundAccessState((struct _BI_WORK_ITEM *)a2, WorkItemDebugMode);
                  BipSyncAcquireLock(v6);
                  v9 = *((_DWORD *)a2 + 126);
                }
                while ( (v9 & 0x10) != 0 );
                v5 = v71;
                v7 = a2 + 488;
              }
              if ( (v9 & 0x200) == 0 )
                break;
              LOBYTE(v8) = 1;
              *((_DWORD *)a2 + 126) = v9 & 0xFFFFFDFF;
              BipSyncReleaseLock(v6, v8);
              v20 = BipWorkItemRequiresConnectivityInStandby(a2);
              BipSystemStateCheckSetWorkItemNetworkRequest((struct _BI_WORK_ITEM *)a2, v20);
            }
            if ( (v9 & 8) == 0 )
              break;
            LOBYTE(v8) = 1;
            *((_DWORD *)a2 + 126) = v9 & 0xFFFFFFF7;
            BipSyncReleaseLock(v6, v8);
            BipWorkItemUpdateCrmActivity((struct _BI_WORK_ITEM *)a2);
          }
          if ( (v9 & 2) == 0 )
            break;
          LOBYTE(v8) = 1;
          *((_DWORD *)a2 + 126) = v9 & 0xFFFFFFFD;
          BipSyncReleaseLock(v6, v8);
          BipWorkItemPendingInstanceProcessHamActivities((struct _BI_WORK_ITEM *)a2);
        }
        if ( (v9 & 4) != 0 )
        {
          LOBYTE(v8) = 1;
          *((_DWORD *)a2 + 126) = v9 & 0xFFFFFFFB;
          BipSyncReleaseLock(v6, v8);
          BipAcquireGlobalLock();
          v21 = *(_QWORD *)v5;
          v22 = 1 << dword_1800C46D8;
          if ( *(_DWORD *)(*(_QWORD *)v5 + 4LL) >= (unsigned int)(1 << dword_1800C46D8) && IsDebuggerPresent() )
            BipSyncDebugPrintLockBug((struct _BI_LOCK *)BipSessionLock);
          RtlAcquireSRWLockShared(BipSessionLock);
          v23 = *((_QWORD *)a2 + 10);
          *(_DWORD *)(v21 + 4) |= v22;
          v24 = BipPackageGetActiveSessionId(v23);
          v25 = ~(1 << dword_1800C46D8);
          RtlReleaseSRWLockShared(BipSessionLock);
          *(_DWORD *)(v21 + 4) &= v25;
          BipLockWatchdogContextDisarmWatchdog(v26);
          *(_QWORD *)&EventDescriptor.Id = v21 + 8;
          v27 = ~(1 << dword_1800C3CB0);
          dword_1800C3CB4 = 0;
          *(_DWORD *)(v21 + 8) &= v27;
          RtlReleaseSRWLockExclusive(&BipGlobalLock);
          *(_DWORD *)(v21 + 4) &= v27;
          ActivationType = BipGetActivationType(a2);
          BipUtilTerminationDataInitialize(
            *((_QWORD *)a2 + 11) + 60LL,
            *((_QWORD *)a2 + 10) + 160LL,
            v24,
            *(_QWORD *)(*((_QWORD *)a2 + 10) + 24LL),
            ActivationType,
            v76);
          v29 = 0;
          *(_OWORD *)P = 0;
          LODWORD(P[1]) = 10;
          v70 = 0;
          UserData = 0;
          v80 = 0;
          v81 = 0;
          v82 = 0;
          v83 = 0;
          BipAcquireGlobalLock();
          v30 = 0;
          v31 = 0;
          FirstActivatedInstance = BipWorkItemGetFirstActivatedInstance(a2);
          while ( FirstActivatedInstance )
          {
            if ( (*(_BYTE *)(FirstActivatedInstance + 136) & 0x20) != 0 )
            {
              v30 = BipTaskInstanceVariableArrayEnsureCapacity((unsigned int)(v31 + 1), &UserData, &v70);
              if ( v30 < 0 )
              {
                BipLockWatchdogContextDisarmWatchdog(v34);
                v40 = ~(1 << dword_1800C3CB0);
                dword_1800C3CB4 = 0;
                **(_DWORD **)&EventDescriptor.Id &= v40;
                RtlReleaseSRWLockExclusive(&BipGlobalLock);
                v5 = v71;
                *(_DWORD *)(*(_QWORD *)v71 + 4LL) &= v40;
                goto LABEL_44;
              }
              v29 = v70;
              *(_QWORD *)(v70 + 8 * v31) = FirstActivatedInstance;
              v31 = (unsigned int)(v31 + 1);
            }
            v35 = *(char **)(FirstActivatedInstance + 16);
            FirstActivatedInstance = 0;
            v32 = (struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)(v35 - 16);
            if ( v35 != a2 + 112 )
              FirstActivatedInstance = (__int64)(v35 - 16);
          }
          BipLockWatchdogContextDisarmWatchdog(v32);
          v36 = ~(1 << dword_1800C3CB0);
          dword_1800C3CB4 = 0;
          **(_DWORD **)&EventDescriptor.Id &= v36;
          RtlReleaseSRWLockExclusive(&BipGlobalLock);
          v37 = v71;
          *(_DWORD *)(*(_QWORD *)v71 + 4LL) &= v36;
          v38 = 0;
          if ( (_DWORD)v31 )
          {
            while ( 1 )
            {
              v39 = BipWorkItemActOnInstanceForTermination(*(struct _BI_ACTIVATED_TASK_INSTANCE **)(v29 + 8 * v38), v76);
              if ( v39 < 0 )
                break;
              v38 = (unsigned int)(v38 + 1);
              if ( (unsigned int)v38 >= (unsigned int)v31 )
              {
                v5 = v71;
                goto LABEL_44;
              }
            }
            v5 = v71;
            v30 = v39;
          }
          else
          {
            v5 = v37;
          }
LABEL_44:
          if ( P[0] )
            RtlFreeHeap(BipHeap, 0, P[0]);
          if ( v30 < 0 )
          {
            v76[592] = 1;
            v41 = BipWorkItemGetFirstActivatedInstance(a2);
            v77 = *(_QWORD *)(v41 + 320);
            v78 = *(_OWORD *)v41;
            BipUtilTerminationDataIssueTermination(v76);
          }
          goto LABEL_6;
        }
        if ( (v9 & 0x40) == 0 )
          break;
        LOBYTE(v8) = 1;
        *((_DWORD *)a2 + 126) = v9 & 0xFFFFFFBF;
        BipSyncReleaseLock(v6, v8);
        if ( (unsigned __int8)BipWorkItemRequiresIdleDetection(a2, 0) )
        {
          v42 = 0;
          *(_OWORD *)P = 0;
          LODWORD(P[1]) = 10;
          v70 = 0;
          UserData = 0;
          v80 = 0;
          v81 = 0;
          v82 = 0;
          v83 = 0;
          BipAcquireGlobalLock();
          v43 = 0;
          v45 = BipWorkItemGetFirstActivatedInstance(a2);
          while ( v45 )
          {
            v46 = BipTaskInstanceVariableArrayEnsureCapacity((unsigned int)(v43 + 1), &UserData, &v70);
            v42 = v70;
            if ( v46 < 0 )
              break;
            *(_QWORD *)(v70 + 8 * v43) = v45;
            v44 = (struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)(a2 + 112);
            v47 = *(char **)(v45 + 16);
            v43 = (unsigned int)(v43 + 1);
            v45 = 0;
            if ( v47 != a2 + 112 )
              v45 = (__int64)(v47 - 16);
          }
          BipLockWatchdogContextDisarmWatchdog(v44);
          v48 = *(_QWORD *)v5;
          v49 = ~(1 << dword_1800C3CB0);
          dword_1800C3CB4 = 0;
          *(_DWORD *)(v48 + 8) &= v49;
          RtlReleaseSRWLockExclusive(&BipGlobalLock);
          *(_DWORD *)(v48 + 4) &= v49;
          for ( i = 0; (unsigned int)i < (unsigned int)v43; i = (unsigned int)(i + 1) )
            BipWorkItemActOnInstanceForIdleDetection(*(struct _BI_ACTIVATED_TASK_INSTANCE **)(v42 + 8 * i), 0);
          if ( P[0] )
            RtlFreeHeap(BipHeap, 0, P[0]);
          goto LABEL_6;
        }
      }
      if ( (v9 & 0x80u) != 0 )
      {
        LOBYTE(v8) = 1;
        *((_DWORD *)a2 + 126) = v9 & 0xFFFFFF7F;
        BipSyncReleaseLock(v6, v8);
        v51 = 0;
        *(_OWORD *)P = 0;
        LODWORD(P[1]) = 10;
        v70 = 0;
        UserData = 0;
        v80 = 0;
        v81 = 0;
        v82 = 0;
        v83 = 0;
        BipAcquireGlobalLock();
        v52 = 0;
        v53 = 0;
        v55 = BipWorkItemGetFirstActivatedInstance(a2);
        while ( v55 )
        {
          if ( !BipWorkItemFilterInstanceForReleaseSystemResources((struct _BI_ACTIVATED_TASK_INSTANCE *)v55) )
          {
            v56 = BipTaskInstanceVariableArrayEnsureCapacity((unsigned int)(v53 + 1), &UserData, &v70);
            v51 = v70;
            v52 = v56;
            if ( v56 < 0 )
              break;
            *(_QWORD *)(v70 + 8 * v53) = v55;
            v53 = (unsigned int)(v53 + 1);
          }
          v57 = *(char **)(v55 + 16);
          v55 = 0;
          v54 = (struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)(v57 - 16);
          if ( v57 != a2 + 112 )
            v55 = (__int64)(v57 - 16);
        }
        BipLockWatchdogContextDisarmWatchdog(v54);
        v58 = ~(1 << dword_1800C3CB0);
        dword_1800C3CB4 = 0;
        v59 = *(_QWORD *)v71;
        *(_DWORD *)(*(_QWORD *)v71 + 8LL) &= v58;
        RtlReleaseSRWLockExclusive(&BipGlobalLock);
        *(_DWORD *)(v59 + 4) &= v58;
        for ( j = 0; (unsigned int)j < (unsigned int)v53; j = (unsigned int)(j + 1) )
        {
          v61 = BipWorkItemActOnInstanceForReleaseSystemResources(
                  *(struct _BI_ACTIVATED_TASK_INSTANCE **)(v51 + 8 * j),
                  0);
          if ( v61 < 0 && v52 >= 0 )
            v52 = v61;
        }
        if ( P[0] )
          RtlFreeHeap(BipHeap, 0, P[0]);
        v62 = v52 < 0;
        v6 = (struct _BI_LOCK *)(a2 + 56);
        if ( v62 )
        {
          BipSyncAcquireLock((struct _BI_LOCK *)(a2 + 56));
          *((_DWORD *)a2 + 126) |= 0x80u;
          LOBYTE(v63) = 1;
          BipSyncReleaseLock(a2 + 56, v63);
        }
        v5 = v71;
        goto LABEL_7;
      }
      if ( (_QWORD *)*v7 == v7 )
        break;
      while ( 1 )
      {
        v64 = (_QWORD *)*v7;
        if ( (_QWORD *)*v7 == v7 )
          break;
        if ( (_QWORD *)v64[1] != v7 || (v65 = *v64, *(_QWORD **)(*v64 + 8LL) != v64) )
          __fastfail(3u);
        *v7 = v65;
        *(_QWORD *)(v65 + 8) = v7;
        LOBYTE(v8) = 1;
        *(_OWORD *)v64 = 0;
        BipSyncReleaseLock(v6, v8);
        v66 = v64 - 12;
        BipTaskInstanceRundown(v66);
        BipTaskInstanceCleanup(v66);
        RtlFreeHeap(BipHeap, 0, v66);
        BipSyncAcquireLock(v6);
      }
      LOBYTE(v8) = 1;
      BipSyncReleaseLock(v6, v8);
    }
    LOBYTE(v8) = 1;
    if ( (v9 & 0x20) == 0 )
      break;
    *((_DWORD *)a2 + 126) = v9 & 0xFFFFFFDF;
    BipSyncReleaseLock(v6, v8);
    BipWorkItemEaContextCleanupQueuedContexts(a2);
  }
  v74 = *((_OWORD *)a2 + 2);
  if ( (v9 & 0x100) != 0 )
  {
    BipSyncReleaseLock(v6, v8);
    BipWorkItemRundown((struct _BI_WORK_ITEM *)a2);
    BipWorkItemCleanup((struct _BI_WORK_ITEM *)a2);
    RtlFreeHeap(BipHeap, 0, a2);
  }
  else
  {
    *((_DWORD *)a2 + 126) = v9 & 0xFFFFFFFE;
    BipSyncReleaseLock(v6, v8);
  }
  BipSyncAcquireLock((struct _BI_LOCK *)&qword_1800C4600);
  --dword_1800C4650;
  LOBYTE(v67) = 1;
  BipSyncReleaseLock(&qword_1800C4600, v67);
  RtlWakeAddressAll(&dword_1800C4650);
  if ( (unsigned int)dword_1800C3098 > 5 && (qword_1800C30A8 & 2) != 0 && (qword_1800C30B0 & 2) == qword_1800C30B0 )
  {
    v72 = 0;
    *(_QWORD *)&EventDescriptor.Id = &v74;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>>(
      (__int64)&dword_1800C3098,
      (unsigned __int8 *)&dword_1800B3304,
      v68,
      v69,
      &v72,
      (__int64 *)&EventDescriptor);
  }
}

```

## disassembly

```asm
0x180059ad0  push    rbp
0x180059ad2  push    rbx
0x180059ad3  push    rsi
0x180059ad4  push    rdi
0x180059ad5  push    r12
0x180059ad7  push    r13
0x180059ad9  push    r14
0x180059adb  push    r15
0x180059add  lea     rbp, [rsp-268h]
0x180059ae5  sub     rsp, 368h
0x180059aec  mov     rax, cs:__security_cookie
0x180059af3  xor     rax, rsp
0x180059af6  mov     [rbp+2A0h+var_50], rax
0x180059afd  mov     r14, rdx
0x180059b00  lea     rcx, [rbp+2A0h+var_320]; void *
0x180059b04  xor     edx, edx; Val
0x180059b06  mov     r8d, 270h; Size
0x180059b0c  call    memset_0
0x180059b11  mov     rax, [r14+50h]
0x180059b15  xorps   xmm0, xmm0
0x180059b18  mov     [rsp+3A0h+var_360], rax
0x180059b1d  mov     eax, cs:dword_1800C3098
0x180059b23  movups  [rsp+3A0h+var_348], xmm0
0x180059b28  cmp     eax, 5
0x180059b2b  jbe     loc_180059C3C
0x180059b31  mov     rcx, cs:qword_1800C30B0
0x180059b38  mov     rax, cs:qword_1800C30A8
0x180059b3f  test    al, 2
0x180059b41  jz      loc_180059C3C
0x180059b47  mov     rax, rcx
0x180059b4a  and     eax, 2
0x180059b4d  cmp     rax, rcx
0x180059b50  jnz     loc_180059C3C
0x180059b56  mov     eax, [r14+1F8h]
0x180059b5d  lea     rcx, _TraceLoggingMetadata
0x180059b64  movups  xmm0, xmmword ptr [r14+20h]
0x180059b69  mov     dword ptr [rsp+3A0h+var_368], eax
0x180059b6d  lea     rdx, [rsp+3A0h+EventDescriptor]; EventDescriptor
0x180059b72  mov     qword ptr [rbp+2A0h+var_80+8], 10h
0x180059b7d  lea     rax, [rsp+3A0h+var_338]
0x180059b82  mov     qword ptr [rbp+2A0h+var_80], rax
0x180059b89  xor     r9d, r9d; RelatedActivityId
0x180059b8c  lea     rax, [rsp+3A0h+var_368]
0x180059b91  mov     qword ptr [rbp+2A0h+var_90+8], 4
0x180059b9c  mov     qword ptr [rbp+2A0h+var_90], rax
0x180059ba3  xor     r8d, r8d; ActivityId
0x180059ba6  movzx   eax, cs:word_1800B2D32
0x180059bad  mov     dword ptr [rsp+3A0h+EventDescriptor.Level], eax
0x180059bb1  mov     rax, cs:off_1800C30A0
0x180059bb8  mov     [rbp+2A0h+var_B0.Ptr], rax
0x180059bbf  movups  [rsp+3A0h+var_338], xmm0
0x180059bc4  mov     dword ptr [rsp+3A0h+EventDescriptor.Id], 0B000000h
0x180059bcc  mov     [rsp+3A0h+EventDescriptor.Keyword], 2
0x180059bd5  movzx   eax, word ptr [rax]
0x180059bd8  mov     [rbp+2A0h+var_B0.Size], eax
0x180059bde  lea     rax, dword_1800B2D3C
0x180059be5  mov     qword ptr [rbp+2A0h+var_A0], rax
0x180059bec  lea     rax, _TraceLoggingMetadataEnd
0x180059bf3  sub     eax, ecx
0x180059bf5  mov     dword ptr [rbp+2A0h+var_B0.0Ch], 2
0x180059bff  mov     dword ptr [rbp+2A0h+var_A0+8], 2Eh ; '.'
0x180059c09  mov     dword ptr [rbp+2A0h+var_A0+0Ch], 1
0x180059c13  mov     dword ptr [rsp+3A0h+var_370], eax
0x180059c17  mov     eax, dword ptr [rsp+3A0h+var_370]
0x180059c1b  mov     rcx, cs:RegHandle; RegHandle
0x180059c22  lea     rax, [rbp+2A0h+var_B0]
0x180059c29  mov     [rsp+3A0h+UserData], rax; UserData
0x180059c2e  mov     [rsp+3A0h+UserDataCount], 4; UserDataCount
0x180059c36  call    cs:__imp_EventWriteTransfer
0x180059c3c  mov     ecx, cs:_tls_index
0x180059c42  mov     rax, gs:58h
0x180059c4b  mov     r13d, 4
0x180059c51  lea     r12, [rax+rcx*8]
0x180059c55  mov     [rsp+3A0h+var_368], r12
0x180059c5a  lea     rsi, [r14+38h]
0x180059c5e  lea     rdi, [r14+1E8h]
0x180059c65  mov     ebx, 8
0x180059c6a  nop     word ptr [rax+rax+00h]
0x180059c70  mov     dl, 1
0x180059c72  mov     rcx, rsi; struct _BI_LOCK *
0x180059c75  call    BipSyncAcquireLock
0x180059c7a  mov     eax, [r14+1F8h]
0x180059c81  test    al, 10h
0x180059c83  jz      loc_180059DAC
0x180059c89  mov     r15, [r12]
0x180059c8d  mov     r12d, ebx
0x180059c90  and     eax, 0FFFFFFEFh
0x180059c93  mov     dl, 1
0x180059c95  mov     rcx, rsi
0x180059c98  mov     [r14+1F8h], eax
0x180059c9f  call    BipSyncReleaseLock
0x180059ca4  call    BipAcquireGlobalLock
0x180059ca9  mov     ecx, cs:dword_1800C46D8
0x180059caf  mov     ebx, 1
0x180059cb4  shl     ebx, cl
0x180059cb6  cmp     [r15+r13], ebx
0x180059cba  jb      short loc_180059CD2
0x180059cbc  call    cs:__imp_IsDebuggerPresent
0x180059cc2  test    eax, eax
0x180059cc4  jz      short loc_180059CD2
0x180059cc6  lea     rcx, BipSessionLock; struct _BI_LOCK *
0x180059ccd  call    ?BipSyncDebugPrintLockBug@@YAXPEAU_BI_LOCK@@@Z; BipSyncDebugPrintLockBug(_BI_LOCK *)
0x180059cd2  lea     rcx, BipSessionLock
0x180059cd9  call    cs:__imp_RtlAcquireSRWLockShared
0x180059cdf  mov     rcx, [rsp+3A0h+var_360]
0x180059ce4  or      [r15+r13], ebx
0x180059ce8  call    BipPackageGetActiveSessionId
0x180059ced  mov     ecx, cs:dword_1800C46D8
0x180059cf3  mov     ebx, 1
0x180059cf8  shl     ebx, cl
0x180059cfa  mov     edi, eax
0x180059cfc  lea     rcx, BipSessionLock
0x180059d03  not     ebx
0x180059d05  call    cs:__imp_RtlReleaseSRWLockShared
0x180059d0b  and     [r15+r13], ebx
0x180059d0f  call    ?BipLockWatchdogContextDisarmWatchdog@@YAXPEAU_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT@@@Z; BipLockWatchdogContextDisarmWatchdog(_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)
0x180059d14  mov     ecx, cs:dword_1800C3CB0
0x180059d1a  mov     ebx, 1
0x180059d1f  shl     ebx, cl
0x180059d21  lea     rcx, BipGlobalLock
0x180059d28  not     ebx
0x180059d2a  mov     cs:dword_1800C3CB4, 0
0x180059d34  and     [r12+r15], ebx
0x180059d38  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180059d3e  mov     ecx, [r14+190h]
0x180059d45  and     [r15+r13], ebx
0x180059d49  call    BipUtilActTypeIsDebugSupported
0x180059d4e  test    al, al
0x180059d50  jz      short loc_180059D6B
0x180059d52  mov     rbx, [rsp+3A0h+var_360]
0x180059d57  mov     edx, edi
0x180059d59  mov     r8, [rbx+18h]
0x180059d5d  lea     r9, [rbx+1A0h]
0x180059d64  call    BipSystemPsmGetWorkItemDebugMode
0x180059d69  jmp     short loc_180059D6D
0x180059d6b  xor     al, al
0x180059d6d  movzx   edx, al; unsigned __int8
0x180059d70  mov     rcx, r14; struct _BI_WORK_ITEM *
0x180059d73  call    ?BipWorkItemProcessBackgroundAccessState@@YAXPEAU_BI_WORK_ITEM@@E@Z; BipWorkItemProcessBackgroundAccessState(_BI_WORK_ITEM *,uchar)
0x180059d78  mov     dl, 1
0x180059d7a  mov     rcx, rsi; struct _BI_LOCK *
0x180059d7d  call    BipSyncAcquireLock
0x180059d82  mov     eax, [r14+1F8h]
0x180059d89  mov     ecx, 4
0x180059d8e  mov     r13d, ecx
0x180059d91  test    al, 10h
0x180059d93  jnz     loc_180059C90
0x180059d99  mov     r12, [rsp+3A0h+var_368]
0x180059d9e  lea     rdi, [r14+1E8h]
0x180059da5  mov     ebx, 8
0x180059daa  jmp     short loc_180059DB1
0x180059dac  mov     ecx, 4
0x180059db1  mov     r13, rcx
0x180059db4  bt      eax, 9
0x180059db8  jnb     short loc_180059DE7
0x180059dba  btr     eax, 9
0x180059dbe  mov     dl, 1
0x180059dc0  mov     rcx, rsi
0x180059dc3  mov     [r14+1F8h], eax
0x180059dca  call    BipSyncReleaseLock
0x180059dcf  mov     rcx, r14
0x180059dd2  call    BipWorkItemRequiresConnectivityInStandby
0x180059dd7  movzx   edx, al; unsigned __int8
0x180059dda  mov     rcx, r14; struct _BI_WORK_ITEM *
0x180059ddd  call    ?BipSystemStateCheckSetWorkItemNetworkRequest@@YAXPEAU_BI_WORK_ITEM@@E@Z; BipSystemStateCheckSetWorkItemNetworkRequest(_BI_WORK_ITEM *,uchar)
0x180059de2  jmp     loc_180059C70
0x180059de7  test    al, 8
0x180059de9  jz      short loc_180059E0C
0x180059deb  and     eax, 0FFFFFFF7h
0x180059dee  mov     dl, 1
0x180059df0  mov     rcx, rsi
0x180059df3  mov     [r14+1F8h], eax
0x180059dfa  call    BipSyncReleaseLock
0x180059dff  mov     rcx, r14; struct _BI_WORK_ITEM *
0x180059e02  call    BipWorkItemUpdateCrmActivity
0x180059e07  jmp     loc_180059C70
0x180059e0c  test    al, 2
0x180059e0e  jz      short loc_180059E31
0x180059e10  and     eax, 0FFFFFFFDh
0x180059e13  mov     dl, 1
0x180059e15  mov     rcx, rsi
0x180059e18  mov     [r14+1F8h], eax
0x180059e1f  call    BipSyncReleaseLock
0x180059e24  mov     rcx, r14; struct _BI_WORK_ITEM *
0x180059e27  call    ?BipWorkItemPendingInstanceProcessHamActivities@@YAJPEAU_BI_WORK_ITEM@@@Z; BipWorkItemPendingInstanceProcessHamActivities(_BI_WORK_ITEM *)
0x180059e2c  jmp     loc_180059C70
0x180059e31  test    al, 4
0x180059e33  jz      loc_18005A0FD
0x180059e39  and     eax, 0FFFFFFFBh
0x180059e3c  mov     dl, 1
0x180059e3e  mov     rcx, rsi
0x180059e41  mov     [r14+1F8h], eax
0x180059e48  call    BipSyncReleaseLock
0x180059e4d  call    BipAcquireGlobalLock
0x180059e52  mov     r15, [r12]
0x180059e56  mov     ebx, 1
0x180059e5b  mov     ecx, cs:dword_1800C46D8
0x180059e61  mov     r12d, 4
0x180059e67  shl     ebx, cl
0x180059e69  cmp     [r12+r15], ebx
0x180059e6d  jb      short loc_180059E85
0x180059e6f  call    cs:__imp_IsDebuggerPresent
0x180059e75  test    eax, eax
0x180059e77  jz      short loc_180059E85
0x180059e79  lea     rcx, BipSessionLock; struct _BI_LOCK *
0x180059e80  call    ?BipSyncDebugPrintLockBug@@YAXPEAU_BI_LOCK@@@Z; BipSyncDebugPrintLockBug(_BI_LOCK *)
0x180059e85  lea     rcx, BipSessionLock
0x180059e8c  mov     edi, 8
0x180059e91  call    cs:__imp_RtlAcquireSRWLockShared
0x180059e97  mov     rcx, [r14+50h]
0x180059e9b  or      [r12+r15], ebx
0x180059e9f  call    BipPackageGetActiveSessionId
0x180059ea4  mov     ecx, cs:dword_1800C46D8
0x180059eaa  mov     ebx, 1
0x180059eaf  shl     ebx, cl
0x180059eb1  mov     esi, eax
0x180059eb3  lea     rcx, BipSessionLock
0x180059eba  not     ebx
0x180059ebc  call    cs:__imp_RtlReleaseSRWLockShared
0x180059ec2  and     [r12+r15], ebx
0x180059ec6  call    ?BipLockWatchdogContextDisarmWatchdog@@YAXPEAU_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT@@@Z; BipLockWatchdogContextDisarmWatchdog(_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)
0x180059ecb  mov     ecx, cs:dword_1800C3CB0
0x180059ed1  lea     rax, [r15+rdi]
0x180059ed5  mov     ebx, 1
0x180059eda  mov     qword ptr [rsp+3A0h+EventDescriptor.Id], rax
0x180059edf  shl     ebx, cl
0x180059ee1  lea     rcx, BipGlobalLock
0x180059ee8  not     ebx
0x180059eea  mov     cs:dword_1800C3CB4, 0
0x180059ef4  and     [rax], ebx
0x180059ef6  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180059efc  and     [r12+r15], ebx
0x180059f00  mov     rcx, r14
0x180059f03  call    BipGetActivationType
0x180059f08  mov     r9, [r14+50h]
0x180059f0c  lea     r8, [rbp+2A0h+var_320]
0x180059f10  mov     rcx, [r14+58h]
0x180059f14  mov     [rsp+3A0h+UserData], r8
0x180059f19  add     rcx, 3Ch ; '<'
0x180059f1d  mov     r8d, esi
0x180059f20  mov     [rsp+3A0h+UserDataCount], eax
0x180059f24  lea     rdx, [r9+0A0h]
0x180059f2b  mov     r9, [r9+18h]
0x180059f2f  call    BipUtilTerminationDataInitialize
0x180059f34  xorps   xmm0, xmm0
0x180059f37  xor     r12d, r12d
0x180059f3a  movups  xmmword ptr [rbp+2A0h+P], xmm0
0x180059f41  mov     dword ptr [rbp+2A0h+P+8], 0Ah
0x180059f4b  mov     [rsp+3A0h+var_370], r12
0x180059f50  movups  xmmword ptr [rbp+2A0h+var_B0.Ptr], xmm0
0x180059f57  movups  [rbp+2A0h+var_A0], xmm0
0x180059f5e  movups  [rbp+2A0h+var_90], xmm0
0x180059f65  movups  [rbp+2A0h+var_80], xmm0
0x180059f6c  movups  [rbp+2A0h+var_70], xmm0
0x180059f73  call    BipAcquireGlobalLock
0x180059f78  mov     rcx, r14
0x180059f7b  xor     r15d, r15d
0x180059f7e  xor     edi, edi
0x180059f80  call    BipWorkItemGetFirstActivatedInstance
0x180059f85  mov     rbx, rax
0x180059f88  test    rax, rax
0x180059f8b  jz      short loc_180059FDD
0x180059f8d  nop     dword ptr [rax]
0x180059f90  test    byte ptr [rbx+88h], 20h
0x180059f97  jz      short loc_180059FC3
0x180059f99  lea     r8, [rsp+3A0h+var_370]
0x180059f9e  lea     rdx, [rbp+2A0h+var_B0]
0x180059fa5  lea     ecx, [rdi+1]
0x180059fa8  call    BipTaskInstanceVariableArrayEnsureCapacity
0x180059fad  mov     r15d, eax
0x180059fb0  test    eax, eax
0x180059fb2  js      loc_18005A04E
0x180059fb8  mov     r12, [rsp+3A0h+var_370]
0x180059fbd  mov     [r12+rdi*8], rbx
0x180059fc1  inc     edi
0x180059fc3  mov     r8, [rbx+10h]
0x180059fc7  lea     rdx, [r14+70h]
0x180059fcb  xor     ebx, ebx
0x180059fcd  cmp     r8, rdx
0x180059fd0  lea     rcx, [r8-10h]; struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *
0x180059fd4  cmovnz  rbx, rcx
0x180059fd8  test    rbx, rbx
0x180059fdb  jnz     short loc_180059F90
0x180059fdd  call    ?BipLockWatchdogContextDisarmWatchdog@@YAXPEAU_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT@@@Z; BipLockWatchdogContextDisarmWatchdog(_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)
0x180059fe2  mov     ecx, cs:dword_1800C3CB0
0x180059fe8  mov     ebx, 1
0x180059fed  mov     rax, qword ptr [rsp+3A0h+EventDescriptor.Id]
0x180059ff2  shl     ebx, cl
0x180059ff4  lea     rcx, BipGlobalLock
0x180059ffb  not     ebx
0x180059ffd  mov     cs:dword_1800C3CB4, 0
0x18005a007  and     [rax], ebx
0x18005a009  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18005a00f  mov     rcx, [rsp+3A0h+var_368]
0x18005a014  mov     edx, 4
0x18005a019  mov     rax, [rcx]
0x18005a01c  and     [rdx+rax], ebx
0x18005a01f  xor     ebx, ebx
0x18005a021  test    edi, edi
0x18005a023  jz      short loc_18005A0A1
  ... truncated ...
```
