# AfdCleanupCore

- ea: `0x140020970`
- end: `0x1400218cb`
- name: `AfdCleanupCore`
- size: `3931`
- prototype: `__int64 __fastcall(PVOID Object, __int16 *)`
- caller_count: `1`
- callee_count: `28`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140020500`

## callees

- `0x1400049b0`
- `0x140009770`
- `0x14000f450`
- `0x1400137a0`
- `0x14001c708`
- `0x14001ccdc`
- `0x14001ceb0`
- `0x14001db90`
- `0x14001e120`
- `0x14001e86c`
- `0x140020970`
- `0x14002b000`
- `0x14002c770`
- `0x14002dd90`
- `0x14002e5e0`
- `0x14003336c`
- `0x140033898`
- `0x140037944`
- `0x14003965c`
- `0x140041928`
- `0x140041a14`
- `0x14006bbc8`
- `0x1400726a0`
- `0x140072780`
- `0x1400930cc`
- `0x1400931f0`
- `0x1400933d4`
- `0x140093470`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140021614`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14002163c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140021614`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14002163c`
- `ntoskrnl!PsGetProcessExitTime` at `0x1400209b9`
- `ntoskrnl!PsGetProcessExitTime` at `0x1400209b9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400209c8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400209c8`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400209db`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400209db`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400209e7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400209e7`
- `ntoskrnl!IoCancelMiniCompletionPacket` at `0x140021859`
- `ntoskrnl!IoCancelMiniCompletionPacket` at `0x140021859`
- `ntoskrnl!IoFreeMdl` at `0x140020b7d`
- `ntoskrnl!IoFreeMdl` at `0x140020ba1`
- `ntoskrnl!IoFreeMdl` at `0x140020b7d`
- `ntoskrnl!IoFreeMdl` at `0x140020ba1`
- `ntoskrnl!MmUnlockPages` at `0x140020b6d`
- `ntoskrnl!MmUnlockPages` at `0x140020b91`
- `ntoskrnl!MmUnlockPages` at `0x140020b6d`
- `ntoskrnl!MmUnlockPages` at `0x140020b91`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14002146e`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14002164d`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14002146e`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14002164d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400215ec`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400215ec`
- `ntoskrnl!IofCompleteRequest` at `0x140020c9f`
- `ntoskrnl!IofCompleteRequest` at `0x140020d54`
- `ntoskrnl!IofCompleteRequest` at `0x140021484`
- `ntoskrnl!IofCompleteRequest` at `0x140020c9f`
- `ntoskrnl!IofCompleteRequest` at `0x140020d54`
- `ntoskrnl!IofCompleteRequest` at `0x140021484`
- `ntoskrnl!ObfDereferenceObject` at `0x14002186c`
- `ntoskrnl!ObfDereferenceObject` at `0x14002187c`
- `ntoskrnl!ObfDereferenceObject` at `0x14002186c`
- `ntoskrnl!ObfDereferenceObject` at `0x14002187c`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14002145d`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400215d7`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14002145d`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400215d7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140020be0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140020c7e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140020cb4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140020d33`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140020d69`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140020d95`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140020da6`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140020dd3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140020fed`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400211d3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140021206`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140021346`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140021382`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002143c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400214af`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140021575`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400215c6`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002165b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002183a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140020be0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140020c7e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140020cb4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140020d33`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140020d69`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140020d95`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140020da6`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140020dd3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140020fed`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400211d3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140021206`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140021346`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140021382`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002143c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400214af`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140021575`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400215c6`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002165b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002183a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400209fc`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140020a3a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140020c1e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140020cd9`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140021324`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400213ab`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140021499`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140021535`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140021599`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140021823`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400209fc`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140020a3a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140020c1e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140020cd9`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140021324`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400213ab`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140021499`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140021535`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140021599`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140021823`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021520`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021520`
- `ntoskrnl!IoGetCurrentProcess` at `0x140020de3`
- `ntoskrnl!IoGetCurrentProcess` at `0x140020de3`
- `ntoskrnl!EtwWrite` at `0x140020b2c`
- `ntoskrnl!EtwWrite` at `0x140020b2c`
- `NETIO!NsiDeregisterChangeNotification` at `0x1400214e4`
- `NETIO!NsiDeregisterChangeNotification` at `0x140021505`
- `NETIO!NsiDeregisterChangeNotification` at `0x1400214e4`
- `NETIO!NsiDeregisterChangeNotification` at `0x140021505`

## pseudocode

```c
__int64 __fastcall AfdCleanupCore(PVOID Object, __int16 *a2)
{
  PVOID v3; // r13
  int v4; // r12d
  LARGE_INTEGER ProcessExitTime; // rbx
  __int64 v6; // rsi
  int *v7; // rcx
  unsigned int v8; // r15d
  int v9; // eax
  int *v10; // rcx
  __int16 v11; // ax
  _QWORD **v12; // rsi
  _QWORD *v13; // rcx
  _QWORD *v14; // rax
  IRP *v15; // rbx
  CCHAR v16; // dl
  _QWORD **v17; // rsi
  _QWORD *v18; // rcx
  _QWORD *v19; // rax
  IRP *v20; // rbx
  CCHAR v21; // dl
  struct _KPROCESS *v22; // rbx
  __int64 v23; // rsi
  __int64 v24; // r8
  char v25; // cl
  __int64 v26; // rcx
  __int16 v27; // ax
  int v28; // eax
  int v29; // eax
  char v30; // bl
  __int64 v31; // r9
  __int64 v32; // rdx
  _QWORD *v33; // rbx
  __int64 v34; // r9
  int v35; // r9d
  __int64 *v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rax
  int v39; // ebx
  __int64 v40; // rdx
  signed __int64 v41; // rax
  bool v42; // cc
  signed __int64 v43; // rax
  _QWORD **v44; // rsi
  _QWORD *v45; // rax
  _QWORD *v46; // rcx
  __int64 v47; // rdx
  _QWORD *v48; // rbx
  _BYTE *v49; // rax
  _QWORD *v50; // rbx
  _QWORD *v51; // rsi
  _QWORD *v52; // rbx
  _QWORD *v53; // rax
  __int64 v54; // rcx
  __int64 v55; // rbx
  void (__fastcall *v56)(_QWORD, __int64); // rsi
  KIRQL v57; // cl
  struct _FILE_OBJECT *v58; // rsi
  signed __int32 v59; // eax
  unsigned __int8 i; // bl
  char v61; // cl
  __int64 v62; // rbx
  KIRQL Irql[8]; // [rsp+40h] [rbp-C0h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+48h] [rbp-B8h] BYREF
  int v66; // [rsp+60h] [rbp-A0h] BYREF
  int v67; // [rsp+68h] [rbp-98h] BYREF
  int v68; // [rsp+70h] [rbp-90h] BYREF
  int v69; // [rsp+78h] [rbp-88h] BYREF
  __int64 v70; // [rsp+80h] [rbp-80h] BYREF
  PVOID v71; // [rsp+88h] [rbp-78h]
  struct _KLOCK_QUEUE_HANDLE ActivityId; // [rsp+90h] [rbp-70h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v74; // [rsp+C0h] [rbp-40h]
  _BYTE v75[56]; // [rsp+C8h] [rbp-38h] BYREF

  v71 = Object;
  memset(&LockHandle, 0, sizeof(LockHandle));
  v3 = Object;
  v4 = 1;
  ProcessExitTime = PsGetProcessExitTime();
  KeEnterCriticalRegion();
  ExWaitForRundownProtectionRelease((PEX_RUNDOWN_REF)a2 + 49);
  KeLeaveCriticalRegion();
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)a2 + 7, &LockHandle);
  AfdIndicateEventSelectEvent(a2, 32, 0);
  if ( (unsigned __int8)AfdIndicatePollEvent(a2, 32, 0, &LockHandle) )
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)a2 + 7, &LockHandle);
  v6 = *((_QWORD *)a2 + 10);
  *((_DWORD *)a2 + 2) |= 0x800u;
  if ( v6 )
  {
    v7 = *(int **)(v6 + 56);
    v8 = -1073741247;
    if ( *a2 != -20526 )
      v8 = -1073741536;
    v69 = v7[1];
    v9 = *v7;
    v10 = *(int **)(v6 + 128);
    v68 = v9;
    v67 = v10[1];
    v66 = *v10;
    v70 = v6;
    if ( g_AfdEtwTraceEnable )
    {
      ActivityId.LockQueue.Next = (struct _KSPIN_LOCK_QUEUE *volatile)v6;
      ActivityId.LockQueue.Lock = 0;
      UserData.Ptr = (ULONGLONG)&v70;
      *(_QWORD *)&UserData.Size = 8;
      v74 = (__int64)&v66;
      *(_QWORD *)v75 = 4;
      *(_QWORD *)&v75[8] = &v67;
      *(_QWORD *)&v75[24] = &v68;
      *(_QWORD *)&v75[40] = &v69;
      *(_QWORD *)&v75[16] = 4;
      *(_QWORD *)&v75[32] = 4;
      *(_QWORD *)&v75[48] = 4;
      EtwWrite(g_AfdEtwHandle, &AFD_EVENT_CLOSE_RQ, (LPCGUID)&ActivityId, 5u, &UserData);
    }
    if ( *(int *)(v6 + 16) >= 0 )
      *(_DWORD *)(v6 + 16) = -1073741528;
    AfdRioFlushReceiveQueue(a2, v8);
    AfdRioFlushSendQueue(a2, v8);
    *(_QWORD *)(v6 + 56) = 0;
    *(_QWORD *)(v6 + 128) = 0;
    MmUnlockPages(*(PMDL *)(v6 + 48));
    IoFreeMdl(*(PMDL *)(v6 + 48));
    *(_QWORD *)(v6 + 48) = 0;
    MmUnlockPages(*(PMDL *)(v6 + 120));
    IoFreeMdl(*(PMDL *)(v6 + 120));
    *(_QWORD *)(v6 + 120) = 0;
  }
  if ( (*((_DWORD *)a2 + 2) & 0x100) != 0 && (*((_DWORD *)a2 + 2) & 0x1000) != 0 )
    v4 = 0;
  v11 = *a2;
  if ( *a2 != -20527 )
  {
    if ( v11 == 6909 )
    {
      if ( *((__int16 **)a2 + 16) == a2 + 64 )
      {
        KeReleaseInStackQueuedSpinLock(&LockHandle);
      }
      else
      {
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        AfdSanRestartRequestProcessing(a2, 3221225760LL);
      }
      goto LABEL_159;
    }
    if ( v11 == 2813 )
    {
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      v22 = (struct _KPROCESS *)*((_QWORD *)a2 + 6);
      if ( v22 == IoGetCurrentProcess() )
        AfdSanHelperCleanup(a2);
      goto LABEL_159;
    }
    if ( (v11 & 0xAFD2) != 0xAFD2 || (v23 = *((_QWORD *)a2 + 24)) == 0 )
    {
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      goto LABEL_145;
    }
    if ( _InterlockedIncrement64((volatile signed __int64 *)(v23 + 48)) <= 1 )
      __fastfail(0xEu);
    AfdCleanupConnectionTimerWheelEntry(v23, 45010);
    v25 = *((_BYTE *)a2 + 2);
    if ( ((v25 - 3) & 0xFA) != 0 )
      goto LABEL_127;
    if ( v25 == 8 )
      goto LABEL_127;
    v26 = *(unsigned int *)(v23 + 4);
    if ( (v26 & 0x1000) == 0 )
      goto LABEL_127;
    if ( (a2[3] & 1) != 0 )
      goto LABEL_127;
    v27 = a2[5];
    if ( (v27 & 4) != 0 )
      goto LABEL_127;
    if ( (v27 & 1) != 0 )
    {
      if ( (v26 & 1) != 0 )
      {
        if ( *(_QWORD *)(v23 + 56) > *(_QWORD *)(v23 + 64) + *(_QWORD *)(v23 + 72)
          || *(_BYTE *)(v23 + 105)
          || *(_QWORD *)(v23 + 80) > *(_QWORD *)(v23 + 88) + *(_QWORD *)(v23 + 96) )
        {
          goto LABEL_63;
        }
      }
      else if ( *(_WORD *)(v23 + 96) || *(_WORD *)(v23 + 98) )
      {
        goto LABEL_63;
      }
      if ( ((*((_DWORD *)a2 + 2) & 0x100) == 0 && (*((_DWORD *)a2 + 4) & 0x200) != 0 || !*(_DWORD *)(v23 + 100))
        && !*((_DWORD *)a2 + 92) )
      {
        goto LABEL_127;
      }
    }
LABEL_63:
    v28 = *(_DWORD *)(v23 + 4);
    if ( (v28 & 0x10) != 0 )
      goto LABEL_127;
    if ( (v28 & 1) != 0 )
    {
      if ( *(_QWORD *)(v23 + 56) > *(_QWORD *)(v23 + 64) + *(_QWORD *)(v23 + 72)
        || *(_BYTE *)(v23 + 105)
        || *(_QWORD *)(v23 + 80) > *(_QWORD *)(v23 + 88) + *(_QWORD *)(v23 + 96) )
      {
        goto LABEL_68;
      }
    }
    else if ( *(_WORD *)(v23 + 96) || *(_WORD *)(v23 + 98) )
    {
      goto LABEL_68;
    }
    if ( (*((_DWORD *)a2 + 2) & 0x100) == 0 && (*((_DWORD *)a2 + 4) & 0x200) != 0 || !*(_DWORD *)(v23 + 100) )
    {
      if ( ProcessExitTime.QuadPart )
      {
LABEL_69:
        if ( (BYTE8(xmmword_1400875E0) & 4) != 0 )
          WPP_SF_q(1282, 11, WPP_a4fcd062aa8634b00ff718da42c44e71_Traceguids, a2);
LABEL_125:
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        v31 = 7;
        v32 = 8000;
LABEL_126:
        AFDETW_TRACEABORT(2, v32, a2, v31);
        AfdBeginAbort(v23);
        goto LABEL_128;
      }
      if ( *((_DWORD *)a2 + 62)
        || *((_DWORD *)a2 + 92)
        || ((*((_DWORD *)a2 + 2) & 0x100) != 0 || (*((_DWORD *)a2 + 4) & 0x200) == 0)
        && (*(_QWORD *)(v23 + 56) != v23 + 56 || *(int *)(v23 + 136) > 0 || *(_QWORD *)(v23 + 104) != v23 + 104) )
      {
LABEL_93:
        if ( (*(_DWORD *)(v23 + 4) & 1) != 0 )
        {
          if ( *(_QWORD *)(v23 + 56) <= *(_QWORD *)(v23 + 72) + *(_QWORD *)(v23 + 64) && !*(_BYTE *)(v23 + 105) )
          {
            v33 = (_QWORD *)(v23 + 96);
            goto LABEL_105;
          }
          v33 = (_QWORD *)(v23 + 96);
        }
        else
        {
          v33 = (_QWORD *)(v23 + 96);
          if ( !*(_WORD *)(v23 + 96) )
            goto LABEL_105;
        }
        if ( (*((_DWORD *)a2 + 2) & 0x100) != 0 || (*((_DWORD *)a2 + 4) & 0x200) == 0 )
        {
          if ( (BYTE8(xmmword_1400875E0) & 4) != 0 )
            WPP_SF_Dq(1282, 13, WPP_a4fcd062aa8634b00ff718da42c44e71_Traceguids, *(unsigned int *)(v23 + 88), a2);
        }
        else if ( (BYTE8(xmmword_1400875E0) & 4) != 0 )
        {
          WPP_SF_qiii(v26, 12, v24, a2, *(_QWORD *)(v23 + 56), *(_QWORD *)(v23 + 64), *(_QWORD *)(v23 + 72));
        }
LABEL_105:
        if ( (*(_DWORD *)(v23 + 4) & 1) != 0 )
        {
          if ( *(_QWORD *)(v23 + 80) > *(_QWORD *)(v23 + 88) + *v33 )
            goto LABEL_109;
        }
        else if ( *(_WORD *)(v23 + 98) )
        {
LABEL_109:
          if ( (*((_DWORD *)a2 + 2) & 0x100) != 0 || (*((_DWORD *)a2 + 4) & 0x200) == 0 )
          {
            if ( (BYTE8(xmmword_1400875E0) & 4) != 0 )
              WPP_SF_Dq(1282, 15, WPP_a4fcd062aa8634b00ff718da42c44e71_Traceguids, *(unsigned int *)(v23 + 92), a2);
          }
          else if ( (BYTE8(xmmword_1400875E0) & 4) != 0 )
          {
            WPP_SF_qiii(v26, 14, v24, a2, *(_QWORD *)(v23 + 80), *(_QWORD *)(v23 + 88), *v33);
          }
        }
        if ( (*((_DWORD *)a2 + 2) & 0x100) != 0 || (*((_DWORD *)a2 + 4) & 0x200) == 0 )
        {
          v34 = *(unsigned int *)(v23 + 100);
          if ( (_DWORD)v34 )
          {
            if ( (BYTE8(xmmword_1400875E0) & 4) != 0 )
              WPP_SF_Dq(1282, 16, WPP_a4fcd062aa8634b00ff718da42c44e71_Traceguids, v34, a2);
          }
        }
        v35 = *((_DWORD *)a2 + 62);
        if ( v35 && (BYTE8(xmmword_1400875E0) & 4) != 0 )
        {
          v36 = (__int64 *)"(accept, connect, or transmit file)";
          if ( !*((_DWORD *)a2 + 92) )
            v36 = &qword_14007DC38;
          WPP_SF_lsq((_DWORD)v36, (unsigned int)&qword_14007DC38, v24, v35, (__int64)v36, (char)a2);
        }
        goto LABEL_125;
      }
      v29 = *((_DWORD *)a2 + 2);
      v30 = 0;
      if ( (v29 & 0x20000) == 0 )
      {
        *((_DWORD *)a2 + 2) = v29 | 0x20000;
        if ( (*((_DWORD *)a2 + 2) & 0x100) != 0 || (*((_DWORD *)a2 + 2) & 0x200) != 0 )
          v30 = 1;
      }
      if ( *((_BYTE *)a2 + 2) == 4 )
      {
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        if ( v30 )
          AfdDisconnectReceive(v23);
        if ( (int)AfdBeginDisconnect(a2, 0) >= 0 )
          goto LABEL_128;
        v31 = 6;
        v32 = 8001;
        goto LABEL_126;
      }
LABEL_127:
      KeReleaseInStackQueuedSpinLock(&LockHandle);
LABEL_128:
      if ( (*((_DWORD *)a2 + 2) & 0x100) != 0 || (*((_DWORD *)a2 + 4) & 0x200) == 0 )
      {
        if ( (*((_DWORD *)a2 + 2) & 0x100) != 0 && (*(_DWORD *)(v23 + 4) & 0x10) == 0 && *(int *)(v23 + 136) > 0 )
        {
          v37 = *(_QWORD *)(v23 + 16);
          UserData.Ptr = (ULONGLONG)AfdTLDontCareIOCompletion;
          v38 = *(_QWORD *)(v23 + 24);
          *(_QWORD *)&UserData.Size = 0;
          memset(&v75[4], 0, 52);
          v74 = 0xFFFD00000000LL;
          *(_DWORD *)v75 = 4;
          v39 = (*(__int64 (__fastcall **)(__int64, struct _EVENT_DATA_DESCRIPTOR *))(v38 + 8))(v37, &UserData);
          if ( v39 != 259 )
          {
            if ( v39 == -1073741306 )
              v39 = -1073741789;
            ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))UserData.Ptr)(
              *(_QWORD *)&UserData.Size,
              (unsigned int)v39,
              *(_QWORD *)&v75[48]);
          }
          if ( v39 < 0 )
          {
            AFDETW_TRACEABORT(2, 8002, a2, 1);
            AfdBeginAbort(v23);
          }
        }
        AfdCompleteIrpList(v23 + 56, a2, 3221225760LL, 0);
        AfdCompleteIrpList(v23 + 104, a2, 3221225760LL, AfdCleanupSendIrp);
      }
      KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)a2 + 7, &LockHandle);
      *(_DWORD *)(v23 + 4) |= 0x100000u;
      LOBYTE(v40) = 1;
      AfdDeleteConnectedReference(v23, v40);
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      v41 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v23 + 48), 0xFFFFFFFFFFFFFFFFuLL);
      v42 = v41 <= 1;
      v43 = v41 - 1;
      if ( v42 )
      {
        if ( v43 )
          __fastfail(0xEu);
        AfdCloseConnection(v23);
      }
LABEL_145:
      if ( (*a2 & 0xAFD4) == 0xAFD4 )
      {
        KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)a2 + 7, &LockHandle);
        if ( (*a2 & 0xAFD4) == 0xAFD4 )
        {
          v44 = (_QWORD **)(a2 + 64);
          while ( 1 )
          {
            v45 = *v44;
            if ( *v44 == v44 )
              break;
            v46 = a2 + 64;
            if ( (__int16 *)v45[1] != a2 + 64 || (v47 = *v45, *(_QWORD **)(*v45 + 8LL) != v45) )
LABEL_170:
              __fastfail(3u);
            *v46 = v47;
            v48 = v45 - 21;
            *(_QWORD *)(v47 + 8) = v46;
            *v45 = 0;
            v49 = (_BYTE *)v45[2];
            if ( *v49 == 15 && v49[1] == 32 )
            {
              AfdCleanupSuperAccept(v48, 3221225760LL);
            }
            else
            {
              *((_DWORD *)v48 + 12) = -1073741536;
              v48[7] = 0;
            }
            KeReleaseInStackQueuedSpinLock(&LockHandle);
            if ( !_InterlockedExchange64(v48 + 13, 0) )
            {
              Irql[0] = 0;
              IoAcquireCancelSpinLock(Irql);
              IoReleaseCancelSpinLock(Irql[0]);
            }
            IofCompleteRequest((PIRP)v48, AfdPriorityBoost);
            KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)a2 + 7, &LockHandle);
          }
        }
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        AfdFreeQueuedConnections(a2);
      }
      goto LABEL_159;
    }
LABEL_68:
    if ( ProcessExitTime.QuadPart )
      goto LABEL_69;
    goto LABEL_93;
  }
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( (unsigned __int8)(*((_BYTE *)a2 + 2) - 3) <= 1u )
  {
    *((_QWORD *)a2 + 18) = 0;
    v12 = (_QWORD **)(a2 + 48);
    memset(&ActivityId, 0, sizeof(ActivityId));
LABEL_17:
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)a2 + 7, &ActivityId);
    while ( 1 )
    {
      v13 = *v12;
      if ( *v12 == v12 )
        break;
      if ( (_QWORD **)v13[1] != v12 )
        goto LABEL_170;
      v14 = (_QWORD *)*v13;
      if ( *(_QWORD **)(*v13 + 8LL) != v13 )
        goto LABEL_170;
      *v12 = v14;
      v15 = (IRP *)(v13 - 21);
      v14[1] = v12;
      if ( _InterlockedExchange64(v13 - 8, 0) )
      {
        if ( (unsigned __int8)AfdCleanupReceiveDatagramIrp(v13 - 21) )
        {
          KeReleaseInStackQueuedSpinLock(&ActivityId);
          v16 = AfdPriorityBoost;
          v15->IoStatus.Status = -1073741536;
          v15->IoStatus.Information = 0;
          IofCompleteRequest(v15, v16);
          goto LABEL_17;
        }
      }
      else
      {
        *v13 = 0;
      }
    }
    KeReleaseInStackQueuedSpinLock(&ActivityId);
    v17 = (_QWORD **)(a2 + 56);
    memset(&ActivityId, 0, sizeof(ActivityId));
LABEL_26:
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)a2 + 7, &ActivityId);
    while ( 1 )
    {
      v18 = *v17;
      if ( *v17 == v17 )
        break;
      if ( (_QWORD **)v18[1] != v17 )
        goto LABEL_170;
      v19 = (_QWORD *)*v18;
      if ( *(_QWORD **)(*v18 + 8LL) != v18 )
        goto LABEL_170;
      *v17 = v19;
      v20 = (IRP *)(v18 - 21);
      v19[1] = v17;
      if ( _InterlockedExchange64(v18 - 8, 0) )
      {
        if ( (unsigned __int8)AfdCleanupReceiveDatagramIrp(v18 - 21) )
        {
          KeReleaseInStackQueuedSpinLock(&ActivityId);
          v21 = AfdPriorityBoost;
          v20->IoStatus.Status = -1073741536;
          v20->IoStatus.Information = 0;
          IofCompleteRequest(v20, v21);
          goto LABEL_26;
        }
      }
      else
      {
        *v18 = 0;
      }
    }
    KeReleaseInStackQueuedSpinLock(&ActivityId);
  }
LABEL_159:
  v50 = (_QWORD *)*((_QWORD *)a2 + 36);
  if ( v50 )
  {
    if ( v50[2] )
      NsiDeregisterChangeNotification(&NPI_MS_IPV6_MODULEID, 16);
    if ( v50[1] )
      NsiDeregisterChangeNotification(&NPI_MS_IPV4_MODULEID, 16);
    *((_QWORD *)a2 + 36) = 0;
    ExFreePoolWithTag(v50, 0x71646641u);
  }
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)a2 + 7, &LockHandle);
  v51 = a2 + 148;
  while ( 1 )
  {
    v52 = (_QWORD *)*v51;
    if ( (_QWORD *)*v51 == v51 )
      break;
    v53 = a2 + 148;
    if ( (__int16 *)v52[1] != a2 + 148 )
      goto LABEL_170;
    v54 = *v52;
    if ( *(_QWORD **)(*v52 + 8LL) != v52 )
      goto LABEL_170;
    *v53 = v54;
    *(_QWORD *)(v54 + 8) = v53;
    *v52 = 0;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    ((void (__fastcall *)(__int16 *, _QWORD *))v52[2])(a2, v52);
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)a2 + 7, &LockHandle);
  }
  if ( *((_QWORD *)a2 + 45) )
  {
    Irql[0] = 0;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    IoAcquireCancelSpinLock(Irql);
    KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)a2 + 7, &LockHandle);
    v55 = *((_QWORD *)a2 + 45);
    if ( v55 )
    {
      *(_BYTE *)(v55 + 68) = 1;
      v56 = (void (__fastcall *)(_QWORD, __int64))_InterlockedExchange64((volatile __int64 *)(v55 + 104), 0);
      KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
      v57 = Irql[0];
      if ( v56 )
      {
        *(_BYTE *)(v55 + 69) = Irql[0];
        v56(0, v55);
        goto LABEL_178;
      }
    }
    else
    {
      KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
      v57 = Irql[0];
    }
    IoReleaseCancelSpinLock(v57);
  }
  else
  {
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
LABEL_178:
  if ( (*((_DWORD *)a2 + 2) & 0x100) != 0 || !*((_QWORD *)a2 + 32) || *((_BYTE *)a2 + 2) == 1 )
    goto LABEL_202;
  v58 = (struct _FILE_OBJECT *)*((_QWORD *)a2 + 3);
  do
  {
    v59 = *((_DWORD *)a2 + 92);
    if ( v59 > 0 )
      goto LABEL_202;
  }
  while ( v59 != _InterlockedCompareExchange((volatile signed __int32 *)a2 + 92, v59 - 1, v59) );
  if ( *((_BYTE *)a2 + 2) == 1 )
    goto LABEL_201;
  for ( i = 0; ; i = 1 )
  {
    if ( (*((_DWORD *)a2 + 2) & 1) != 0 )
    {
      ActivityId.LockQueue.Next = 0;
LABEL_188:
      *(_OWORD *)&ActivityId.LockQueue.Lock = 0;
      AfdIssueDeviceControl(v58, &ActivityId, 0x18u, 0, 0, 0xBu);
      if ( (*((_DWORD *)a2 + 2) & 0x100) != 0 || (*((_DWORD *)a2 + 4) & 0x100000) != 0 )
        goto LABEL_196;
      goto LABEL_197;
    }
    if ( ((*a2 + 20528) & 0xFFF9) != 0 )
    {
      if ( *a2 != -20527 )
        goto LABEL_197;
      ActivityId.LockQueue.Next = (struct _KSPIN_LOCK_QUEUE *volatile)4;
      *(_OWORD *)&ActivityId.LockQueue.Lock = 0;
      AfdIssueDeviceControl(v58, &ActivityId, 0x18u, 0, 0, 0xBu);
      ActivityId.LockQueue.Next = (struct _KSPIN_LOCK_QUEUE *volatile)10;
      *(_OWORD *)&ActivityId.LockQueue.Lock = 0;
      AfdIssueDeviceControl(v58, &ActivityId, 0x18u, 0, 0, 0xBu);
      ActivityId.LockQueue.Next = (struct _KSPIN_LOCK_QUEUE *volatile)2;
      goto LABEL_188;
    }
    if ( (*((_DWORD *)a2 + 2) & 0x100) != 0 || (*((_DWORD *)a2 + 4) & 0x100000) != 0 )
LABEL_196:
      AfdUnbind(a2, i);
LABEL_197:
    if ( i || (*((_DWORD *)a2 + 2) & 0x400000) == 0 )
      break;
    v58 = *(struct _FILE_OBJECT **)(*((_QWORD *)a2 + 35) + 8LL);
  }
  v3 = v71;
LABEL_201:
  _InterlockedIncrement((volatile signed __int32 *)a2 + 92);
LABEL_202:
  if ( (*((_DWORD *)a2 + 2) & 0x100) != 0 )
  {
    if ( v4 )
    {
      v61 = *((_BYTE *)a2 + 2);
      if ( (unsigned __int8)(v61 - 2) <= 2u || v61 == 7 )
        AfdCloseTransportEndpoint(a2);
    }
  }
  memset(&ActivityId, 0, sizeof(ActivityId));
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)a2 + 7, &ActivityId);
  v62 = *((_QWORD *)a2 + 48);
  KeReleaseInStackQueuedSpinLock(&ActivityId);
  if ( v62 )
  {
    if ( *(_WORD *)(v62 + 104) && (unsigned __int8)IoCancelMiniCompletionPacket(*(_QWORD *)(v62 + 80), v62) )
      ObfDereferenceObject(v3);
    ObfDereferenceObject(*(PVOID *)(v62 + 80));
  }
  AFDETW_TRACECLEANUP(1, 2003, a2);
  _InterlockedIncrement(&AfdEndpointsCleanedUp);
  return 0;
}

```

## disassembly

```asm
0x140020970  mov     [rsp-8+arg_10], rbx
0x140020975  push    rbp
0x140020976  push    rsi
0x140020977  push    rdi
0x140020978  push    r12
0x14002097a  push    r13
0x14002097c  push    r14
0x14002097e  push    r15
0x140020980  lea     rbp, [rsp-10h]
0x140020985  sub     rsp, 110h
0x14002098c  mov     rax, cs:__security_cookie
0x140020993  xor     rax, rsp
0x140020996  mov     [rbp+40h+var_40], rax
0x14002099a  xorps   xmm0, xmm0
0x14002099d  mov     [rbp+40h+var_B8], rcx
0x1400209a1  xor     eax, eax
0x1400209a3  mov     rdi, rdx
0x1400209a6  movups  xmmword ptr [rsp+140h+LockHandle.LockQueue.Next], xmm0
0x1400209ab  mov     qword ptr [rsp+140h+LockHandle.OldIrql], rax
0x1400209b0  mov     r13, rcx
0x1400209b3  mov     r12d, 1
0x1400209b9  call    cs:__imp_PsGetProcessExitTime
0x1400209c0  nop     dword ptr [rax+rax+00h]
0x1400209c5  mov     rbx, rax
0x1400209c8  call    cs:__imp_KeEnterCriticalRegion
0x1400209cf  nop     dword ptr [rax+rax+00h]
0x1400209d4  lea     rcx, [rdi+188h]; RunRef
0x1400209db  call    cs:__imp_ExWaitForRundownProtectionRelease
0x1400209e2  nop     dword ptr [rax+rax+00h]
0x1400209e7  call    cs:__imp_KeLeaveCriticalRegion
0x1400209ee  nop     dword ptr [rax+rax+00h]
0x1400209f3  lea     rdx, [rsp+140h+LockHandle]; LockHandle
0x1400209f8  lea     rcx, [rdi+38h]; SpinLock
0x1400209fc  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140020a03  nop     dword ptr [rax+rax+00h]
0x140020a08  xor     r8d, r8d
0x140020a0b  mov     edx, 20h ; ' '
0x140020a10  mov     rcx, rdi
0x140020a13  call    AfdIndicateEventSelectEvent
0x140020a18  lea     r9, [rsp+140h+LockHandle]
0x140020a1d  xor     r8d, r8d
0x140020a20  mov     edx, 20h ; ' '
0x140020a25  mov     rcx, rdi
0x140020a28  call    AfdIndicatePollEvent
0x140020a2d  test    al, al
0x140020a2f  jz      short loc_140020A46
0x140020a31  lea     rdx, [rsp+140h+LockHandle]; LockHandle
0x140020a36  lea     rcx, [rdi+38h]; SpinLock
0x140020a3a  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140020a41  nop     dword ptr [rax+rax+00h]
0x140020a46  mov     eax, [rdi+8]
0x140020a49  xor     r15d, r15d
0x140020a4c  mov     rsi, [rdi+50h]
0x140020a50  bts     eax, 0Bh
0x140020a54  mov     [rdi+8], eax
0x140020a57  mov     eax, 0C0000120h
0x140020a5c  mov     edx, 0AFD2h
0x140020a61  test    rsi, rsi
0x140020a64  jz      loc_140020BB6
0x140020a6a  mov     rcx, [rsi+38h]
0x140020a6e  mov     r15d, 0C0000241h
0x140020a74  cmp     [rdi], dx
0x140020a77  cmovnz  r15d, eax
0x140020a7b  cmp     cs:g_AfdEtwTraceEnable, 0
0x140020a82  mov     eax, [rcx+4]
0x140020a85  mov     [rsp+140h+var_C8], eax
0x140020a89  mov     eax, [rcx]
0x140020a8b  mov     rcx, [rsi+80h]
0x140020a92  mov     [rsp+140h+var_D0], eax
0x140020a96  mov     eax, [rcx+4]
0x140020a99  mov     [rsp+140h+var_D8], eax
0x140020a9d  mov     eax, [rcx]
0x140020a9f  mov     [rsp+140h+var_E0], eax
0x140020aa3  mov     [rbp+40h+var_C0], rsi
0x140020aa7  jz      loc_140020B38
0x140020aad  xor     ecx, ecx
0x140020aaf  mov     qword ptr [rbp+40h+ActivityId.Data1], rsi
0x140020ab3  lea     rax, [rbp+40h+var_C0]
0x140020ab7  mov     qword ptr [rbp+40h+ActivityId.Data4], rcx
0x140020abb  mov     rcx, cs:g_AfdEtwHandle; RegHandle
0x140020ac2  lea     r8, [rbp+40h+ActivityId]; ActivityId
0x140020ac6  mov     [rbp+40h+var_90.Ptr], rax
0x140020aca  lea     rdx, AFD_EVENT_CLOSE_RQ; EventDescriptor
0x140020ad1  lea     rax, [rsp+140h+var_E0]
0x140020ad6  mov     qword ptr [rbp+40h+var_90.Size], 8
0x140020ade  mov     [rbp+40h+var_80], rax
0x140020ae2  mov     r9d, 5; UserDataCount
0x140020ae8  lea     rax, [rsp+140h+var_D8]
0x140020aed  mov     [rbp+40h+var_78], 4
0x140020af5  mov     [rbp-30h], rax
0x140020af9  lea     rax, [rsp+140h+var_D0]
0x140020afe  mov     [rbp-20h], rax
0x140020b02  lea     rax, [rsp+140h+var_C8]
0x140020b07  mov     [rbp-10h], rax
0x140020b0b  lea     rax, [rbp+40h+var_90]
0x140020b0f  mov     [rsp+140h+UserData], rax; UserData
0x140020b14  mov     [rbp+40h+var_68], 4
0x140020b1c  mov     [rbp+40h+var_58], 4
0x140020b24  mov     [rbp+40h+var_48], 4
0x140020b2c  call    cs:__imp_EtwWrite
0x140020b33  nop     dword ptr [rax+rax+00h]
0x140020b38  cmp     dword ptr [rsi+10h], 0
0x140020b3c  jl      short loc_140020B45
0x140020b3e  mov     dword ptr [rsi+10h], 0C0000128h
0x140020b45  mov     edx, r15d
0x140020b48  mov     rcx, rdi
0x140020b4b  call    AfdRioFlushReceiveQueue
0x140020b50  mov     edx, r15d
0x140020b53  mov     rcx, rdi
0x140020b56  call    AfdRioFlushSendQueue
0x140020b5b  xor     r15d, r15d
0x140020b5e  mov     [rsi+38h], r15
0x140020b62  mov     [rsi+80h], r15
0x140020b69  mov     rcx, [rsi+30h]; MemoryDescriptorList
0x140020b6d  call    cs:__imp_MmUnlockPages
0x140020b74  nop     dword ptr [rax+rax+00h]
0x140020b79  mov     rcx, [rsi+30h]; Mdl
0x140020b7d  call    cs:__imp_IoFreeMdl
0x140020b84  nop     dword ptr [rax+rax+00h]
0x140020b89  mov     [rsi+30h], r15
0x140020b8d  mov     rcx, [rsi+78h]; MemoryDescriptorList
0x140020b91  call    cs:__imp_MmUnlockPages
0x140020b98  nop     dword ptr [rax+rax+00h]
0x140020b9d  mov     rcx, [rsi+78h]; Mdl
0x140020ba1  call    cs:__imp_IoFreeMdl
0x140020ba8  nop     dword ptr [rax+rax+00h]
0x140020bad  mov     edx, 0AFD2h
0x140020bb2  mov     [rsi+78h], r15
0x140020bb6  mov     eax, [rdi+8]
0x140020bb9  bt      eax, 8
0x140020bbd  jnb     short loc_140020BCA
0x140020bbf  test    dword ptr [rdi+8], 1000h
0x140020bc6  cmovnz  r12d, r15d
0x140020bca  movzx   eax, word ptr [rdi]
0x140020bcd  mov     ecx, 0AFD1h
0x140020bd2  cmp     ax, cx
0x140020bd5  jnz     loc_140020D7A
0x140020bdb  lea     rcx, [rsp+140h+LockHandle]; LockHandle
0x140020be0  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140020be7  nop     dword ptr [rax+rax+00h]
0x140020bec  movzx   eax, byte ptr [rdi+2]
0x140020bf0  sub     al, 3
0x140020bf2  cmp     al, 1
0x140020bf4  ja      loc_1400214C3
0x140020bfa  xorps   xmm0, xmm0
0x140020bfd  mov     qword ptr [rdi+90h], 0
0x140020c08  xor     eax, eax
0x140020c0a  lea     rsi, [rdi+60h]
0x140020c0e  movups  xmmword ptr [rbp+40h+ActivityId.Data1], xmm0
0x140020c12  mov     [rbp+40h+var_A0], rax
0x140020c16  lea     rdx, [rbp+40h+ActivityId]; LockHandle
0x140020c1a  lea     rcx, [rdi+38h]; SpinLock
0x140020c1e  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140020c25  nop     dword ptr [rax+rax+00h]
0x140020c2a  nop     word ptr [rax+rax+00h]
0x140020c30  mov     rcx, [rsi]
0x140020c33  cmp     rcx, rsi
0x140020c36  jz      short loc_140020CB0
0x140020c38  cmp     [rcx+8], rsi
0x140020c3c  jnz     loc_1400215A7
0x140020c42  mov     rax, [rcx]
0x140020c45  cmp     [rax+8], rcx
0x140020c49  jnz     loc_1400215A7
0x140020c4f  mov     [rsi], rax
0x140020c52  lea     rbx, [rcx-0A8h]
0x140020c59  mov     [rax+8], rsi
0x140020c5d  mov     rax, r15
0x140020c60  xchg    rax, [rbx+68h]
0x140020c64  test    rax, rax
0x140020c67  jnz     short loc_140020C6E
0x140020c69  mov     [rcx], r15
0x140020c6c  jmp     short loc_140020C30
0x140020c6e  mov     rcx, rbx
0x140020c71  call    AfdCleanupReceiveDatagramIrp
0x140020c76  test    al, al
0x140020c78  jz      short loc_140020C30
0x140020c7a  lea     rcx, [rbp+40h+ActivityId]; LockHandle
0x140020c7e  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140020c85  nop     dword ptr [rax+rax+00h]
0x140020c8a  movzx   edx, cs:AfdPriorityBoost; PriorityBoost
0x140020c91  mov     rcx, rbx; Irp
0x140020c94  mov     dword ptr [rbx+30h], 0C0000120h
0x140020c9b  mov     [rbx+38h], r15
0x140020c9f  call    cs:__imp_IofCompleteRequest
0x140020ca6  nop     dword ptr [rax+rax+00h]
0x140020cab  jmp     loc_140020C16
0x140020cb0  lea     rcx, [rbp+40h+ActivityId]; LockHandle
0x140020cb4  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140020cbb  nop     dword ptr [rax+rax+00h]
0x140020cc0  xorps   xmm0, xmm0
0x140020cc3  lea     rsi, [rdi+70h]
0x140020cc7  xor     eax, eax
0x140020cc9  movups  xmmword ptr [rbp+40h+ActivityId.Data1], xmm0
0x140020ccd  mov     [rbp+40h+var_A0], rax
0x140020cd1  lea     rdx, [rbp+40h+ActivityId]; LockHandle
0x140020cd5  lea     rcx, [rdi+38h]; SpinLock
0x140020cd9  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140020ce0  nop     dword ptr [rax+rax+00h]
0x140020ce5  mov     rcx, [rsi]
0x140020ce8  cmp     rcx, rsi
0x140020ceb  jz      short loc_140020D65
0x140020ced  cmp     [rcx+8], rsi
0x140020cf1  jnz     loc_1400215A7
0x140020cf7  mov     rax, [rcx]
0x140020cfa  cmp     [rax+8], rcx
0x140020cfe  jnz     loc_1400215A7
0x140020d04  mov     [rsi], rax
0x140020d07  lea     rbx, [rcx-0A8h]
0x140020d0e  mov     [rax+8], rsi
0x140020d12  mov     rax, r15
0x140020d15  xchg    rax, [rbx+68h]
0x140020d19  test    rax, rax
0x140020d1c  jnz     short loc_140020D23
0x140020d1e  mov     [rcx], r15
0x140020d21  jmp     short loc_140020CE5
0x140020d23  mov     rcx, rbx
0x140020d26  call    AfdCleanupReceiveDatagramIrp
0x140020d2b  test    al, al
0x140020d2d  jz      short loc_140020CE5
0x140020d2f  lea     rcx, [rbp+40h+ActivityId]; LockHandle
0x140020d33  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140020d3a  nop     dword ptr [rax+rax+00h]
0x140020d3f  movzx   edx, cs:AfdPriorityBoost; PriorityBoost
0x140020d46  mov     rcx, rbx; Irp
0x140020d49  mov     dword ptr [rbx+30h], 0C0000120h
0x140020d50  mov     [rbx+38h], r15
0x140020d54  call    cs:__imp_IofCompleteRequest
0x140020d5b  nop     dword ptr [rax+rax+00h]
0x140020d60  jmp     loc_140020CD1
0x140020d65  lea     rcx, [rbp+40h+ActivityId]; LockHandle
0x140020d69  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140020d70  nop     dword ptr [rax+rax+00h]
0x140020d75  jmp     loc_1400214C3
0x140020d7a  mov     ecx, 1AFDh
0x140020d7f  cmp     ax, cx
0x140020d82  jnz     short loc_140020DC4
0x140020d84  lea     rax, [rdi+80h]
0x140020d8b  lea     rcx, [rsp+140h+LockHandle]; LockHandle
0x140020d90  cmp     [rax], rax
0x140020d93  jnz     short loc_140020DA6
0x140020d95  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140020d9c  nop     dword ptr [rax+rax+00h]
0x140020da1  jmp     loc_1400214C3
0x140020da6  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140020dad  nop     dword ptr [rax+rax+00h]
0x140020db2  mov     edx, 0C0000120h
0x140020db7  mov     rcx, rdi
0x140020dba  call    AfdSanRestartRequestProcessing
0x140020dbf  jmp     loc_1400214C3
0x140020dc4  mov     ecx, 0AFDh
0x140020dc9  cmp     ax, cx
0x140020dcc  jnz     short loc_140020E05
0x140020dce  lea     rcx, [rsp+140h+LockHandle]; LockHandle
0x140020dd3  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140020dda  nop     dword ptr [rax+rax+00h]
0x140020ddf  mov     rbx, [rdi+30h]
0x140020de3  call    cs:__imp_IoGetCurrentProcess
0x140020dea  nop     dword ptr [rax+rax+00h]
0x140020def  cmp     rbx, rax
0x140020df2  jnz     loc_1400214C3
0x140020df8  mov     rcx, rdi
0x140020dfb  call    AfdSanHelperCleanup
0x140020e00  jmp     loc_1400214C3
0x140020e05  and     ax, dx
0x140020e08  cmp     ax, dx
0x140020e0b  jnz     loc_14002137D
0x140020e11  mov     rsi, [rdi+0C0h]
0x140020e18  test    rsi, rsi
0x140020e1b  jz      loc_14002137D
0x140020e21  mov     eax, 1
0x140020e26  lock xadd [rsi+30h], rax
0x140020e2c  inc     rax
0x140020e2f  cmp     rax, 1
0x140020e33  jg      short loc_140020E3C
0x140020e35  mov     ecx, 0Eh
0x140020e3a  int     29h; Win8: RtlFailFast(ecx)
0x140020e3c  mov     rcx, rsi
0x140020e3f  call    AfdCleanupConnectionTimerWheelEntry
0x140020e44  movzx   ecx, byte ptr [rdi+2]
0x140020e48  lea     eax, [rcx-3]
0x140020e4b  test    al, 0FAh
0x140020e4d  jnz     loc_140021201
0x140020e53  cmp     cl, 8
0x140020e56  jz      loc_140021201
0x140020e5c  mov     ecx, [rsi+4]
0x140020e5f  bt      ecx, 0Ch
0x140020e63  jnb     loc_140021201
0x140020e69  test    byte ptr [rdi+6], 1
0x140020e6d  jnz     loc_140021201
0x140020e73  movzx   eax, word ptr [rdi+0Ah]
0x140020e77  test    al, 4
0x140020e79  jnz     loc_140021201
0x140020e7f  test    al, 1
0x140020e81  jz      short loc_140020EDF
0x140020e83  test    cl, 1
0x140020e86  jz      short loc_140020EAC
0x140020e88  mov     rax, [rsi+48h]
0x140020e8c  add     rax, [rsi+40h]
0x140020e90  cmp     [rsi+38h], rax
0x140020e94  jg      short loc_140020EDF
  ... truncated ...
```
