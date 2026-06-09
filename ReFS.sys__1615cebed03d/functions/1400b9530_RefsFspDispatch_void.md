# RefsFspDispatch(void *)

- ea: `0x1400b9530`
- end: `0x1400ba064`
- name: `?RefsFspDispatch@@YAXPEAX@Z`
- size: `2868`
- prototype: `KSTART_ROUTINE`
- caller_count: `3`
- callee_count: `30`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1400b6650`
- `0x1400f8820`
- `0x1402e6f3c`

## callees

- `0x14000b1b0`
- `0x14000c180`
- `0x14000dfe0`
- `0x14000e0e0`
- `0x1400892a0`
- `0x14009a130`
- `0x1400a069c`
- `0x1400a2c60`
- `0x1400b9530`
- `0x1400ba4d0`
- `0x1400e6524`
- `0x1400e9e48`
- `0x1401f3fc0`
- `0x1401f4400`
- `0x14028d92c`
- `0x14028dacc`
- `0x14029d114`
- `0x1402c90a0`
- `0x140305020`
- `0x1403066d0`
- `0x14030bca0`
- `0x14030d820`
- `0x1403115a0`
- `0x1403162c0`
- `0x140319010`
- `0x14031cca8`
- `0x140323ce0`
- `0x14032b620`
- `0x14033a7a8`
- `0x1403411a0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400ba02c`
- `ntoskrnl!ObfDereferenceObject` at `0x1400ba02c`
- `ntoskrnl!KeBugCheckEx` at `0x1400b9a2f`
- `ntoskrnl!KeBugCheckEx` at `0x1400b9a2f`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1400b9701`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1400b9701`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1400b9830`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1400b9830`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400b96b5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400b96b5`
- `ntoskrnl!IoClearActivityIdThread` at `0x1400b9d81`
- `ntoskrnl!IoClearActivityIdThread` at `0x1400b9d81`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400b9d8d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400b9d8d`
- `ntoskrnl!KeSetEvent` at `0x1400b9fa8`
- `ntoskrnl!KeSetEvent` at `0x1400b9fa8`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1400b97d2`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1400b97d2`
- `ntoskrnl!IoRetrievePriorityInfo` at `0x1400b97bf`
- `ntoskrnl!IoRetrievePriorityInfo` at `0x1400b97bf`
- `ntoskrnl!IoSetIoPriorityHintIntoThread` at `0x1400b97e9`
- `ntoskrnl!IoSetIoPriorityHintIntoThread` at `0x1400b97e9`
- `ntoskrnl!IoApplyPriorityInfoThread` at `0x1400b9d68`
- `ntoskrnl!IoApplyPriorityInfoThread` at `0x1400b9d68`
- `ntoskrnl!ObfReferenceObject` at `0x1400b9666`
- `ntoskrnl!ObfReferenceObject` at `0x1400b9666`
- `ntoskrnl!IoSetActivityIdThread` at `0x1400b96ea`
- `ntoskrnl!IoSetActivityIdThread` at `0x1400b96ea`
- `ntoskrnl!CcIsCacheManagerCallbackNeeded` at `0x1400b98b3`
- `ntoskrnl!CcIsCacheManagerCallbackNeeded` at `0x1400b9cae`
- `ntoskrnl!CcIsCacheManagerCallbackNeeded` at `0x1400b98b3`
- `ntoskrnl!CcIsCacheManagerCallbackNeeded` at `0x1400b9cae`
- `ntoskrnl!CcErrorCallbackRoutine` at `0x1400b98db`
- `ntoskrnl!CcErrorCallbackRoutine` at `0x1400b98db`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400b9946`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400b9dc6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400b9f2b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400b9946`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400b9dc6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400b9f2b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400b995c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400b9f1c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400b9f8a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400ba018`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400b995c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400b9f1c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400b9f8a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400ba018`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400ba053`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400ba053`
- `ntoskrnl!IoWithinStackLimits` at `0x1400b9718`
- `ntoskrnl!IoWithinStackLimits` at `0x1400b9718`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400b9ee4`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400b9ee4`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400b9f01`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400b9f43`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400b9f01`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400b9f43`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400b9980`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400b9980`
- `ntoskrnl!KeInitializeEvent` at `0x1400b9af8`
- `ntoskrnl!KeInitializeEvent` at `0x1400b9af8`

## pseudocode

```c
void __fastcall RefsFspDispatch(struct _IRP_CONTEXT *StartContext)
{
  struct _IRP_CONTEXT *v1; // r14
  __int64 v2; // rdx
  __int64 v3; // r13
  unsigned int v4; // edi
  __int64 v5; // rbx
  int v6; // ecx
  __int64 v7; // rax
  _OWORD *v8; // rax
  PVOID *v9; // rcx
  bool v10; // r15
  ULONG_PTR TopLevelIrp; // rsi
  IRP *p_Irp; // rax
  IO_PRIORITY_HINT IoPriorityHint; // eax
  char Type; // al
  int v15; // edx
  bool v16; // r8
  __int64 v17; // r12
  __int64 v18; // rsi
  KIRQL v19; // al
  int v20; // eax
  struct REFS_IO_CONTEXT *v21; // rdx
  struct _IRP_CONTEXT *v22; // rcx
  char v23; // r15
  int v24; // esi
  int v25; // eax
  KSPIN_LOCK *v26; // rbx
  KIRQL v27; // dl
  __int64 v28; // rsi
  struct _IO_STATUS_BLOCK *v29; // rcx
  unsigned int v30; // ecx
  __int64 *v31; // r15
  __int64 v32; // rcx
  __int64 *v33; // rax
  char v34; // [rsp+30h] [rbp-108h]
  char v35; // [rsp+31h] [rbp-107h]
  char v36; // [rsp+33h] [rbp-105h]
  KIRQL Irql; // [rsp+34h] [rbp-104h] BYREF
  KIRQL v38; // [rsp+35h] [rbp-103h]
  bool v39; // [rsp+36h] [rbp-102h]
  int v40; // [rsp+38h] [rbp-100h]
  unsigned int v41; // [rsp+3Ch] [rbp-FCh]
  int v42; // [rsp+40h] [rbp-F8h]
  unsigned int v43; // [rsp+44h] [rbp-F4h]
  int v44; // [rsp+48h] [rbp-F0h]
  int v45; // [rsp+4Ch] [rbp-ECh]
  struct _IO_STATUS_BLOCK *v46; // [rsp+50h] [rbp-E8h]
  struct _IRP_CONTEXT *v47; // [rsp+58h] [rbp-E0h]
  IRP Irp; // [rsp+60h] [rbp-D8h] BYREF

  v1 = StartContext;
  memset(&Irp, 0, 40);
  Irp.IoStatus.Pointer = 0;
  v2 = 0;
  v45 = 0;
  v41 = 0;
  v43 = 0;
  v3 = 0;
  v39 = 0;
  v4 = 0;
  v40 = 0;
  memset(&Irp.Overlay.AllocationSize + 1, 0, 40);
  v36 = 0;
  v47 = StartContext;
  *((_QWORD *)StartContext + 15) = (char *)StartContext + 112;
  *((_QWORD *)StartContext + 14) = (char *)StartContext + 112;
  v5 = *((_QWORD *)StartContext + 9);
  *(_QWORD *)&Irp.RequestorMode = v5;
  if ( v5 )
    v2 = *(_QWORD *)(v5 + 184);
  v6 = *((_DWORD *)StartContext + 1);
  v42 = v6 & 0x4000000;
  HIDWORD(Irp.ThreadListEntry.Blink) = v6 & 0x4000000;
  v44 = v6 & 0x100000;
  LODWORD(Irp.ThreadListEntry.Blink) = v6 & 0x100000;
  v7 = *((_QWORD *)v1 + 1);
  v46 = (struct _IO_STATUS_BLOCK *)(v7 & 0x1000);
  Irp.UserIosb = v46;
  v34 = v6 & 1;
  *((_DWORD *)v1 + 1) = v6 & 0xFFFFFFFE;
  *((_QWORD *)v1 + 1) = v7 | 1;
  if ( (v6 & 0x4000000) == 0 && (v6 & 0x100000) == 0 )
  {
    if ( v5 && *(_QWORD *)(v2 + 48) )
    {
      v3 = *(_QWORD *)(v2 + 40);
      Irp.ThreadListEntry.Flink = (struct _LIST_ENTRY *)v3;
      ObfReferenceObject((PVOID)v3);
    }
    else
    {
      Irp.ThreadListEntry.Flink = 0;
    }
    v39 = (*((_DWORD *)v1 + 1) & 0x400000) != 0;
  }
  Irp.UserEvent = (PKEVENT)v3;
  do
  {
    memset(&Irp.Tail.CompletionKey + 2, 0, 24);
    KeEnterCriticalRegion();
    v8 = (_OWORD *)*((_QWORD *)v1 + 10);
    if ( v8 )
    {
      *(_OWORD *)(&Irp.Tail.CompletionKey + 3) = *v8;
      v9 = &Irp.Tail.Overlay.DriverContext[3];
    }
    else
    {
      v9 = 0;
    }
    Irp.Tail.Overlay.DriverContext[2] = v9;
    Irp.Overlay.AllocationSize.QuadPart = IoSetActivityIdThread();
    v10 = 0;
    TopLevelIrp = (ULONG_PTR)IoGetTopLevelIrp();
    if ( IoWithinStackLimits(TopLevelIrp, 0x18u) && (TopLevelIrp & 3) == 0 )
      v10 = *(_DWORD *)(TopLevelIrp + 4) == 1397140410;
    *(_DWORD *)(&Irp.Size + 1) = 0;
    Irp.MdlAddress = (PMDL)TopLevelIrp;
    *(_QWORD *)&Irp.Flags = 0;
    LOBYTE(Irp.Type) = 1;
    if ( v10 )
    {
      HIBYTE(Irp.Type) = 1;
      LOBYTE(Irp.Size) = *(_BYTE *)(TopLevelIrp + 2);
    }
    else
    {
      *(CSHORT *)((char *)&Irp.Type + 1) = 0;
    }
    p_Irp = &Irp;
    Irp.IoStatus.Information = (ULONG_PTR)&Irp;
    if ( v5 )
    {
      LODWORD(Irp.Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink) = 16;
      *(PVOID *)((char *)Irp.Tail.Overlay.DriverContext + 4) = (PVOID)0xFFFF;
      *((_DWORD *)&Irp.Tail.CompletionKey + 3) = 2;
      if ( IoRetrievePriorityInfo(0, 0, KeGetCurrentThread(), (PIO_PRIORITY_INFO)&Irp.Tail) >= 0 )
      {
        IoPriorityHint = IoGetIoPriorityHint((PIRP)v5);
        IoSetIoPriorityHintIntoThread(KeGetCurrentThread(), (unsigned int)IoPriorityHint);
        v36 = 1;
      }
      v4 = 0;
      v40 = 0;
      p_Irp = (IRP *)Irp.IoStatus.Information;
    }
    ++RefsPostRequests;
    do
    {
      if ( !*(_QWORD *)&Irp.Flags )
      {
        *(_DWORD *)(&Irp.Size + 1) = 1397140410;
        *(_QWORD *)&Irp.Flags = v1;
        *((_QWORD *)v1 + 1) |= 0x100000uLL;
        IoSetTopLevelIrp(p_Irp);
      }
      *((_QWORD *)v1 + 13) = *(_QWORD *)&Irp.Flags;
      Type = Irp.Type;
      if ( (*((_DWORD *)v1 + 2) & 0x2000LL) != 0 )
        Type = 0;
      LOBYTE(Irp.Type) = Type;
      v35 = 0;
      *((_DWORD *)v1 + 4) = 0;
      *((_QWORD *)v1 + 1) |= 0x40uLL;
      if ( v46 && !v42 )
        *((_DWORD *)v1 + 1) |= 0x8000000u;
      if ( v4 == -1073741432 || !v5 )
      {
        RefsCheckpointForLogFileFull(v1);
        if ( (unsigned int)++v45 >= 2 )
          *((_DWORD *)v1 + 1) |= 0x10u;
        v4 = 0;
        v40 = 0;
      }
      if ( (unsigned __int8)CcIsCacheManagerCallbackNeeded(v4) )
      {
        Irp.AssociatedIrp.IrpCount = 8;
        HIDWORD(Irp.AssociatedIrp.SystemBuffer) = v4;
        CcErrorCallbackRoutine(&Irp.AssociatedIrp);
      }
      RefsPreRequestProcessingExtend(v1, v15);
      if ( v5 )
      {
        switch ( *((_BYTE *)v1 + 40) )
        {
          case 0:
            *((_QWORD *)v1 + 1) &= ~2uLL;
            v17 = *((_QWORD *)v1 + 18);
            if ( (*(_DWORD *)(v17 + 144) & 0x100000) != 0 )
            {
              v18 = *(_QWORD *)(*((_QWORD *)v1 + 8) + 112LL);
              v19 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v18 + 3976));
              KeReleaseSpinLock((PKSPIN_LOCK)(v18 + 3976), v19);
              KeWaitForSingleObject((PVOID)(v18 + 4008), Executive, 0, 0, 0);
            }
            memset((void *)v17, 0, 0xD8u);
            *(_QWORD *)(v17 + 160) = *(_QWORD *)(v5 + 184);
            if ( (*((_DWORD *)v1 + 2) & 0x200LL) != 0 )
              v20 = RefsCommonVolumeOpen(v1, (struct _IRP *)v5, (struct _CREATE_CONTEXT *)v17);
            else
              v20 = RefsCommonCreate(v1, (PIRP)v5, (struct _CREATE_CONTEXT *)v17);
            v4 = v20;
            v40 = v20;
            goto LABEL_72;
          case 2:
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_1e930544d89f3ce82d53e09c7070df23_Traceguids);
            }
            KeBugCheckEx(0x149u, 0x130184u, 0, 0, 0);
          case 3:
            Irp.IoStatus.Pointer = (char *)v1 + 800;
            v21 = (struct _IRP_CONTEXT *)((char *)v1 + 800);
            v22 = v1;
            if ( (*((_DWORD *)v1 + 2) & 0x1000LL) != 0 )
              goto LABEL_53;
            RefsInitializeIoContext(v1, v21, v16, (*(_DWORD *)(v5 + 16) & 2) != 0);
            RefsCommonRead(v1, (struct _IRP_CONTEXT *)((char *)v1 + 800), (PIRP)v5);
            goto LABEL_72;
          case 4:
            Irp.IoStatus.Pointer = (char *)v1 + 800;
            v21 = (struct _IRP_CONTEXT *)((char *)v1 + 800);
            v22 = v1;
            if ( (*((_DWORD *)v1 + 2) & 0x1000LL) != 0 )
            {
LABEL_53:
              RefsCommonIoCompletionWorker(v22, v21, (struct _IRP *)v5);
            }
            else
            {
              RefsInitializeIoContext(v1, v21, v16, (*(_DWORD *)(v5 + 16) & 2) != 0);
              RefsCommonWrite(v1, (struct _IRP_CONTEXT *)((char *)v1 + 800), (PIRP)v5);
            }
            goto LABEL_72;
          case 5:
            RefsCommonQueryInformation(v1, (PIRP)v5);
            goto LABEL_72;
          case 6:
            KeInitializeEvent((PRKEVENT)(&Irp.Overlay.AllocationSize + 1), NotificationEvent, 0);
            *((_QWORD *)v1 + 19) = &Irp.Overlay.AsynchronousParameters.UserApcContext;
            v4 = RefsCommonSetInformation(v1, (PIRP)v5);
            v40 = v4;
            if ( v4 != 871 )
              goto LABEL_72;
            RefsWaitForOplockCompletionEvent((PIRP)v5, (PRKEVENT)(&Irp.Overlay.AllocationSize + 1));
            v35 = 1;
            v23 = v34;
            v24 = v42;
            break;
          case 9:
            RefsCommonFlushBuffers(v1, (PIRP)v5);
            goto LABEL_72;
          case 0xA:
            RefsCommonQueryVolumeInfo(v1, (struct _IRP *)v5);
            goto LABEL_72;
          case 0xB:
            RefsCommonSetVolumeInfo(v1, (PIRP)v5);
            goto LABEL_72;
          case 0xC:
            RefsCommonDirectoryControl(v1, (struct _IRP *)v5);
            goto LABEL_72;
          case 0xD:
            RefsCommonFileSystemControl(v1, (struct _IRP *)v5);
            goto LABEL_72;
          case 0xE:
            RefsCommonDeviceControl(v1, (PIRP)v5);
            goto LABEL_72;
          case 0x11:
            RefsCommonLockControl(v1, (PIRP)v5);
            goto LABEL_72;
          case 0x12:
            RefsCommonCleanup(v1, (struct _IRP *)v5);
            goto LABEL_72;
          case 0x14:
            RefsCommonQuerySecurityInfo(v1, (PIRP)v5);
            goto LABEL_72;
          case 0x15:
            RefsCommonSetSecurityInfo(v1, (PIRP)v5);
            goto LABEL_72;
          default:
            RefsCompleteRequest(v1, (PIRP)v5, -1073741808);
            goto LABEL_72;
        }
      }
      else
      {
        RefsCompleteRequest(v1, 0, 0);
        v1 = 0;
        v47 = 0;
LABEL_72:
        v23 = v34;
        v24 = v42;
      }
      p_Irp = (IRP *)Irp.IoStatus.Information;
    }
    while ( v35 );
    if ( v36 )
    {
      IoApplyPriorityInfoThread((PIO_PRIORITY_INFO)&Irp.Tail, 0, KeGetCurrentThread());
      v36 = 0;
    }
    ((void (__fastcall *)(_QWORD))IoClearActivityIdThread)((LARGE_INTEGER)Irp.Overlay.AllocationSize.QuadPart);
    KeLeaveCriticalRegion();
    v25 = v44;
    if ( v24 )
      return;
    if ( v44 )
      continue;
    if ( !Irp.ThreadListEntry.Flink )
    {
      if ( v39 )
        KeReleaseSemaphore(&RefsGlobalPostThrottle, 0, 1, 0);
      return;
    }
    v26 = (KSPIN_LOCK *)(v3 + 6216);
    v27 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 6216));
    v38 = v27;
    if ( v23 )
      --*(_DWORD *)(v3 + 6060);
    while ( 1 )
    {
      v28 = 0;
      v29 = v46;
      if ( v46 )
      {
        if ( *(_DWORD *)(v3 + 6208) )
          v28 = v3 + 6168;
      }
      else
      {
        if ( !*(_DWORD *)(v3 + 6160) || *(_DWORD *)(v3 + 6060) )
        {
          v41 = 0;
          v43 = 0;
          v34 = 0;
          if ( !*(_DWORD *)(v3 + 6112) )
            goto LABEL_93;
        }
        else
        {
          v30 = v41 + 1;
          v41 = v30;
          if ( v30 > 0x14 || !*(_DWORD *)(v3 + 6112) )
          {
            v41 = 0;
            v43 = 0;
            v34 = 1;
            v28 = v3 + 6120;
            v29 = v46;
            goto LABEL_93;
          }
          v43 = v30;
          v29 = v46;
          if ( !*(_DWORD *)(v3 + 6112) )
            goto LABEL_93;
          v34 = 0;
        }
        v28 = v3 + 6072;
      }
LABEL_93:
      if ( !v28 )
      {
        if ( v29 )
          --*(_DWORD *)(v3 + 6064);
        else
          --*(_DWORD *)(v3 + 6056);
        KeReleaseSpinLock(v26, v27);
        ObfDereferenceObject(Irp.ThreadListEntry.Flink);
        return;
      }
      v31 = *(__int64 **)(v28 + 24);
      v1 = (struct _IRP_CONTEXT *)(v31 - 14);
      v47 = (struct _IRP_CONTEXT *)(v31 - 14);
      v5 = *(v31 - 5);
      *(_QWORD *)&Irp.RequestorMode = v5;
      if ( v29 )
        goto LABEL_98;
      Irql = 0;
      IoAcquireCancelSpinLock(&Irql);
      if ( _InterlockedExchange64((volatile __int64 *)(v5 + 104), 0) )
        break;
      IoReleaseCancelSpinLock(Irql);
      v26 = (KSPIN_LOCK *)(v3 + 6216);
      KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 6216), v38);
      v27 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 6216));
      v38 = v27;
    }
    IoReleaseCancelSpinLock(Irql);
    *(_QWORD *)(v5 + 56) = 0;
    v27 = v38;
LABEL_98:
    --*(_DWORD *)(v28 + 40);
    v32 = *v31;
    v33 = (__int64 *)v31[1];
    *v33 = *v31;
    *(_QWORD *)(v32 + 8) = v33;
    v31[1] = (__int64)v31;
    *v31 = (__int64)v31;
    if ( v34 )
      ++*(_DWORD *)(v3 + 6060);
    KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 6216), v27);
    if ( *(_DWORD *)(v28 + 40) < 0x3E8u )
      KeSetEvent((PRKEVENT)v28, 0, 0);
    v45 = 0;
    *((_QWORD *)v1 + 1) |= 1uLL;
    v24 = v42;
    v25 = v44;
  }
  while ( !v24 && !v25 );
}

```

## disassembly

```asm
0x1400b9530  mov     r11, rsp
0x1400b9533  mov     [r11+10h], rbx
0x1400b9537  mov     [r11+18h], rsi
0x1400b953b  push    rdi
0x1400b953c  push    r12
0x1400b953e  push    r13
0x1400b9540  push    r14
0x1400b9542  push    r15
0x1400b9544  sub     rsp, 110h
0x1400b954b  mov     rax, cs:__security_cookie
0x1400b9552  xor     rax, rsp
0x1400b9555  mov     qword ptr [rsp+138h+Irp.Tail+28h], rax
0x1400b955d  mov     r14, rcx
0x1400b9560  xorps   xmm0, xmm0
0x1400b9563  xor     eax, eax
0x1400b9565  movups  xmmword ptr [rsp+138h+Irp.Type], xmm0
0x1400b956a  mov     qword ptr [rsp+138h+Irp.Flags], rax
0x1400b956f  xor     r12d, r12d
0x1400b9572  mov     [r11-0A8h], r12
0x1400b9579  mov     edx, r12d
0x1400b957c  mov     [rsp+138h+var_EC], r12d
0x1400b9581  mov     [rsp+138h+var_FC], eax
0x1400b9585  mov     [rsp+138h+var_F4], eax
0x1400b9589  mov     r13d, r12d
0x1400b958c  mov     [rsp+138h+Irp.ThreadListEntry.Flink], r12
0x1400b9594  mov     [rsp+138h+var_102], al
0x1400b9598  mov     edi, r12d
0x1400b959b  mov     [rsp+138h+var_100], r12d
0x1400b95a0  movups  xmmword ptr [r11-78h], xmm0
0x1400b95a5  mov     [r11-68h], rax
0x1400b95a9  mov     [rsp+138h+var_105], al
0x1400b95ad  movups  xmmword ptr [r11-60h], xmm0
0x1400b95b2  mov     qword ptr [rsp+138h+Irp.AssociatedIrp], r12
0x1400b95b7  mov     [rsp+138h+var_E0], rcx
0x1400b95bc  lea     rax, [rcx+70h]
0x1400b95c0  mov     [rax+8], rax
0x1400b95c4  mov     [rax], rax
0x1400b95c7  mov     rbx, [rcx+48h]
0x1400b95cb  mov     qword ptr [rsp+138h+Irp.RequestorMode], rbx
0x1400b95d3  test    rbx, rbx
0x1400b95d6  jz      short loc_1400B95DF
0x1400b95d8  mov     rdx, [rbx+0B8h]
0x1400b95df  mov     ecx, [rcx+4]
0x1400b95e2  mov     esi, ecx
0x1400b95e4  and     esi, 4000000h
0x1400b95ea  mov     [rsp+138h+var_F8], esi
0x1400b95ee  mov     dword ptr [rsp+138h+Irp.ThreadListEntry.Blink+4], esi
0x1400b95f5  mov     r9d, ecx
0x1400b95f8  and     r9d, 100000h
0x1400b95ff  mov     [rsp+138h+var_F0], r9d
0x1400b9604  mov     dword ptr [rsp+138h+Irp.ThreadListEntry.Blink], r9d
0x1400b960c  mov     rax, [r14+8]
0x1400b9610  mov     r8, rax
0x1400b9613  and     r8d, 1000h
0x1400b961a  mov     [rsp+138h+var_E8], r8
0x1400b961f  mov     [rsp+138h+Irp.UserIosb], r8
0x1400b9627  movzx   r15d, cl
0x1400b962b  and     r15b, 1
0x1400b962f  mov     [rsp+138h+var_108], r15b
0x1400b9634  and     ecx, 0FFFFFFFEh
0x1400b9637  mov     [r14+4], ecx
0x1400b963b  or      rax, 1
0x1400b963f  mov     [r14+8], rax
0x1400b9643  test    esi, esi
0x1400b9645  jnz     short loc_1400B9689
0x1400b9647  test    r9d, r9d
0x1400b964a  jnz     short loc_1400B9689
0x1400b964c  test    rbx, rbx
0x1400b964f  jz      short loc_1400B9674
0x1400b9651  cmp     [rdx+30h], rdi
0x1400b9655  jz      short loc_1400B9674
0x1400b9657  mov     r13, [rdx+28h]
0x1400b965b  mov     [rsp+138h+Irp.ThreadListEntry.Flink], r13
0x1400b9663  mov     rcx, r13; Object
0x1400b9666  call    cs:__imp_ObfReferenceObject
0x1400b966d  nop     dword ptr [rax+rax+00h]
0x1400b9672  jmp     short loc_1400B967C
0x1400b9674  mov     [rsp+138h+Irp.ThreadListEntry.Flink], r13
0x1400b967c  mov     eax, [r14+4]
0x1400b9680  shr     eax, 16h
0x1400b9683  and     al, 1
0x1400b9685  mov     [rsp+138h+var_102], al
0x1400b9689  mov     [rsp+138h+Irp.UserEvent], r13
0x1400b9691  mov     [rsp+138h+var_106], r15b
0x1400b9696  nop     word ptr [rax+rax+00000000h]
0x1400b96a0  xorps   xmm0, xmm0
0x1400b96a3  xor     eax, eax
0x1400b96a5  movups  xmmword ptr [rsp+138h+Irp.Tail+10h], xmm0
0x1400b96ad  mov     qword ptr [rsp+138h+Irp.Tail+20h], rax
0x1400b96b5  call    cs:__imp_KeEnterCriticalRegion
0x1400b96bc  nop     dword ptr [rax+rax+00h]
0x1400b96c1  mov     rax, [r14+50h]
0x1400b96c5  test    rax, rax
0x1400b96c8  jz      short loc_1400B96DF
0x1400b96ca  movups  xmm0, xmmword ptr [rax]
0x1400b96cd  movups  xmmword ptr [rsp+138h+Irp.Tail+18h], xmm0
0x1400b96d5  lea     rcx, [rsp+138h+Irp.Tail+18h]
0x1400b96dd  jmp     short loc_1400B96E2
0x1400b96df  mov     rcx, r12
0x1400b96e2  mov     qword ptr [rsp+138h+Irp.Tail+10h], rcx
0x1400b96ea  call    cs:__imp_IoSetActivityIdThread
0x1400b96f1  nop     dword ptr [rax+rax+00h]
0x1400b96f6  mov     qword ptr [rsp+138h+Irp.Overlay], rax
0x1400b96fe  xor     r15b, r15b
0x1400b9701  call    cs:__imp_IoGetTopLevelIrp
0x1400b9708  nop     dword ptr [rax+rax+00h]
0x1400b970d  mov     rsi, rax
0x1400b9710  mov     edx, 18h; RegionSize
0x1400b9715  mov     rcx, rax; RegionStart
0x1400b9718  call    cs:__imp_IoWithinStackLimits
0x1400b971f  nop     dword ptr [rax+rax+00h]
0x1400b9724  test    eax, eax
0x1400b9726  jz      short loc_1400B9743
0x1400b9728  test    sil, 3
0x1400b972c  jnz     short loc_1400B9743
0x1400b972e  movzx   r15d, r15b
0x1400b9732  cmp     dword ptr [rsi+4], 5346ABBAh
0x1400b9739  mov     r8d, 1
0x1400b973f  cmovz   r15d, r8d
0x1400b9743  mov     dword ptr [rsp+138h+Irp+4], r12d
0x1400b9748  mov     [rsp+138h+Irp.MdlAddress], rsi
0x1400b974d  mov     qword ptr [rsp+138h+Irp.Flags], r12
0x1400b9752  mov     byte ptr [rsp+138h+Irp.Type], 1
0x1400b9757  test    r15b, r15b
0x1400b975a  jz      short loc_1400B976B
0x1400b975c  mov     byte ptr [rsp+138h+Irp.Type+1], 1
0x1400b9761  movzx   eax, byte ptr [rsi+2]
0x1400b9765  mov     byte ptr [rsp+138h+Irp.Size], al
0x1400b9769  jmp     short loc_1400B9772
0x1400b976b  mov     [rsp+138h+Irp.Type+1], 0
0x1400b9772  lea     rax, [rsp+138h+Irp]
0x1400b9777  mov     [rsp+138h+Irp.IoStatus.Information], rax
0x1400b977f  test    rbx, rbx
0x1400b9782  jz      loc_1400B980A
0x1400b9788  mov     dword ptr [rsp+138h+Irp.Tail], 10h
0x1400b9793  mov     qword ptr [rsp+138h+Irp.Tail+4], 0FFFFh
0x1400b979f  mov     dword ptr [rsp+138h+Irp.Tail+0Ch], 2
0x1400b97aa  mov     r8, gs:188h; Thread
0x1400b97b3  lea     r9, [rsp+138h+Irp.Tail]; PriorityInfo
0x1400b97bb  xor     edx, edx; FileObject
0x1400b97bd  xor     ecx, ecx; Irp
0x1400b97bf  call    cs:__imp_IoRetrievePriorityInfo
0x1400b97c6  nop     dword ptr [rax+rax+00h]
0x1400b97cb  test    eax, eax
0x1400b97cd  js      short loc_1400B97FA
0x1400b97cf  mov     rcx, rbx; Irp
0x1400b97d2  call    cs:__imp_IoGetIoPriorityHint
0x1400b97d9  nop     dword ptr [rax+rax+00h]
0x1400b97de  mov     rcx, gs:188h
0x1400b97e7  mov     edx, eax
0x1400b97e9  call    cs:__imp_IoSetIoPriorityHintIntoThread
0x1400b97f0  nop     dword ptr [rax+rax+00h]
0x1400b97f5  mov     [rsp+138h+var_105], 1
0x1400b97fa  mov     edi, r12d
0x1400b97fd  mov     [rsp+138h+var_100], r12d
0x1400b9802  mov     rax, [rsp+138h+Irp.IoStatus.Information]
0x1400b980a  inc     cs:?RefsPostRequests@@3KA; ulong RefsPostRequests
0x1400b9810  cmp     qword ptr [rsp+138h+Irp.Flags], 0
0x1400b9816  jnz     short loc_1400B983C
0x1400b9818  mov     dword ptr [rsp+138h+Irp+4], 5346ABBAh
0x1400b9820  mov     qword ptr [rsp+138h+Irp.Flags], r14
0x1400b9825  or      qword ptr [r14+8], 100000h
0x1400b982d  mov     rcx, rax; Irp
0x1400b9830  call    cs:__imp_IoSetTopLevelIrp
0x1400b9837  nop     dword ptr [rax+rax+00h]
0x1400b983c  mov     rax, qword ptr [rsp+138h+Irp.Flags]
0x1400b9841  mov     [r14+68h], rax
0x1400b9845  mov     eax, [r14+8]
0x1400b9849  bt      rax, 0Dh
0x1400b984e  movzx   eax, byte ptr [rsp+138h+Irp.Type]
0x1400b9853  cmovb   eax, r12d
0x1400b9857  mov     byte ptr [rsp+138h+Irp.Type], al
0x1400b985b  mov     [rsp+138h+var_107], 0
0x1400b9860  mov     [r14+10h], r12d
0x1400b9864  or      qword ptr [r14+8], 40h
0x1400b9869  cmp     [rsp+138h+var_E8], 0
0x1400b986f  jz      short loc_1400B9880
0x1400b9871  cmp     [rsp+138h+var_F8], 0
0x1400b9876  jnz     short loc_1400B9880
0x1400b9878  or      dword ptr [r14+4], 8000000h
0x1400b9880  cmp     edi, 0C0000188h
0x1400b9886  jz      short loc_1400B988D
0x1400b9888  test    rbx, rbx
0x1400b988b  jnz     short loc_1400B98B1
0x1400b988d  mov     rcx, r14; struct _IRP_CONTEXT *
0x1400b9890  call    ?RefsCheckpointForLogFileFull@@YAXPEAU_IRP_CONTEXT@@@Z; RefsCheckpointForLogFileFull(_IRP_CONTEXT *)
0x1400b9895  mov     eax, [rsp+138h+var_EC]
0x1400b9899  inc     eax
0x1400b989b  mov     [rsp+138h+var_EC], eax
0x1400b989f  cmp     eax, 2
0x1400b98a2  jb      short loc_1400B98A9
0x1400b98a4  or      dword ptr [r14+4], 10h
0x1400b98a9  mov     edi, r12d
0x1400b98ac  mov     [rsp+138h+var_100], r12d
0x1400b98b1  mov     ecx, edi
0x1400b98b3  call    cs:__imp_CcIsCacheManagerCallbackNeeded
0x1400b98ba  nop     dword ptr [rax+rax+00h]
0x1400b98bf  test    al, al
0x1400b98c1  jz      short loc_1400B98E7
0x1400b98c3  mov     qword ptr [rsp+138h+Irp.AssociatedIrp], r12
0x1400b98c8  mov     eax, 8
0x1400b98cd  mov     word ptr [rsp+138h+Irp.AssociatedIrp], ax
0x1400b98d2  mov     dword ptr [rsp+138h+Irp.AssociatedIrp+4], edi
0x1400b98d6  lea     rcx, [rsp+138h+Irp.AssociatedIrp]
0x1400b98db  call    cs:__imp_CcErrorCallbackRoutine
0x1400b98e2  nop     dword ptr [rax+rax+00h]
0x1400b98e7  mov     rcx, r14; struct _IRP_CONTEXT *
0x1400b98ea  call    ?RefsPreRequestProcessingExtend@@YAXPEAU_IRP_CONTEXT@@J@Z; RefsPreRequestProcessingExtend(_IRP_CONTEXT *,long)
0x1400b98ef  test    rbx, rbx
0x1400b98f2  jz      loc_1400B9BF1
0x1400b98f8  movzx   eax, byte ptr [r14+28h]
0x1400b98fd  cmp     eax, 15h; switch 22 cases
0x1400b9900  ja      def_1400B9917; jumptable 00000001400B9917 default case, cases 1,7,8,15,16,19
0x1400b9906  lea     rdx, cs:140000000h
0x1400b990d  mov     ecx, ds:(jpt_1400B9917 - 140000000h)[rdx+rax*4]
0x1400b9914  add     rcx, rdx
0x1400b9917  jmp     rcx; switch jump
0x1400b991d  and     qword ptr [r14+8], 0FFFFFFFFFFFFFFFDh; jumptable 00000001400B9917 case 0
0x1400b9922  mov     r12, [r14+90h]
0x1400b9929  test    dword ptr [r12+90h], 100000h
0x1400b9935  jz      short loc_1400B998C
0x1400b9937  mov     rax, [r14+40h]
0x1400b993b  mov     rsi, [rax+70h]
0x1400b993f  lea     rcx, [rsi+0F88h]; SpinLock
0x1400b9946  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400b994d  nop     dword ptr [rax+rax+00h]
0x1400b9952  movzx   edx, al; NewIrql
0x1400b9955  lea     rcx, [rsi+0F88h]; SpinLock
0x1400b995c  call    cs:__imp_KeReleaseSpinLock
0x1400b9963  nop     dword ptr [rax+rax+00h]
0x1400b9968  lea     rcx, [rsi+0FA8h]; Object
0x1400b996f  mov     [rsp+138h+Timeout], 0; Timeout
0x1400b9978  xor     r9d, r9d; Alertable
0x1400b997b  xor     r8d, r8d; WaitMode
0x1400b997e  xor     edx, edx; WaitReason
0x1400b9980  call    cs:__imp_KeWaitForSingleObject
0x1400b9987  nop     dword ptr [rax+rax+00h]
0x1400b998c  xor     edx, edx; Val
0x1400b998e  mov     r8d, 0D8h; Size
0x1400b9994  mov     rcx, r12; void *
0x1400b9997  call    memset
0x1400b999c  mov     rax, [rbx+0B8h]
0x1400b99a3  mov     [r12+0A0h], rax
0x1400b99ab  mov     eax, [r14+8]
0x1400b99af  mov     r8, r12; struct _CREATE_CONTEXT *
0x1400b99b2  mov     rdx, rbx; Irp
0x1400b99b5  mov     rcx, r14; struct _IRP_CONTEXT *
0x1400b99b8  bt      rax, 9
0x1400b99bd  jnb     short loc_1400B99D2
0x1400b99bf  call    ?RefsCommonVolumeOpen@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@PEAU_CREATE_CONTEXT@@@Z; RefsCommonVolumeOpen(_IRP_CONTEXT *,_IRP *,_CREATE_CONTEXT *)
0x1400b99c4  mov     edi, eax
0x1400b99c6  mov     [rsp+138h+var_100], eax
0x1400b99ca  xor     r12d, r12d
0x1400b99cd  jmp     loc_1400B9C06
0x1400b99d2  call    ?RefsCommonCreate@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@PEAU_CREATE_CONTEXT@@@Z; RefsCommonCreate(_IRP_CONTEXT *,_IRP *,_CREATE_CONTEXT *)
0x1400b99d7  mov     edi, eax
0x1400b99d9  mov     [rsp+138h+var_100], eax
0x1400b99dd  xor     r12d, r12d
0x1400b99e0  jmp     loc_1400B9C06
0x1400b99e5  lea     rax, WPP_GLOBAL_Control; jumptable 00000001400B9917 case 2
0x1400b99ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b99f3  cmp     rcx, rax
0x1400b99f6  jz      short loc_1400B9A1A
0x1400b99f8  mov     eax, [rcx+2Ch]
0x1400b99fb  test    al, 1
0x1400b99fd  jz      short loc_1400B9A1A
0x1400b99ff  cmp     byte ptr [rcx+29h], 2
0x1400b9a03  jb      short loc_1400B9A1A
0x1400b9a05  mov     edx, 0Ah
0x1400b9a0a  lea     r8, WPP_1e930544d89f3ce82d53e09c7070df23_Traceguids
0x1400b9a11  mov     rcx, [rcx+18h]
0x1400b9a15  call    WPP_SF_
0x1400b9a1a  mov     [rsp+138h+Timeout], r12; BugCheckParameter4
0x1400b9a1f  xor     r9d, r9d; BugCheckParameter3
0x1400b9a22  xor     r8d, r8d; BugCheckParameter2
0x1400b9a25  mov     edx, 130184h; BugCheckParameter1
0x1400b9a2a  mov     ecx, 149h; BugCheckCode
0x1400b9a2f  call    cs:__imp_KeBugCheckEx
0x1400b9a3b  lea     rsi, [r14+320h]; jumptable 00000001400B9917 case 3
0x1400b9a42  mov     qword ptr [rsp+138h+Irp.IoStatus], rsi
0x1400b9a4a  mov     eax, [r14+8]
0x1400b9a4e  mov     rdx, rsi; struct REFS_IO_CONTEXT *
0x1400b9a51  mov     rcx, r14; struct _IRP_CONTEXT *
0x1400b9a54  bt      rax, 0Ch
0x1400b9a59  jnb     short loc_1400B9A68
0x1400b9a5b  mov     r8, rbx; struct _IRP *
0x1400b9a5e  call    ?RefsCommonIoCompletionWorker@@YAXPEAU_IRP_CONTEXT@@PEAUREFS_IO_CONTEXT@@PEAU_IRP@@@Z; RefsCommonIoCompletionWorker(_IRP_CONTEXT *,REFS_IO_CONTEXT *,_IRP *)
0x1400b9a63  jmp     loc_1400B9C06
0x1400b9a68  mov     r9d, [rbx+10h]
0x1400b9a6c  shr     r9d, 1
0x1400b9a6f  and     r9b, 1; bool
0x1400b9a73  call    ?RefsInitializeIoContext@@YAXPEAU_IRP_CONTEXT@@PEAUREFS_IO_CONTEXT@@_N2@Z; RefsInitializeIoContext(_IRP_CONTEXT *,REFS_IO_CONTEXT *,bool,bool)
0x1400b9a78  mov     r8, rbx; Irp
0x1400b9a7b  mov     rdx, rsi; struct REFS_IO_CONTEXT *
0x1400b9a7e  mov     rcx, r14; struct _IRP_CONTEXT *
0x1400b9a81  call    ?RefsCommonRead@@YAJPEAU_IRP_CONTEXT@@PEAUREFS_IO_CONTEXT@@PEAU_IRP@@@Z; RefsCommonRead(_IRP_CONTEXT *,REFS_IO_CONTEXT *,_IRP *)
0x1400b9a86  jmp     loc_1400B9C06
0x1400b9a8b  lea     rsi, [r14+320h]; jumptable 00000001400B9917 case 4
0x1400b9a92  mov     qword ptr [rsp+138h+Irp.IoStatus], rsi
0x1400b9a9a  mov     eax, [r14+8]
  ... truncated ...
```
