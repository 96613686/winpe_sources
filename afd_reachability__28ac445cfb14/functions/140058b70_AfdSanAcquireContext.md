# AfdSanAcquireContext

- ea: `0x140058b70`
- end: `0x1400593e3`
- name: `AfdSanAcquireContext`
- size: `2163`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14001ef30`

## callees

- `0x140019190`
- `0x1400191f0`
- `0x14002fd5c`
- `0x140041a14`
- `0x1400445b8`
- `0x140058b70`
- `0x14005aa70`
- `0x14005d69c`
- `0x1400726d0`
- `0x1400930cc`
- `0x1400931d0`
- `0x14009327c`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x140058bd9`
- `ntoskrnl!ExRaiseStatus` at `0x140058c4e`
- `ntoskrnl!ExRaiseStatus` at `0x140058ca6`
- `ntoskrnl!ExRaiseStatus` at `0x140058cd7`
- `ntoskrnl!ExRaiseStatus` at `0x140058d32`
- `ntoskrnl!ExRaiseStatus` at `0x140058d7d`
- `ntoskrnl!ExRaiseStatus` at `0x140058dd8`
- `ntoskrnl!ExRaiseStatus` at `0x140058e10`
- `ntoskrnl!ExRaiseStatus` at `0x140058bd9`
- `ntoskrnl!ExRaiseStatus` at `0x140058c4e`
- `ntoskrnl!ExRaiseStatus` at `0x140058ca6`
- `ntoskrnl!ExRaiseStatus` at `0x140058cd7`
- `ntoskrnl!ExRaiseStatus` at `0x140058d32`
- `ntoskrnl!ExRaiseStatus` at `0x140058d7d`
- `ntoskrnl!ExRaiseStatus` at `0x140058dd8`
- `ntoskrnl!ExRaiseStatus` at `0x140058e10`
- `ntoskrnl!MmMapLockedPages` at `0x140058fcd`
- `ntoskrnl!MmMapLockedPages` at `0x140059010`
- `ntoskrnl!MmMapLockedPages` at `0x140058fcd`
- `ntoskrnl!MmMapLockedPages` at `0x140059010`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140058d1c`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140058dc2`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140058d1c`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140058dc2`
- `ntoskrnl!IoFreeMdl` at `0x140059385`
- `ntoskrnl!IoFreeMdl` at `0x140059385`
- `ntoskrnl!MmUnlockPages` at `0x140059376`
- `ntoskrnl!MmUnlockPages` at `0x140059376`
- `ntoskrnl!MmProbeAndLockPages` at `0x140058cec`
- `ntoskrnl!MmProbeAndLockPages` at `0x140058d8f`
- `ntoskrnl!MmProbeAndLockPages` at `0x140058cec`
- `ntoskrnl!MmProbeAndLockPages` at `0x140058d8f`
- `ntoskrnl!IoAllocateMdl` at `0x140058cbd`
- `ntoskrnl!IoAllocateMdl` at `0x140058d5d`
- `ntoskrnl!IoAllocateMdl` at `0x140058cbd`
- `ntoskrnl!IoAllocateMdl` at `0x140058d5d`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140058bf3`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140058c68`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140058bf3`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140058c68`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140059121`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400591ee`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140059121`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400591ee`
- `ntoskrnl!IofCompleteRequest` at `0x140059099`
- `ntoskrnl!IofCompleteRequest` at `0x140059310`
- `ntoskrnl!IofCompleteRequest` at `0x1400593c1`
- `ntoskrnl!IofCompleteRequest` at `0x140059099`
- `ntoskrnl!IofCompleteRequest` at `0x140059310`
- `ntoskrnl!IofCompleteRequest` at `0x1400593c1`
- `ntoskrnl!ObfDereferenceObject` at `0x14005932e`
- `ntoskrnl!ObfDereferenceObject` at `0x1400593a9`
- `ntoskrnl!ObfDereferenceObject` at `0x14005932e`
- `ntoskrnl!ObfDereferenceObject` at `0x1400593a9`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14005910e`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400591db`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14005910e`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400591db`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140058f66`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140058faf`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005906f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400590e6`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400591b3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140059289`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140058f66`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140058faf`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005906f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400590e6`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400591b3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140059289`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140058f48`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400590bd`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140058f48`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400590bd`
- `ntoskrnl!IoFileObjectType` at `0x140058e60`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140058e6f`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140058e6f`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140059220`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400592d1`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140059220`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400592d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005903d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005903d`
- `ntoskrnl!IoGetCurrentProcess` at `0x140058efc`
- `ntoskrnl!IoGetCurrentProcess` at `0x140058efc`
- `ntoskrnl!IoIs32bitProcess` at `0x140058baf`
- `ntoskrnl!IoIs32bitProcess` at `0x140058baf`
- `ntoskrnl!ProbeForWrite` at `0x140058e2b`
- `ntoskrnl!ProbeForWrite` at `0x140058e2b`

## pseudocode

```c
__int64 __fastcall AfdSanAcquireContext(PIRP Irp, __int64 a2)
{
  unsigned int v4; // edi
  BOOLEAN v5; // al
  unsigned int v6; // ecx
  KPROCESSOR_MODE RequestorMode; // cl
  void *v8; // rdx
  PVOID v9; // rcx
  ULONG v10; // edx
  KPROCESSOR_MODE v11; // cl
  void *v12; // rdx
  struct _MDL *Mdl; // rax
  PMDL MdlAddress; // rcx
  PVOID MappedSystemVa; // rax
  ULONG v16; // edx
  PMDL v17; // rbx
  struct _MDL *Next; // rcx
  PMDL v19; // rax
  struct _MDL *v20; // rcx
  PVOID v21; // rax
  int v22; // ebx
  struct _FILE_OBJECT *v23; // r13
  struct _KPROCESS **v24; // rbx
  __int64 v25; // r14
  __int64 v26; // r12
  struct _KPROCESS *v27; // rbx
  unsigned int v28; // ebx
  unsigned int v29; // ebx
  char *v30; // r12
  PMDL v31; // rcx
  PVOID v32; // rax
  __int64 v33; // rdx
  PMDL v34; // rax
  struct _MDL *v35; // rcx
  PVOID v36; // rax
  int v37; // eax
  int v38; // ecx
  struct _LIST_ENTRY *v39; // rbx
  char v40; // r15
  struct _LIST_ENTRY *v41; // rdx
  HANDLE CurrentProcessId; // rax
  int v43; // esi
  IRP *v44; // rax
  __int128 v46; // [rsp+38h] [rbp-80h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+48h] [rbp-70h] BYREF
  volatile void *Address[2]; // [rsp+60h] [rbp-58h] BYREF
  PVOID VirtualAddress[2]; // [rsp+70h] [rbp-48h]
  struct _KPROCESS **Irql; // [rsp+D0h] [rbp+18h] BYREF
  PVOID Object; // [rsp+D8h] [rbp+20h] BYREF

  v4 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  *(_OWORD *)Address = 0;
  *(_OWORD *)VirtualAddress = 0;
  v5 = IoIs32bitProcess(Irp);
  v6 = *(_DWORD *)(a2 + 16);
  if ( v5 )
  {
    v46 = 0;
    if ( v6 < 0x10 )
      ExRaiseStatus(-1073741811);
    RequestorMode = Irp->RequestorMode;
    if ( RequestorMode && (*(_BYTE *)(a2 + 32) & 3) != 0 )
      ExRaiseDatatypeMisalignment();
    v8 = *(void **)(a2 + 32);
    if ( RequestorMode )
      RtlCopyFromUser(&v46, v8, 0x10u);
    else
      RtlCopyVolatileMemory(&v46, v8, 0x10u);
    Address[0] = (volatile void *)(int)v46;
    Address[1] = (volatile void *)DWORD1(v46);
    v9 = (PVOID)DWORD2(v46);
    VirtualAddress[0] = (PVOID)DWORD2(v46);
    v10 = HIDWORD(v46);
    LODWORD(VirtualAddress[1]) = HIDWORD(v46);
  }
  else
  {
    if ( v6 < 0x20 )
      ExRaiseStatus(-1073741811);
    v11 = Irp->RequestorMode;
    if ( v11 && (*(_BYTE *)(a2 + 32) & 3) != 0 )
      ExRaiseDatatypeMisalignment();
    v12 = *(void **)(a2 + 32);
    if ( v11 )
      RtlCopyFromUser(Address, v12, 0x20u);
    else
      RtlCopyVolatileMemory(Address, v12, 0x20u);
    v10 = (ULONG)VirtualAddress[1];
    v9 = VirtualAddress[0];
  }
  if ( !v10 )
    ExRaiseStatus(-1073741811);
  Mdl = IoAllocateMdl(v9, v10, 0, 1u, 0);
  Irp->MdlAddress = Mdl;
  if ( !Mdl )
    ExRaiseStatus(-1073741670);
  MmProbeAndLockPages(Mdl, Irp->RequestorMode, IoWriteAccess);
  MdlAddress = Irp->MdlAddress;
  if ( (MdlAddress->MdlFlags & 5) != 0 )
    MappedSystemVa = MdlAddress->MappedSystemVa;
  else
    MappedSystemVa = MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000000u);
  if ( !MappedSystemVa )
    ExRaiseStatus(-1073741670);
  v16 = *(_DWORD *)(a2 + 8);
  if ( v16 )
  {
    v17 = Irp->MdlAddress;
    v17->Next = IoAllocateMdl(Irp->UserBuffer, v16, 0, 1u, 0);
    Next = Irp->MdlAddress->Next;
    if ( !Next )
      ExRaiseStatus(-1073741670);
    MmProbeAndLockPages(Next, Irp->RequestorMode, IoWriteAccess);
    v19 = Irp->MdlAddress;
    v20 = v19->Next;
    if ( (v19->Next->MdlFlags & 5) != 0 )
      v21 = v20->MappedSystemVa;
    else
      v21 = MmMapLockedPagesSpecifyCache(v20, 0, MmCached, 0, 0, 0x40000000u);
    if ( !v21 )
      ExRaiseStatus(-1073741670);
  }
  if ( !Address[1] )
  {
    if ( (BYTE2(xmmword_1400875E0) & 8) != 0 )
      WPP_SF_(1043, (unsigned int)(LODWORD(Address[1]) + 36), WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids);
    ExRaiseStatus(-1073741811);
  }
  if ( Irp->RequestorMode )
    ProbeForWrite(Address[1], 0x14u, 4u);
  Object = 0;
  v22 = ObReferenceObjectByHandle(
          (HANDLE)Address[0],
          (unsigned __int8)HIBYTE(*(_WORD *)(a2 + 24)) >> 6,
          (POBJECT_TYPE)IoFileObjectType,
          Irp->RequestorMode,
          &Object,
          0);
  v23 = (struct _FILE_OBJECT *)Object;
  if ( v22 < 0 )
    goto LABEL_97;
  if ( *((PVOID *)Object + 1) != AfdDeviceObject )
    goto LABEL_45;
  v24 = *(struct _KPROCESS ***)(*(_QWORD *)(a2 + 48) + 24LL);
  Irql = v24;
  v25 = *((_QWORD *)Object + 3);
  if ( (BYTE2(xmmword_1400875E0) & 8) != 0 )
    WPP_SF_q(1043, 37, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids, *((_QWORD *)Object + 3));
  v26 = AfdLockEndpointContext(v25);
  *(_QWORD *)&v46 = v26;
  if ( *(_WORD *)v24 == 2813 )
  {
    v27 = v24[6];
    if ( v27 == IoGetCurrentProcess() && *(_WORD *)v25 == 6909 )
    {
      if ( *(_QWORD *)(v25 + 96) != AfdSanServiceHelper || Irql != (struct _KPROCESS **)AfdSanServiceHelper )
      {
        KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v25 + 56), &LockHandle);
        _InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, (__int64)&AfdSanCancelRequest);
        if ( Irp->Cancel )
        {
          Irp->Tail.Overlay.ListEntry.Flink = 0;
          KeReleaseInStackQueuedSpinLock(&LockHandle);
          if ( !_InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, 0) )
          {
            LOBYTE(Irql) = 0;
            IoAcquireCancelSpinLock((PKIRQL)&Irql);
            IoReleaseCancelSpinLock((KIRQL)Irql);
          }
          AfdUnlockEndpointContext(v25, v26);
          v22 = -1073741536;
          goto LABEL_97;
        }
        v37 = *(_DWORD *)(v25 + 156);
        if ( v37 == 259 || v37 == -1073741802 )
        {
          Irp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = 0;
          v40 = 0;
          v39 = 0;
        }
        else
        {
          if ( v37 < 0 || *(_BYTE *)(v25 + 161) )
          {
            if ( *(_BYTE *)(v25 + 161) )
              v37 = -1073741536;
            v22 = v37;
            Irp->Tail.Overlay.ListEntry.Flink = 0;
            KeReleaseInStackQueuedSpinLock(&LockHandle);
            if ( !_InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, 0) )
            {
              LOBYTE(Irql) = 0;
              IoAcquireCancelSpinLock((PKIRQL)&Irql);
              IoReleaseCancelSpinLock((KIRQL)Irql);
            }
            AfdUnlockEndpointContext(v25, v26);
            goto LABEL_97;
          }
          v38 = *(_DWORD *)(v25 + 148);
          v39 = (struct _LIST_ENTRY *)(unsigned int)(8 * v38 + 3);
          *(_DWORD *)(v25 + 148) = v38 + 1;
          Irp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = v39;
          *(_DWORD *)(v25 + 156) = 259;
          v40 = 1;
        }
        Irp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink = (struct _LIST_ENTRY *)Address[1];
        Irp->Tail.Overlay.DriverContext[2] = PsGetCurrentProcessId();
        Irp->Tail.Overlay.DriverContext[3] = Irql;
        Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
        v41 = *(struct _LIST_ENTRY **)(v25 + 136);
        if ( v41->Flink != (struct _LIST_ENTRY *)(v25 + 128) )
          __fastfail(3u);
        Irp->Tail.Overlay.ListEntry.Flink = (struct _LIST_ENTRY *)(v25 + 128);
        Irp->Tail.Overlay.ListEntry.Blink = v41;
        v41->Flink = &Irp->Tail.Overlay.ListEntry;
        *(_QWORD *)(v25 + 136) = &Irp->Tail.Overlay.ListEntry;
        Irp->Tail.Overlay.CurrentStackLocation->FileObject = v23;
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        AfdUnlockEndpointContext(v25, v26);
        if ( (BYTE2(xmmword_1400875E0) & 8) != 0 )
          WPP_SF_qqq(1043, 38, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids, v25, Irp, v39, 0);
        if ( v40 )
        {
          CurrentProcessId = PsGetCurrentProcessId();
          v43 = AfdSanNotifyRequest(v25, v39, 0, CurrentProcessId);
          if ( v43 < 0 )
          {
            v44 = (IRP *)AfdSanDequeueRequest(v25, v39);
            if ( v44 )
            {
              v44->IoStatus.Status = v43;
              IofCompleteRequest(v44, AfdPriorityBoost);
            }
            AfdSanRestartRequestProcessing(v25, 0);
          }
        }
        v4 = 259;
LABEL_95:
        ObfDereferenceObject(v23);
        return v4;
      }
      KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v25 + 56), &LockHandle);
      if ( *(_DWORD *)(v25 + 156) == -1073741802 )
      {
        v29 = *(_DWORD *)(v25 + 144);
        if ( LODWORD(VirtualAddress[1]) <= v29 && *(_DWORD *)(a2 + 8) + LODWORD(VirtualAddress[1]) >= v29 )
        {
          v30 = *(char **)(v25 + 112);
          *(_QWORD *)(v25 + 112) = 0;
          *(_DWORD *)(v25 + 144) = 0;
          KeReleaseInStackQueuedSpinLock(&LockHandle);
          v31 = Irp->MdlAddress;
          if ( (v31->MdlFlags & 5) != 0 )
            v32 = v31->MappedSystemVa;
          else
            v32 = MmMapLockedPages(v31, 0);
          RtlCopyVolatileMemory(v32, v30, LODWORD(VirtualAddress[1]));
          if ( *(_DWORD *)(a2 + 8) )
          {
            v33 = LODWORD(VirtualAddress[1]);
            Irp->IoStatus.Information = v29 - LODWORD(VirtualAddress[1]);
            v34 = Irp->MdlAddress;
            v35 = v34->Next;
            if ( (v34->Next->MdlFlags & 5) != 0 )
            {
              v36 = v35->MappedSystemVa;
            }
            else
            {
              v36 = MmMapLockedPages(v35, 0);
              v33 = LODWORD(VirtualAddress[1]);
            }
            RtlCopyVolatileMemory(v36, &v30[v33], Irp->IoStatus.Information);
          }
          else
          {
            Irp->IoStatus.Information = 0;
          }
          ExFreePoolWithTag(v30, 0x78646641u);
          *(volatile void **)(v25 + 112) = Address[1];
          v28 = 0;
          _InterlockedAdd((volatile signed __int32 *)(AfdSanServiceHelper + 132), 0xFFFFFFFE);
          v26 = v46;
          goto LABEL_69;
        }
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        v28 = -1073741789;
      }
      else
      {
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        v28 = -1073741536;
      }
      v4 = v28;
LABEL_69:
      AfdUnlockEndpointContext(v25, v26);
      Irp->IoStatus.Status = v28;
      IofCompleteRequest(Irp, AfdPriorityBoost);
      AfdSanRestartRequestProcessing(v25, v28);
      goto LABEL_95;
    }
  }
  AfdUnlockEndpointContext(v25, v26);
LABEL_45:
  v22 = -1073741816;
LABEL_97:
  if ( v23 )
    ObfDereferenceObject(v23);
  Irp->IoStatus.Status = v22;
  IofCompleteRequest(Irp, AfdPriorityBoost);
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x140058b70  mov     [rsp+arg_0], rcx
0x140058b75  push    rbx
0x140058b76  push    rsi
0x140058b77  push    rdi
0x140058b78  push    r12
0x140058b7a  push    r13
0x140058b7c  push    r14
0x140058b7e  push    r15
0x140058b80  sub     rsp, 80h
0x140058b87  mov     r15, rdx
0x140058b8a  mov     rsi, rcx
0x140058b8d  xor     edi, edi
0x140058b8f  xorps   xmm0, xmm0
0x140058b92  xor     eax, eax
0x140058b94  movups  xmmword ptr [rsp+0B8h+LockHandle.LockQueue.Next], xmm0
0x140058b99  mov     qword ptr [rsp+0B8h+LockHandle.OldIrql], rax
0x140058b9e  xorps   xmm1, xmm1
0x140058ba1  movups  xmmword ptr [rsp+0B8h+Address], xmm1
0x140058ba6  movups  xmmword ptr [rsp+0B8h+VirtualAddress], xmm1
0x140058bab  mov     [rsp+0B8h+var_88], edi
0x140058baf  call    cs:__imp_IoIs32bitProcess
0x140058bb6  nop     dword ptr [rax+rax+00h]
0x140058bbb  mov     ecx, [r15+10h]
0x140058bbf  test    al, al
0x140058bc1  jz      short loc_140058C3E
0x140058bc3  xorps   xmm0, xmm0
0x140058bc6  movups  [rsp+0B8h+var_80], xmm0
0x140058bcb  lea     r8d, [rdi+10h]
0x140058bcf  cmp     ecx, r8d
0x140058bd2  jnb     short loc_140058BE5
0x140058bd4  mov     ecx, 0C000000Dh; Status
0x140058bd9  call    cs:__imp_ExRaiseStatus
0x140058be5  mov     cl, [rsi+40h]
0x140058be8  test    cl, cl
0x140058bea  jz      short loc_140058BFF
0x140058bec  test    byte ptr [r15+20h], 3
0x140058bf1  jz      short loc_140058BFF
0x140058bf3  call    cs:__imp_ExRaiseDatatypeMisalignment
0x140058bfa  nop     dword ptr [rax+rax+00h]
0x140058bff  mov     rdx, [r15+20h]; Src
0x140058c03  test    cl, cl
0x140058c05  lea     rcx, [rsp+0B8h+var_80]; void *
0x140058c0a  jz      short loc_140058C13
0x140058c0c  call    RtlCopyFromUser
0x140058c11  jmp     short loc_140058C18
0x140058c13  call    RtlCopyVolatileMemory
0x140058c18  movsxd  rax, dword ptr [rsp+0B8h+var_80]
0x140058c1d  mov     [rsp+0B8h+Address], rax
0x140058c22  mov     eax, dword ptr [rsp+0B8h+var_80+4]
0x140058c26  mov     [rsp+0B8h+Address+8], rax
0x140058c2b  mov     ecx, dword ptr [rsp+0B8h+var_80+8]
0x140058c2f  mov     [rsp+0B8h+VirtualAddress], rcx
0x140058c34  mov     edx, dword ptr [rsp+0B8h+var_80+0Ch]
0x140058c38  mov     dword ptr [rsp+0B8h+VirtualAddress+8], edx
0x140058c3c  jmp     short loc_140058C96
0x140058c3e  mov     r8d, 20h ; ' '
0x140058c44  cmp     ecx, r8d
0x140058c47  jnb     short loc_140058C5A
0x140058c49  mov     ecx, 0C000000Dh; Status
0x140058c4e  call    cs:__imp_ExRaiseStatus
0x140058c5a  mov     cl, [rsi+40h]
0x140058c5d  test    cl, cl
0x140058c5f  jz      short loc_140058C74
0x140058c61  test    byte ptr [r15+20h], 3
0x140058c66  jz      short loc_140058C74
0x140058c68  call    cs:__imp_ExRaiseDatatypeMisalignment
0x140058c6f  nop     dword ptr [rax+rax+00h]
0x140058c74  mov     rdx, [r15+20h]; Src
0x140058c78  test    cl, cl
0x140058c7a  lea     rcx, [rsp+0B8h+Address]; void *
0x140058c7f  jz      short loc_140058C88
0x140058c81  call    RtlCopyFromUser
0x140058c86  jmp     short loc_140058C8D
0x140058c88  call    RtlCopyVolatileMemory
0x140058c8d  mov     edx, dword ptr [rsp+0B8h+VirtualAddress+8]; Length
0x140058c91  mov     rcx, [rsp+0B8h+VirtualAddress]; VirtualAddress
0x140058c96  mov     r14d, 1
0x140058c9c  cmp     edx, r14d
0x140058c9f  jnb     short loc_140058CB2
0x140058ca1  mov     ecx, 0C000000Dh; Status
0x140058ca6  call    cs:__imp_ExRaiseStatus
0x140058cb2  mov     [rsp+0B8h+Irp], rdi; Irp
0x140058cb7  mov     r9b, r14b; ChargeQuota
0x140058cba  xor     r8d, r8d; SecondaryBuffer
0x140058cbd  call    cs:__imp_IoAllocateMdl
0x140058cc4  nop     dword ptr [rax+rax+00h]
0x140058cc9  mov     [rsi+8], rax
0x140058ccd  test    rax, rax
0x140058cd0  jnz     short loc_140058CE3
0x140058cd2  mov     ecx, 0C000009Ah; Status
0x140058cd7  call    cs:__imp_ExRaiseStatus
0x140058ce3  mov     r8d, r14d; Operation
0x140058ce6  mov     dl, [rsi+40h]; AccessMode
0x140058ce9  mov     rcx, rax; MemoryDescriptorList
0x140058cec  call    cs:__imp_MmProbeAndLockPages
0x140058cf3  nop     dword ptr [rax+rax+00h]
0x140058cf8  mov     rcx, [rsi+8]; MemoryDescriptorList
0x140058cfc  test    byte ptr [rcx+0Ah], 5
0x140058d00  jz      short loc_140058D08
0x140058d02  mov     rax, [rcx+18h]
0x140058d06  jmp     short loc_140058D28
0x140058d08  mov     [rsp+0B8h+Priority], 40000000h; Priority
0x140058d10  mov     dword ptr [rsp+0B8h+Irp], edi; BugCheckOnFailure
0x140058d14  xor     r9d, r9d; RequestedAddress
0x140058d17  mov     r8d, r14d; CacheType
0x140058d1a  xor     edx, edx; AccessMode
0x140058d1c  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140058d23  nop     dword ptr [rax+rax+00h]
0x140058d28  test    rax, rax
0x140058d2b  jnz     short loc_140058D3E
0x140058d2d  mov     ecx, 0C000009Ah; Status
0x140058d32  call    cs:__imp_ExRaiseStatus
0x140058d3e  mov     edx, [r15+8]; Length
0x140058d42  test    edx, edx
0x140058d44  jz      loc_140058DE4
0x140058d4a  mov     rbx, [rsi+8]
0x140058d4e  mov     [rsp+0B8h+Irp], rdi; Irp
0x140058d53  mov     r9b, r14b; ChargeQuota
0x140058d56  xor     r8d, r8d; SecondaryBuffer
0x140058d59  mov     rcx, [rsi+70h]; VirtualAddress
0x140058d5d  call    cs:__imp_IoAllocateMdl
0x140058d64  nop     dword ptr [rax+rax+00h]
0x140058d69  mov     [rbx], rax
0x140058d6c  mov     rax, [rsi+8]
0x140058d70  mov     rcx, [rax]; MemoryDescriptorList
0x140058d73  test    rcx, rcx
0x140058d76  jnz     short loc_140058D89
0x140058d78  mov     ecx, 0C000009Ah; Status
0x140058d7d  call    cs:__imp_ExRaiseStatus
0x140058d89  mov     r8d, r14d; Operation
0x140058d8c  mov     dl, [rsi+40h]; AccessMode
0x140058d8f  call    cs:__imp_MmProbeAndLockPages
0x140058d96  nop     dword ptr [rax+rax+00h]
0x140058d9b  mov     rax, [rsi+8]
0x140058d9f  mov     rcx, [rax]; MemoryDescriptorList
0x140058da2  test    byte ptr [rcx+0Ah], 5
0x140058da6  jz      short loc_140058DAE
0x140058da8  mov     rax, [rcx+18h]
0x140058dac  jmp     short loc_140058DCE
0x140058dae  mov     [rsp+0B8h+Priority], 40000000h; Priority
0x140058db6  mov     dword ptr [rsp+0B8h+Irp], edi; BugCheckOnFailure
0x140058dba  xor     r9d, r9d; RequestedAddress
0x140058dbd  mov     r8d, r14d; CacheType
0x140058dc0  xor     edx, edx; AccessMode
0x140058dc2  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140058dc9  nop     dword ptr [rax+rax+00h]
0x140058dce  test    rax, rax
0x140058dd1  jnz     short loc_140058DE4
0x140058dd3  mov     ecx, 0C000009Ah; Status
0x140058dd8  call    cs:__imp_ExRaiseStatus
0x140058de4  mov     rcx, [rsp+0B8h+Address+8]; Address
0x140058de9  test    rcx, rcx
0x140058dec  jnz     short loc_140058E1C
0x140058dee  test    byte ptr cs:xmmword_1400875E0+2, 8
0x140058df5  jz      short loc_140058E0B
0x140058df7  lea     edx, [rcx+24h]
0x140058dfa  mov     ecx, 413h
0x140058dff  lea     r8, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids
0x140058e06  call    WPP_SF_
0x140058e0b  mov     ecx, 0C000000Dh; Status
0x140058e10  call    cs:__imp_ExRaiseStatus
0x140058e1c  cmp     [rsi+40h], dil
0x140058e20  jz      short loc_140058E38
0x140058e22  mov     edx, 14h; Length
0x140058e27  lea     r8d, [rdx-10h]; Alignment
0x140058e2b  call    cs:__imp_ProbeForWrite
0x140058e32  nop     dword ptr [rax+rax+00h]
0x140058e37  nop
0x140058e38  mov     [rsp+0B8h+Object], rdi
0x140058e40  mov     edx, [r15+18h]
0x140058e44  shr     edx, 0Eh
0x140058e47  and     edx, 3; DesiredAccess
0x140058e4a  mov     qword ptr [rsp+0B8h+Priority], rdi; HandleInformation
0x140058e4f  lea     rax, [rsp+0B8h+Object]
0x140058e57  mov     [rsp+0B8h+Irp], rax; Object
0x140058e5c  mov     r9b, [rsi+40h]; AccessMode
0x140058e60  mov     r8, cs:__imp_IoFileObjectType
0x140058e67  mov     r8, [r8]; ObjectType
0x140058e6a  mov     rcx, [rsp+0B8h+Address]; Handle
0x140058e6f  call    cs:__imp_ObReferenceObjectByHandle
0x140058e76  nop     dword ptr [rax+rax+00h]
0x140058e7b  mov     ebx, eax
0x140058e7d  mov     r13, [rsp+0B8h+Object]
0x140058e85  test    eax, eax
0x140058e87  js      loc_1400593A1
0x140058e8d  mov     rax, cs:AfdDeviceObject
0x140058e94  cmp     [r13+8], rax
0x140058e98  jz      short loc_140058EA4
0x140058e9a  mov     ebx, 0C0000008h
0x140058e9f  jmp     loc_1400593A1
0x140058ea4  mov     rax, [r15+30h]
0x140058ea8  mov     rbx, [rax+18h]
0x140058eac  mov     [rsp+0B8h+Irql], rbx
0x140058eb4  mov     r14, [r13+18h]
0x140058eb8  test    byte ptr cs:xmmword_1400875E0+2, 8
0x140058ebf  jz      short loc_140058EDA
0x140058ec1  mov     edx, 25h ; '%'
0x140058ec6  mov     ecx, 413h
0x140058ecb  mov     r9, r14
0x140058ece  lea     r8, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids
0x140058ed5  call    WPP_SF_q
0x140058eda  mov     rcx, r14
0x140058edd  call    AfdLockEndpointContext
0x140058ee2  mov     r12, rax
0x140058ee5  mov     qword ptr [rsp+0B8h+var_80], rax
0x140058eea  mov     eax, 0AFDh
0x140058eef  cmp     [rbx], ax
0x140058ef2  jnz     loc_140059341
0x140058ef8  mov     rbx, [rbx+30h]
0x140058efc  call    cs:__imp_IoGetCurrentProcess
0x140058f03  nop     dword ptr [rax+rax+00h]
0x140058f08  cmp     rbx, rax
0x140058f0b  jnz     loc_140059341
0x140058f11  mov     eax, 1AFDh
0x140058f16  cmp     [r14], ax
0x140058f1a  jnz     loc_140059341
0x140058f20  mov     rax, cs:AfdSanServiceHelper
0x140058f27  cmp     [r14+60h], rax
0x140058f2b  jnz     loc_1400590B4
0x140058f31  cmp     [rsp+0B8h+Irql], rax
0x140058f39  jnz     loc_1400590B4
0x140058f3f  lea     rcx, [r14+38h]; SpinLock
0x140058f43  lea     rdx, [rsp+0B8h+LockHandle]; LockHandle
0x140058f48  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140058f4f  nop     dword ptr [rax+rax+00h]
0x140058f54  cmp     dword ptr [r14+9Ch], 0C0000016h
0x140058f5f  jz      short loc_140058F7C
0x140058f61  lea     rcx, [rsp+0B8h+LockHandle]; LockHandle
0x140058f66  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140058f6d  nop     dword ptr [rax+rax+00h]
0x140058f72  mov     ebx, 0C0000120h
0x140058f77  jmp     loc_140059080
0x140058f7c  mov     ebx, [r14+90h]
0x140058f83  mov     ecx, dword ptr [rsp+0B8h+VirtualAddress+8]
0x140058f87  cmp     ecx, ebx
0x140058f89  ja      loc_14005906A
0x140058f8f  add     ecx, [r15+8]
0x140058f93  cmp     ecx, ebx
0x140058f95  jb      loc_14005906A
0x140058f9b  mov     r12, [r14+70h]
0x140058f9f  mov     [r14+70h], rdi
0x140058fa3  mov     [r14+90h], edi
0x140058faa  lea     rcx, [rsp+0B8h+LockHandle]; LockHandle
0x140058faf  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140058fb6  nop     dword ptr [rax+rax+00h]
0x140058fbb  mov     rcx, [rsi+8]; MemoryDescriptorList
0x140058fbf  test    byte ptr [rcx+0Ah], 5
0x140058fc3  jz      short loc_140058FCB
0x140058fc5  mov     rax, [rcx+18h]
0x140058fc9  jmp     short loc_140058FD9
0x140058fcb  xor     edx, edx; AccessMode
0x140058fcd  call    cs:__imp_MmMapLockedPages
0x140058fd4  nop     dword ptr [rax+rax+00h]
0x140058fd9  mov     r8d, dword ptr [rsp+0B8h+VirtualAddress+8]; Size
0x140058fde  mov     rdx, r12; Src
0x140058fe1  mov     rcx, rax; void *
0x140058fe4  call    RtlCopyVolatileMemory
0x140058fe9  cmp     [r15+8], edi
0x140058fed  jz      short loc_140059031
0x140058fef  mov     edx, dword ptr [rsp+0B8h+VirtualAddress+8]
0x140058ff3  sub     ebx, edx
0x140058ff5  mov     eax, ebx
0x140058ff7  mov     [rsi+38h], rax
0x140058ffb  mov     rax, [rsi+8]
0x140058fff  mov     rcx, [rax]; MemoryDescriptorList
0x140059002  test    byte ptr [rcx+0Ah], 5
0x140059006  jz      short loc_14005900E
0x140059008  mov     rax, [rcx+18h]
0x14005900c  jmp     short loc_140059020
0x14005900e  xor     edx, edx; AccessMode
0x140059010  call    cs:__imp_MmMapLockedPages
0x140059017  nop     dword ptr [rax+rax+00h]
0x14005901c  mov     edx, dword ptr [rsp+0B8h+VirtualAddress+8]
0x140059020  add     rdx, r12; Src
0x140059023  mov     r8, [rsi+38h]; Size
0x140059027  mov     rcx, rax; void *
0x14005902a  call    RtlCopyVolatileMemory
0x14005902f  jmp     short loc_140059035
0x140059031  mov     [rsi+38h], rdi
0x140059035  mov     edx, 78646641h; Tag
0x14005903a  mov     rcx, r12; P
0x14005903d  call    cs:__imp_ExFreePoolWithTag
0x140059044  nop     dword ptr [rax+rax+00h]
0x140059049  mov     rax, [rsp+0B8h+Address+8]
0x14005904e  mov     [r14+70h], rax
0x140059052  mov     ebx, edi
0x140059054  mov     rax, cs:AfdSanServiceHelper
0x14005905b  lock add dword ptr [rax+84h], 0FFFFFFFEh
0x140059063  mov     r12, qword ptr [rsp+0B8h+var_80]
0x140059068  jmp     short loc_140059082
0x14005906a  lea     rcx, [rsp+0B8h+LockHandle]; LockHandle
0x14005906f  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140059076  nop     dword ptr [rax+rax+00h]
0x14005907b  mov     ebx, 0C0000023h
0x140059080  mov     edi, ebx
0x140059082  mov     rdx, r12
0x140059085  mov     rcx, r14
0x140059088  call    AfdUnlockEndpointContext
0x14005908d  mov     [rsi+30h], ebx
0x140059090  mov     dl, cs:AfdPriorityBoost; PriorityBoost
  ... truncated ...
```
