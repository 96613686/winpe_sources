# AfdSanConnectHandler

- ea: `0x140059910`
- end: `0x14005a7df`
- name: `AfdSanConnectHandler`
- size: `3791`
- prototype: `__int64 __fastcall(PIRP Irp, __int64)`
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
- `0x14002fd5c`
- `0x14003604c`
- `0x140036dac`
- `0x140039198`
- `0x14003f7d8`
- `0x140059910`
- `0x14005d5c0`
- `0x1400726d0`
- `0x1400726e0`
- `0x140072800`
- `0x14009220c`
- `0x140092254`
- `0x140093008`
- `0x1400930cc`
- `0x1400931d0`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x140059b37`
- `ntoskrnl!ExRaiseStatus` at `0x140059b37`
- `ntoskrnl!ObCloseHandle` at `0x14005a311`
- `ntoskrnl!ObCloseHandle` at `0x14005a311`
- `ntoskrnl!IoThreadToProcess` at `0x140059df3`
- `ntoskrnl!IoThreadToProcess` at `0x140059e55`
- `ntoskrnl!IoThreadToProcess` at `0x140059e67`
- `ntoskrnl!IoThreadToProcess` at `0x140059df3`
- `ntoskrnl!IoThreadToProcess` at `0x140059e55`
- `ntoskrnl!IoThreadToProcess` at `0x140059e67`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140059ec9`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140059ec9`
- `ntoskrnl!MmMapLockedPages` at `0x140059f5a`
- `ntoskrnl!MmMapLockedPages` at `0x140059f98`
- `ntoskrnl!MmMapLockedPages` at `0x140059fe9`
- `ntoskrnl!MmMapLockedPages` at `0x14005a046`
- `ntoskrnl!MmMapLockedPages` at `0x140059f5a`
- `ntoskrnl!MmMapLockedPages` at `0x140059f98`
- `ntoskrnl!MmMapLockedPages` at `0x140059fe9`
- `ntoskrnl!MmMapLockedPages` at `0x14005a046`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140059be7`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140059be7`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140059db7`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140059db7`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14005a2b1`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14005a519`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14005a683`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14005a2b1`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14005a519`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14005a683`
- `ntoskrnl!IofCompleteRequest` at `0x140059a83`
- `ntoskrnl!IofCompleteRequest` at `0x14005a223`
- `ntoskrnl!IofCompleteRequest` at `0x14005a341`
- `ntoskrnl!IofCompleteRequest` at `0x14005a698`
- `ntoskrnl!IofCompleteRequest` at `0x14005a791`
- `ntoskrnl!IofCompleteRequest` at `0x140059a83`
- `ntoskrnl!IofCompleteRequest` at `0x14005a223`
- `ntoskrnl!IofCompleteRequest` at `0x14005a341`
- `ntoskrnl!IofCompleteRequest` at `0x14005a698`
- `ntoskrnl!IofCompleteRequest` at `0x14005a791`
- `ntoskrnl!ObfDereferenceObject` at `0x140059a69`
- `ntoskrnl!ObfDereferenceObject` at `0x14005a237`
- `ntoskrnl!ObfDereferenceObject` at `0x14005a7a7`
- `ntoskrnl!ObfDereferenceObject` at `0x140059a69`
- `ntoskrnl!ObfDereferenceObject` at `0x14005a237`
- `ntoskrnl!ObfDereferenceObject` at `0x14005a7a7`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14005a29e`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14005a506`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14005a670`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14005a29e`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14005a506`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14005a670`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005a209`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005a28a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005a2bf`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005a2d2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005a4f2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005a527`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005a209`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005a28a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005a2bf`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005a2d2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005a4f2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005a527`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140059efb`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005a4a9`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005a6ad`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140059efb`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005a4a9`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005a6ad`
- `ntoskrnl!IoFileObjectType` at `0x140059bb0`
- `ntoskrnl!IoFileObjectType` at `0x140059ea5`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140059bbd`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140059bbd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400599d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005a3c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400599d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005a3c6`
- `ntoskrnl!ExAllocatePool2` at `0x140059993`
- `ntoskrnl!ExAllocatePool2` at `0x14005a3ff`
- `ntoskrnl!ExAllocatePool2` at `0x140059993`
- `ntoskrnl!ExAllocatePool2` at `0x14005a3ff`
- `ntoskrnl!IoGetCurrentProcess` at `0x140059af7`
- `ntoskrnl!IoGetCurrentProcess` at `0x140059e02`
- `ntoskrnl!IoGetCurrentProcess` at `0x140059af7`
- `ntoskrnl!IoGetCurrentProcess` at `0x140059e02`
- `ntoskrnl!IoIs32bitProcess` at `0x140059955`
- `ntoskrnl!IoIs32bitProcess` at `0x140059a3a`
- `ntoskrnl!IoIs32bitProcess` at `0x140059b6f`
- `ntoskrnl!IoIs32bitProcess` at `0x14005a145`
- `ntoskrnl!IoIs32bitProcess` at `0x140059955`
- `ntoskrnl!IoIs32bitProcess` at `0x140059a3a`
- `ntoskrnl!IoIs32bitProcess` at `0x140059b6f`
- `ntoskrnl!IoIs32bitProcess` at `0x14005a145`
- `ntoskrnl!ProbeForWrite` at `0x140059b53`
- `ntoskrnl!ProbeForWrite` at `0x140059b53`

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
  NTSTATUS Connection; // r14d
  __int64 v16; // rcx
  int v17; // edi
  struct _KPROCESS *v18; // rbx
  PMDL MdlAddress; // rcx
  _DWORD *v20; // rbx
  _QWORD *v21; // r13
  __int64 v22; // r13
  unsigned __int8 v23; // r9
  __int64 v24; // rdi
  PSLIST_ENTRY FreeConnection; // rax
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
  USHORT FileAttributes; // r8
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
  void *v68; // rax
  void *v69; // rdx
  _QWORD *v70; // rcx
  __int64 v71; // rax
  _QWORD *v72; // rdx
  _QWORD *v73; // rbx
  _QWORD *v74; // rdx
  __int64 v75; // rcx
  struct _KLOCK_QUEUE_HANDLE *p_LockHandle; // rdx
  IRP *v77; // rcx
  struct _LIST_ENTRY *v78; // r8
  struct _LIST_ENTRY *Blink; // rdx
  PIRP v80; // [rsp+40h] [rbp-E8h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-E0h] BYREF
  struct _IRP *v82; // [rsp+50h] [rbp-D8h]
  int v83; // [rsp+58h] [rbp-D0h]
  void *Src; // [rsp+60h] [rbp-C8h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+68h] [rbp-C0h] BYREF
  struct _IO_STACK_LOCATION *CurrentStackLocation; // [rsp+80h] [rbp-A8h]
  size_t Size; // [rsp+88h] [rbp-A0h]
  PVOID Object; // [rsp+90h] [rbp-98h]
  __int128 v89; // [rsp+98h] [rbp-90h] BYREF
  PVOID v90; // [rsp+A8h] [rbp-80h] BYREF
  PVOID Parameters; // [rsp+B0h] [rbp-78h]
  void *v92; // [rsp+B8h] [rbp-70h]
  __int64 v93; // [rsp+C0h] [rbp-68h]
  __int64 v94; // [rsp+C8h] [rbp-60h]
  __int64 v95; // [rsp+D0h] [rbp-58h]
  void *v96; // [rsp+D8h] [rbp-50h]
  struct _IRP *v97; // [rsp+E0h] [rbp-48h]
  struct _IRP *v98; // [rsp+E8h] [rbp-40h]
  PSLIST_ENTRY Irql; // [rsp+140h] [rbp+18h] BYREF
  __int64 Length; // [rsp+148h] [rbp+20h]

  memset(&LockHandle, 0, sizeof(LockHandle));
  v80 = 0;
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
    v98 = Pool2;
    *(_QWORD *)&Pool2->Type = *(int *)&MasterIrp->Type;
    Pool2->MdlAddress = (PMDL)*(unsigned int *)(&MasterIrp->Size + 1);
    memmove(&Pool2->Flags, &MasterIrp->MdlAddress, *v4 - 8);
    ExFreePoolWithTag(Irp->AssociatedIrp.MasterIrp, 0);
    Irp->AssociatedIrp.MasterIrp = Pool2;
    *v4 = v7;
  }
  v9 = *(_QWORD *)(*(_QWORD *)(a2 + 48) + 24LL);
  v93 = v9;
  Irp->IoStatus.Information = 0;
  v10 = *v4;
  if ( (unsigned int)v10 < 0x20
    || (v11 = Irp->AssociatedIrp.MasterIrp, v82 = v11, Src = &v11->Flags, v11->Flags != 2)
    || v10 < (unsigned __int64)*((unsigned __int16 *)&v11->Flags + 2) + 30 )
  {
LABEL_10:
    Connection = -1073741811;
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
  v92 = (char *)&v11->AssociatedIrp + v16;
  if ( (__int64)((__int64)v92 + *(unsigned __int16 *)v92 - (unsigned __int64)Irp->AssociatedIrp.MasterIrp + 4) > (int)*v4 )
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
  v90 = 0;
  Connection = ObReferenceObjectByHandle(
                 *(HANDLE *)&v11->Type,
                 (unsigned __int8)HIBYTE(*(_WORD *)(a2 + 24)) >> 6,
                 (POBJECT_TYPE)IoFileObjectType,
                 Irp->RequestorMode,
                 &v90,
                 0);
  v21 = v90;
  Object = v90;
  if ( Connection < 0 )
    goto LABEL_11;
  if ( IoGetRelatedDeviceObject((PFILE_OBJECT)v90) != AfdDeviceObject
    || (v22 = v21[3], v95 = v22, (*(_DWORD *)(v22 + 8) & 1) == 0)
    || *(_BYTE *)(v22 + 2) == 6
    || (*(_DWORD *)(v22 + 8) & 0x800) != 0 )
  {
LABEL_162:
    Connection = -1073741816;
    goto LABEL_11;
  }
  v96 = Src;
  v97 = v82;
  v83 = v17;
  if ( (BYTE2(xmmword_1400875E0) & 8) != 0 )
    WPP_SF_qq(1043, 24, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids, v22, Irp);
  if ( (*(_DWORD *)(v22 + 8) & 2) == 0 || (*(_DWORD *)(v22 + 8) & 0x100) != 0 )
  {
    while ( 1 )
    {
      FreeConnection = AfdGetFreeConnection(v22, 0, (__int64 *)&v80);
      v24 = (__int64)FreeConnection;
      Irql = FreeConnection;
      if ( !FreeConnection )
        goto LABEL_110;
      v26 = v80;
      if ( !v80 )
        goto LABEL_110;
      if ( (BYTE1(xmmword_1400875E0) & 1) != 0 )
        WPP_SF_q(1032, 25, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids, FreeConnection);
      CurrentStackLocation = v26->Tail.Overlay.CurrentStackLocation;
      Parameters = CurrentStackLocation->Parameters.CreatePipe.Parameters;
      Irql = (PSLIST_ENTRY)*((_QWORD *)Parameters + 3);
      v94 = (__int64)Irql;
      if ( (*(_DWORD *)(v22 + 8) & 0x100) != 0 )
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
        _InterlockedDecrement((volatile signed __int32 *)(v22 + 176));
        ExpInterlockedPushEntrySList((PSLIST_HEADER)(v22 + 144), (PSLIST_ENTRY)(v24 + 176));
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
              v26 = v80;
              Handle = v80->Tail.Overlay.DriverContext[3];
              v31 = 0;
              LOBYTE(Length) = 0;
            }
            else
            {
              v31 = ObOpenObjectByPointer(Parameters, 0x40u, 0, 0x2000000u, (POBJECT_TYPE)IoFileObjectType, 1, &Handle);
              LOBYTE(Length) = 1;
              v26 = v80;
            }
            if ( v31 >= 0 )
            {
              v34 = (__int64)Irql;
              KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)&Irql[3].Next + 1, &LockHandle);
              if ( (*(_DWORD *)(v34 + 8) & 0x800) != 0 )
              {
                KeReleaseInStackQueuedSpinLock(&LockHandle);
                if ( (BYTE2(xmmword_1400875E0) & 8) != 0 )
                  WPP_SF_q(1043, 27, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids, v34);
              }
              else
              {
                _InterlockedExchange64((volatile __int64 *)&v26->CancelRoutine, (__int64)AfdSanCancelAccept);
                if ( !v26->Cancel )
                {
                  v35 = v34;
                  v36 = v26->MdlAddress;
                  if ( *(_BYTE *)(v34 + 188) )
                  {
                    v37 = *((_WORD *)&v82->Flags + 2) + 2;
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
                      (char *)&v82->Flags + 6,
                      v37);
                    *(_WORD *)&v42[Length - 2] = v37;
                    v35 = (__int64)Irql;
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
                      FileAttributes = (unsigned __int16)Irql;
                    }
                    v49 = &v48[v39->Parameters.Read.Length];
                    v50 = v92;
                    v51 = *(unsigned __int16 *)v92;
                    if ( *(_BYTE *)(v35 + 188) )
                    {
                      v52 = v51 + 2;
                      v53 = v51 + 2;
                      if ( v52 >= (unsigned __int64)FileAttributes - 2 )
                        v53 = FileAttributes - 2;
                      v54 = v53;
                      v55 = v39->Parameters.Read.ByteOffset.LowPart;
                      RtlMoveVolatileMemory(v49, (char *)v92 + 2, v53);
                      *(_WORD *)&v49[v55 - 2] = v54;
                      v26 = v80;
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
                  AfdSanInitEndpoint(v93, Parameters, v82->MdlAddress);
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
                  IoReleaseCancelSpinLock((KIRQL)Irql);
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
      AfdCleanupSuperAccept((__int64)v26, v31);
      IofCompleteRequest(v26, AfdPriorityBoost);
    }
  }
  Irql = 0;
  if ( (*(_DWORD *)(v22 + 8) & 0x100) != 0 || (v23 = 1, (*(_DWORD *)(v22 + 16) & 0x200) == 0) )
    v23 = 0;
  Connection = AfdCreateConnection(
                 v22,
                 *(void **)(v22 + 272),
                 *(void **)(v22 + 256),
                 v23,
                 0,
                 (*(_DWORD *)(v22 + 8) >> 7) & 1,
                 *(struct _KPROCESS **)(v22 + 48),
                 (__int64 *)&Irql);
  if ( Connection < 0 )
  {
LABEL_11:
    if ( Object )
      ObfDereferenceObject(Object);
    Irp->IoStatus.Status = Connection;
    IofCompleteRequest(Irp, AfdPriorityBoost);
    return (unsigned int)Connection;
  }
  _InterlockedDecrement((volatile signed __int32 *)(v22 + 176));
  v24 = (__int64)Irql;
LABEL_110:
  if ( !v24 )
  {
LABEL_126:
    Connection = -1073741670;
    goto LABEL_11;
  }
  v89 = 0;
  v64 = Size;
  if ( (*(_DWORD *)(v22 + 8) & 0x100) != 0 )
  {
    v64 = Size - 6;
    v83 = Size - 6;
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
      PplFreeToLookasideList((__int64)PplAddressPool, *(void **)(v24 + 152));
    *v65 = 0;
LABEL_119:
    v66 = 0;
  }
  if ( !v66 )
  {
    v68 = v64 > (unsigned int)AfdStandardAddressLength
        ? (void *)ExAllocatePool2(97, v64, 1382311489)
        : AfdAllocateZeroedFromLookasideList(0, v64);
    *v65 = v68;
    if ( !*v65 )
    {
      AfdSanReleaseConnection(v22, v24, 1);
      goto LABEL_126;
    }
  }
  *(_DWORD *)(v24 + 160) = v64;
  if ( (*(_DWORD *)(v22 + 8) & 0x100) != 0 )
    v69 = (char *)&v82->Flags + 6;
  else
    v69 = Src;
  memmove(*v65, v69, v64);
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v22 + 56), &LockHandle);
  *(_QWORD *)(v24 + 40) = 0;
  *(_QWORD *)(a2 + 32) = v24;
  _InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, (__int64)AfdSanCancelConnect);
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
      IoReleaseCancelSpinLock((KIRQL)Irql);
    }
    AfdSanReleaseConnection(v22, v24, 1);
    Connection = -1073741536;
    goto LABEL_11;
  }
  Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  *(_QWORD *)(v24 + 8) = v22;
  if ( _InterlockedIncrement64((volatile signed __int64 *)(v22 + 64)) <= 1 )
    __fastfail(0xEu);
  *(_QWORD *)(v24 + 40) = Irp;
  *(_DWORD *)(v24 + 4) |= 0x20000000u;
  *(_WORD *)(v24 + 2) = 1;
  *((_QWORD *)&v89 + 1) = &v89;
  *(_QWORD *)&v89 = &v89;
  while ( 1 )
  {
    if ( (*(_DWORD *)(v22 + 8) & 2) == 0 && AfdServiceSuperAccept(v22, v24, &LockHandle, (__int64)&v89) )
      goto LABEL_156;
    v70 = *(_QWORD **)(v22 + 128);
    if ( v70 == (_QWORD *)(v22 + 128) )
      break;
    v71 = *v70;
    if ( *(_QWORD **)(*v70 + 8LL) != v70 )
      goto LABEL_161;
    v72 = (_QWORD *)v70[1];
    if ( (_QWORD *)*v72 != v70 )
      goto LABEL_161;
    v73 = v70 - 21;
    *v72 = v71;
    *(_QWORD *)(v71 + 8) = v72;
    *v70 = 0;
    if ( (BYTE2(xmmword_1400875E0) & 8) != 0 )
      WPP_SF_q(1043, 28, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids, v73);
    if ( (int)AfdServiceWaitForListen((PIRP)v73, v24, &LockHandle, 0) >= 0 )
      goto LABEL_160;
    AfdNotifySockIndicateEventsUnlock((struct _EX_RUNDOWN_REF *)v22, &LockHandle, 0);
    if ( !_InterlockedExchange64(v73 + 13, 0) )
    {
      LOBYTE(Irql) = 0;
      IoAcquireCancelSpinLock((PKIRQL)&Irql);
      IoReleaseCancelSpinLock((KIRQL)Irql);
    }
    IofCompleteRequest((PIRP)v73, AfdPriorityBoost);
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v22 + 56), &LockHandle);
  }
  v74 = *(_QWORD **)(v22 + 104);
  if ( *v74 != v22 + 96 )
    goto LABEL_161;
  *(_QWORD *)(v24 + 176) = v22 + 96;
  *(_QWORD *)(v24 + 184) = v74;
  *v74 = v24 + 176;
  *(_QWORD *)(v22 + 104) = v24 + 176;
  if ( (BYTE2(xmmword_1400875E0) & 8) != 0 )
    WPP_SF_q(1043, 29, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids, v24);
  AfdIndicateEventSelectEvent(v22, 128, 0);
  AfdNotifySockEventsChangedUnderLock(v22, 128, 0);
  if ( AfdIndicatePollEvent(v75, 0x80u, 0, &LockHandle) )
    p_LockHandle = 0;
  else
    p_LockHandle = &LockHandle;
  AfdNotifySockIndicateEventsUnlock((struct _EX_RUNDOWN_REF *)v22, p_LockHandle, 0);
LABEL_156:
  while ( (__int128 *)v89 != &v89 )
  {
    v77 = (IRP *)(v89 - 168);
    v78 = *(struct _LIST_ENTRY **)v89;
    if ( *(_QWORD *)(*(_QWORD *)v89 + 8LL) != (_QWORD)v89 )
      goto LABEL_161;
    Blink = v77->Tail.Overlay.ListEntry.Blink;
    if ( Blink->Flink != (struct _LIST_ENTRY *)v89 )
      goto LABEL_161;
    Blink->Flink = v78;
    v78->Blink = Blink;
    IofCompleteRequest(v77, AfdPriorityBoost);
  }
LABEL_160:
  ObfDereferenceObject(Object);
  return 259;
}

```

## disassembly

```asm
0x140059910  mov     [rsp+arg_8], rdx
0x140059915  mov     [rsp+Irp], rcx
0x14005991a  push    rbx
0x14005991b  push    rsi
0x14005991c  push    rdi
0x14005991d  push    r12
0x14005991f  push    r13
0x140059921  push    r14
0x140059923  push    r15
0x140059925  sub     rsp, 0F0h
0x14005992c  mov     r13, rdx
0x14005992f  mov     r12, rcx
0x140059932  xorps   xmm0, xmm0
0x140059935  xor     eax, eax
0x140059937  movups  xmmword ptr [rsp+128h+LockHandle.LockQueue.Next], xmm0
0x14005993c  mov     qword ptr [rsp+128h+LockHandle.OldIrql], rax
0x140059941  xor     r15d, r15d
0x140059944  mov     [rsp+128h+var_E8], r15
0x140059949  mov     [rsp+128h+Object], r15
0x140059951  lea     rbx, [rdx+10h]
0x140059955  call    cs:__imp_IoIs32bitProcess
0x14005995c  nop     dword ptr [rax+rax+00h]
0x140059961  test    al, al
0x140059963  jz      loc_1400599F5
0x140059969  mov     eax, [rbx]
0x14005996b  cmp     eax, 14h
0x14005996e  jb      loc_140059A53
0x140059974  cmp     eax, 0FFFFFFF3h
0x140059977  ja      loc_140059A53
0x14005997d  mov     rsi, [r12+18h]
0x140059982  lea     r14d, [rax+0Ch]
0x140059986  mov     edx, r14d
0x140059989  lea     ecx, [r15+63h]
0x14005998d  mov     r8d, 73646641h
0x140059993  call    cs:__imp_ExAllocatePool2
0x14005999a  nop     dword ptr [rax+rax+00h]
0x14005999f  mov     rdi, rax
0x1400599a2  mov     [rsp+128h+var_40], rax
0x1400599aa  movsxd  rax, dword ptr [rsi]
0x1400599ad  mov     [rdi], rax
0x1400599b0  mov     eax, [rsi+4]
0x1400599b3  mov     [rdi+8], rax
0x1400599b7  mov     r8d, [rbx]
0x1400599ba  sub     r8d, 8; Size
0x1400599be  lea     rdx, [rsi+8]; Src
0x1400599c2  lea     rcx, [rdi+10h]; void *
0x1400599c6  call    memmove
0x1400599cb  xor     edx, edx; Tag
0x1400599cd  mov     rcx, [r12+18h]; P
0x1400599d2  call    cs:__imp_ExFreePoolWithTag
0x1400599d9  nop     dword ptr [rax+rax+00h]
0x1400599de  mov     [r12+18h], rdi
0x1400599e3  mov     [rbx], r14d
0x1400599e6  jmp     short loc_1400599F5
0x1400599e8  mov     r14d, eax
0x1400599eb  mov     r12, [rsp+128h+Irp]
0x1400599f3  jmp     short loc_140059A59
0x1400599f5  mov     rax, [r13+30h]
0x1400599f9  mov     rsi, [rax+18h]
0x1400599fd  mov     [rsp+128h+var_68], rsi
0x140059a05  mov     [r12+38h], r15
0x140059a0a  mov     eax, [rbx]
0x140059a0c  cmp     eax, 20h ; ' '
0x140059a0f  jb      short loc_140059A53
0x140059a11  mov     r14, [r12+18h]
0x140059a16  mov     [rsp+128h+var_D8], r14
0x140059a1b  lea     rcx, [r14+10h]
0x140059a1f  mov     [rsp+128h+Src], rcx
0x140059a24  cmp     dword ptr [rcx], 2
0x140059a27  jnz     short loc_140059A53
0x140059a29  movzx   ecx, word ptr [r14+14h]
0x140059a2e  add     rcx, 1Eh
0x140059a32  cmp     rax, rcx
0x140059a35  jb      short loc_140059A53
0x140059a37  mov     rcx, r12; Irp
0x140059a3a  call    cs:__imp_IoIs32bitProcess
0x140059a41  nop     dword ptr [rax+rax+00h]
0x140059a46  mov     ecx, [r13+8]
0x140059a4a  test    al, al
0x140059a4c  jz      short loc_140059AA6
0x140059a4e  cmp     ecx, 8
0x140059a51  jnb     short loc_140059AAB
0x140059a53  mov     r14d, 0C000000Dh
0x140059a59  mov     rbx, [rsp+128h+Object]
0x140059a61  test    rbx, rbx
0x140059a64  jz      short loc_140059A75
0x140059a66  mov     rcx, rbx; Object
0x140059a69  call    cs:__imp_ObfDereferenceObject
0x140059a70  nop     dword ptr [rax+rax+00h]
0x140059a75  mov     [r12+30h], r14d
0x140059a7a  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x140059a80  mov     rcx, r12; Irp
0x140059a83  call    cs:__imp_IofCompleteRequest
0x140059a8a  nop     dword ptr [rax+rax+00h]
0x140059a8f  mov     eax, r14d
0x140059a92  add     rsp, 0F0h
0x140059a99  pop     r15
0x140059a9b  pop     r14
0x140059a9d  pop     r13
0x140059a9f  pop     r12
0x140059aa1  pop     rdi
0x140059aa2  pop     rsi
0x140059aa3  pop     rbx
0x140059aa4  retn
0x140059aa6  cmp     ecx, 10h
0x140059aa9  jb      short loc_140059A53
0x140059aab  movzx   ecx, word ptr [r14+14h]
0x140059ab0  lea     edi, [rcx+8]
0x140059ab3  mov     [rsp+128h+Size], rdi
0x140059abb  add     rcx, 18h
0x140059abf  add     rcx, r14
0x140059ac2  mov     [rsp+128h+var_70], rcx
0x140059aca  movzx   eax, word ptr [rcx]
0x140059acd  sub     rax, [r12+18h]
0x140059ad2  add     rcx, 4
0x140059ad6  add     rcx, rax
0x140059ad9  movsxd  rax, dword ptr [rbx]
0x140059adc  cmp     rcx, rax
0x140059adf  jg      loc_140059A53
0x140059ae5  mov     eax, 0AFDh
0x140059aea  cmp     [rsi], ax
0x140059aed  jnz     loc_14005A7D4
0x140059af3  mov     rbx, [rsi+30h]
0x140059af7  call    cs:__imp_IoGetCurrentProcess
0x140059afe  nop     dword ptr [rax+rax+00h]
0x140059b03  cmp     rbx, rax
0x140059b06  jnz     loc_14005A7D4
0x140059b0c  mov     rcx, [r14+8]; Address
0x140059b10  test    rcx, rcx
0x140059b13  jnz     short loc_140059B43
0x140059b15  test    byte ptr cs:xmmword_1400875E0+2, 8
0x140059b1c  jz      short loc_140059B32
0x140059b1e  lea     edx, [rcx+17h]
0x140059b21  mov     ecx, 413h
0x140059b26  lea     r8, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids
0x140059b2d  call    WPP_SF_
0x140059b32  mov     ecx, 0C000000Dh; Status
0x140059b37  call    cs:__imp_ExRaiseStatus
0x140059b43  cmp     [r12+40h], r15b
0x140059b48  jz      short loc_140059B60
0x140059b4a  mov     edx, 14h; Length
0x140059b4f  lea     r8d, [rdx-10h]; Alignment
0x140059b53  call    cs:__imp_ProbeForWrite
0x140059b5a  nop     dword ptr [rax+rax+00h]
0x140059b5f  nop
0x140059b60  mov     esi, 1
0x140059b65  mov     rax, [rsp+128h+Src]
0x140059b6a  mov     [rax], esi
0x140059b6c  mov     rcx, r12; Irp
0x140059b6f  call    cs:__imp_IoIs32bitProcess
0x140059b76  nop     dword ptr [rax+rax+00h]
0x140059b7b  mov     rax, [r12+8]
0x140059b80  mov     ebx, [rax+2Ch]
0x140059b83  add     rbx, [rax+20h]
0x140059b87  mov     [rsp+128h+var_80], r15
0x140059b8f  mov     edx, [r13+18h]
0x140059b93  shr     edx, 0Eh
0x140059b96  and     edx, 3; DesiredAccess
0x140059b99  mov     [rsp+128h+HandleInformation], r15; HandleInformation
0x140059b9e  lea     rax, [rsp+128h+var_80]
0x140059ba6  mov     [rsp+128h+ObjectType], rax; Object
0x140059bab  mov     r9b, [r12+40h]; AccessMode
0x140059bb0  mov     r8, cs:__imp_IoFileObjectType
0x140059bb7  mov     r8, [r8]; ObjectType
0x140059bba  mov     rcx, [r14]; Handle
0x140059bbd  call    cs:__imp_ObReferenceObjectByHandle
0x140059bc4  nop     dword ptr [rax+rax+00h]
0x140059bc9  mov     r14d, eax
0x140059bcc  mov     r13, [rsp+128h+var_80]
0x140059bd4  mov     [rsp+128h+Object], r13
0x140059bdc  test    eax, eax
0x140059bde  js      loc_140059A59
0x140059be4  mov     rcx, r13; FileObject
0x140059be7  call    cs:__imp_IoGetRelatedDeviceObject
0x140059bee  nop     dword ptr [rax+rax+00h]
0x140059bf3  cmp     rax, cs:AfdDeviceObject
0x140059bfa  jnz     loc_14005A7D4
0x140059c00  mov     r13, [r13+18h]
0x140059c04  mov     [rsp+128h+var_58], r13
0x140059c0c  mov     eax, [r13+8]
0x140059c10  test    sil, al
0x140059c13  jz      loc_14005A7D4
0x140059c19  cmp     byte ptr [r13+2], 6
0x140059c1e  jz      loc_14005A7D4
0x140059c24  mov     eax, [r13+8]
0x140059c28  bt      eax, 0Bh
0x140059c2c  jb      loc_14005A7D4
0x140059c32  mov     rax, [rsp+128h+Src]
0x140059c37  mov     [rsp+128h+var_50], rax
0x140059c3f  mov     rdx, [rsp+128h+var_D8]
0x140059c44  mov     [rsp+128h+var_48], rdx
0x140059c4c  mov     [rsp+128h+var_D0], edi
0x140059c50  test    byte ptr cs:xmmword_1400875E0+2, 8
0x140059c57  jz      short loc_140059C75
0x140059c59  lea     edx, [rsi+17h]
0x140059c5c  mov     ecx, 413h
0x140059c61  mov     [rsp+128h+ObjectType], r12
0x140059c66  mov     r9, r13
0x140059c69  lea     r8, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids
0x140059c70  call    WPP_SF_qq
0x140059c75  mov     eax, [r13+8]
0x140059c79  test    al, 2
0x140059c7b  jz      loc_140059D0F
0x140059c81  mov     eax, [r13+8]
0x140059c85  bt      eax, 8
0x140059c89  jb      loc_140059D0F
0x140059c8f  mov     [rsp+128h+Irql], r15
0x140059c97  mov     eax, [r13+8]
0x140059c9b  bt      eax, 8
0x140059c9f  jb      short loc_140059CAE
0x140059ca1  test    dword ptr [r13+10h], 200h
0x140059ca9  mov     r9b, sil
0x140059cac  jnz     short loc_140059CB1
0x140059cae  mov     r9b, r15b
0x140059cb1  mov     eax, [r13+8]
0x140059cb5  shr     eax, 7
0x140059cb8  and     eax, esi
0x140059cba  lea     rcx, [rsp+128h+Irql]
0x140059cc2  mov     [rsp+128h+var_F0], rcx
0x140059cc7  mov     rcx, [r13+30h]
0x140059ccb  mov     [rsp+128h+Handle], rcx
0x140059cd0  mov     dword ptr [rsp+128h+HandleInformation], eax
0x140059cd4  mov     dword ptr [rsp+128h+ObjectType], r15d
0x140059cd9  mov     r8, [r13+100h]
0x140059ce0  mov     rdx, [r13+110h]
0x140059ce7  mov     rcx, r13
0x140059cea  call    AfdCreateConnection
0x140059cef  mov     r14d, eax
0x140059cf2  test    eax, eax
0x140059cf4  js      loc_140059A59
0x140059cfa  lock dec dword ptr [r13+0B0h]
0x140059d02  mov     rdi, [rsp+128h+Irql]
0x140059d0a  jmp     loc_14005A357
0x140059d0f  mov     r14d, 0C0000008h
0x140059d15  lea     r8, [rsp+128h+var_E8]
0x140059d1a  xor     edx, edx
0x140059d1c  mov     rcx, r13
0x140059d1f  call    AfdGetFreeConnection
0x140059d24  mov     rdi, rax
0x140059d27  mov     [rsp+128h+Irql], rax
0x140059d2f  test    rax, rax
0x140059d32  jz      loc_14005A352
0x140059d38  mov     rsi, [rsp+128h+var_E8]
0x140059d3d  test    rsi, rsi
0x140059d40  jz      loc_14005A352
0x140059d46  test    byte ptr cs:xmmword_1400875E0+1, 1
0x140059d4d  jz      short loc_140059D68
0x140059d4f  mov     edx, 19h
0x140059d54  mov     ecx, 408h
0x140059d59  mov     r9, rax
0x140059d5c  lea     r8, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids
0x140059d63  call    WPP_SF_q
0x140059d68  mov     rax, [rsi+0B8h]
0x140059d6f  mov     [rsp+128h+var_A8], rax
0x140059d77  mov     rax, [rax+20h]
0x140059d7b  mov     [rsp+128h+var_78], rax
0x140059d83  mov     rax, [rax+18h]
0x140059d87  mov     [rsp+128h+Irql], rax
0x140059d8f  mov     [rsp+128h+var_60], rax
0x140059d97  mov     eax, [r13+8]
0x140059d9b  bt      eax, 8
0x140059d9f  jb      short loc_140059DC5
0x140059da1  lock dec dword ptr [r13+0B0h]
0x140059da9  lea     rdx, [rdi+0B0h]; ListEntry
0x140059db0  lea     rcx, [r13+90h]; ListHead
0x140059db7  call    cs:__imp_ExpInterlockedPushEntrySList
0x140059dbe  nop     dword ptr [rax+rax+00h]
0x140059dc3  jmp     short loc_140059DEB
0x140059dc5  or      rax, 0FFFFFFFFFFFFFFFFh
0x140059dc9  lock xadd [rdi+30h], rax
0x140059dcf  sub     rax, 1
0x140059dd3  jg      short loc_140059DEB
0x140059dd5  test    rax, rax
0x140059dd8  jnz     short loc_140059DE4
0x140059dda  mov     rcx, rdi
0x140059ddd  call    AfdCloseConnection
0x140059de2  jmp     short loc_140059DEB
0x140059de4  mov     ecx, 0Eh
0x140059de9  int     29h; Win8: RtlFailFast(ecx)
0x140059deb  mov     rcx, [r12+98h]; Thread
0x140059df3  call    cs:__imp_IoThreadToProcess
0x140059dfa  nop     dword ptr [rax+rax+00h]
0x140059dff  mov     rdi, rax
0x140059e02  call    cs:__imp_IoGetCurrentProcess
0x140059e09  nop     dword ptr [rax+rax+00h]
0x140059e0e  cmp     rdi, rax
0x140059e11  jnz     loc_14005A32B
0x140059e17  mov     rax, [rsp+128h+var_A8]
0x140059e1f  mov     rcx, [rsp+128h+Size]
0x140059e27  cmp     ecx, [rax+10h]
0x140059e2a  ja      loc_14005A324
0x140059e30  mov     rcx, [rsi+8]; MemoryDescriptorList
0x140059e34  call    AfdMapMdlChain
0x140059e39  test    eax, eax
0x140059e3b  js      loc_14005A32E
0x140059e41  mov     [rsp+128h+var_E0], r15
0x140059e46  mov     rcx, [rsi+98h]; Thread
0x140059e4d  mov     rdi, [r12+98h]
0x140059e55  call    cs:__imp_IoThreadToProcess
0x140059e5c  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
