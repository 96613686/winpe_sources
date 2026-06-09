# AfdSuperAccept

- ea: `0x14002e9c0`
- end: `0x14002f3e4`
- name: `AfdSuperAccept`
- size: `2596`
- prototype: `__int64 __fastcall(PIRP Irp, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14001ef30`

## callees

- `0x1400044fc`
- `0x140004848`
- `0x1400049b0`
- `0x14001b800`
- `0x14002e9c0`
- `0x14002f6ac`
- `0x14002f800`
- `0x14002fd5c`
- `0x140033898`
- `0x14003604c`
- `0x1400445b8`
- `0x140044a9c`
- `0x140044b34`
- `0x1400726d0`
- `0x1400930cc`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x14002f3a4`
- `ntoskrnl!IoFreeMdl` at `0x14002f3a4`
- `ntoskrnl!MmUnlockPages` at `0x14002f394`
- `ntoskrnl!MmUnlockPages` at `0x14002f394`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14002ef81`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14002ef81`
- `ntoskrnl!ExQueryDepthSList` at `0x14002ef0d`
- `ntoskrnl!ExQueryDepthSList` at `0x14002f13c`
- `ntoskrnl!ExQueryDepthSList` at `0x14002ef0d`
- `ntoskrnl!ExQueryDepthSList` at `0x14002f13c`
- `ntoskrnl!ObfReferenceObject` at `0x14002ed72`
- `ntoskrnl!ObfReferenceObject` at `0x14002ed72`
- `ntoskrnl!MmProbeAndLockPages` at `0x14002ecfe`
- `ntoskrnl!MmProbeAndLockPages` at `0x14002ecfe`
- `ntoskrnl!IoAllocateMdl` at `0x14002eca9`
- `ntoskrnl!IoAllocateMdl` at `0x14002eca9`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14002ea73`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14002eb69`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14002ea73`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14002eb69`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14002f099`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14002f1dd`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14002f099`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14002f1dd`
- `ntoskrnl!IofCompleteRequest` at `0x14002f0f6`
- `ntoskrnl!IofCompleteRequest` at `0x14002f1f2`
- `ntoskrnl!IofCompleteRequest` at `0x14002f3c1`
- `ntoskrnl!IofCompleteRequest` at `0x14002f0f6`
- `ntoskrnl!IofCompleteRequest` at `0x14002f1f2`
- `ntoskrnl!IofCompleteRequest` at `0x14002f3c1`
- `ntoskrnl!ObfDereferenceObject` at `0x14002f366`
- `ntoskrnl!ObfDereferenceObject` at `0x14002f379`
- `ntoskrnl!ObfDereferenceObject` at `0x14002f366`
- `ntoskrnl!ObfDereferenceObject` at `0x14002f379`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14002f086`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14002f1ca`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14002f086`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14002f1ca`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002f113`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002f17f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002f113`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002f17f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002efa2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002f02b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002f164`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002efa2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002f02b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002f164`
- `ntoskrnl!IoFileObjectType` at `0x14002ed2e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002ed3b`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002ed3b`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14002ec0b`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14002ec0b`
- `ntoskrnl!IoIs32bitProcess` at `0x14002ea02`
- `ntoskrnl!IoIs32bitProcess` at `0x14002ea02`

## pseudocode

```c
__int64 __fastcall AfdSuperAccept(PIRP Irp, __int64 a2)
{
  __int64 v4; // rdi
  PVOID v5; // r13
  __int64 v6; // rdx
  NTSTATUS v7; // r14d
  KPROCESSOR_MODE RequestorMode; // cl
  void *v9; // rdx
  void *v10; // r14
  ULONG v11; // r9d
  unsigned int v12; // ecx
  unsigned int v13; // r8d
  char v14; // al
  KPROCESSOR_MODE v15; // cl
  void *v16; // rdx
  HANDLE CurrentProcessId; // rax
  ULONG v18; // edx
  NTSTATUS v19; // eax
  __int64 v20; // r15
  __int64 FreeConnection; // rdx
  __int64 v22; // rcx
  __int64 v23; // r14
  _QWORD *v24; // rsi
  __int64 v25; // rax
  _QWORD *v26; // rcx
  _QWORD *v27; // rax
  __int64 v28; // rbx
  __int64 v29; // rdx
  _QWORD *v30; // rcx
  USHORT DepthSList; // bx
  PMDL MdlAddress; // rcx
  PVOID Object; // [rsp+48h] [rbp-B0h] BYREF
  int v35; // [rsp+50h] [rbp-A8h]
  __int128 v36; // [rsp+58h] [rbp-A0h] BYREF
  __int128 v37; // [rsp+68h] [rbp-90h]
  _QWORD v38[2]; // [rsp+78h] [rbp-80h] BYREF
  __int64 v39; // [rsp+88h] [rbp-70h]
  int v40; // [rsp+90h] [rbp-68h]
  __int64 v41; // [rsp+98h] [rbp-60h]
  void *v42; // [rsp+A0h] [rbp-58h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+A8h] [rbp-50h] BYREF
  KIRQL Irql; // [rsp+108h] [rbp+10h] BYREF
  int v45; // [rsp+110h] [rbp+18h]
  int v46; // [rsp+118h] [rbp+20h]

  memset(&LockHandle, 0, sizeof(LockHandle));
  v4 = *(_QWORD *)(*(_QWORD *)(a2 + 48) + 24LL);
  v41 = v4;
  v5 = 0;
  if ( IoIs32bitProcess(Irp) )
  {
    if ( *(_DWORD *)(a2 + 16) < 0x14u )
    {
      v6 = 6013;
LABEL_4:
      v7 = -1073741811;
      AFDETW_TRACEACCEPTEX(0, v6, v4, 0, 0, -1073741811, 0, 0);
      goto LABEL_94;
    }
    v36 = 0;
    LODWORD(v37) = 0;
    RequestorMode = Irp->RequestorMode;
    if ( RequestorMode && (*(_BYTE *)(a2 + 32) & 3) != 0 )
      ExRaiseDatatypeMisalignment();
    v9 = *(void **)(a2 + 32);
    if ( RequestorMode )
      RtlCopyFromUser(&v36, v9, 0x14u);
    else
      RtlCopyVolatileMemory(&v36, v9, 0x14u);
    v10 = (void *)SDWORD1(v36);
    v42 = (void *)SDWORD1(v36);
    v11 = DWORD2(v36);
    v45 = DWORD2(v36);
    v39 = *((_QWORD *)&v36 + 1);
    v12 = HIDWORD(v36);
    v46 = HIDWORD(v36);
    v13 = v37;
    v35 = v37;
    v40 = v37;
    Irql = BYTE1(v36);
    v14 = v36;
  }
  else
  {
    v36 = 0;
    v37 = 0;
    v15 = Irp->RequestorMode;
    if ( v15 && (*(_BYTE *)(a2 + 32) & 3) != 0 )
      ExRaiseDatatypeMisalignment();
    v16 = *(void **)(a2 + 32);
    if ( v15 )
      RtlCopyFromUser(&v36, v16, 0x20u);
    else
      RtlCopyVolatileMemory(&v36, v16, 0x20u);
    v10 = (void *)*((_QWORD *)&v36 + 1);
    v42 = (void *)*((_QWORD *)&v36 + 1);
    v11 = v37;
    v45 = v37;
    v39 = v37;
    v12 = DWORD1(v37);
    v46 = DWORD1(v37);
    v13 = DWORD2(v37);
    v35 = DWORD2(v37);
    v40 = DWORD2(v37);
    Irql = BYTE1(v36);
    v14 = v36;
  }
  if ( !v14 && AfdSanServiceHelper )
  {
    if ( (BYTE9(xmmword_1400875E0) & 2) != 0 )
    {
      CurrentProcessId = PsGetCurrentProcessId();
      WPP_SF_q(1289, 15, WPP_6216d3581a803072be4346b6e903d992_Traceguids, CurrentProcessId);
    }
    v7 = -1073741574;
    AFDETW_TRACEACCEPTEX(0, 6016, v4, 0, 0, -1073741574, 0, 0);
    goto LABEL_94;
  }
  if ( (*(_DWORD *)(v4 + 8) & 1) == 0
    || v13 < 8
    || v12 == 1
    || (v18 = *(_DWORD *)(a2 + 8), v18 < v11)
    || v18 - v11 < v12
    || v18 - v11 - v12 < v13 )
  {
    if ( (*(_DWORD *)(v4 + 8) & 1) != 0 )
    {
      v7 = -1073741789;
    }
    else
    {
      if ( (BYTE9(xmmword_1400875E0) & 2) != 0 )
        WPP_SF_q(1289, 16, WPP_6216d3581a803072be4346b6e903d992_Traceguids, v4);
      v7 = -1073741811;
    }
    AFDETW_TRACEACCEPTEX(0, 6017, v4, 0, 0, v7, 0, 0);
    goto LABEL_94;
  }
  if ( !IoAllocateMdl(Irp->UserBuffer, v18, 0, 1u, Irp) )
  {
    AFDETW_TRACEACCEPTEX(0, 6018, v4, 0, 0, -1073741670, 0, 0);
    v7 = -1073741670;
LABEL_94:
    if ( v5 )
    {
      ObfDereferenceObject(v5);
      ObfDereferenceObject(Irp->Tail.Overlay.Thread);
    }
    MdlAddress = Irp->MdlAddress;
    if ( MdlAddress )
    {
      if ( (MdlAddress->MdlFlags & 2) != 0 )
        MmUnlockPages(MdlAddress);
      IoFreeMdl(Irp->MdlAddress);
      Irp->MdlAddress = 0;
    }
    Irp->IoStatus.Information = 0;
    Irp->IoStatus.Status = v7;
    IofCompleteRequest(Irp, 0);
    return (unsigned int)v7;
  }
  MmProbeAndLockPages(Irp->MdlAddress, Irp->RequestorMode, IoWriteAccess);
  Object = 0;
  v19 = ObReferenceObjectByHandle(
          v10,
          (unsigned __int8)HIBYTE(*(_WORD *)(a2 + 24)) >> 6,
          (POBJECT_TYPE)IoFileObjectType,
          Irp->RequestorMode,
          &Object,
          0);
  v7 = v19;
  v5 = Object;
  if ( v19 < 0 )
  {
    AFDETW_TRACEACCEPTEX(0, 6020, v4, 0, 0, v19, 0, 0);
    goto LABEL_94;
  }
  ObfReferenceObject(Irp->Tail.Overlay.Thread);
  if ( *((PVOID *)v5 + 1) != AfdDeviceObject )
  {
    v7 = -1073741816;
    AFDETW_TRACEACCEPTEX(0, 6021, v4, 0, 0, -1073741816, 0, 0);
    goto LABEL_94;
  }
  v20 = *((_QWORD *)v5 + 3);
  if ( _InterlockedCompareExchange((volatile signed __int32 *)(v20 + 368), 4, 0) )
  {
    v6 = 6022;
    goto LABEL_4;
  }
  if ( (*(_BYTE *)(v20 + 6) & 1) != 0
    || *(_QWORD *)(v20 + 272) != *(_QWORD *)(v4 + 272)
    && ((*(_DWORD *)(v4 + 8) & 0x200000) == 0 || *(_QWORD *)(v20 + 272) != *(_QWORD *)(v4 + 280))
    || (*(_DWORD *)(v20 + 8) & 0x100) != 0 && *(_BYTE *)(v20 + 2) != 2
    || (*(_DWORD *)(v20 + 8) & 0x100) == 0 && *(_BYTE *)(v20 + 2) != 1
    || *(_QWORD *)(v20 + 40) )
  {
    v7 = -1073741811;
    AFDETW_TRACEACCEPTEX(0, 6023, v4, 0, 0, -1073741811, 0, 0);
    _InterlockedExchange((volatile __int32 *)(v20 + 368), 0);
    goto LABEL_94;
  }
  *(_BYTE *)(v20 + 188) = Irql;
  Irp->Tail.Overlay.DriverContext[3] = v42;
  AFDETW_TRACEACCEPTEX(0, 6024, v4, Irp->MdlAddress, *(_DWORD *)(a2 + 8), v7, 0, v20);
  *(_QWORD *)(a2 + 32) = v5;
  *(_DWORD *)(a2 + 8) = v45;
  *(_DWORD *)(a2 + 24) = v46;
  *(_DWORD *)(a2 + 16) = v35;
  if ( (*(_DWORD *)(v4 + 8) & 0x100) == 0 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v4 + 176));
    if ( (*(_DWORD *)(v4 + 8) & 0x400000) != 0 )
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(v4 + 280) + 48LL));
    v7 = AfdReplenishListenBacklog(v4);
  }
  *(_QWORD *)(v20 + 360) = Irp;
  if ( AfdDisableDirectSuperAccept
    || (*(_DWORD *)(v4 + 8) & 0x400000) != 0
    || (*(_DWORD *)(v4 + 8) & 2) != 0
    || ExQueryDepthSList((PSLIST_HEADER)(v4 + 160)) > 0x7FFFu
    || (FreeConnection = AfdGetFreeConnection(v4, 0, 0)) == 0 )
  {
    *(_BYTE *)a2 = 15;
    Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
    AfdWaitForListen(Irp);
    if ( (*(_DWORD *)(v4 + 8) & 0x100) == 0 && v7 < 0 )
      AfdReportConnectionAllocationFailure(v4, (unsigned int)v7);
  }
  else
  {
    *(_QWORD *)(FreeConnection + 40) = -1;
    Irp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = (struct _LIST_ENTRY *)FreeConnection;
    Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
    v22 = _InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, (__int64)&AfdCancelSuperAccept);
    if ( Irp->Cancel
      || _InterlockedCompareExchange64((volatile signed __int64 *)(FreeConnection + 40), (signed __int64)Irp, -1) != -1 )
    {
      AFDETW_TRACEACCEPT_ERROR(v22, 6202, Irp, 3221225760LL);
      AfdCleanupSuperAccept(Irp, 3221225760LL);
      if ( !_InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, 0) )
      {
        Irql = 0;
        IoAcquireCancelSpinLock(&Irql);
        IoReleaseCancelSpinLock(Irql);
      }
      IofCompleteRequest(Irp, AfdPriorityBoost);
    }
    else if ( ExpInterlockedPushEntrySList((PSLIST_HEADER)(v4 + 160), (PSLIST_ENTRY)(FreeConnection + 176)) )
    {
      if ( (*(_DWORD *)(v4 + 8) & 0x100) == 0 )
      {
        DepthSList = ExQueryDepthSList((PSLIST_HEADER)(v4 + 160));
        if ( DepthSList > *(_WORD *)(v4 + 190) )
        {
          KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v4 + 56), &LockHandle);
          *(_WORD *)(v4 + 190) = DepthSList;
          KeReleaseInStackQueuedSpinLock(&LockHandle);
        }
      }
    }
    else
    {
      KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v4 + 56), &LockHandle);
      if ( (*(_DWORD *)(v4 + 8) & 0x800) != 0 )
      {
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        AfdFreeQueuedConnections(v4);
      }
      else
      {
        v38[1] = v38;
        v38[0] = v38;
        v23 = v4 + 96;
        while ( 1 )
        {
          v24 = *(_QWORD **)v23;
          if ( *(_QWORD *)v23 == v23 )
            break;
          v25 = *v24;
          if ( *(_QWORD **)(*v24 + 8LL) != v24 )
            goto LABEL_75;
          v26 = (_QWORD *)v24[1];
          if ( (_QWORD *)*v26 != v24 )
            goto LABEL_75;
          *v26 = v25;
          *(_QWORD *)(v25 + 8) = v26;
          if ( !(unsigned __int8)AfdServiceSuperAccept(v4, v24 - 22, &LockHandle, v38) )
          {
            v27 = *(_QWORD **)v23;
            if ( *(_QWORD *)(*(_QWORD *)v23 + 8LL) != v23 )
LABEL_75:
              __fastfail(3u);
            *v24 = v27;
            v24[1] = v23;
            v27[1] = v24;
            *(_QWORD *)v23 = v24;
            break;
          }
          KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v4 + 56), &LockHandle);
        }
        AfdNotifySockIndicateEventsUnlock(v4, &LockHandle, 0);
        if ( (_QWORD *)v38[0] != v38 )
        {
          Irql = 0;
          IoAcquireCancelSpinLock(&Irql);
          IoReleaseCancelSpinLock(Irql);
          while ( 1 )
          {
            v28 = v38[0];
            if ( (_QWORD *)v38[0] == v38 )
              break;
            v29 = *(_QWORD *)v38[0];
            if ( *(_QWORD *)(*(_QWORD *)v38[0] + 8LL) != v38[0] )
              goto LABEL_75;
            v30 = *(_QWORD **)(v38[0] + 8LL);
            if ( *v30 != v38[0] )
              goto LABEL_75;
            *v30 = v29;
            *(_QWORD *)(v29 + 8) = v30;
            AFDETW_TRACEACCEPT_ERROR(v30, 6201, v28 - 168, *(unsigned int *)(v28 - 120));
            IofCompleteRequest((PIRP)(v28 - 168), AfdPriorityBoost);
          }
        }
      }
    }
  }
  return 259;
}

```

## disassembly

```asm
0x14002e9c0  mov     r11, rsp
0x14002e9c3  mov     [r11+8], rcx
0x14002e9c7  push    rbx
0x14002e9c8  push    rsi
0x14002e9c9  push    rdi
0x14002e9ca  push    r12
0x14002e9cc  push    r13
0x14002e9ce  push    r14
0x14002e9d0  push    r15
0x14002e9d2  sub     rsp, 0C0h
0x14002e9d9  mov     r12, rdx
0x14002e9dc  mov     rsi, rcx
0x14002e9df  xorps   xmm0, xmm0
0x14002e9e2  xor     eax, eax
0x14002e9e4  movups  xmmword ptr [r11-50h], xmm0
0x14002e9e9  mov     [r11-40h], rax
0x14002e9ed  mov     rax, [rdx+30h]
0x14002e9f1  mov     rdi, [rax+18h]
0x14002e9f5  mov     [rsp+0F8h+var_60], rdi
0x14002e9fd  xor     ebx, ebx
0x14002e9ff  mov     r13d, ebx
0x14002ea02  call    cs:__imp_IoIs32bitProcess
0x14002ea09  nop     dword ptr [rax+rax+00h]
0x14002ea0e  test    al, al
0x14002ea10  jz      loc_14002EB49
0x14002ea16  lea     r8d, [rbx+14h]
0x14002ea1a  cmp     [r12+10h], r8d
0x14002ea1f  jnb     short loc_14002EA52
0x14002ea21  mov     edx, 177Dh
0x14002ea26  mov     [rsp+0F8h+var_C0], rbx
0x14002ea2b  mov     [rsp+0F8h+var_C8], rbx
0x14002ea30  mov     eax, 0C000000Dh
0x14002ea35  mov     dword ptr [rsp+0F8h+HandleInformation], eax
0x14002ea39  mov     r14d, eax
0x14002ea3c  mov     r8, rdi
0x14002ea3f  xor     r9d, r9d
0x14002ea42  mov     dword ptr [rsp+0F8h+Irp], ebx
0x14002ea46  xor     ecx, ecx
0x14002ea48  call    AFDETW_TRACEACCEPTEX
0x14002ea4d  jmp     loc_14002F35E
0x14002ea52  mov     [rsp+0F8h+var_B8], ebx
0x14002ea56  xorps   xmm0, xmm0
0x14002ea59  xor     eax, eax
0x14002ea5b  movups  [rsp+0F8h+var_A0], xmm0
0x14002ea60  mov     dword ptr [rsp+0F8h+var_90], eax
0x14002ea64  mov     cl, [rsi+40h]
0x14002ea67  test    cl, cl
0x14002ea69  jz      short loc_14002EA80
0x14002ea6b  test    byte ptr [r12+20h], 3
0x14002ea71  jz      short loc_14002EA80
0x14002ea73  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14002ea7a  nop     dword ptr [rax+rax+00h]
0x14002ea7f  int     3; Trap to Debugger
0x14002ea80  mov     rdx, [r12+20h]; Src
0x14002ea85  test    cl, cl
0x14002ea87  lea     rcx, [rsp+0F8h+var_A0]; void *
0x14002ea8c  jz      short loc_14002EA95
0x14002ea8e  call    RtlCopyFromUser
0x14002ea93  jmp     short loc_14002EA9A
0x14002ea95  call    RtlCopyVolatileMemory
0x14002ea9a  movsxd  r14, dword ptr [rsp+0F8h+var_A0+4]
0x14002ea9f  mov     [rsp+0F8h+var_58], r14
0x14002eaa7  mov     r9d, dword ptr [rsp+0F8h+var_A0+8]
0x14002eaac  mov     [rsp+0F8h+arg_10], r9d
0x14002eab4  mov     dword ptr [rsp+0F8h+var_70], r9d
0x14002eabc  mov     ecx, dword ptr [rsp+0F8h+var_A0+0Ch]
0x14002eac0  mov     [rsp+0F8h+arg_18], ecx
0x14002eac7  mov     dword ptr [rsp+0F8h+var_70+4], ecx
0x14002eace  mov     r8d, dword ptr [rsp+0F8h+var_90]
0x14002ead3  mov     [rsp+0F8h+var_A8], r8d
0x14002ead8  mov     [rsp+0F8h+var_68], r8d
0x14002eae0  mov     al, byte ptr [rsp+0F8h+var_A0]
0x14002eae4  mov     [rsp+0F8h+var_B4], al
0x14002eae8  mov     dl, byte ptr [rsp+0F8h+var_A0+1]
0x14002eaec  mov     [rsp+0F8h+Irql], dl
0x14002eaf3  mov     [rsp+0F8h+var_B3], dl
0x14002eaf7  jmp     loc_14002EBF4
0x14002eafc  mov     [rsp+0F8h+var_C0], 0
0x14002eb05  mov     [rsp+0F8h+var_C8], 0
0x14002eb0e  mov     r14d, [rsp+0F8h+var_B8]
0x14002eb13  mov     dword ptr [rsp+0F8h+HandleInformation], r14d
0x14002eb18  mov     dword ptr [rsp+0F8h+Irp], 0
0x14002eb20  xor     r9d, r9d
0x14002eb23  mov     r8, [rsp+0F8h+var_60]
0x14002eb2b  mov     edx, 177Eh
0x14002eb30  xor     ecx, ecx
0x14002eb32  call    AFDETW_TRACEACCEPTEX
0x14002eb37  xor     ebx, ebx
0x14002eb39  mov     rsi, [rsp+0F8h+arg_0]
0x14002eb41  mov     r13d, ebx
0x14002eb44  jmp     loc_14002F35E
0x14002eb49  mov     [rsp+0F8h+var_B8], ebx
0x14002eb4d  xorps   xmm0, xmm0
0x14002eb50  movups  [rsp+0F8h+var_A0], xmm0
0x14002eb55  movups  [rsp+0F8h+var_90], xmm0
0x14002eb5a  mov     cl, [rsi+40h]
0x14002eb5d  test    cl, cl
0x14002eb5f  jz      short loc_14002EB76
0x14002eb61  test    byte ptr [r12+20h], 3
0x14002eb67  jz      short loc_14002EB76
0x14002eb69  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14002eb70  nop     dword ptr [rax+rax+00h]
0x14002eb75  int     3; Trap to Debugger
0x14002eb76  mov     rdx, [r12+20h]; Src
0x14002eb7b  mov     r8d, 20h ; ' '; Size
0x14002eb81  test    cl, cl
0x14002eb83  lea     rcx, [rsp+0F8h+var_A0]; void *
0x14002eb88  jz      short loc_14002EB91
0x14002eb8a  call    RtlCopyFromUser
0x14002eb8f  jmp     short loc_14002EB96
0x14002eb91  call    RtlCopyVolatileMemory
0x14002eb96  mov     r14, qword ptr [rsp+0F8h+var_A0+8]
0x14002eb9b  mov     [rsp+0F8h+var_58], r14
0x14002eba3  mov     r9d, dword ptr [rsp+0F8h+var_90]
0x14002eba8  mov     [rsp+0F8h+arg_10], r9d
0x14002ebb0  mov     dword ptr [rsp+0F8h+var_70], r9d
0x14002ebb8  mov     ecx, dword ptr [rsp+0F8h+var_90+4]
0x14002ebbc  mov     [rsp+0F8h+arg_18], ecx
0x14002ebc3  mov     dword ptr [rsp+0F8h+var_70+4], ecx
0x14002ebca  mov     r8d, dword ptr [rsp+0F8h+var_90+8]
0x14002ebcf  mov     [rsp+0F8h+var_A8], r8d
0x14002ebd4  mov     [rsp+0F8h+var_68], r8d
0x14002ebdc  mov     rax, qword ptr [rsp+0F8h+var_A0]
0x14002ebe1  mov     [rsp+0F8h+var_B4], al
0x14002ebe5  mov     dl, byte ptr [rsp+0F8h+var_A0+1]
0x14002ebe9  mov     [rsp+0F8h+Irql], dl
0x14002ebf0  mov     [rsp+0F8h+var_B3], dl
0x14002ebf4  test    al, al
0x14002ebf6  jnz     short loc_14002EC4F
0x14002ebf8  cmp     cs:AfdSanServiceHelper, 0
0x14002ec00  jz      short loc_14002EC4F
0x14002ec02  test    byte ptr cs:xmmword_1400875E0+9, 2
0x14002ec09  jz      short loc_14002EC30
0x14002ec0b  call    cs:__imp_PsGetCurrentProcessId
0x14002ec12  nop     dword ptr [rax+rax+00h]
0x14002ec17  mov     r9, rax
0x14002ec1a  mov     edx, 0Fh
0x14002ec1f  mov     ecx, 509h
0x14002ec24  lea     r8, WPP_6216d3581a803072be4346b6e903d992_Traceguids
0x14002ec2b  call    WPP_SF_q
0x14002ec30  mov     r14d, 0C00000FAh
0x14002ec36  mov     [rsp+0F8h+var_C0], rbx
0x14002ec3b  mov     [rsp+0F8h+var_C8], rbx
0x14002ec40  mov     dword ptr [rsp+0F8h+HandleInformation], r14d
0x14002ec45  mov     edx, 1780h
0x14002ec4a  jmp     loc_14002EA3C
0x14002ec4f  mov     eax, [rdi+8]
0x14002ec52  mov     r15d, 1
0x14002ec58  test    r15b, al
0x14002ec5b  jz      loc_14002F2C5
0x14002ec61  cmp     r8d, 8
0x14002ec65  jb      loc_14002F2C5
0x14002ec6b  cmp     ecx, r15d
0x14002ec6e  jz      loc_14002F2C5
0x14002ec74  mov     edx, [r12+8]; Length
0x14002ec79  cmp     edx, r9d
0x14002ec7c  jb      loc_14002F2C5
0x14002ec82  mov     eax, edx
0x14002ec84  sub     eax, r9d
0x14002ec87  cmp     eax, ecx
0x14002ec89  jb      loc_14002F2C5
0x14002ec8f  sub     eax, ecx
0x14002ec91  cmp     eax, r8d
0x14002ec94  jb      loc_14002F2C5
0x14002ec9a  mov     [rsp+0F8h+Irp], rsi; Irp
0x14002ec9f  mov     r9b, r15b; ChargeQuota
0x14002eca2  xor     r8d, r8d; SecondaryBuffer
0x14002eca5  mov     rcx, [rsi+70h]; VirtualAddress
0x14002eca9  call    cs:__imp_IoAllocateMdl
0x14002ecb0  nop     dword ptr [rax+rax+00h]
0x14002ecb5  test    rax, rax
0x14002ecb8  jnz     short loc_14002ECF4
0x14002ecba  mov     [rsp+0F8h+var_B8], 0C000009Ah
0x14002ecc2  mov     [rsp+0F8h+var_C0], rbx
0x14002ecc7  mov     [rsp+0F8h+var_C8], rbx
0x14002eccc  mov     eax, [rsp+0F8h+var_B8]
0x14002ecd0  mov     dword ptr [rsp+0F8h+HandleInformation], eax
0x14002ecd4  mov     dword ptr [rsp+0F8h+Irp], ebx
0x14002ecd8  xor     r9d, r9d
0x14002ecdb  mov     r8, rdi
0x14002ecde  mov     edx, 1782h
0x14002ece3  xor     ecx, ecx
0x14002ece5  call    AFDETW_TRACEACCEPTEX
0x14002ecea  mov     r14d, [rsp+0F8h+var_B8]
0x14002ecef  jmp     loc_14002F35E
0x14002ecf4  mov     r8d, r15d; Operation
0x14002ecf7  mov     dl, [rsi+40h]; AccessMode
0x14002ecfa  mov     rcx, [rsi+8]; MemoryDescriptorList
0x14002ecfe  call    cs:__imp_MmProbeAndLockPages
0x14002ed05  nop     dword ptr [rax+rax+00h]
0x14002ed0a  nop
0x14002ed0b  mov     [rsp+0F8h+Object], rbx
0x14002ed10  mov     edx, [r12+18h]
0x14002ed15  shr     edx, 0Eh
0x14002ed18  and     edx, 3; DesiredAccess
0x14002ed1b  mov     [rsp+0F8h+HandleInformation], rbx; HandleInformation
0x14002ed20  lea     rax, [rsp+0F8h+Object]
0x14002ed25  mov     [rsp+0F8h+Irp], rax; Object
0x14002ed2a  mov     r9b, [rsi+40h]; AccessMode
0x14002ed2e  mov     r8, cs:__imp_IoFileObjectType
0x14002ed35  mov     r8, [r8]; ObjectType
0x14002ed38  mov     rcx, r14; Handle
0x14002ed3b  call    cs:__imp_ObReferenceObjectByHandle
0x14002ed42  nop     dword ptr [rax+rax+00h]
0x14002ed47  mov     r14d, eax
0x14002ed4a  mov     r13, [rsp+0F8h+Object]
0x14002ed4f  test    eax, eax
0x14002ed51  jns     short loc_14002ED6B
0x14002ed53  mov     [rsp+0F8h+var_C0], rbx
0x14002ed58  mov     [rsp+0F8h+var_C8], rbx
0x14002ed5d  mov     dword ptr [rsp+0F8h+HandleInformation], eax
0x14002ed61  mov     edx, 1784h
0x14002ed66  jmp     loc_14002EA3C
0x14002ed6b  mov     rcx, [rsi+98h]; Object
0x14002ed72  call    cs:__imp_ObfReferenceObject
0x14002ed79  nop     dword ptr [rax+rax+00h]
0x14002ed7e  mov     rax, cs:AfdDeviceObject
0x14002ed85  cmp     [r13+8], rax
0x14002ed89  jz      short loc_14002EDAA
0x14002ed8b  mov     r14d, 0C0000008h
0x14002ed91  mov     [rsp+0F8h+var_C0], rbx
0x14002ed96  mov     [rsp+0F8h+var_C8], rbx
0x14002ed9b  mov     dword ptr [rsp+0F8h+HandleInformation], r14d
0x14002eda0  mov     edx, 1785h
0x14002eda5  jmp     loc_14002EA3C
0x14002edaa  mov     r15, [r13+18h]
0x14002edae  mov     ecx, 4
0x14002edb3  xor     eax, eax
0x14002edb5  lock cmpxchg [r15+170h], ecx
0x14002edbe  jz      short loc_14002EDCA
0x14002edc0  mov     edx, 1786h
0x14002edc5  jmp     loc_14002EA26
0x14002edca  test    byte ptr [r15+6], 1
0x14002edcf  jnz     loc_14002F23E
0x14002edd5  mov     rax, [rdi+110h]
0x14002eddc  cmp     [r15+110h], rax
0x14002ede3  jz      short loc_14002EE06
0x14002ede5  mov     eax, [rdi+8]
0x14002ede8  bt      eax, 15h
0x14002edec  jnb     loc_14002F23E
0x14002edf2  mov     rax, [rdi+118h]
0x14002edf9  cmp     [r15+110h], rax
0x14002ee00  jnz     loc_14002F23E
0x14002ee06  mov     eax, [r15+8]
0x14002ee0a  bt      eax, 8
0x14002ee0e  jnb     short loc_14002EE1B
0x14002ee10  cmp     byte ptr [r15+2], 2
0x14002ee15  jnz     loc_14002F23E
0x14002ee1b  mov     eax, [r15+8]
0x14002ee1f  bt      eax, 8
0x14002ee23  jb      short loc_14002EE30
0x14002ee25  cmp     byte ptr [r15+2], 1
0x14002ee2a  jnz     loc_14002F23E
0x14002ee30  cmp     [r15+28h], rbx
0x14002ee34  jnz     loc_14002F23E
0x14002ee3a  mov     al, [rsp+0F8h+Irql]
0x14002ee41  mov     [r15+0BCh], al
0x14002ee48  mov     rax, [rsp+0F8h+var_58]
0x14002ee50  mov     [rsi+90h], rax
0x14002ee57  mov     [rsp+0F8h+var_C0], r15
0x14002ee5c  mov     [rsp+0F8h+var_C8], rbx
0x14002ee61  mov     dword ptr [rsp+0F8h+HandleInformation], r14d
0x14002ee66  mov     eax, [r12+8]
0x14002ee6b  mov     dword ptr [rsp+0F8h+Irp], eax
0x14002ee6f  mov     r9, [rsi+8]
0x14002ee73  mov     r8, rdi
0x14002ee76  mov     edx, 1788h
0x14002ee7b  xor     ecx, ecx
0x14002ee7d  call    AFDETW_TRACEACCEPTEX
0x14002ee82  mov     [r12+20h], r13
0x14002ee87  mov     eax, [rsp+0F8h+arg_10]
0x14002ee8e  mov     [r12+8], eax
0x14002ee93  mov     eax, [rsp+0F8h+arg_18]
0x14002ee9a  mov     [r12+18h], eax
0x14002ee9f  mov     eax, [rsp+0F8h+var_A8]
0x14002eea3  mov     [r12+10h], eax
0x14002eea8  mov     eax, [rdi+8]
0x14002eeab  bt      eax, 8
0x14002eeaf  jb      short loc_14002EED7
0x14002eeb1  lock inc dword ptr [rdi+0B0h]
0x14002eeb8  mov     eax, [rdi+8]
0x14002eebb  bt      eax, 16h
0x14002eebf  jnb     short loc_14002EECC
0x14002eec1  mov     rax, [rdi+118h]
0x14002eec8  lock inc dword ptr [rax+30h]
0x14002eecc  mov     rcx, rdi
0x14002eecf  call    AfdReplenishListenBacklog
0x14002eed4  mov     r14d, eax
0x14002eed7  mov     [r15+168h], rsi
0x14002eede  cmp     cs:AfdDisableDirectSuperAccept, 0
0x14002eee5  jnz     loc_14002F200
0x14002eeeb  mov     eax, [rdi+8]
0x14002eeee  bt      eax, 16h
0x14002eef2  jb      loc_14002F200
0x14002eef8  mov     eax, [rdi+8]
0x14002eefb  test    al, 2
0x14002eefd  jnz     loc_14002F200
0x14002ef03  lea     r15, [rdi+0A0h]
0x14002ef0a  mov     rcx, r15; SListHead
0x14002ef0d  call    cs:__imp_ExQueryDepthSList
  ... truncated ...
```
