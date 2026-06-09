# AfdSanConnectHandler

- ea: `0x140059ab0`
- end: `0x14005a97f`
- name: `AfdSanConnectHandler`
- size: `3791`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x14001ef30`

## callees

- `0x1400044fc`
- `0x1400049b0`
- `0x140009fb0`
- `0x14000f450`
- `0x140013030`
- `0x1400137a0`
- `0x140015990`
- `0x14001b0d0`
- `0x14001b800`
- `0x14001c708`
- `0x14002fd7c`
- `0x14003606c`
- `0x140036dcc`
- `0x1400391b8`
- `0x14003f7f8`
- `0x140059ab0`
- `0x14005d760`
- `0x140072870`
- `0x140072880`
- `0x140072980`
- `0x14009220c`
- `0x140092254`
- `0x140093008`
- `0x1400930cc`
- `0x1400931d0`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x140059cd7`
- `ntoskrnl!ExRaiseStatus` at `0x140059cd7`
- `ntoskrnl!ObCloseHandle` at `0x14005a4b1`
- `ntoskrnl!ObCloseHandle` at `0x14005a4b1`
- `ntoskrnl!IoThreadToProcess` at `0x140059f93`
- `ntoskrnl!IoThreadToProcess` at `0x140059ff5`
- `ntoskrnl!IoThreadToProcess` at `0x14005a007`
- `ntoskrnl!IoThreadToProcess` at `0x140059f93`
- `ntoskrnl!IoThreadToProcess` at `0x140059ff5`
- `ntoskrnl!IoThreadToProcess` at `0x14005a007`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14005a069`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14005a069`
- `ntoskrnl!MmMapLockedPages` at `0x14005a0fa`
- `ntoskrnl!MmMapLockedPages` at `0x14005a138`
- `ntoskrnl!MmMapLockedPages` at `0x14005a189`
- `ntoskrnl!MmMapLockedPages` at `0x14005a1e6`
- `ntoskrnl!MmMapLockedPages` at `0x14005a0fa`
- `ntoskrnl!MmMapLockedPages` at `0x14005a138`
- `ntoskrnl!MmMapLockedPages` at `0x14005a189`
- `ntoskrnl!MmMapLockedPages` at `0x14005a1e6`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140059d87`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140059d87`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140059f57`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140059f57`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14005a451`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14005a6b9`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14005a823`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14005a451`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14005a6b9`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14005a823`
- `ntoskrnl!IofCompleteRequest` at `0x140059c23`
- `ntoskrnl!IofCompleteRequest` at `0x14005a3c3`
- `ntoskrnl!IofCompleteRequest` at `0x14005a4e1`
- `ntoskrnl!IofCompleteRequest` at `0x14005a838`
- `ntoskrnl!IofCompleteRequest` at `0x14005a931`
- `ntoskrnl!IofCompleteRequest` at `0x140059c23`
- `ntoskrnl!IofCompleteRequest` at `0x14005a3c3`
- `ntoskrnl!IofCompleteRequest` at `0x14005a4e1`
- `ntoskrnl!IofCompleteRequest` at `0x14005a838`
- `ntoskrnl!IofCompleteRequest` at `0x14005a931`
- `ntoskrnl!ObfDereferenceObject` at `0x140059c09`
- `ntoskrnl!ObfDereferenceObject` at `0x14005a3d7`
- `ntoskrnl!ObfDereferenceObject` at `0x14005a947`
- `ntoskrnl!ObfDereferenceObject` at `0x140059c09`
- `ntoskrnl!ObfDereferenceObject` at `0x14005a3d7`
- `ntoskrnl!ObfDereferenceObject` at `0x14005a947`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14005a43e`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14005a6a6`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14005a810`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14005a43e`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14005a6a6`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14005a810`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005a3a9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005a42a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005a45f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005a472`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005a692`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005a6c7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005a3a9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005a42a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005a45f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005a472`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005a692`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005a6c7`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005a09b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005a649`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005a84d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005a09b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005a649`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005a84d`
- `ntoskrnl!IoFileObjectType` at `0x140059d50`
- `ntoskrnl!IoFileObjectType` at `0x14005a045`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140059d5d`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140059d5d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140059b72`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005a566`
- `ntoskrnl!ExFreePoolWithTag` at `0x140059b72`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005a566`
- `ntoskrnl!ExAllocatePool2` at `0x140059b33`
- `ntoskrnl!ExAllocatePool2` at `0x14005a59f`
- `ntoskrnl!ExAllocatePool2` at `0x140059b33`
- `ntoskrnl!ExAllocatePool2` at `0x14005a59f`
- `ntoskrnl!IoGetCurrentProcess` at `0x140059c97`
- `ntoskrnl!IoGetCurrentProcess` at `0x140059fa2`
- `ntoskrnl!IoGetCurrentProcess` at `0x140059c97`
- `ntoskrnl!IoGetCurrentProcess` at `0x140059fa2`
- `ntoskrnl!IoIs32bitProcess` at `0x140059af5`
- `ntoskrnl!IoIs32bitProcess` at `0x140059bda`
- `ntoskrnl!IoIs32bitProcess` at `0x140059d0f`
- `ntoskrnl!IoIs32bitProcess` at `0x14005a2e5`
- `ntoskrnl!IoIs32bitProcess` at `0x140059af5`
- `ntoskrnl!IoIs32bitProcess` at `0x140059bda`
- `ntoskrnl!IoIs32bitProcess` at `0x140059d0f`
- `ntoskrnl!IoIs32bitProcess` at `0x14005a2e5`
- `ntoskrnl!ProbeForWrite` at `0x140059cf3`
- `ntoskrnl!ProbeForWrite` at `0x140059cf3`

## pseudocode

```c
__int64 __fastcall AfdSanConnectHandler(PIRP Irp, __int64 a2)
{
  unsigned int *v4; // rbx
  unsigned int v5; // eax
  struct _IRP *MasterIrp; // rsi
  unsigned int v7; // r14d
  struct _IRP *Pool2; // rdi
  __int64 v9; // rsi
  unsigned __int64 v10; // rax
  struct _IRP *v11; // r14
  BOOLEAN v12; // al
  unsigned int v13; // ecx
  int v14; // r14d
  __int64 v16; // rcx
  int v17; // edi
  struct _KPROCESS *v18; // rbx
  PMDL MdlAddress; // rcx
  _DWORD *v20; // rbx
  _QWORD *v21; // r13
  __int64 v22; // r9
  __int64 v23; // r13
  __int64 v24; // rdi
  __int64 FreeConnection; // rax
  PIRP v26; // rsi
  signed __int64 v27; // rax
  bool v28; // cc
  signed __int64 v29; // rax
  struct _KPROCESS *v30; // rdi
  NTSTATUS v31; // eax
  struct _KTHREAD *Thread; // rdi
  struct _KPROCESS *v33; // rsi
  __int64 v34; // rdi
  __int64 v35; // r13
  PMDL v36; // rcx
  unsigned __int16 v37; // r13
  char *MappedSystemVa; // rax
  struct _IO_STACK_LOCATION *v39; // rdi
  __int64 LowPart; // rcx
  char *v41; // r14
  char *v42; // r14
  PMDL v43; // rcx
  char *v44; // rax
  char *v45; // rax
  unsigned __int16 FileAttributes; // r8
  PMDL v47; // rcx
  char *v48; // rax
  char *v49; // r14
  void *v50; // r9
  __int64 v51; // rdx
  unsigned __int64 v52; // rax
  unsigned __int16 v53; // dx
  unsigned __int16 v54; // si
  __int64 v55; // rdi
  int v56; // r8d
  int v57; // eax
  unsigned __int16 v58; // dx
  struct _LIST_ENTRY *v59; // rcx
  BOOLEAN v60; // al
  KPROCESSOR_MODE RequestorMode; // cl
  ULONG v62; // eax
  ULONG v63; // eax
  unsigned int v64; // r14d
  void **v65; // rbx
  void *v66; // rcx
  unsigned int v67; // edx
  __int64 v68; // rax
  __int64 v69; // r8
  void *v70; // rdx
  __int64 v71; // r8
  _QWORD *v72; // rcx
  __int64 v73; // rax
  _QWORD *v74; // rdx
  _QWORD *v75; // rbx
  _QWORD *v76; // rdx
  __int64 v77; // rcx
  struct _KLOCK_QUEUE_HANDLE *p_LockHandle; // rdx
  IRP *v79; // rcx
  struct _LIST_ENTRY *v80; // r8
  struct _LIST_ENTRY *Blink; // rdx
  PIRP v82; // [rsp+40h] [rbp-E8h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-E0h] BYREF
  struct _IRP *v84; // [rsp+50h] [rbp-D8h]
  int v85; // [rsp+58h] [rbp-D0h]
  void *Src; // [rsp+60h] [rbp-C8h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+68h] [rbp-C0h] BYREF
  struct _IO_STACK_LOCATION *CurrentStackLocation; // [rsp+80h] [rbp-A8h]
  size_t Size; // [rsp+88h] [rbp-A0h]
  PVOID Object; // [rsp+90h] [rbp-98h]
  __int128 v91; // [rsp+98h] [rbp-90h] BYREF
  PVOID v92; // [rsp+A8h] [rbp-80h] BYREF
  PVOID Parameters; // [rsp+B0h] [rbp-78h]
  void *v94; // [rsp+B8h] [rbp-70h]
  __int64 v95; // [rsp+C0h] [rbp-68h]
  __int64 v96; // [rsp+C8h] [rbp-60h]
  __int64 v97; // [rsp+D0h] [rbp-58h]
  void *v98; // [rsp+D8h] [rbp-50h]
  struct _IRP *v99; // [rsp+E0h] [rbp-48h]
  struct _IRP *v100; // [rsp+E8h] [rbp-40h]
  __int64 Irql; // [rsp+140h] [rbp+18h] BYREF
  __int64 Length; // [rsp+148h] [rbp+20h]

  memset(&LockHandle, 0, sizeof(LockHandle));
  v82 = 0;
  Object = 0;
  v4 = (unsigned int *)(a2 + 16);
  if ( IoIs32bitProcess(Irp) )
  {
    v5 = *v4;
    if ( *v4 < 0x14 || v5 > 0xFFFFFFF3 )
      goto LABEL_10;
    MasterIrp = Irp->AssociatedIrp.MasterIrp;
    v7 = v5 + 12;
    Pool2 = (struct _IRP *)ExAllocatePool2(99, v5 + 12, 1935959617);
    v100 = Pool2;
    *(_QWORD *)&Pool2->Type = *(int *)&MasterIrp->Type;
    Pool2->MdlAddress = (PMDL)*(unsigned int *)(&MasterIrp->Size + 1);
    memmove(&Pool2->Flags, &MasterIrp->MdlAddress, *v4 - 8);
    ExFreePoolWithTag(Irp->AssociatedIrp.MasterIrp, 0);
    Irp->AssociatedIrp.MasterIrp = Pool2;
    *v4 = v7;
  }
  v9 = *(_QWORD *)(*(_QWORD *)(a2 + 48) + 24LL);
  v95 = v9;
  Irp->IoStatus.Information = 0;
  v10 = *v4;
  if ( (unsigned int)v10 < 0x20
    || (v11 = Irp->AssociatedIrp.MasterIrp, v84 = v11, Src = &v11->Flags, v11->Flags != 2)
    || v10 < (unsigned __int64)*((unsigned __int16 *)&v11->Flags + 2) + 30 )
  {
LABEL_10:
    v14 = -1073741811;
    goto LABEL_11;
  }
  v12 = IoIs32bitProcess(Irp);
  v13 = *(_DWORD *)(a2 + 8);
  if ( v12 )
  {
    if ( v13 < 8 )
      goto LABEL_10;
  }
  else if ( v13 < 0x10 )
  {
    goto LABEL_10;
  }
  v16 = *((unsigned __int16 *)&v11->Flags + 2);
  v17 = v16 + 8;
  Size = (unsigned int)(v16 + 8);
  v94 = (char *)&v11->AssociatedIrp + v16;
  if ( (__int64)((__int64)v94 + *(unsigned __int16 *)v94 - (unsigned __int64)Irp->AssociatedIrp.MasterIrp + 4) > (int)*v4 )
    goto LABEL_10;
  if ( *(_WORD *)v9 != 2813 )
    goto LABEL_162;
  v18 = *(struct _KPROCESS **)(v9 + 48);
  if ( v18 != IoGetCurrentProcess() )
    goto LABEL_162;
  MdlAddress = v11->MdlAddress;
  if ( !MdlAddress )
  {
    if ( (BYTE2(xmmword_1400875E0) & 8) != 0 )
      WPP_SF_(1043, 23, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids);
    ExRaiseStatus(-1073741811);
  }
  if ( Irp->RequestorMode )
    ProbeForWrite(MdlAddress, 0x14u, 4u);
  *(_DWORD *)Src = 1;
  IoIs32bitProcess(Irp);
  v20 = (char *)Irp->MdlAddress->StartVa + Irp->MdlAddress->ByteOffset;
  v92 = 0;
  v14 = ObReferenceObjectByHandle(
          *(HANDLE *)&v11->Type,
          (unsigned __int8)HIBYTE(*(_WORD *)(a2 + 24)) >> 6,
          (POBJECT_TYPE)IoFileObjectType,
          Irp->RequestorMode,
          &v92,
          0);
  v21 = v92;
  Object = v92;
  if ( v14 < 0 )
    goto LABEL_11;
  if ( IoGetRelatedDeviceObject((PFILE_OBJECT)v92) != AfdDeviceObject
    || (v23 = v21[3], v97 = v23, (*(_DWORD *)(v23 + 8) & 1) == 0)
    || *(_BYTE *)(v23 + 2) == 6
    || (*(_DWORD *)(v23 + 8) & 0x800) != 0 )
  {
LABEL_162:
    v14 = -1073741816;
    goto LABEL_11;
  }
  v98 = Src;
  v99 = v84;
  v85 = v17;
  if ( (BYTE2(xmmword_1400875E0) & 8) != 0 )
    WPP_SF_qq(1043, 24, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids, v23, Irp);
  if ( (*(_DWORD *)(v23 + 8) & 2) == 0 || (*(_DWORD *)(v23 + 8) & 0x100) != 0 )
  {
    while ( 1 )
    {
      FreeConnection = AfdGetFreeConnection(v23, 0, &v82);
      v24 = FreeConnection;
      Irql = FreeConnection;
      if ( !FreeConnection )
        goto LABEL_110;
      v26 = v82;
      if ( !v82 )
        goto LABEL_110;
      if ( (BYTE1(xmmword_1400875E0) & 1) != 0 )
        WPP_SF_q(1032, 25, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids, FreeConnection);
      CurrentStackLocation = v26->Tail.Overlay.CurrentStackLocation;
      Parameters = CurrentStackLocation->Parameters.CreatePipe.Parameters;
      Irql = *((_QWORD *)Parameters + 3);
      v96 = Irql;
      if ( (*(_DWORD *)(v23 + 8) & 0x100) != 0 )
      {
        v27 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v24 + 48), 0xFFFFFFFFFFFFFFFFuLL);
        v28 = v27 <= 1;
        v29 = v27 - 1;
        if ( v28 )
        {
          if ( v29 )
            __fastfail(0xEu);
          AfdCloseConnection(v24);
        }
      }
      else
      {
        _InterlockedDecrement((volatile signed __int32 *)(v23 + 176));
        ExpInterlockedPushEntrySList((PSLIST_HEADER)(v23 + 144), (PSLIST_ENTRY)(v24 + 176));
      }
      v30 = IoThreadToProcess(Irp->Tail.Overlay.Thread);
      if ( v30 == IoGetCurrentProcess() )
      {
        if ( (unsigned int)Size > CurrentStackLocation->Parameters.Create.Options )
        {
          v31 = -1073741789;
        }
        else
        {
          v31 = AfdMapMdlChain(v26->MdlAddress);
          if ( v31 >= 0 )
          {
            Handle = 0;
            Thread = Irp->Tail.Overlay.Thread;
            v33 = IoThreadToProcess(v26->Tail.Overlay.Thread);
            if ( IoThreadToProcess(Thread) == v33 )
            {
              v26 = v82;
              Handle = v82->Tail.Overlay.DriverContext[3];
              v31 = 0;
              LOBYTE(Length) = 0;
            }
            else
            {
              v31 = ObOpenObjectByPointer(Parameters, 0x40u, 0, 0x2000000u, (POBJECT_TYPE)IoFileObjectType, 1, &Handle);
              LOBYTE(Length) = 1;
              v26 = v82;
            }
            if ( v31 >= 0 )
            {
              v34 = Irql;
              KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(Irql + 56), &LockHandle);
              if ( (*(_DWORD *)(v34 + 8) & 0x800) != 0 )
              {
                KeReleaseInStackQueuedSpinLock(&LockHandle);
                if ( (BYTE2(xmmword_1400875E0) & 8) != 0 )
                  WPP_SF_q(1043, 27, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids, v34);
              }
              else
              {
                _InterlockedExchange64((volatile __int64 *)&v26->CancelRoutine, (__int64)&AfdSanCancelAccept);
                if ( !v26->Cancel )
                {
                  v35 = v34;
                  v36 = v26->MdlAddress;
                  if ( *(_BYTE *)(v34 + 188) )
                  {
                    v37 = *((_WORD *)&v84->Flags + 2) + 2;
                    if ( (v36->MdlFlags & 5) != 0 )
                      MappedSystemVa = (char *)v36->MappedSystemVa;
                    else
                      MappedSystemVa = (char *)MmMapLockedPages(v36, 0);
                    v39 = CurrentStackLocation;
                    LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
                    v41 = &MappedSystemVa[CurrentStackLocation->Parameters.Create.Options];
                    Length = CurrentStackLocation->Parameters.Read.Length;
                    v42 = &v41[LowPart];
                    v43 = v26->MdlAddress;
                    if ( (v43->MdlFlags & 5) != 0 )
                      v44 = (char *)v43->MappedSystemVa;
                    else
                      v44 = (char *)MmMapLockedPages(v43, 0);
                    RtlMoveVolatileMemory(
                      &v44[v39->Parameters.Read.ByteOffset.LowPart + v39->Parameters.Read.Length],
                      (char *)&v84->Flags + 6,
                      v37);
                    *(_WORD *)&v42[Length - 2] = v37;
                    v35 = Irql;
                  }
                  else
                  {
                    if ( (v36->MdlFlags & 5) != 0 )
                      v45 = (char *)v36->MappedSystemVa;
                    else
                      v45 = (char *)MmMapLockedPages(v36, 0);
                    v39 = CurrentStackLocation;
                    RtlMoveVolatileMemory(
                      &v45[CurrentStackLocation->Parameters.Read.ByteOffset.LowPart
                         + CurrentStackLocation->Parameters.Read.Length],
                      Src,
                      (unsigned int)Size);
                  }
                  if ( v39->Parameters.Read.ByteOffset.LowPart >= 6 )
                  {
                    FileAttributes = v39->Parameters.Create.FileAttributes;
                    LOWORD(Irql) = FileAttributes;
                    v47 = v26->MdlAddress;
                    if ( (v47->MdlFlags & 5) != 0 )
                    {
                      v48 = (char *)v47->MappedSystemVa;
                    }
                    else
                    {
                      v48 = (char *)MmMapLockedPages(v47, 0);
                      FileAttributes = Irql;
                    }
                    v49 = &v48[v39->Parameters.Read.Length];
                    v50 = v94;
                    v51 = *(unsigned __int16 *)v94;
                    if ( *(_BYTE *)(v35 + 188) )
                    {
                      v52 = v51 + 2;
                      v53 = v51 + 2;
                      if ( v52 >= (unsigned __int64)FileAttributes - 2 )
                        v53 = FileAttributes - 2;
                      v54 = v53;
                      v55 = v39->Parameters.Read.ByteOffset.LowPart;
                      RtlMoveVolatileMemory(v49, (char *)v94 + 2, v53);
                      *(_WORD *)&v49[v55 - 2] = v54;
                      v26 = v82;
                      v39 = CurrentStackLocation;
                    }
                    else
                    {
                      v56 = FileAttributes - 8;
                      *(_DWORD *)v49 = 0;
                      *((_DWORD *)v49 + 1) = 1;
                      v57 = v51 + 4;
                      v58 = v51 + 4;
                      if ( v57 >= v56 )
                        v58 = v56;
                      RtlMoveVolatileMemory(v49 + 8, v50, v58);
                    }
                  }
                  *(_QWORD *)(v35 + 360) = 0;
                  AfdSanInitEndpoint(v95, Parameters, v84->MdlAddress);
                  v59 = *(struct _LIST_ENTRY **)(v35 + 136);
                  if ( v59->Flink == (struct _LIST_ENTRY *)(v35 + 128) )
                  {
                    v26->Tail.Overlay.ListEntry.Flink = (struct _LIST_ENTRY *)(v35 + 128);
                    v26->Tail.Overlay.ListEntry.Blink = v59;
                    v59->Flink = &v26->Tail.Overlay.ListEntry;
                    *(_QWORD *)(v35 + 136) = &v26->Tail.Overlay.ListEntry;
                    v60 = IoIs32bitProcess(Irp);
                    RequestorMode = Irp->RequestorMode;
                    if ( v60 )
                    {
                      LODWORD(Irql) = (_DWORD)Handle;
                      if ( RequestorMode )
                        RtlWriteULongToUser(v20, Handle);
                      else
                        RtlCopyVolatileMemory(v20, &Irql, 4u);
                      v62 = v39->Parameters.Read.Length;
                      if ( Irp->RequestorMode )
                        RtlWriteULongToUser(v20 + 1, v62);
                      else
                        v20[1] = v62;
                      Irp->IoStatus.Information = 8;
                    }
                    else
                    {
                      if ( RequestorMode )
                        RtlWriteULong64ToUser(v20, Handle);
                      else
                        *(_QWORD *)v20 = Handle;
                      v63 = v39->Parameters.Read.Length;
                      if ( Irp->RequestorMode )
                        RtlWriteULongToUser(v20 + 2, v63);
                      else
                        v20[2] = v63;
                      Irp->IoStatus.Information = 16;
                    }
                    KeReleaseInStackQueuedSpinLock(&LockHandle);
                    Irp->IoStatus.Status = 0;
                    IofCompleteRequest(Irp, AfdPriorityBoost);
                    ObfDereferenceObject(Object);
                    if ( (BYTE2(xmmword_1400875E0) & 8) != 0 )
                      WPP_SF_qq(1043, 26, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids, v35, v26);
                    return 0;
                  }
LABEL_161:
                  __fastfail(3u);
                }
                if ( _InterlockedExchange64((volatile __int64 *)&v26->CancelRoutine, 0) )
                {
                  KeReleaseInStackQueuedSpinLock(&LockHandle);
                }
                else
                {
                  LOBYTE(Irql) = 0;
                  KeReleaseInStackQueuedSpinLock(&LockHandle);
                  IoAcquireCancelSpinLock((PKIRQL)&Irql);
                  IoReleaseCancelSpinLock(Irql);
                }
              }
              if ( (_BYTE)Length )
                ObCloseHandle(Handle, 1);
              v31 = -1073741536;
            }
          }
        }
      }
      else
      {
        v31 = -1073741816;
      }
      AfdCleanupSuperAccept(v26, (unsigned int)v31);
      IofCompleteRequest(v26, AfdPriorityBoost);
    }
  }
  Irql = 0;
  if ( (*(_DWORD *)(v23 + 8) & 0x100) != 0 || (LOBYTE(v22) = 1, (*(_DWORD *)(v23 + 16) & 0x200) == 0) )
    LOBYTE(v22) = 0;
  v14 = AfdCreateConnection(
          v23,
          *(_QWORD *)(v23 + 272),
          *(_QWORD *)(v23 + 256),
          v22,
          0,
          (*(_DWORD *)(v23 + 8) >> 7) & 1,
          *(_QWORD *)(v23 + 48),
          &Irql);
  if ( v14 < 0 )
  {
LABEL_11:
    if ( Object )
      ObfDereferenceObject(Object);
    Irp->IoStatus.Status = v14;
    IofCompleteRequest(Irp, AfdPriorityBoost);
    return (unsigned int)v14;
  }
  _InterlockedDecrement((volatile signed __int32 *)(v23 + 176));
  v24 = Irql;
LABEL_110:
  if ( !v24 )
  {
LABEL_126:
    v14 = -1073741670;
    goto LABEL_11;
  }
  v91 = 0;
  v64 = Size;
  if ( (*(_DWORD *)(v23 + 8) & 0x100) != 0 )
  {
    v64 = Size - 6;
    v85 = Size - 6;
  }
  v65 = (void **)(v24 + 152);
  Length = v24 + 152;
  v66 = *(void **)(v24 + 152);
  if ( !v66 )
    goto LABEL_119;
  v67 = *(_DWORD *)(v24 + 160);
  if ( v67 < v64 )
  {
    if ( v67 > (unsigned int)AfdStandardAddressLength )
      ExFreePoolWithTag(v66, 0x52646641u);
    else
      PplFreeToLookasideList(PplAddressPool, *(_QWORD *)(v24 + 152));
    *v65 = 0;
LABEL_119:
    v66 = 0;
  }
  if ( !v66 )
  {
    v68 = v64 > (unsigned int)AfdStandardAddressLength
        ? ExAllocatePool2(97, v64, 1382311489)
        : AfdAllocateZeroedFromLookasideList(0, v64);
    *v65 = (void *)v68;
    if ( !*v65 )
    {
      LOBYTE(v69) = 1;
      AfdSanReleaseConnection(v23, v24, v69);
      goto LABEL_126;
    }
  }
  *(_DWORD *)(v24 + 160) = v64;
  if ( (*(_DWORD *)(v23 + 8) & 0x100) != 0 )
    v70 = (char *)&v84->Flags + 6;
  else
    v70 = Src;
  memmove(*v65, v70, v64);
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v23 + 56), &LockHandle);
  *(_QWORD *)(v24 + 40) = 0;
  *(_QWORD *)(a2 + 32) = v24;
  _InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, (__int64)&AfdSanCancelConnect);
  if ( Irp->Cancel )
  {
    if ( _InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, 0) )
    {
      KeReleaseInStackQueuedSpinLock(&LockHandle);
    }
    else
    {
      LOBYTE(Irql) = 0;
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      IoAcquireCancelSpinLock((PKIRQL)&Irql);
      IoReleaseCancelSpinLock(Irql);
    }
    LOBYTE(v71) = 1;
    AfdSanReleaseConnection(v23, v24, v71);
    v14 = -1073741536;
    goto LABEL_11;
  }
  Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  *(_QWORD *)(v24 + 8) = v23;
  if ( _InterlockedIncrement64((volatile signed __int64 *)(v23 + 64)) <= 1 )
    __fastfail(0xEu);
  *(_QWORD *)(v24 + 40) = Irp;
  *(_DWORD *)(v24 + 4) |= 0x20000000u;
  *(_WORD *)(v24 + 2) = 1;
  *((_QWORD *)&v91 + 1) = &v91;
  *(_QWORD *)&v91 = &v91;
  while ( 1 )
  {
    if ( (*(_DWORD *)(v23 + 8) & 2) == 0 && (unsigned __int8)AfdServiceSuperAccept(v23, v24, &LockHandle, &v91) )
      goto LABEL_156;
    v72 = *(_QWORD **)(v23 + 128);
    if ( v72 == (_QWORD *)(v23 + 128) )
      break;
    v73 = *v72;
    if ( *(_QWORD **)(*v72 + 8LL) != v72 )
      goto LABEL_161;
    v74 = (_QWORD *)v72[1];
    if ( (_QWORD *)*v74 != v72 )
      goto LABEL_161;
    v75 = v72 - 21;
    *v74 = v73;
    *(_QWORD *)(v73 + 8) = v74;
    *v72 = 0;
    if ( (BYTE2(xmmword_1400875E0) & 8) != 0 )
      WPP_SF_q(1043, 28, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids, v75);
    if ( (int)AfdServiceWaitForListen((PIRP)v75) >= 0 )
      goto LABEL_160;
    AfdNotifySockIndicateEventsUnlock(v23, &LockHandle, 0);
    if ( !_InterlockedExchange64(v75 + 13, 0) )
    {
      LOBYTE(Irql) = 0;
      IoAcquireCancelSpinLock((PKIRQL)&Irql);
      IoReleaseCancelSpinLock(Irql);
    }
    IofCompleteRequest((PIRP)v75, AfdPriorityBoost);
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v23 + 56), &LockHandle);
  }
  v76 = *(_QWORD **)(v23 + 104);
  if ( *v76 != v23 + 96 )
    goto LABEL_161;
  *(_QWORD *)(v24 + 176) = v23 + 96;
  *(_QWORD *)(v24 + 184) = v76;
  *v76 = v24 + 176;
  *(_QWORD *)(v23 + 104) = v24 + 176;
  if ( (BYTE2(xmmword_1400875E0) & 8) != 0 )
    WPP_SF_q(1043, 29, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids, v24);
  AfdIndicateEventSelectEvent(v23, 128, 0);
  AfdNotifySockEventsChangedUnderLock(v23, 128, 0);
  if ( (unsigned __int8)AfdIndicatePollEvent(v77, 128, 0, &LockHandle) )
    p_LockHandle = 0;
  else
    p_LockHandle = &LockHandle;
  AfdNotifySockIndicateEventsUnlock(v23, p_LockHandle, 0);
LABEL_156:
  while ( (__int128 *)v91 != &v91 )
  {
    v79 = (IRP *)(v91 - 168);
    v80 = *(struct _LIST_ENTRY **)v91;
    if ( *(_QWORD *)(*(_QWORD *)v91 + 8LL) != (_QWORD)v91 )
      goto LABEL_161;
    Blink = v79->Tail.Overlay.ListEntry.Blink;
    if ( Blink->Flink != (struct _LIST_ENTRY *)v91 )
      goto LABEL_161;
    Blink->Flink = v80;
    v80->Blink = Blink;
    IofCompleteRequest(v79, AfdPriorityBoost);
  }
LABEL_160:
  ObfDereferenceObject(Object);
  return 259;
}

```

## disassembly

```asm
0x140059ab0  mov     [rsp+arg_8], rdx
0x140059ab5  mov     [rsp+Irp], rcx
0x140059aba  push    rbx
0x140059abb  push    rsi
0x140059abc  push    rdi
0x140059abd  push    r12
0x140059abf  push    r13
0x140059ac1  push    r14
0x140059ac3  push    r15
0x140059ac5  sub     rsp, 0F0h
0x140059acc  mov     r13, rdx
0x140059acf  mov     r12, rcx
0x140059ad2  xorps   xmm0, xmm0
0x140059ad5  xor     eax, eax
0x140059ad7  movups  xmmword ptr [rsp+128h+LockHandle.LockQueue.Next], xmm0
0x140059adc  mov     qword ptr [rsp+128h+LockHandle.OldIrql], rax
0x140059ae1  xor     r15d, r15d
0x140059ae4  mov     [rsp+128h+var_E8], r15
0x140059ae9  mov     [rsp+128h+Object], r15
0x140059af1  lea     rbx, [rdx+10h]
0x140059af5  call    cs:__imp_IoIs32bitProcess
0x140059afc  nop     dword ptr [rax+rax+00h]
0x140059b01  test    al, al
0x140059b03  jz      loc_140059B95
0x140059b09  mov     eax, [rbx]
0x140059b0b  cmp     eax, 14h
0x140059b0e  jb      loc_140059BF3
0x140059b14  cmp     eax, 0FFFFFFF3h
0x140059b17  ja      loc_140059BF3
0x140059b1d  mov     rsi, [r12+18h]
0x140059b22  lea     r14d, [rax+0Ch]
0x140059b26  mov     edx, r14d
0x140059b29  lea     ecx, [r15+63h]
0x140059b2d  mov     r8d, 73646641h
0x140059b33  call    cs:__imp_ExAllocatePool2
0x140059b3a  nop     dword ptr [rax+rax+00h]
0x140059b3f  mov     rdi, rax
0x140059b42  mov     [rsp+128h+var_40], rax
0x140059b4a  movsxd  rax, dword ptr [rsi]
0x140059b4d  mov     [rdi], rax
0x140059b50  mov     eax, [rsi+4]
0x140059b53  mov     [rdi+8], rax
0x140059b57  mov     r8d, [rbx]
0x140059b5a  sub     r8d, 8; Size
0x140059b5e  lea     rdx, [rsi+8]; Src
0x140059b62  lea     rcx, [rdi+10h]; void *
0x140059b66  call    memmove
0x140059b6b  xor     edx, edx; Tag
0x140059b6d  mov     rcx, [r12+18h]; P
0x140059b72  call    cs:__imp_ExFreePoolWithTag
0x140059b79  nop     dword ptr [rax+rax+00h]
0x140059b7e  mov     [r12+18h], rdi
0x140059b83  mov     [rbx], r14d
0x140059b86  jmp     short loc_140059B95
0x140059b88  mov     r14d, eax
0x140059b8b  mov     r12, [rsp+128h+Irp]
0x140059b93  jmp     short loc_140059BF9
0x140059b95  mov     rax, [r13+30h]
0x140059b99  mov     rsi, [rax+18h]
0x140059b9d  mov     [rsp+128h+var_68], rsi
0x140059ba5  mov     [r12+38h], r15
0x140059baa  mov     eax, [rbx]
0x140059bac  cmp     eax, 20h ; ' '
0x140059baf  jb      short loc_140059BF3
0x140059bb1  mov     r14, [r12+18h]
0x140059bb6  mov     [rsp+128h+var_D8], r14
0x140059bbb  lea     rcx, [r14+10h]
0x140059bbf  mov     [rsp+128h+Src], rcx
0x140059bc4  cmp     dword ptr [rcx], 2
0x140059bc7  jnz     short loc_140059BF3
0x140059bc9  movzx   ecx, word ptr [r14+14h]
0x140059bce  add     rcx, 1Eh
0x140059bd2  cmp     rax, rcx
0x140059bd5  jb      short loc_140059BF3
0x140059bd7  mov     rcx, r12; Irp
0x140059bda  call    cs:__imp_IoIs32bitProcess
0x140059be1  nop     dword ptr [rax+rax+00h]
0x140059be6  mov     ecx, [r13+8]
0x140059bea  test    al, al
0x140059bec  jz      short loc_140059C46
0x140059bee  cmp     ecx, 8
0x140059bf1  jnb     short loc_140059C4B
0x140059bf3  mov     r14d, 0C000000Dh
0x140059bf9  mov     rbx, [rsp+128h+Object]
0x140059c01  test    rbx, rbx
0x140059c04  jz      short loc_140059C15
0x140059c06  mov     rcx, rbx; Object
0x140059c09  call    cs:__imp_ObfDereferenceObject
0x140059c10  nop     dword ptr [rax+rax+00h]
0x140059c15  mov     [r12+30h], r14d
0x140059c1a  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x140059c20  mov     rcx, r12; Irp
0x140059c23  call    cs:__imp_IofCompleteRequest
0x140059c2a  nop     dword ptr [rax+rax+00h]
0x140059c2f  mov     eax, r14d
0x140059c32  add     rsp, 0F0h
0x140059c39  pop     r15
0x140059c3b  pop     r14
0x140059c3d  pop     r13
0x140059c3f  pop     r12
0x140059c41  pop     rdi
0x140059c42  pop     rsi
0x140059c43  pop     rbx
0x140059c44  retn
0x140059c46  cmp     ecx, 10h
0x140059c49  jb      short loc_140059BF3
0x140059c4b  movzx   ecx, word ptr [r14+14h]
0x140059c50  lea     edi, [rcx+8]
0x140059c53  mov     [rsp+128h+Size], rdi
0x140059c5b  add     rcx, 18h
0x140059c5f  add     rcx, r14
0x140059c62  mov     [rsp+128h+var_70], rcx
0x140059c6a  movzx   eax, word ptr [rcx]
0x140059c6d  sub     rax, [r12+18h]
0x140059c72  add     rcx, 4
0x140059c76  add     rcx, rax
0x140059c79  movsxd  rax, dword ptr [rbx]
0x140059c7c  cmp     rcx, rax
0x140059c7f  jg      loc_140059BF3
0x140059c85  mov     eax, 0AFDh
0x140059c8a  cmp     [rsi], ax
0x140059c8d  jnz     loc_14005A974
0x140059c93  mov     rbx, [rsi+30h]
0x140059c97  call    cs:__imp_IoGetCurrentProcess
0x140059c9e  nop     dword ptr [rax+rax+00h]
0x140059ca3  cmp     rbx, rax
0x140059ca6  jnz     loc_14005A974
0x140059cac  mov     rcx, [r14+8]; Address
0x140059cb0  test    rcx, rcx
0x140059cb3  jnz     short loc_140059CE3
0x140059cb5  test    byte ptr cs:xmmword_1400875E0+2, 8
0x140059cbc  jz      short loc_140059CD2
0x140059cbe  lea     edx, [rcx+17h]
0x140059cc1  mov     ecx, 413h
0x140059cc6  lea     r8, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids
0x140059ccd  call    WPP_SF_
0x140059cd2  mov     ecx, 0C000000Dh; Status
0x140059cd7  call    cs:__imp_ExRaiseStatus
0x140059ce3  cmp     [r12+40h], r15b
0x140059ce8  jz      short loc_140059D00
0x140059cea  mov     edx, 14h; Length
0x140059cef  lea     r8d, [rdx-10h]; Alignment
0x140059cf3  call    cs:__imp_ProbeForWrite
0x140059cfa  nop     dword ptr [rax+rax+00h]
0x140059cff  nop
0x140059d00  mov     esi, 1
0x140059d05  mov     rax, [rsp+128h+Src]
0x140059d0a  mov     [rax], esi
0x140059d0c  mov     rcx, r12; Irp
0x140059d0f  call    cs:__imp_IoIs32bitProcess
0x140059d16  nop     dword ptr [rax+rax+00h]
0x140059d1b  mov     rax, [r12+8]
0x140059d20  mov     ebx, [rax+2Ch]
0x140059d23  add     rbx, [rax+20h]
0x140059d27  mov     [rsp+128h+var_80], r15
0x140059d2f  mov     edx, [r13+18h]
0x140059d33  shr     edx, 0Eh
0x140059d36  and     edx, 3; DesiredAccess
0x140059d39  mov     [rsp+128h+HandleInformation], r15; HandleInformation
0x140059d3e  lea     rax, [rsp+128h+var_80]
0x140059d46  mov     [rsp+128h+ObjectType], rax; Object
0x140059d4b  mov     r9b, [r12+40h]; AccessMode
0x140059d50  mov     r8, cs:__imp_IoFileObjectType
0x140059d57  mov     r8, [r8]; ObjectType
0x140059d5a  mov     rcx, [r14]; Handle
0x140059d5d  call    cs:__imp_ObReferenceObjectByHandle
0x140059d64  nop     dword ptr [rax+rax+00h]
0x140059d69  mov     r14d, eax
0x140059d6c  mov     r13, [rsp+128h+var_80]
0x140059d74  mov     [rsp+128h+Object], r13
0x140059d7c  test    eax, eax
0x140059d7e  js      loc_140059BF9
0x140059d84  mov     rcx, r13; FileObject
0x140059d87  call    cs:__imp_IoGetRelatedDeviceObject
0x140059d8e  nop     dword ptr [rax+rax+00h]
0x140059d93  cmp     rax, cs:AfdDeviceObject
0x140059d9a  jnz     loc_14005A974
0x140059da0  mov     r13, [r13+18h]
0x140059da4  mov     [rsp+128h+var_58], r13
0x140059dac  mov     eax, [r13+8]
0x140059db0  test    sil, al
0x140059db3  jz      loc_14005A974
0x140059db9  cmp     byte ptr [r13+2], 6
0x140059dbe  jz      loc_14005A974
0x140059dc4  mov     eax, [r13+8]
0x140059dc8  bt      eax, 0Bh
0x140059dcc  jb      loc_14005A974
0x140059dd2  mov     rax, [rsp+128h+Src]
0x140059dd7  mov     [rsp+128h+var_50], rax
0x140059ddf  mov     rdx, [rsp+128h+var_D8]
0x140059de4  mov     [rsp+128h+var_48], rdx
0x140059dec  mov     [rsp+128h+var_D0], edi
0x140059df0  test    byte ptr cs:xmmword_1400875E0+2, 8
0x140059df7  jz      short loc_140059E15
0x140059df9  lea     edx, [rsi+17h]
0x140059dfc  mov     ecx, 413h
0x140059e01  mov     [rsp+128h+ObjectType], r12
0x140059e06  mov     r9, r13
0x140059e09  lea     r8, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids
0x140059e10  call    WPP_SF_qq
0x140059e15  mov     eax, [r13+8]
0x140059e19  test    al, 2
0x140059e1b  jz      loc_140059EAF
0x140059e21  mov     eax, [r13+8]
0x140059e25  bt      eax, 8
0x140059e29  jb      loc_140059EAF
0x140059e2f  mov     [rsp+128h+Irql], r15
0x140059e37  mov     eax, [r13+8]
0x140059e3b  bt      eax, 8
0x140059e3f  jb      short loc_140059E4E
0x140059e41  test    dword ptr [r13+10h], 200h
0x140059e49  mov     r9b, sil
0x140059e4c  jnz     short loc_140059E51
0x140059e4e  mov     r9b, r15b
0x140059e51  mov     eax, [r13+8]
0x140059e55  shr     eax, 7
0x140059e58  and     eax, esi
0x140059e5a  lea     rcx, [rsp+128h+Irql]
0x140059e62  mov     [rsp+128h+var_F0], rcx
0x140059e67  mov     rcx, [r13+30h]
0x140059e6b  mov     [rsp+128h+Handle], rcx
0x140059e70  mov     dword ptr [rsp+128h+HandleInformation], eax
0x140059e74  mov     dword ptr [rsp+128h+ObjectType], r15d
0x140059e79  mov     r8, [r13+100h]
0x140059e80  mov     rdx, [r13+110h]
0x140059e87  mov     rcx, r13
0x140059e8a  call    AfdCreateConnection
0x140059e8f  mov     r14d, eax
0x140059e92  test    eax, eax
0x140059e94  js      loc_140059BF9
0x140059e9a  lock dec dword ptr [r13+0B0h]
0x140059ea2  mov     rdi, [rsp+128h+Irql]
0x140059eaa  jmp     loc_14005A4F7
0x140059eaf  mov     r14d, 0C0000008h
0x140059eb5  lea     r8, [rsp+128h+var_E8]
0x140059eba  xor     edx, edx
0x140059ebc  mov     rcx, r13
0x140059ebf  call    AfdGetFreeConnection
0x140059ec4  mov     rdi, rax
0x140059ec7  mov     [rsp+128h+Irql], rax
0x140059ecf  test    rax, rax
0x140059ed2  jz      loc_14005A4F2
0x140059ed8  mov     rsi, [rsp+128h+var_E8]
0x140059edd  test    rsi, rsi
0x140059ee0  jz      loc_14005A4F2
0x140059ee6  test    byte ptr cs:xmmword_1400875E0+1, 1
0x140059eed  jz      short loc_140059F08
0x140059eef  mov     edx, 19h
0x140059ef4  mov     ecx, 408h
0x140059ef9  mov     r9, rax
0x140059efc  lea     r8, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids
0x140059f03  call    WPP_SF_q
0x140059f08  mov     rax, [rsi+0B8h]
0x140059f0f  mov     [rsp+128h+var_A8], rax
0x140059f17  mov     rax, [rax+20h]
0x140059f1b  mov     [rsp+128h+var_78], rax
0x140059f23  mov     rax, [rax+18h]
0x140059f27  mov     [rsp+128h+Irql], rax
0x140059f2f  mov     [rsp+128h+var_60], rax
0x140059f37  mov     eax, [r13+8]
0x140059f3b  bt      eax, 8
0x140059f3f  jb      short loc_140059F65
0x140059f41  lock dec dword ptr [r13+0B0h]
0x140059f49  lea     rdx, [rdi+0B0h]; ListEntry
0x140059f50  lea     rcx, [r13+90h]; ListHead
0x140059f57  call    cs:__imp_ExpInterlockedPushEntrySList
0x140059f5e  nop     dword ptr [rax+rax+00h]
0x140059f63  jmp     short loc_140059F8B
0x140059f65  or      rax, 0FFFFFFFFFFFFFFFFh
0x140059f69  lock xadd [rdi+30h], rax
0x140059f6f  sub     rax, 1
0x140059f73  jg      short loc_140059F8B
0x140059f75  test    rax, rax
0x140059f78  jnz     short loc_140059F84
0x140059f7a  mov     rcx, rdi
0x140059f7d  call    AfdCloseConnection
0x140059f82  jmp     short loc_140059F8B
0x140059f84  mov     ecx, 0Eh
0x140059f89  int     29h; Win8: RtlFailFast(ecx)
0x140059f8b  mov     rcx, [r12+98h]; Thread
0x140059f93  call    cs:__imp_IoThreadToProcess
0x140059f9a  nop     dword ptr [rax+rax+00h]
0x140059f9f  mov     rdi, rax
0x140059fa2  call    cs:__imp_IoGetCurrentProcess
0x140059fa9  nop     dword ptr [rax+rax+00h]
0x140059fae  cmp     rdi, rax
0x140059fb1  jnz     loc_14005A4CB
0x140059fb7  mov     rax, [rsp+128h+var_A8]
0x140059fbf  mov     rcx, [rsp+128h+Size]
0x140059fc7  cmp     ecx, [rax+10h]
0x140059fca  ja      loc_14005A4C4
0x140059fd0  mov     rcx, [rsi+8]; MemoryDescriptorList
0x140059fd4  call    AfdMapMdlChain
0x140059fd9  test    eax, eax
0x140059fdb  js      loc_14005A4CE
0x140059fe1  mov     [rsp+128h+var_E0], r15
0x140059fe6  mov     rcx, [rsi+98h]; Thread
0x140059fed  mov     rdi, [r12+98h]
0x140059ff5  call    cs:__imp_IoThreadToProcess
0x140059ffc  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
