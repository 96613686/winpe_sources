# AfdSanAcquireContext

- ea: `0x140058d10`
- end: `0x140059583`
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
- `0x14002fd7c`
- `0x140041a34`
- `0x1400445d8`
- `0x140058d10`
- `0x14005ac10`
- `0x14005d83c`
- `0x140072870`
- `0x1400930cc`
- `0x1400931d0`
- `0x14009327c`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x140058d79`
- `ntoskrnl!ExRaiseStatus` at `0x140058dee`
- `ntoskrnl!ExRaiseStatus` at `0x140058e46`
- `ntoskrnl!ExRaiseStatus` at `0x140058e77`
- `ntoskrnl!ExRaiseStatus` at `0x140058ed2`
- `ntoskrnl!ExRaiseStatus` at `0x140058f1d`
- `ntoskrnl!ExRaiseStatus` at `0x140058f78`
- `ntoskrnl!ExRaiseStatus` at `0x140058fb0`
- `ntoskrnl!ExRaiseStatus` at `0x140058d79`
- `ntoskrnl!ExRaiseStatus` at `0x140058dee`
- `ntoskrnl!ExRaiseStatus` at `0x140058e46`
- `ntoskrnl!ExRaiseStatus` at `0x140058e77`
- `ntoskrnl!ExRaiseStatus` at `0x140058ed2`
- `ntoskrnl!ExRaiseStatus` at `0x140058f1d`
- `ntoskrnl!ExRaiseStatus` at `0x140058f78`
- `ntoskrnl!ExRaiseStatus` at `0x140058fb0`
- `ntoskrnl!MmMapLockedPages` at `0x14005916d`
- `ntoskrnl!MmMapLockedPages` at `0x1400591b0`
- `ntoskrnl!MmMapLockedPages` at `0x14005916d`
- `ntoskrnl!MmMapLockedPages` at `0x1400591b0`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140058ebc`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140058f62`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140058ebc`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140058f62`
- `ntoskrnl!IoFreeMdl` at `0x140059525`
- `ntoskrnl!IoFreeMdl` at `0x140059525`
- `ntoskrnl!MmUnlockPages` at `0x140059516`
- `ntoskrnl!MmUnlockPages` at `0x140059516`
- `ntoskrnl!MmProbeAndLockPages` at `0x140058e8c`
- `ntoskrnl!MmProbeAndLockPages` at `0x140058f2f`
- `ntoskrnl!MmProbeAndLockPages` at `0x140058e8c`
- `ntoskrnl!MmProbeAndLockPages` at `0x140058f2f`
- `ntoskrnl!IoAllocateMdl` at `0x140058e5d`
- `ntoskrnl!IoAllocateMdl` at `0x140058efd`
- `ntoskrnl!IoAllocateMdl` at `0x140058e5d`
- `ntoskrnl!IoAllocateMdl` at `0x140058efd`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140058d93`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140058e08`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140058d93`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140058e08`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400592c1`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14005938e`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400592c1`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14005938e`
- `ntoskrnl!IofCompleteRequest` at `0x140059239`
- `ntoskrnl!IofCompleteRequest` at `0x1400594b0`
- `ntoskrnl!IofCompleteRequest` at `0x140059561`
- `ntoskrnl!IofCompleteRequest` at `0x140059239`
- `ntoskrnl!IofCompleteRequest` at `0x1400594b0`
- `ntoskrnl!IofCompleteRequest` at `0x140059561`
- `ntoskrnl!ObfDereferenceObject` at `0x1400594ce`
- `ntoskrnl!ObfDereferenceObject` at `0x140059549`
- `ntoskrnl!ObfDereferenceObject` at `0x1400594ce`
- `ntoskrnl!ObfDereferenceObject` at `0x140059549`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400592ae`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14005937b`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400592ae`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14005937b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140059106`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005914f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005920f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140059286`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140059353`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140059429`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140059106`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005914f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005920f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140059286`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140059353`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140059429`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400590e8`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005925d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400590e8`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005925d`
- `ntoskrnl!IoFileObjectType` at `0x140059000`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14005900f`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14005900f`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400593c0`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140059471`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400593c0`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140059471`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400591dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400591dd`
- `ntoskrnl!IoGetCurrentProcess` at `0x14005909c`
- `ntoskrnl!IoGetCurrentProcess` at `0x14005909c`
- `ntoskrnl!IoIs32bitProcess` at `0x140058d4f`
- `ntoskrnl!IoIs32bitProcess` at `0x140058d4f`
- `ntoskrnl!ProbeForWrite` at `0x140058fcb`
- `ntoskrnl!ProbeForWrite` at `0x140058fcb`

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
0x140058d10  mov     [rsp+arg_0], rcx
0x140058d15  push    rbx
0x140058d16  push    rsi
0x140058d17  push    rdi
0x140058d18  push    r12
0x140058d1a  push    r13
0x140058d1c  push    r14
0x140058d1e  push    r15
0x140058d20  sub     rsp, 80h
0x140058d27  mov     r15, rdx
0x140058d2a  mov     rsi, rcx
0x140058d2d  xor     edi, edi
0x140058d2f  xorps   xmm0, xmm0
0x140058d32  xor     eax, eax
0x140058d34  movups  xmmword ptr [rsp+0B8h+LockHandle.LockQueue.Next], xmm0
0x140058d39  mov     qword ptr [rsp+0B8h+LockHandle.OldIrql], rax
0x140058d3e  xorps   xmm1, xmm1
0x140058d41  movups  xmmword ptr [rsp+0B8h+Address], xmm1
0x140058d46  movups  xmmword ptr [rsp+0B8h+VirtualAddress], xmm1
0x140058d4b  mov     [rsp+0B8h+var_88], edi
0x140058d4f  call    cs:__imp_IoIs32bitProcess
0x140058d56  nop     dword ptr [rax+rax+00h]
0x140058d5b  mov     ecx, [r15+10h]
0x140058d5f  test    al, al
0x140058d61  jz      short loc_140058DDE
0x140058d63  xorps   xmm0, xmm0
0x140058d66  movups  [rsp+0B8h+var_80], xmm0
0x140058d6b  lea     r8d, [rdi+10h]
0x140058d6f  cmp     ecx, r8d
0x140058d72  jnb     short loc_140058D85
0x140058d74  mov     ecx, 0C000000Dh; Status
0x140058d79  call    cs:__imp_ExRaiseStatus
0x140058d85  mov     cl, [rsi+40h]
0x140058d88  test    cl, cl
0x140058d8a  jz      short loc_140058D9F
0x140058d8c  test    byte ptr [r15+20h], 3
0x140058d91  jz      short loc_140058D9F
0x140058d93  call    cs:__imp_ExRaiseDatatypeMisalignment
0x140058d9a  nop     dword ptr [rax+rax+00h]
0x140058d9f  mov     rdx, [r15+20h]; Src
0x140058da3  test    cl, cl
0x140058da5  lea     rcx, [rsp+0B8h+var_80]; void *
0x140058daa  jz      short loc_140058DB3
0x140058dac  call    RtlCopyFromUser
0x140058db1  jmp     short loc_140058DB8
0x140058db3  call    RtlCopyVolatileMemory
0x140058db8  movsxd  rax, dword ptr [rsp+0B8h+var_80]
0x140058dbd  mov     [rsp+0B8h+Address], rax
0x140058dc2  mov     eax, dword ptr [rsp+0B8h+var_80+4]
0x140058dc6  mov     [rsp+0B8h+Address+8], rax
0x140058dcb  mov     ecx, dword ptr [rsp+0B8h+var_80+8]
0x140058dcf  mov     [rsp+0B8h+VirtualAddress], rcx
0x140058dd4  mov     edx, dword ptr [rsp+0B8h+var_80+0Ch]
0x140058dd8  mov     dword ptr [rsp+0B8h+VirtualAddress+8], edx
0x140058ddc  jmp     short loc_140058E36
0x140058dde  mov     r8d, 20h ; ' '
0x140058de4  cmp     ecx, r8d
0x140058de7  jnb     short loc_140058DFA
0x140058de9  mov     ecx, 0C000000Dh; Status
0x140058dee  call    cs:__imp_ExRaiseStatus
0x140058dfa  mov     cl, [rsi+40h]
0x140058dfd  test    cl, cl
0x140058dff  jz      short loc_140058E14
0x140058e01  test    byte ptr [r15+20h], 3
0x140058e06  jz      short loc_140058E14
0x140058e08  call    cs:__imp_ExRaiseDatatypeMisalignment
0x140058e0f  nop     dword ptr [rax+rax+00h]
0x140058e14  mov     rdx, [r15+20h]; Src
0x140058e18  test    cl, cl
0x140058e1a  lea     rcx, [rsp+0B8h+Address]; void *
0x140058e1f  jz      short loc_140058E28
0x140058e21  call    RtlCopyFromUser
0x140058e26  jmp     short loc_140058E2D
0x140058e28  call    RtlCopyVolatileMemory
0x140058e2d  mov     edx, dword ptr [rsp+0B8h+VirtualAddress+8]; Length
0x140058e31  mov     rcx, [rsp+0B8h+VirtualAddress]; VirtualAddress
0x140058e36  mov     r14d, 1
0x140058e3c  cmp     edx, r14d
0x140058e3f  jnb     short loc_140058E52
0x140058e41  mov     ecx, 0C000000Dh; Status
0x140058e46  call    cs:__imp_ExRaiseStatus
0x140058e52  mov     [rsp+0B8h+Irp], rdi; Irp
0x140058e57  mov     r9b, r14b; ChargeQuota
0x140058e5a  xor     r8d, r8d; SecondaryBuffer
0x140058e5d  call    cs:__imp_IoAllocateMdl
0x140058e64  nop     dword ptr [rax+rax+00h]
0x140058e69  mov     [rsi+8], rax
0x140058e6d  test    rax, rax
0x140058e70  jnz     short loc_140058E83
0x140058e72  mov     ecx, 0C000009Ah; Status
0x140058e77  call    cs:__imp_ExRaiseStatus
0x140058e83  mov     r8d, r14d; Operation
0x140058e86  mov     dl, [rsi+40h]; AccessMode
0x140058e89  mov     rcx, rax; MemoryDescriptorList
0x140058e8c  call    cs:__imp_MmProbeAndLockPages
0x140058e93  nop     dword ptr [rax+rax+00h]
0x140058e98  mov     rcx, [rsi+8]; MemoryDescriptorList
0x140058e9c  test    byte ptr [rcx+0Ah], 5
0x140058ea0  jz      short loc_140058EA8
0x140058ea2  mov     rax, [rcx+18h]
0x140058ea6  jmp     short loc_140058EC8
0x140058ea8  mov     [rsp+0B8h+Priority], 40000000h; Priority
0x140058eb0  mov     dword ptr [rsp+0B8h+Irp], edi; BugCheckOnFailure
0x140058eb4  xor     r9d, r9d; RequestedAddress
0x140058eb7  mov     r8d, r14d; CacheType
0x140058eba  xor     edx, edx; AccessMode
0x140058ebc  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140058ec3  nop     dword ptr [rax+rax+00h]
0x140058ec8  test    rax, rax
0x140058ecb  jnz     short loc_140058EDE
0x140058ecd  mov     ecx, 0C000009Ah; Status
0x140058ed2  call    cs:__imp_ExRaiseStatus
0x140058ede  mov     edx, [r15+8]; Length
0x140058ee2  test    edx, edx
0x140058ee4  jz      loc_140058F84
0x140058eea  mov     rbx, [rsi+8]
0x140058eee  mov     [rsp+0B8h+Irp], rdi; Irp
0x140058ef3  mov     r9b, r14b; ChargeQuota
0x140058ef6  xor     r8d, r8d; SecondaryBuffer
0x140058ef9  mov     rcx, [rsi+70h]; VirtualAddress
0x140058efd  call    cs:__imp_IoAllocateMdl
0x140058f04  nop     dword ptr [rax+rax+00h]
0x140058f09  mov     [rbx], rax
0x140058f0c  mov     rax, [rsi+8]
0x140058f10  mov     rcx, [rax]; MemoryDescriptorList
0x140058f13  test    rcx, rcx
0x140058f16  jnz     short loc_140058F29
0x140058f18  mov     ecx, 0C000009Ah; Status
0x140058f1d  call    cs:__imp_ExRaiseStatus
0x140058f29  mov     r8d, r14d; Operation
0x140058f2c  mov     dl, [rsi+40h]; AccessMode
0x140058f2f  call    cs:__imp_MmProbeAndLockPages
0x140058f36  nop     dword ptr [rax+rax+00h]
0x140058f3b  mov     rax, [rsi+8]
0x140058f3f  mov     rcx, [rax]; MemoryDescriptorList
0x140058f42  test    byte ptr [rcx+0Ah], 5
0x140058f46  jz      short loc_140058F4E
0x140058f48  mov     rax, [rcx+18h]
0x140058f4c  jmp     short loc_140058F6E
0x140058f4e  mov     [rsp+0B8h+Priority], 40000000h; Priority
0x140058f56  mov     dword ptr [rsp+0B8h+Irp], edi; BugCheckOnFailure
0x140058f5a  xor     r9d, r9d; RequestedAddress
0x140058f5d  mov     r8d, r14d; CacheType
0x140058f60  xor     edx, edx; AccessMode
0x140058f62  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140058f69  nop     dword ptr [rax+rax+00h]
0x140058f6e  test    rax, rax
0x140058f71  jnz     short loc_140058F84
0x140058f73  mov     ecx, 0C000009Ah; Status
0x140058f78  call    cs:__imp_ExRaiseStatus
0x140058f84  mov     rcx, [rsp+0B8h+Address+8]; Address
0x140058f89  test    rcx, rcx
0x140058f8c  jnz     short loc_140058FBC
0x140058f8e  test    byte ptr cs:xmmword_1400875E0+2, 8
0x140058f95  jz      short loc_140058FAB
0x140058f97  lea     edx, [rcx+24h]
0x140058f9a  mov     ecx, 413h
0x140058f9f  lea     r8, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids
0x140058fa6  call    WPP_SF_
0x140058fab  mov     ecx, 0C000000Dh; Status
0x140058fb0  call    cs:__imp_ExRaiseStatus
0x140058fbc  cmp     [rsi+40h], dil
0x140058fc0  jz      short loc_140058FD8
0x140058fc2  mov     edx, 14h; Length
0x140058fc7  lea     r8d, [rdx-10h]; Alignment
0x140058fcb  call    cs:__imp_ProbeForWrite
0x140058fd2  nop     dword ptr [rax+rax+00h]
0x140058fd7  nop
0x140058fd8  mov     [rsp+0B8h+Object], rdi
0x140058fe0  mov     edx, [r15+18h]
0x140058fe4  shr     edx, 0Eh
0x140058fe7  and     edx, 3; DesiredAccess
0x140058fea  mov     qword ptr [rsp+0B8h+Priority], rdi; HandleInformation
0x140058fef  lea     rax, [rsp+0B8h+Object]
0x140058ff7  mov     [rsp+0B8h+Irp], rax; Object
0x140058ffc  mov     r9b, [rsi+40h]; AccessMode
0x140059000  mov     r8, cs:__imp_IoFileObjectType
0x140059007  mov     r8, [r8]; ObjectType
0x14005900a  mov     rcx, [rsp+0B8h+Address]; Handle
0x14005900f  call    cs:__imp_ObReferenceObjectByHandle
0x140059016  nop     dword ptr [rax+rax+00h]
0x14005901b  mov     ebx, eax
0x14005901d  mov     r13, [rsp+0B8h+Object]
0x140059025  test    eax, eax
0x140059027  js      loc_140059541
0x14005902d  mov     rax, cs:AfdDeviceObject
0x140059034  cmp     [r13+8], rax
0x140059038  jz      short loc_140059044
0x14005903a  mov     ebx, 0C0000008h
0x14005903f  jmp     loc_140059541
0x140059044  mov     rax, [r15+30h]
0x140059048  mov     rbx, [rax+18h]
0x14005904c  mov     [rsp+0B8h+Irql], rbx
0x140059054  mov     r14, [r13+18h]
0x140059058  test    byte ptr cs:xmmword_1400875E0+2, 8
0x14005905f  jz      short loc_14005907A
0x140059061  mov     edx, 25h ; '%'
0x140059066  mov     ecx, 413h
0x14005906b  mov     r9, r14
0x14005906e  lea     r8, WPP_80e72b6a7d993578b586d54102b8ccdb_Traceguids
0x140059075  call    WPP_SF_q
0x14005907a  mov     rcx, r14
0x14005907d  call    AfdLockEndpointContext
0x140059082  mov     r12, rax
0x140059085  mov     qword ptr [rsp+0B8h+var_80], rax
0x14005908a  mov     eax, 0AFDh
0x14005908f  cmp     [rbx], ax
0x140059092  jnz     loc_1400594E1
0x140059098  mov     rbx, [rbx+30h]
0x14005909c  call    cs:__imp_IoGetCurrentProcess
0x1400590a3  nop     dword ptr [rax+rax+00h]
0x1400590a8  cmp     rbx, rax
0x1400590ab  jnz     loc_1400594E1
0x1400590b1  mov     eax, 1AFDh
0x1400590b6  cmp     [r14], ax
0x1400590ba  jnz     loc_1400594E1
0x1400590c0  mov     rax, cs:AfdSanServiceHelper
0x1400590c7  cmp     [r14+60h], rax
0x1400590cb  jnz     loc_140059254
0x1400590d1  cmp     [rsp+0B8h+Irql], rax
0x1400590d9  jnz     loc_140059254
0x1400590df  lea     rcx, [r14+38h]; SpinLock
0x1400590e3  lea     rdx, [rsp+0B8h+LockHandle]; LockHandle
0x1400590e8  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400590ef  nop     dword ptr [rax+rax+00h]
0x1400590f4  cmp     dword ptr [r14+9Ch], 0C0000016h
0x1400590ff  jz      short loc_14005911C
0x140059101  lea     rcx, [rsp+0B8h+LockHandle]; LockHandle
0x140059106  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14005910d  nop     dword ptr [rax+rax+00h]
0x140059112  mov     ebx, 0C0000120h
0x140059117  jmp     loc_140059220
0x14005911c  mov     ebx, [r14+90h]
0x140059123  mov     ecx, dword ptr [rsp+0B8h+VirtualAddress+8]
0x140059127  cmp     ecx, ebx
0x140059129  ja      loc_14005920A
0x14005912f  add     ecx, [r15+8]
0x140059133  cmp     ecx, ebx
0x140059135  jb      loc_14005920A
0x14005913b  mov     r12, [r14+70h]
0x14005913f  mov     [r14+70h], rdi
0x140059143  mov     [r14+90h], edi
0x14005914a  lea     rcx, [rsp+0B8h+LockHandle]; LockHandle
0x14005914f  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140059156  nop     dword ptr [rax+rax+00h]
0x14005915b  mov     rcx, [rsi+8]; MemoryDescriptorList
0x14005915f  test    byte ptr [rcx+0Ah], 5
0x140059163  jz      short loc_14005916B
0x140059165  mov     rax, [rcx+18h]
0x140059169  jmp     short loc_140059179
0x14005916b  xor     edx, edx; AccessMode
0x14005916d  call    cs:__imp_MmMapLockedPages
0x140059174  nop     dword ptr [rax+rax+00h]
0x140059179  mov     r8d, dword ptr [rsp+0B8h+VirtualAddress+8]; Size
0x14005917e  mov     rdx, r12; Src
0x140059181  mov     rcx, rax; void *
0x140059184  call    RtlCopyVolatileMemory
0x140059189  cmp     [r15+8], edi
0x14005918d  jz      short loc_1400591D1
0x14005918f  mov     edx, dword ptr [rsp+0B8h+VirtualAddress+8]
0x140059193  sub     ebx, edx
0x140059195  mov     eax, ebx
0x140059197  mov     [rsi+38h], rax
0x14005919b  mov     rax, [rsi+8]
0x14005919f  mov     rcx, [rax]; MemoryDescriptorList
0x1400591a2  test    byte ptr [rcx+0Ah], 5
0x1400591a6  jz      short loc_1400591AE
0x1400591a8  mov     rax, [rcx+18h]
0x1400591ac  jmp     short loc_1400591C0
0x1400591ae  xor     edx, edx; AccessMode
0x1400591b0  call    cs:__imp_MmMapLockedPages
0x1400591b7  nop     dword ptr [rax+rax+00h]
0x1400591bc  mov     edx, dword ptr [rsp+0B8h+VirtualAddress+8]
0x1400591c0  add     rdx, r12; Src
0x1400591c3  mov     r8, [rsi+38h]; Size
0x1400591c7  mov     rcx, rax; void *
0x1400591ca  call    RtlCopyVolatileMemory
0x1400591cf  jmp     short loc_1400591D5
0x1400591d1  mov     [rsi+38h], rdi
0x1400591d5  mov     edx, 78646641h; Tag
0x1400591da  mov     rcx, r12; P
0x1400591dd  call    cs:__imp_ExFreePoolWithTag
0x1400591e4  nop     dword ptr [rax+rax+00h]
0x1400591e9  mov     rax, [rsp+0B8h+Address+8]
0x1400591ee  mov     [r14+70h], rax
0x1400591f2  mov     ebx, edi
0x1400591f4  mov     rax, cs:AfdSanServiceHelper
0x1400591fb  lock add dword ptr [rax+84h], 0FFFFFFFEh
0x140059203  mov     r12, qword ptr [rsp+0B8h+var_80]
0x140059208  jmp     short loc_140059222
0x14005920a  lea     rcx, [rsp+0B8h+LockHandle]; LockHandle
0x14005920f  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140059216  nop     dword ptr [rax+rax+00h]
0x14005921b  mov     ebx, 0C0000023h
0x140059220  mov     edi, ebx
0x140059222  mov     rdx, r12
0x140059225  mov     rcx, r14
0x140059228  call    AfdUnlockEndpointContext
0x14005922d  mov     [rsi+30h], ebx
0x140059230  mov     dl, cs:AfdPriorityBoost; PriorityBoost
  ... truncated ...
```
