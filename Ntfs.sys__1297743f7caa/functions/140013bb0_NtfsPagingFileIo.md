# NtfsPagingFileIo

- ea: `0x140013bb0`
- end: `0x140014e6b`
- name: `NtfsPagingFileIo`
- size: `4795`
- prototype: `__int64 __fastcall(int, int)`
- caller_count: `3`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400130f0`
- `0x140015540`
- `0x140016850`

## callees

- `0x14000549c`
- `0x140005558`
- `0x140007670`
- `0x140007ea0`
- `0x1400082b0`
- `0x14001310c`
- `0x1400133cc`
- `0x140013bb0`
- `0x140014e74`
- `0x14003c2f0`
- `0x1400593e0`

## import_xrefs

- `ntoskrnl!IoGetStackLimits` at `0x140013fae`
- `ntoskrnl!IoGetStackLimits` at `0x140013fae`
- `ntoskrnl!MmBadPointer` at `0x140013f6f`
- `ntoskrnl!IoFreeIrp` at `0x14005a2bf`
- `ntoskrnl!IoFreeIrp` at `0x14005e321`
- `ntoskrnl!IoFreeIrp` at `0x14005a2bf`
- `ntoskrnl!IoFreeIrp` at `0x14005e321`
- `ntoskrnl!KeBugCheckEx` at `0x140014bf6`
- `ntoskrnl!KeBugCheckEx` at `0x14005e261`
- `ntoskrnl!KeBugCheckEx` at `0x140014bf6`
- `ntoskrnl!KeBugCheckEx` at `0x14005e261`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x1400141c9`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x1400141c9`
- `ntoskrnl!IofCompleteRequest` at `0x1400144a1`
- `ntoskrnl!IofCompleteRequest` at `0x140014bb1`
- `ntoskrnl!IofCompleteRequest` at `0x1400144a1`
- `ntoskrnl!IofCompleteRequest` at `0x140014bb1`
- `ntoskrnl!PsGetThreadProcess` at `0x140013cdf`
- `ntoskrnl!PsGetThreadProcess` at `0x140013cdf`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400144b2`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400144b2`
- `ntoskrnl!IoBuildPartialMdl` at `0x140014845`
- `ntoskrnl!IoBuildPartialMdl` at `0x140014ccd`
- `ntoskrnl!IoBuildPartialMdl` at `0x140014845`
- `ntoskrnl!IoBuildPartialMdl` at `0x140014ccd`
- `ntoskrnl!MmUnmapLockedPages` at `0x140014d66`
- `ntoskrnl!MmUnmapLockedPages` at `0x140014d66`
- `ntoskrnl!IoAllocateMdl` at `0x140014356`
- `ntoskrnl!IoAllocateMdl` at `0x140014818`
- `ntoskrnl!IoAllocateMdl` at `0x14001499f`
- `ntoskrnl!IoAllocateMdl` at `0x140014356`
- `ntoskrnl!IoAllocateMdl` at `0x140014818`
- `ntoskrnl!IoAllocateMdl` at `0x14001499f`
- `ntoskrnl!IoFreeMdl` at `0x140014c4a`
- `ntoskrnl!IoFreeMdl` at `0x140014e56`
- `ntoskrnl!IoFreeMdl` at `0x14005a2ed`
- `ntoskrnl!IoFreeMdl` at `0x140014c4a`
- `ntoskrnl!IoFreeMdl` at `0x140014e56`
- `ntoskrnl!IoFreeMdl` at `0x14005a2ed`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x140014cf3`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x140014cf3`
- `ntoskrnl!MmUnmapReservedMapping` at `0x140014d40`
- `ntoskrnl!MmUnmapReservedMapping` at `0x140014d40`
- `ntoskrnl!PsUpdateDiskCounters` at `0x140013d06`
- `ntoskrnl!PsUpdateDiskCounters` at `0x140013d06`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400149c0`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140014dda`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400149c0`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140014dda`
- `ntoskrnl!FsRtlUpdateDiskCounters` at `0x14001405e`
- `ntoskrnl!FsRtlUpdateDiskCounters` at `0x140014639`
- `ntoskrnl!FsRtlUpdateDiskCounters` at `0x14001405e`
- `ntoskrnl!FsRtlUpdateDiskCounters` at `0x140014639`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x140014b59`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x140014b59`
- `ntoskrnl!IoSetGenericIrpExtension` at `0x140013ec1`
- `ntoskrnl!IoSetGenericIrpExtension` at `0x1400148da`
- `ntoskrnl!IoSetGenericIrpExtension` at `0x140013ec1`
- `ntoskrnl!IoSetGenericIrpExtension` at `0x1400148da`
- `ntoskrnl!IoMakeAssociatedIrpEx` at `0x1400147a2`
- `ntoskrnl!IoMakeAssociatedIrpEx` at `0x1400147a2`
- `ntoskrnl!IofCallDriver` at `0x140013fde`
- `ntoskrnl!IofCallDriver` at `0x140013fde`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001445b`
- `ntoskrnl!KeWaitForSingleObject` at `0x140014afd`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001445b`
- `ntoskrnl!KeWaitForSingleObject` at `0x140014afd`
- `ntoskrnl!KeInitializeEvent` at `0x140014201`
- `ntoskrnl!KeInitializeEvent` at `0x140014201`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140014d79`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140014d79`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001437a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014b18`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014c5b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001437a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014b18`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014c5b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14001422c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14001422c`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140014ca7`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140014ca7`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140013ddc`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140013ded`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140013ddc`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140013ded`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001430f`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001430f`
- `ntoskrnl!IoGetRequestorProcessId` at `0x140013c7d`
- `ntoskrnl!IoGetRequestorProcessId` at `0x140013c7d`

## pseudocode

```c
void __fastcall NtfsPagingFileIo(IRP *a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v6; // esi
  __int64 v7; // r13
  __int64 v8; // r12
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  ULONG v10; // r14d
  unsigned __int64 CurrentProcessId; // rax
  struct _KTHREAD *CurrentThread; // r8
  unsigned __int8 v13; // cl
  unsigned int v14; // r14d
  unsigned int v15; // edx
  unsigned int v16; // edi
  PEPROCESS ThreadProcess; // rax
  __int64 v18; // rax
  ULONG_PTR v19; // rdi
  __int64 v20; // rcx
  struct _IO_STACK_LOCATION *v21; // rsi
  int v22; // r10d
  __int64 v23; // r8
  unsigned int v24; // edx
  LARGE_INTEGER v25; // rsi
  __int64 v26; // r9
  LARGE_INTEGER *v27; // rdi
  bool v28; // zf
  struct _IO_STACK_LOCATION *v29; // rcx
  char v30; // al
  struct _IO_STACK_LOCATION *v31; // rdi
  UCHAR MajorFunction; // r12
  int v33; // eax
  PVOID v34; // rdi
  struct _MDL *v35; // rsi
  struct _IO_STACK_LOCATION *v36; // rdx
  unsigned int v37; // edi
  __int64 StartVa_low; // rdx
  ULONG v39; // eax
  __int64 v40; // rcx
  PVOID PoolWithTag; // r10
  __int64 v42; // rdx
  PMDL v43; // rcx
  PVOID MappedSystemVa; // rcx
  struct _IO_STACK_LOCATION *v45; // rax
  struct _MDL *v46; // rax
  int v47; // ecx
  int v48; // r8d
  __int64 *v49; // rdx
  PVOID v50; // rdi
  struct _MDL *v51; // rdi
  __int64 v52; // r12
  struct _IO_STACK_LOCATION *v53; // rax
  struct _IO_STACK_LOCATION *v54; // rax
  int v55; // eax
  UCHAR v56; // di
  __int64 v57; // r8
  __int64 v58; // rax
  __int64 v59; // rdx
  __int64 v60; // rcx
  char v61; // al
  __int64 v62; // rdx
  int v63; // ecx
  __int64 v64; // rcx
  IRP *AssociatedIrp; // r9
  struct _LIST_ENTRY *v66; // rcx
  struct _MDL *v67; // rdx
  __int64 v68; // r10
  __int64 v69; // rdx
  __int64 v70; // rdx
  char v71; // r8
  __int64 v72; // r9
  __int64 v73; // rcx
  char v74; // al
  struct _MDL *v75; // rax
  int v76; // ecx
  int v77; // r8d
  __int64 *v78; // rdx
  NTSTATUS Status; // ecx
  NTSTATUS v80; // ecx
  __int64 v81; // rdx
  PVOID v82; // rax
  unsigned int v83; // edi
  ULONG v84; // esi
  IRP *v85; // rbx
  struct _MDL *v86; // rcx
  PVOID Context; // [rsp+20h] [rbp-158h]
  ULONG Length[2]; // [rsp+50h] [rbp-128h] BYREF
  __int128 v89; // [rsp+58h] [rbp-120h] BYREF
  PVOID VirtualAddress; // [rsp+68h] [rbp-110h]
  int v91; // [rsp+70h] [rbp-108h]
  LONG v92; // [rsp+74h] [rbp-104h]
  __int64 v93; // [rsp+78h] [rbp-100h] BYREF
  LARGE_INTEGER *v94; // [rsp+80h] [rbp-F8h]
  __int64 v95; // [rsp+88h] [rbp-F0h]
  __int64 v96; // [rsp+90h] [rbp-E8h] BYREF
  ULONG_PTR v97; // [rsp+98h] [rbp-E0h] BYREF
  PMDL MdlAddress; // [rsp+A0h] [rbp-D8h]
  __int64 v99; // [rsp+A8h] [rbp-D0h]
  struct _MDL Parameter; // [rsp+B0h] [rbp-C8h] BYREF
  __int64 v101; // [rsp+E0h] [rbp-98h]
  __int128 Event; // [rsp+E8h] [rbp-90h] BYREF
  __int128 Event_16; // [rsp+F8h] [rbp-80h]
  unsigned __int64 v104; // [rsp+108h] [rbp-70h]
  unsigned __int64 HighLimit; // [rsp+110h] [rbp-68h] BYREF
  __int64 v106; // [rsp+118h] [rbp-60h]
  __int64 v107; // [rsp+120h] [rbp-58h]
  __int64 v108; // [rsp+128h] [rbp-50h]
  __int64 v109; // [rsp+130h] [rbp-48h]
  ULONG_PTR v110; // [rsp+138h] [rbp-40h]
  unsigned __int64 LowLimit; // [rsp+180h] [rbp+8h] BYREF
  unsigned int v112; // [rsp+188h] [rbp+10h]
  PMDL Mdl; // [rsp+190h] [rbp+18h] BYREF
  __int64 QuadPart; // [rsp+198h] [rbp+20h] BYREF

  v6 = 0;
  QuadPart = 0;
  v97 = 0;
  v93 = 0;
  v96 = 0;
  v7 = *(_QWORD *)(a2 + 192);
  MdlAddress = a1->MdlAddress;
  v89 = 0;
  v8 = 0;
  v95 = 0;
  Event = 0;
  Event_16 = 0;
  v104 = 0;
  *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v7 + 248) + 16LL) + 48LL) &= ~2u;
  CurrentStackLocation = a1->Tail.Overlay.CurrentStackLocation;
  QuadPart = CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart;
  v10 = CurrentStackLocation->Parameters.Read.Length;
  v112 = v10;
  if ( !v10 )
  {
    CurrentStackLocation->Control |= 1u;
    LOBYTE(a4) = a1 != 0;
    NtfsExtendedCompleteRequestInternal(0, a1, 0, a4, 1);
    return;
  }
  if ( a1->CurrentLocation > a1->StackCount
    || (CurrentStackLocation->Control & 1) != 0
    || (LODWORD(CurrentProcessId) = IoGetRequestorProcessId(a1), !(_DWORD)CurrentProcessId) )
  {
    CurrentProcessId = (unsigned __int64)PsGetCurrentProcessId();
  }
  else
  {
    CurrentProcessId = (unsigned int)CurrentProcessId;
  }
  v104 = CurrentProcessId;
  if ( NtfsDiskAccountingEnabled )
  {
    CurrentThread = KeGetCurrentThread();
    if ( CurrentStackLocation->MajorFunction == 4 )
    {
      v13 = 1;
      LODWORD(LowLimit) = 1;
    }
    else
    {
      v13 = 0;
      LODWORD(LowLimit) = 0;
    }
    v14 = v13 ^ 1;
    v15 = v112;
    if ( v13 )
    {
      v6 = v112;
      v15 = 0;
    }
    v16 = v15;
    ThreadProcess = PsGetThreadProcess(CurrentThread);
    PsUpdateDiskCounters(ThreadProcess, v16, v6, v14, LowLimit, 0);
    v10 = v112;
  }
  v18 = *(unsigned int *)(v7 + 480);
  v112 = QuadPart & *(_DWORD *)(v7 + 480);
  LODWORD(Mdl) = *(char *)(v7 + 488);
  v109 = v10;
  v99 = QuadPart + v10 + v18;
  v19 = QuadPart >> (char)Mdl;
  v108 = QuadPart >> (char)Mdl;
  if ( !(unsigned __int8)NtfsLookupNtfsMcbEntryWithSyncFlag(a2 + 400, QuadPart >> (char)Mdl, &v96, &v93, 0, 0, 0, 0) )
  {
    if ( (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x800) != 0 )
      McTemplateU0_EtwWriteTransfer(v20, deviosup_c2543);
    KeBugCheckEx(0x24u, 0xAF000C09F6uLL, v19, *(_QWORD *)(a2 + 24), *(_QWORD *)(a2 + 32));
  }
  VirtualAddress = 0;
  v107 = v96 << *(_BYTE *)(v7 + 488);
  a1->IoStatus.Status = 0;
  a1->IoStatus.Information = v10;
  v21 = a1->Tail.Overlay.CurrentStackLocation;
  v94 = (LARGE_INTEGER *)v21;
  if ( IoGetTopLevelIrp() )
  {
    if ( *(_QWORD *)&IoGetTopLevelIrp()->Flags )
      v8 = 2;
    v95 = v8;
  }
  if ( *(_QWORD *)(a2 + 504) )
  {
    if ( *(int *)(a2 + 200) >= 0 )
    {
      KeInitializeEvent((PRKEVENT)&Event, SynchronizationEvent, 0);
      DWORD2(Event_16) = v8;
      if ( v21->MajorFunction == 4 )
      {
        PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)512, v10, 0x4446744Eu);
        VirtualAddress = PoolWithTag;
        if ( !PoolWithTag )
        {
LABEL_77:
          LODWORD(Context) = v10;
          NtfsPagingFileIoWithNoAllocation((int)a1, a2, (SIZE_T)Context);
          return;
        }
        v42 = QuadPart;
        *(_QWORD *)Length = QuadPart;
        memset(&Parameter, 0, sizeof(Parameter));
        v101 = 0;
        v43 = a1->MdlAddress;
        if ( v43 )
        {
          if ( (v43->MdlFlags & 5) != 0 )
          {
            MappedSystemVa = v43->MappedSystemVa;
          }
          else
          {
            MappedSystemVa = MmMapLockedPagesSpecifyCache(v43, 0, MmCached, 0, 0, 0x40000020u);
            v42 = *(_QWORD *)Length;
            PoolWithTag = VirtualAddress;
          }
        }
        else
        {
          MappedSystemVa = a1->UserBuffer;
        }
        if ( MappedSystemVa )
        {
          (*((void (__fastcall **)(PVOID, PVOID, ULONG *, _QWORD, _QWORD))&xmmword_140095740 + 1))(
            MappedSystemVa,
            PoolWithTag,
            Length,
            v10,
            *(_QWORD *)(a2 + 504));
        }
        else
        {
          LODWORD(LowLimit) = 0;
          *(_QWORD *)Length = v42;
          Parameter.Next = 0;
          *(_DWORD *)&Parameter.Size = 56;
          Parameter.StartVa = 0;
          *(_QWORD *)&Parameter.ByteCount = 4096;
          v84 = 4096 - v42 % 4096;
          if ( v10 < v84 )
            v84 = v10;
          if ( v10 )
          {
            v83 = LowLimit;
            do
            {
              KeAcquireGuardedMutex((PKGUARDED_MUTEX)(v7 + 5688));
              IoBuildPartialMdl(
                a1->MdlAddress,
                &Parameter,
                (char *)a1->MdlAddress->StartVa + v83 + a1->MdlAddress->ByteOffset,
                v84);
              v82 = MmMapLockedPagesWithReservedMapping(*(PVOID *)(v7 + 5680), 0x6266744Eu, &Parameter, MmCached);
              (*((void (__fastcall **)(PVOID, char *, ULONG *, _QWORD, _QWORD))&xmmword_140095740 + 1))(
                v82,
                (char *)VirtualAddress + v83,
                Length,
                v84,
                *(_QWORD *)(a2 + 504));
              MmUnmapReservedMapping(*(PVOID *)(v7 + 5680), 0x6266744Eu, &Parameter);
              if ( (Parameter.MdlFlags & 0x20) != 0 )
                MmUnmapLockedPages(Parameter.MappedSystemVa, &Parameter);
              KeReleaseGuardedMutex((PKGUARDED_MUTEX)(v7 + 5688));
              v83 += v84;
              *(_QWORD *)Length += v84;
              v84 = 4096;
              if ( v10 < 0x1000 )
                v84 = v10;
            }
            while ( v83 < v10 );
            v8 = v95;
            v19 = v108;
          }
        }
      }
    }
  }
  v22 = 0;
  LODWORD(LowLimit) = 0;
  v23 = v99 >> (char)Mdl;
  v99 = v23;
  v24 = v112;
  v25.QuadPart = v107 + v112;
  v26 = v93;
  if ( (__int64)(v19 + v93) >= v23 )
  {
    Mdl = 0;
    v27 = v94;
    if ( *(_QWORD *)(a2 + 504) && LOBYTE(v94->LowPart) == 4 && *(int *)(a2 + 200) >= 0 )
    {
      v46 = IoAllocateMdl(VirtualAddress, v10, 0, 0, 0);
      Mdl = v46;
      if ( !v46 )
      {
        ExFreePoolWithTag(VirtualAddress, 0);
        goto LABEL_77;
      }
      MmBuildMdlForNonPagedPool(v46);
      a1->MdlAddress = Mdl;
    }
    v27[3] = v25;
    v27[2].LowPart = QuadPart;
    if ( *(_QWORD *)(a2 + 504) && *(int *)(a2 + 200) >= 0 )
    {
      v45 = a1->Tail.Overlay.CurrentStackLocation;
      v45[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&NtfsSyncPagingFileCompletionRoutine;
      v45[-1].Context = &Event;
      v45[-1].Control = -32;
    }
    else
    {
      LODWORD(LowLimit) = v104;
      if ( (int)IoSetGenericIrpExtension(a1, &LowLimit, 4, 0) >= 0 )
        v8 |= 4uLL;
      v28 = (*(_DWORD *)(v7 + 4) & 0x40) == 0;
      v29 = a1->Tail.Overlay.CurrentStackLocation;
      v29[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)NtfsPagingFileCompletionRoutine;
      v29[-1].Context = (PVOID)v8;
      v30 = 0;
      if ( v28 )
        v30 = 64;
      v29[-1].Control = v30 | 0xA0;
    }
    v31 = a1->Tail.Overlay.CurrentStackLocation;
    v31[-1].Flags |= 2u;
    v31[-1].MajorFunction = a1->Tail.Overlay.CurrentStackLocation->MajorFunction;
    v31[-1].Parameters.Read.Length = v10;
    v31[-1].Parameters.Read.ByteOffset = v25;
    MajorFunction = v31[-1].MajorFunction;
    v33 = *(_DWORD *)(a2 + 200);
    if ( v33 < 0
      && *(_DWORD *)(a2 + 256) == 128
      && *(_QWORD *)(a2 + 504)
      && ((v33 & 0x6000000) == 0
       || (v33 & 0x2000000) != 0 && *(_QWORD *)(a2 + 632) > QuadPart
       || (v33 & 0x4000000) != 0 && *(_QWORD *)(a2 + 632) <= QuadPart)
      && xmmword_140095760 )
    {
      xmmword_140095760(&QuadPart, *(unsigned int *)(*(_QWORD *)(*(_QWORD *)(a2 + 184) + 96LL) + 364LL));
      if ( v31[-1].MajorFunction == 4 )
      {
        if ( (Microsoft_Windows_NtfsEnableBits & 0x40000000) == 0 )
          goto LABEL_27;
        v49 = EFS_OFFLOADING_WRITE_FILE;
      }
      else
      {
        if ( (Microsoft_Windows_NtfsEnableBits & 0x40000000) == 0 )
          goto LABEL_27;
        v49 = EFS_OFFLOADING_READ_FILE;
      }
      McTemplateK0ixqzr2_EtwWriteTransfer(
        v47,
        (_DWORD)v49,
        v48,
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 184) + 96LL) + 440LL),
        *(_QWORD *)(*(_QWORD *)(a2 + 184) + 8LL));
    }
LABEL_27:
    a1->Tail.Overlay.CurrentStackLocation->Control |= 1u;
    v34 = NtfsReserveStackStorage;
    v35 = *(struct _MDL **)(v7 + 224);
    memset(&Parameter, 0, 40);
    if ( (PVOID)a2 != MmBadPointer )
    {
      v36 = a1->Tail.Overlay.CurrentStackLocation;
      if ( v36[-1].MajorFunction == 4
        && (*(_DWORD *)(v7 + 24) & 0x40000) != 0
        && (*(_DWORD *)(*(_QWORD *)(a2 + 184) + 4LL) & 0x100) == 0 )
      {
        v36[-1].Flags |= 0x20u;
      }
    }
    HighLimit = 0;
    LowLimit = 0;
    IoGetStackLimits(&LowLimit, &HighLimit);
    if ( (unsigned __int64)&HighLimit - LowLimit <= 0x4800 )
    {
      Parameter.Next = v35;
      *(_QWORD *)&Parameter.Size = a1;
      v37 = KeExpandKernelStackAndCalloutEx(NtfsStorageDriverCallout, &Parameter, 0x6000u, 0, v34);
      StartVa_low = LODWORD(Parameter.StartVa);
    }
    else
    {
      v37 = 0;
      StartVa_low = (unsigned int)IofCallDriver((PDEVICE_OBJECT)v35, a1);
    }
    if ( ((_DWORD)StartVa_low == -1073741566 || (_DWORD)StartVa_low == -1073741774 || (_DWORD)StartVa_low == -1073741741)
      && NtfsStatusDebugFlags
      && (unsigned int)(StartVa_low - 298) > 1
      && (unsigned int)(StartVa_low + 2147483643) > 1 )
    {
      NtfsStatusTraceAndDebugInternal(0, StartVa_low, 809644);
    }
    if ( NtfsStatusDebugFlags
      && v37
      && v37 != 294
      && v37 - 298 > 1
      && v37 < 0xFFFFFFED
      && v37 != -1073741608
      && v37 != -1073741802
      && v37 != -1073741807
      && v37 + 2147483643 > 1
      && v37 != 259 )
    {
      NtfsStatusTraceAndDebugInternal(0, v37, 809686);
    }
    if ( NtfsDiskAccountingEnabled )
    {
      v39 = 0;
      if ( MajorFunction == 4 )
        v39 = v10;
      v40 = v10;
      if ( MajorFunction == 4 )
        v40 = 0;
      FsRtlUpdateDiskCounters(v40, v39);
    }
    if ( *(_QWORD *)(a2 + 504) && *(int *)(a2 + 200) >= 0 )
    {
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      v50 = VirtualAddress;
      if ( VirtualAddress )
      {
        IoFreeMdl(Mdl);
        ExFreePoolWithTag(v50, 0);
        v51 = MdlAddress;
      }
      else
      {
        v51 = MdlAddress;
        NtfsDecryptPagingFileBuffer(v7, a2, MdlAddress, QuadPart, v10);
      }
      a1->MdlAddress = v51;
      IofCompleteRequest(a1, 1);
    }
    return;
  }
  LODWORD(Mdl) = v104;
  *((_QWORD *)&v89 + 1) = &v89;
  *(_QWORD *)&v89 = &v89;
  v92 = 0;
  v52 = v8 | 1;
  v107 = v52;
  if ( !*(_QWORD *)(a2 + 504) || *(int *)(a2 + 200) < 0 )
    goto LABEL_115;
  a1->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  v53 = a1->Tail.Overlay.CurrentStackLocation;
  *(_OWORD *)&v53[-1].MajorFunction = *(_OWORD *)&v53->MajorFunction;
  *(_OWORD *)&v53[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v53->Parameters.NotifyDirectoryEx.CompletionFilter;
  *(_OWORD *)(&v53[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v53->Parameters.SetQuota + 6);
  v53[-1].FileObject = v53->FileObject;
  v53[-1].Control = 0;
  v54 = a1->Tail.Overlay.CurrentStackLocation;
  v54[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&NtfsSimpleCompletionRoutine;
  v54[-1].Context = &Event;
  v54[-1].Control = 0;
  v54[-1].Control = 64;
  v54[-1].Control = -64;
  v54[-1].Control = -32;
  --a1->CurrentLocation;
  --a1->Tail.Overlay.CurrentStackLocation;
  while ( 1 )
  {
    v26 = v93;
LABEL_115:
    v106 = v52;
    if ( (__int64)(v19 + v26) >= v23 )
      *(_QWORD *)Length = v10 - v22;
    else
      *(_QWORD *)Length = ((_DWORD)v26 << *(_DWORD *)(v7 + 488)) - v24;
    AssociatedIrp = (IRP *)IoMakeAssociatedIrpEx(
                             a1,
                             a1->Tail.Overlay.CurrentStackLocation->DeviceObject,
                             (unsigned __int8)(*(_BYTE *)(*(_QWORD *)(v7 + 224) + 76LL) + 1));
    v95 = (__int64)AssociatedIrp;
    if ( !AssociatedIrp )
    {
      v55 = 0;
      v91 = 0;
      goto LABEL_95;
    }
    v66 = (struct _LIST_ENTRY *)*((_QWORD *)&v89 + 1);
    if ( **((__int128 ***)&v89 + 1) != &v89 )
LABEL_166:
      __fastfail(3u);
    AssociatedIrp->Tail.Overlay.ListEntry.Flink = (struct _LIST_ENTRY *)&v89;
    AssociatedIrp->Tail.Overlay.ListEntry.Blink = v66;
    v66->Flink = &AssociatedIrp->Tail.Overlay.ListEntry;
    *((_QWORD *)&v89 + 1) = &AssociatedIrp->Tail.Overlay.ListEntry;
    if ( !*(_QWORD *)(a2 + 504) || LOBYTE(v94->LowPart) != 4 || *(int *)(a2 + 200) < 0 )
      break;
    v75 = IoAllocateMdl((char *)VirtualAddress + (unsigned int)LowLimit, Length[0], 0, 0, AssociatedIrp);
    if ( !v75 )
    {
      v55 = 0;
      v91 = 0;
      goto LABEL_95;
    }
    MmBuildMdlForNonPagedPool(v75);
LABEL_122:
    v97 = v19 << *(_BYTE *)(v7 + 488);
    ++v92;
    v68 = v95;
    --*(_BYTE *)(v95 + 67);
    *(_QWORD *)(v68 + 184) -= 72LL;
    v69 = *(_QWORD *)(v68 + 184);
    *(_BYTE *)v69 = a1->Tail.Overlay.CurrentStackLocation->MajorFunction;
    *(_QWORD *)(v69 + 48) = a1->Tail.Overlay.CurrentStackLocation->FileObject;
    *(_QWORD *)(v69 + 40) = a1->Tail.Overlay.CurrentStackLocation->DeviceObject;
    *(_DWORD *)(v69 + 8) = Length[0];
    *(LARGE_INTEGER *)(v69 + 24) = v25;
    *(_DWORD *)(v69 + 16) = v97;
    if ( (int)IoSetGenericIrpExtension(v68, &Mdl, 4, 0) < 0 )
    {
      v70 = v106;
    }
    else
    {
      v70 = v52 | 4;
      v106 = v52 | 4;
    }
    if ( (*(_DWORD *)(v7 + 4) & 0x40) != 0 )
    {
      v112 = 0;
      v71 = 0;
    }
    else
    {
      v112 = 1;
      v71 = 1;
    }
    v72 = v95;
    v73 = *(_QWORD *)(v95 + 184);
    *(_QWORD *)(v73 - 16) = NtfsPagingFileCompletionRoutine;
    *(_QWORD *)(v73 - 8) = v70;
    *(_BYTE *)(v73 - 69) = 0;
    v74 = 0;
    if ( v71 )
    {
      *(_BYTE *)(v73 - 69) = 64;
      v74 = 64;
    }
    v61 = v74 | 0x80;
    *(_BYTE *)(v73 - 69) = v61;
    *(_BYTE *)(v73 - 69) = v61 | 0x20;
    v62 = *(_QWORD *)(v72 + 184) - 72LL;
    v94 = (LARGE_INTEGER *)v62;
    *(_BYTE *)v62 = a1->Tail.Overlay.CurrentStackLocation->MajorFunction;
    *(_DWORD *)(v62 + 8) = Length[0];
    *(LARGE_INTEGER *)(v62 + 24) = v25;
    *(_BYTE *)(v62 + 2) |= 2u;
    v63 = *(_DWORD *)(a2 + 200);
    if ( v63 < 0
      && *(_DWORD *)(a2 + 256) == 128
      && *(_QWORD *)(a2 + 504)
      && ((v63 & 0x6000000) == 0
       || (v63 & 0x2000000) != 0 && *(_QWORD *)(a2 + 632) > QuadPart
       || (v63 & 0x4000000) != 0 && *(_QWORD *)(a2 + 632) <= QuadPart)
      && xmmword_140095760 )
    {
      xmmword_140095760(&v97, *(unsigned int *)(*(_QWORD *)(*(_QWORD *)(a2 + 184) + 96LL) + 364LL));
      if ( LOBYTE(v94->LowPart) == 4 )
      {
        if ( (Microsoft_Windows_NtfsEnableBits & 0x40000000) == 0 )
          goto LABEL_111;
        v78 = EFS_OFFLOADING_WRITE_FILE;
      }
      else
      {
        if ( (Microsoft_Windows_NtfsEnableBits & 0x40000000) == 0 )
          goto LABEL_111;
        v78 = EFS_OFFLOADING_READ_FILE;
      }
      McTemplateK0ixqzr2_EtwWriteTransfer(
        v76,
        (_DWORD)v78,
        v77,
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 184) + 96LL) + 440LL),
        *(_QWORD *)(*(_QWORD *)(a2 + 184) + 8LL));
    }
LABEL_111:
    v55 = Length[0] + LowLimit;
    LODWORD(LowLimit) = v55;
    v91 = v55;
    v112 = 0;
    v19 += v93;
    v110 = v19;
    if ( v55 == v10 )
      goto LABEL_95;
    if ( !(unsigned __int8)NtfsLookupNtfsMcbEntryWithSyncFlag(a2 + 400, v19, &v96, &v93, 0, 0, 0, 0) )
    {
      if ( (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x800) != 0 )
        McTemplateU0_EtwWriteTransfer(v64, deviosup_c3099);
      KeBugCheckEx(0x24u, 0xB0000C0C22uLL, v19, *(_QWORD *)(a2 + 24), *(_QWORD *)(a2 + 32));
    }
    v25.QuadPart = v96 << *(_BYTE *)(v7 + 488);
    v24 = v112;
    v23 = v99;
    v22 = LowLimit;
  }
  v67 = IoAllocateMdl((char *)a1->UserBuffer + (unsigned int)LowLimit, Length[0], 0, 0, AssociatedIrp);
  if ( v67 )
  {
    IoBuildPartialMdl(a1->MdlAddress, v67, (char *)a1->UserBuffer + (unsigned int)LowLimit, Length[0]);
    goto LABEL_122;
  }
  v55 = 0;
  v91 = 0;
LABEL_95:
  if ( v55 == v10 )
  {
    a1->Tail.Overlay.CurrentStackLocation->Control |= 1u;
    a1->AssociatedIrp.IrpCount = v92;
    v56 = a1->Tail.Overlay.CurrentStackLocation->MajorFunction;
    while ( 1 )
    {
      v57 = v89;
      if ( (__int128 *)v89 == &v89 )
        break;
      if ( *(__int128 **)(v89 + 8) != &v89 )
        goto LABEL_166;
      v58 = *(_QWORD *)v89;
      if ( *(_QWORD *)(*(_QWORD *)v89 + 8LL) != (_QWORD)v89 )
        goto LABEL_166;
      *(_QWORD *)&v89 = *(_QWORD *)v89;
      *(_QWORD *)(v58 + 8) = &v89;
      NtfsCallStorageDriver(0, *(_QWORD *)(v7 + 224), v57 - 168, v7, a2, NtfsReserveStackStorage, 0);
    }
    if ( NtfsDiskAccountingEnabled )
    {
      v59 = 0;
      if ( v56 == 4 )
        v59 = v10;
      v60 = v10;
      if ( v56 == 4 )
        v60 = 0;
      FsRtlUpdateDiskCounters(v60, v59);
    }
    if ( *(_QWORD *)(a2 + 504) && *(int *)(a2 + 200) >= 0 )
    {
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      if ( VirtualAddress )
        ExFreePoolWithTag(VirtualAddress, 0);
      else
        NtfsDecryptPagingFileBuffer(v7, a2, MdlAddress, QuadPart, v10);
      Status = a1->IoStatus.Status;
      if ( (Status <= -1 || (unsigned int)(Status - 1073741834) <= 1) && !FsRtlIsTotalDeviceFailure(Status) )
      {
        v80 = a1->IoStatus.Status;
        if ( v80 != -2147483626 && v80 != -1073741608 && a1->CurrentLocation <= a1->StackCount )
          NtfsIoFailurePostFileObjectError(v7, (_DWORD)a1, v104, 0, v109, v80);
      }
      IofCompleteRequest(a1, 1);
    }
  }
  else
  {
    LODWORD(Context) = v10;
    NtfsPagingFileIoWithNoAllocation((int)a1, a2, (SIZE_T)Context);
  }
  while ( (__int128 *)v89 != &v89 )
  {
    if ( *(__int128 **)(v89 + 8) != &v89 || (v81 = *(_QWORD *)v89, *(_QWORD *)(*(_QWORD *)v89 + 8LL) != (_QWORD)v89) )
      __fastfail(3u);
    v85 = (IRP *)(v89 - 168);
    *(_QWORD *)&v89 = *(_QWORD *)v89;
    *(_QWORD *)(v81 + 8) = &v89;
    v86 = v85->MdlAddress;
    if ( v86 )
    {
      IoFreeMdl(v86);
      v85->MdlAddress = 0;
    }
    IoFreeIrp(v85);
  }
}

```

## disassembly

```asm
0x140013bb0  mov     r11, rsp
0x140013bb3  push    rbx
0x140013bb4  push    rsi
0x140013bb5  push    rdi
0x140013bb6  push    r12
0x140013bb8  push    r13
0x140013bba  push    r14
0x140013bbc  push    r15
0x140013bbe  sub     rsp, 140h
0x140013bc5  mov     r15, rdx
0x140013bc8  mov     rbx, rcx
0x140013bcb  xor     esi, esi
0x140013bcd  mov     [r11+20h], rsi
0x140013bd1  mov     [r11-0E0h], rsi
0x140013bd8  mov     [rsp+178h+var_100], rsi
0x140013bdd  mov     [r11-0E8h], rsi
0x140013be4  mov     r13, [rdx+0C0h]
0x140013beb  mov     rax, [rcx+8]
0x140013bef  mov     [rsp+178h+var_D8], rax
0x140013bf7  xorps   xmm0, xmm0
0x140013bfa  movups  [rsp+178h+var_120], xmm0
0x140013bff  mov     r12d, esi
0x140013c02  mov     [rsp+178h+var_F0], rsi
0x140013c0a  xorps   xmm1, xmm1
0x140013c0d  xor     eax, eax
0x140013c0f  movups  xmmword ptr [rsp+178h+Event.Header], xmm1
0x140013c17  movups  xmmword ptr [r11-80h], xmm1
0x140013c1c  mov     [r11-70h], rax
0x140013c20  mov     rax, [r13+0F8h]
0x140013c27  mov     rcx, [rax+10h]
0x140013c2b  mov     edx, [rcx+30h]
0x140013c2e  and     edx, 0FFFFFFFDh
0x140013c31  mov     rax, [r13+0F8h]
0x140013c38  mov     rcx, [rax+10h]
0x140013c3c  mov     [rcx+30h], edx
0x140013c3f  mov     rdi, [rbx+0B8h]
0x140013c46  mov     rax, [rdi+18h]
0x140013c4a  mov     [r11+20h], rax
0x140013c4e  mov     r14d, [rdi+8]
0x140013c52  mov     [rsp+178h+arg_8], r14d
0x140013c5a  test    r14d, r14d
0x140013c5d  jz      loc_140014C74
0x140013c63  movzx   eax, byte ptr [rbx+42h]
0x140013c67  cmp     [rbx+43h], al
0x140013c6a  jg      loc_1400144B2
0x140013c70  test    byte ptr [rdi+3], 1
0x140013c74  jnz     loc_1400144B2
0x140013c7a  mov     rcx, rbx; Irp
0x140013c7d  call    cs:__imp_IoGetRequestorProcessId
0x140013c84  nop     dword ptr [rax+rax+00h]
0x140013c89  test    eax, eax
0x140013c8b  jz      loc_1400144B2
0x140013c91  mov     eax, eax
0x140013c93  mov     [rsp+178h+var_70], rax
0x140013c9b  cmp     cs:NtfsDiskAccountingEnabled, sil
0x140013ca2  jz      short loc_140013D1A
0x140013ca4  mov     r8, gs:188h
0x140013cad  cmp     byte ptr [rdi], 4
0x140013cb0  jz      loc_14001415F
0x140013cb6  xor     cl, cl
0x140013cb8  mov     dword ptr [rsp+178h+LowLimit], esi
0x140013cbf  movzx   r14d, cl
0x140013cc3  xor     r14d, 1
0x140013cc7  test    cl, cl
0x140013cc9  mov     edx, [rsp+178h+arg_8]
0x140013cd0  cmovnz  esi, edx
0x140013cd3  xor     eax, eax
0x140013cd5  test    cl, cl
0x140013cd7  cmovnz  edx, eax
0x140013cda  mov     edi, edx
0x140013cdc  mov     rcx, r8; Thread
0x140013cdf  call    cs:__imp_PsGetThreadProcess
0x140013ce6  nop     dword ptr [rax+rax+00h]
0x140013ceb  mov     rcx, rax
0x140013cee  mov     [rsp+178h+Priority], r12d
0x140013cf3  mov     eax, dword ptr [rsp+178h+LowLimit]
0x140013cfa  mov     dword ptr [rsp+178h+Context], eax
0x140013cfe  mov     r9d, r14d
0x140013d01  mov     r8d, esi
0x140013d04  mov     edx, edi
0x140013d06  call    cs:__imp_PsUpdateDiskCounters
0x140013d0d  nop     dword ptr [rax+rax+00h]
0x140013d12  mov     r14d, [rsp+178h+arg_8]
0x140013d1a  mov     eax, [r13+1E0h]
0x140013d21  mov     ecx, eax
0x140013d23  mov     rdi, [rsp+178h+arg_18]
0x140013d2b  and     ecx, edi
0x140013d2d  mov     [rsp+178h+arg_8], ecx
0x140013d34  movsx   edx, byte ptr [r13+1E8h]
0x140013d3c  mov     dword ptr [rsp+178h+Mdl], edx
0x140013d43  mov     esi, r14d
0x140013d46  mov     [rsp+178h+var_48], rsi
0x140013d4e  lea     rcx, [rsi+rax]
0x140013d52  add     rcx, rdi
0x140013d55  mov     [rsp+178h+var_D0], rcx
0x140013d5d  mov     ecx, edx
0x140013d5f  sar     rdi, cl
0x140013d62  mov     [rsp+178h+var_50], rdi
0x140013d6a  xor     ecx, ecx
0x140013d6c  mov     [rsp+178h+var_140], rcx
0x140013d71  mov     [rsp+178h+var_148], rcx
0x140013d76  mov     qword ptr [rsp+178h+Priority], rcx
0x140013d7b  mov     [rsp+178h+Context], rcx
0x140013d80  lea     r9, [rsp+178h+var_100]
0x140013d85  lea     r8, [rsp+178h+var_E8]
0x140013d8d  mov     rdx, rdi
0x140013d90  lea     rcx, [r15+190h]
0x140013d97  call    NtfsLookupNtfsMcbEntryWithSyncFlag
0x140013d9c  test    al, al
0x140013d9e  jz      loc_140014DB8
0x140013da4  xor     edx, edx
0x140013da6  mov     [rsp+178h+VirtualAddress], rdx
0x140013dab  movzx   ecx, byte ptr [r13+1E8h]
0x140013db3  mov     rax, [rsp+178h+var_E8]
0x140013dbb  shl     rax, cl
0x140013dbe  mov     [rsp+178h+var_58], rax
0x140013dc6  mov     [rbx+30h], edx
0x140013dc9  mov     [rbx+38h], rsi
0x140013dcd  mov     rsi, [rbx+0B8h]
0x140013dd4  mov     [rsp+178h+var_F8], rsi
0x140013ddc  call    cs:__imp_IoGetTopLevelIrp
0x140013de3  nop     dword ptr [rax+rax+00h]
0x140013de8  test    rax, rax
0x140013deb  jz      short loc_140013E0E
0x140013ded  call    cs:__imp_IoGetTopLevelIrp
0x140013df4  nop     dword ptr [rax+rax+00h]
0x140013df9  mov     ecx, 2
0x140013dfe  cmp     [rax+10h], r12
0x140013e02  cmovnz  r12, rcx
0x140013e06  mov     [rsp+178h+var_F0], r12
0x140013e0e  cmp     qword ptr [r15+1F8h], 0
0x140013e16  jnz     loc_1400141E3
0x140013e1c  xor     r10d, r10d
0x140013e1f  mov     dword ptr [rsp+178h+LowLimit], r10d
0x140013e27  mov     ecx, dword ptr [rsp+178h+Mdl]
0x140013e2e  mov     r8, [rsp+178h+var_D0]
0x140013e36  sar     r8, cl
0x140013e39  mov     [rsp+178h+var_D0], r8
0x140013e41  mov     edx, [rsp+178h+arg_8]
0x140013e48  mov     esi, edx
0x140013e4a  add     rsi, [rsp+178h+var_58]
0x140013e52  mov     r9, [rsp+178h+var_100]
0x140013e57  lea     rax, [rdi+r9]
0x140013e5b  cmp     rax, r8
0x140013e5e  jl      loc_1400144C3
0x140013e64  xor     eax, eax
0x140013e66  mov     [rsp+178h+Mdl], rax
0x140013e6e  mov     rdi, [rsp+178h+var_F8]
0x140013e76  cmp     [r15+1F8h], rax
0x140013e7d  jnz     loc_14001432D
0x140013e83  mov     [rdi+18h], rsi
0x140013e87  mov     eax, dword ptr [rsp+178h+arg_18]
0x140013e8e  mov     [rdi+10h], eax
0x140013e91  cmp     qword ptr [r15+1F8h], 0
0x140013e99  jnz     loc_1400142C3
0x140013e9f  mov     eax, dword ptr [rsp+178h+var_70]
0x140013ea6  mov     dword ptr [rsp+178h+LowLimit], eax
0x140013ead  mov     r8d, 4
0x140013eb3  xor     r9d, r9d
0x140013eb6  lea     rdx, [rsp+178h+LowLimit]
0x140013ebe  mov     rcx, rbx
0x140013ec1  call    cs:__imp_IoSetGenericIrpExtension
0x140013ec8  nop     dword ptr [rax+rax+00h]
0x140013ecd  test    eax, eax
0x140013ecf  js      short loc_140013ED5
0x140013ed1  or      r12, 4
0x140013ed5  test    dword ptr [r13+4], 40h
0x140013edd  mov     rcx, [rbx+0B8h]
0x140013ee4  lea     rax, NtfsPagingFileCompletionRoutine
0x140013eeb  mov     [rcx-10h], rax
0x140013eef  mov     [rcx-8], r12
0x140013ef3  mov     al, 0
0x140013ef5  movzx   eax, al
0x140013ef8  mov     edx, 40h ; '@'
0x140013efd  cmovz   eax, edx
0x140013f00  or      al, 0A0h
0x140013f02  mov     [rcx-45h], al
0x140013f05  mov     rdi, [rbx+0B8h]
0x140013f0c  or      byte ptr [rdi-46h], 2
0x140013f10  mov     rax, [rbx+0B8h]
0x140013f17  movzx   ecx, byte ptr [rax]
0x140013f1a  mov     [rdi-48h], cl
0x140013f1d  mov     [rdi-40h], r14d
0x140013f21  mov     [rdi-30h], rsi
0x140013f25  movzx   r12d, byte ptr [rdi-48h]
0x140013f2a  mov     eax, [r15+0C8h]
0x140013f31  test    eax, eax
0x140013f33  js      loc_1400143AB
0x140013f39  mov     rax, [rbx+0B8h]
0x140013f40  or      byte ptr [rax+3], 1
0x140013f44  mov     rdi, cs:NtfsReserveStackStorage
0x140013f4b  mov     rsi, [r13+0E0h]
0x140013f52  xorps   xmm0, xmm0
0x140013f55  xor     eax, eax
0x140013f57  movups  [rsp+178h+Parameter], xmm0
0x140013f5f  movups  xmmword ptr [rsp+178h+BaseAddress], xmm0
0x140013f67  mov     qword ptr [rsp+178h+var_A8], rax
0x140013f6f  mov     rax, cs:MmBadPointer
0x140013f76  cmp     r15, [rax]
0x140013f79  jz      short loc_140013F8C
0x140013f7b  mov     rdx, [rbx+0B8h]
0x140013f82  cmp     byte ptr [rdx-48h], 4
0x140013f86  jz      loc_140014171
0x140013f8c  xor     eax, eax
0x140013f8e  mov     [rsp+178h+HighLimit], rax
0x140013f96  mov     [rsp+178h+LowLimit], rax
0x140013f9e  lea     rdx, [rsp+178h+HighLimit]; HighLimit
0x140013fa6  lea     rcx, [rsp+178h+LowLimit]; LowLimit
0x140013fae  call    cs:__imp_IoGetStackLimits
0x140013fb5  nop     dword ptr [rax+rax+00h]
0x140013fba  lea     rax, [rsp+178h+HighLimit]
0x140013fc2  sub     rax, [rsp+178h+LowLimit]
0x140013fca  cmp     rax, 4800h
0x140013fd0  jbe     loc_14001419C
0x140013fd6  xor     edi, edi
0x140013fd8  mov     rdx, rbx; Irp
0x140013fdb  mov     rcx, rsi; DeviceObject
0x140013fde  call    cs:__imp_IofCallDriver
0x140013fe5  nop     dword ptr [rax+rax+00h]
0x140013fea  mov     edx, eax
0x140013fec  cmp     edx, 0C0000102h
0x140013ff2  jz      loc_1400140D3
0x140013ff8  cmp     edx, 0C0000032h
0x140013ffe  jz      loc_1400140D3
0x140014004  cmp     edx, 0C0000053h
0x14001400a  jz      loc_1400140D3
0x140014010  movzx   eax, cs:NtfsStatusDebugFlags
0x140014017  test    al, al
0x140014019  jnz     short loc_14001406C
0x14001401b  cmp     cs:NtfsDiskAccountingEnabled, 0
0x140014022  jnz     short loc_140014046
0x140014024  cmp     qword ptr [r15+1F8h], 0
0x14001402c  jnz     loc_140014434
0x140014032  add     rsp, 140h
0x140014039  pop     r15
0x14001403b  pop     r14
0x14001403d  pop     r13
0x14001403f  pop     r12
0x140014041  pop     rdi
0x140014042  pop     rsi
0x140014043  pop     rbx
0x140014044  retn
0x140014046  xor     eax, eax
0x140014048  cmp     r12b, 4
0x14001404c  cmovz   eax, r14d
0x140014050  mov     edx, eax
0x140014052  mov     ecx, r14d
0x140014055  xor     eax, eax
0x140014057  cmp     r12b, 4
0x14001405b  cmovz   ecx, eax
0x14001405e  call    cs:__imp_FsRtlUpdateDiskCounters
0x140014065  nop     dword ptr [rax+rax+00h]
0x14001406a  jmp     short loc_140014024
0x14001406c  test    edi, edi
0x14001406e  jz      short loc_14001401B
0x140014070  cmp     edi, 126h
0x140014076  jz      short loc_14001401B
0x140014078  lea     eax, [rdi-12Ah]
0x14001407e  cmp     eax, 1
0x140014081  jbe     short loc_14001401B
0x140014083  cmp     edi, 0FFFFFFEDh
0x140014086  jnb     short loc_14001401B
0x140014088  cmp     edi, 0C00000D8h
0x14001408e  jz      short loc_14001401B
0x140014090  cmp     edi, 0C0000016h
0x140014096  jz      short loc_14001401B
0x140014098  cmp     edi, 0C0000011h
0x14001409e  jz      loc_14001401B
0x1400140a4  lea     eax, [rdi+7FFFFFFBh]
0x1400140aa  cmp     eax, 1
0x1400140ad  jbe     loc_14001401B
0x1400140b3  cmp     edi, 103h
0x1400140b9  jz      loc_14001401B
0x1400140bf  mov     r8d, 0C5AD6h
0x1400140c5  mov     edx, edi
0x1400140c7  xor     ecx, ecx
0x1400140c9  call    NtfsStatusTraceAndDebugInternal
0x1400140ce  jmp     loc_14001401B
0x1400140d3  movzx   eax, cs:NtfsStatusDebugFlags
0x1400140da  test    al, al
0x1400140dc  jz      loc_140014010
0x1400140e2  test    edx, edx
0x1400140e4  jz      loc_140014010
0x1400140ea  cmp     edx, 126h
0x1400140f0  jz      loc_140014010
0x1400140f6  lea     eax, [rdx-12Ah]
0x1400140fc  cmp     eax, 1
0x1400140ff  jbe     loc_140014010
0x140014105  cmp     edx, 0FFFFFFEDh
0x140014108  jnb     loc_140014010
0x14001410e  cmp     edx, 0C00000D8h
0x140014114  jz      loc_140014010
0x14001411a  cmp     edx, 0C0000016h
0x140014120  jz      loc_140014010
0x140014126  cmp     edx, 0C0000011h
0x14001412c  jz      loc_140014010
0x140014132  lea     eax, [rdx+7FFFFFFBh]
0x140014138  cmp     eax, 1
0x14001413b  jbe     loc_140014010
0x140014141  cmp     edx, 103h
  ... truncated ...
```
