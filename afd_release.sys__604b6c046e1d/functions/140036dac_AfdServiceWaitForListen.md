# AfdServiceWaitForListen

- ea: `0x140036dac`
- end: `0x14003736e`
- name: `AfdServiceWaitForListen`
- size: `1474`
- prototype: `__int64 __fastcall(PIRP Irp, __int64, struct _KLOCK_QUEUE_HANDLE *, char)`
- caller_count: `5`
- callee_count: `13`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x14002d8d0`
- `0x14002f800`
- `0x14004c6d0`
- `0x14004d510`
- `0x140059910`

## callees

- `0x1400049b0`
- `0x140004c10`
- `0x140009fb0`
- `0x14000dc90`
- `0x14001a030`
- `0x14001aabc`
- `0x14002e7a8`
- `0x1400366e8`
- `0x140036d0c`
- `0x140036dac`
- `0x14004d360`
- `0x1400726e0`
- `0x140072800`

## import_xrefs

- `ntoskrnl!MmMapLockedPages` at `0x140036fad`
- `ntoskrnl!MmMapLockedPages` at `0x140036fea`
- `ntoskrnl!MmMapLockedPages` at `0x14003703b`
- `ntoskrnl!MmMapLockedPages` at `0x140036fad`
- `ntoskrnl!MmMapLockedPages` at `0x140036fea`
- `ntoskrnl!MmMapLockedPages` at `0x14003703b`
- `ntoskrnl!IoAllocateMdl` at `0x140036f02`
- `ntoskrnl!IoAllocateMdl` at `0x140036f02`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14003712a`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140037323`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14003712a`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140037323`
- `ntoskrnl!IofCompleteRequest` at `0x14003734f`
- `ntoskrnl!IofCompleteRequest` at `0x14003734f`
- `ntoskrnl!IofCallDriver` at `0x140037242`
- `ntoskrnl!IofCallDriver` at `0x140037242`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140037117`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400371af`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140037310`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140037117`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400371af`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140037310`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400370de`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400372e3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400370de`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400372e3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140036ec9`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140036ec9`

## pseudocode

```c
__int64 __fastcall AfdServiceWaitForListen(PIRP Irp, __int64 a2, struct _KLOCK_QUEUE_HANDLE *a3, char a4)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r15
  __int64 FsContext; // r14
  unsigned int v9; // ecx
  int v10; // edi
  ULONG LowPart; // edx
  __int64 QuadPart; // rdi
  PMDL MdlAddress; // rcx
  unsigned __int16 v15; // r12
  char *MappedSystemVa; // rax
  PMDL v17; // rcx
  char *v18; // rax
  char *v19; // rax
  _QWORD *v20; // rdx
  PMDL v21; // rax
  int v22; // r8d
  struct _IO_STACK_LOCATION *v23; // rax
  struct _IRP *MasterIrp; // rcx
  int v25; // eax
  bool v26; // zf
  int v27; // eax
  _QWORD *v28; // rdx
  CCHAR v29; // dl
  PNAMED_PIPE_CREATE_PARAMETERS Parameters; // [rsp+30h] [rbp-58h]
  __int64 v31; // [rsp+38h] [rbp-50h]
  __int64 Length; // [rsp+40h] [rbp-48h]
  char *Irql; // [rsp+90h] [rbp+8h] BYREF
  PKLOCK_QUEUE_HANDLE LockHandle; // [rsp+A0h] [rbp+18h]
  char v35; // [rsp+A8h] [rbp+20h]

  v35 = a4;
  LockHandle = a3;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  FsContext = (__int64)CurrentStackLocation->FileObject->FsContext;
  if ( *(_WORD *)&CurrentStackLocation->MajorFunction != 8207 )
  {
    if ( *(_DWORD *)(a2 + 160) + 4 > CurrentStackLocation->Parameters.Read.Length )
    {
      v10 = -1073741789;
      Irp->IoStatus.Status = -1073741789;
      return (unsigned int)v10;
    }
    MasterIrp = Irp->AssociatedIrp.MasterIrp;
    do
    {
      v25 = *(_DWORD *)(FsContext + 184);
      v26 = v25 == -1;
      v27 = v25 + 1;
      *(_DWORD *)(FsContext + 184) = v27;
      *(_DWORD *)(a2 + 164) = v27;
    }
    while ( v26 );
    *(_DWORD *)&MasterIrp->Type = v27;
    memmove(&MasterIrp->Size + 1, *(const void **)(a2 + 152), *(unsigned int *)(a2 + 160));
    Irp->IoStatus.Information = (unsigned int)(*(_DWORD *)(a2 + 160) + 4);
    v28 = *(_QWORD **)(FsContext + 120);
    if ( *v28 == FsContext + 112 )
    {
      v10 = 0;
      *(_QWORD *)(a2 + 176) = FsContext + 112;
      *(_QWORD *)(a2 + 184) = v28;
      *v28 = a2 + 176;
      *(_QWORD *)(FsContext + 120) = a2 + 176;
      *(_WORD *)(a2 + 2) = 2;
      KeReleaseInStackQueuedSpinLock(a3);
      if ( !_InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, 0) && Irp->Cancel )
      {
        LOBYTE(Irql) = 0;
        IoAcquireCancelSpinLock((PKIRQL)&Irql);
        IoReleaseCancelSpinLock((KIRQL)Irql);
      }
      AFDETW_TRACEWAITLISTEN(1, 6220, FsContext, 0);
      v29 = AfdPriorityBoost;
      Irp->IoStatus.Status = 0;
      IofCompleteRequest(Irp, v29);
      return (unsigned int)v10;
    }
    goto LABEL_69;
  }
  if ( (*(_DWORD *)(FsContext + 8) & 0x100) == 0 && (*(_DWORD *)(FsContext + 8) & 0x400000) != 0 )
  {
    if ( (*(_DWORD *)(a2 + 4) & 2) != 0 )
      _InterlockedDecrement((volatile signed __int32 *)(FsContext + 176));
    else
      _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(FsContext + 280) + 48LL));
  }
  if ( ((*(_DWORD *)(FsContext + 8) & 0x100) != 0
     || *(_DWORD *)(a2 + 160) <= CurrentStackLocation->Parameters.Create.Options)
    && ((*(_DWORD *)(FsContext + 8) & 0x100) == 0
     || *(_DWORD *)(a2 + 160) + 6 <= CurrentStackLocation->Parameters.Create.Options)
    && ((*(_DWORD *)(FsContext + 8) & 0x100) == 0
     || (v9 = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart) == 0
     || *(_DWORD *)(a2 + 168) + 6 <= v9) )
  {
    v10 = AfdMapMdlChain(Irp->MdlAddress);
    if ( v10 < 0 )
      goto LABEL_15;
    if ( (*(_DWORD *)(a2 + 4) & 0x20000000) != 0 )
    {
      v10 = AfdSanAcceptCore((__int64)Irp, (char *)CurrentStackLocation->Parameters.CreatePipe.Parameters, a2, a3);
      if ( v10 != 259 )
      {
        KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(FsContext + 56), a3);
        goto LABEL_15;
      }
      return 0;
    }
    if ( (*(_DWORD *)(FsContext + 8) & 0x100) == 0 )
    {
      LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
      if ( LowPart )
      {
        if ( !IoAllocateMdl((char *)Irp->UserBuffer + CurrentStackLocation->Parameters.Read.Length, LowPart, 1u, 0, Irp) )
        {
          v10 = -1073741670;
          goto LABEL_15;
        }
      }
    }
    AFDETW_TRACEWAITLISTEN(1, 6221, FsContext, 0);
    Parameters = CurrentStackLocation->Parameters.CreatePipe.Parameters;
    QuadPart = Parameters->DefaultTimeout.QuadPart;
    v31 = QuadPart;
    if ( (*(_DWORD *)(FsContext + 8) & 0x100) != 0 )
    {
      AfdTLCopyRemoteAndLocalAddresses(
        QuadPart,
        *(const void **)(a2 + 224),
        *(_DWORD *)(a2 + 168),
        *(const void **)(a2 + 152),
        *(_DWORD *)(a2 + 160),
        (__int64)Irp);
    }
    else
    {
      MdlAddress = Irp->MdlAddress;
      if ( *(_BYTE *)(QuadPart + 188) )
      {
        v15 = *(_WORD *)(*(_QWORD *)(a2 + 152) + 4LL) + 2;
        if ( (MdlAddress->MdlFlags & 5) != 0 )
          MappedSystemVa = (char *)MdlAddress->MappedSystemVa;
        else
          MappedSystemVa = (char *)MmMapLockedPages(MdlAddress, 0);
        Length = CurrentStackLocation->Parameters.Read.Length;
        v17 = Irp->MdlAddress;
        Irql = &MappedSystemVa[CurrentStackLocation->Parameters.Create.Options
                             + CurrentStackLocation->Parameters.Read.ByteOffset.LowPart];
        if ( (v17->MdlFlags & 5) != 0 )
          v18 = (char *)v17->MappedSystemVa;
        else
          v18 = (char *)MmMapLockedPages(v17, 0);
        RtlMoveVolatileMemory(
          &v18[CurrentStackLocation->Parameters.Read.ByteOffset.LowPart + CurrentStackLocation->Parameters.Read.Length],
          (const void *)(*(_QWORD *)(a2 + 152) + 6LL),
          v15);
        *(_WORD *)&Irql[Length - 2] = v15;
      }
      else
      {
        if ( (MdlAddress->MdlFlags & 5) != 0 )
          v19 = (char *)MdlAddress->MappedSystemVa;
        else
          v19 = (char *)MmMapLockedPages(MdlAddress, 0);
        RtlMoveVolatileMemory(
          &v19[CurrentStackLocation->Parameters.Read.ByteOffset.LowPart + CurrentStackLocation->Parameters.Read.Length],
          *(const void **)(a2 + 152),
          *(unsigned int *)(a2 + 160));
      }
    }
    v10 = AfdAcceptCore((__int64)Irp, QuadPart, a2);
    if ( v10 < 0 )
      goto LABEL_15;
    if ( (*(_DWORD *)(FsContext + 8) & 0x100) == 0 || v10 != 259 )
    {
LABEL_46:
      KeReleaseInStackQueuedSpinLock(LockHandle);
      if ( (*(_DWORD *)(v31 + 8) & 0x2000) != 0 )
        AfdDerefTLBaseEndpoint(v31);
      if ( !_InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, 0) )
      {
        LOBYTE(Irql) = 0;
        IoAcquireCancelSpinLock((PKIRQL)&Irql);
        IoReleaseCancelSpinLock((KIRQL)Irql);
      }
      if ( v10 != 259 )
      {
        v21 = Irp->MdlAddress;
        Irp->IoStatus.Status = 0;
        CurrentStackLocation->Parameters.CreatePipe.Parameters = (PNAMED_PIPE_CREATE_PARAMETERS)v21;
        Irp->MdlAddress = 0;
        CurrentStackLocation->FileObject = (PFILE_OBJECT)Parameters;
        if ( (*(_DWORD *)(FsContext + 8) & 0x100) != 0 )
          CurrentStackLocation->Parameters.Read.ByteOffset.LowPart = 0;
        AfdRestartSuperAcceptListen(Irp, a2);
        return 0;
      }
      if ( (*(_DWORD *)(FsContext + 8) & 0x100) == 0 )
      {
        _InterlockedAdd((volatile signed __int32 *)(FsContext + 180), 1u);
        CurrentStackLocation->Parameters.CreatePipe.Parameters = (PNAMED_PIPE_CREATE_PARAMETERS)Irp->MdlAddress;
        v23 = Irp->Tail.Overlay.CurrentStackLocation;
        Irp->MdlAddress = 0;
        v23[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)AfdRestartDelayedSuperAccept;
        v23[-1].Context = Parameters;
        v23[-1].Control = -32;
        _InterlockedAdd((volatile signed __int32 *)(v31 + 248), 1u);
        IofCallDriver(*(PDEVICE_OBJECT *)(a2 + 24), Irp);
        return 259;
      }
      Irp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = (struct _LIST_ENTRY *)a2;
      *(_QWORD *)(a2 + 40) = Irp;
      _InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, (__int64)AfdTLCancelResumeDelayAccept);
      if ( Irp->Cancel && _InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, 0) )
      {
        IoAcquireCancelSpinLock(&Irp->CancelIrql);
        AfdTLCancelResumeDelayAccept(0, Irp);
        if ( !v35 )
        {
          v22 = 2;
LABEL_61:
          AfdTLResumeConnectionSetup(FsContext, a2, v22);
        }
      }
      else if ( !v35 )
      {
        v22 = 1;
        goto LABEL_61;
      }
      return 259;
    }
    if ( _InterlockedIncrement64((volatile signed __int64 *)(FsContext + 64)) <= 1 )
      __fastfail(0xEu);
    v20 = *(_QWORD **)(FsContext + 152);
    if ( *v20 == FsContext + 144 )
    {
      *(_QWORD *)(a2 + 176) = FsContext + 144;
      *(_QWORD *)(a2 + 184) = v20;
      *v20 = a2 + 176;
      *(_QWORD *)(FsContext + 152) = a2 + 176;
      goto LABEL_46;
    }
LABEL_69:
    __fastfail(3u);
  }
  v10 = -1073741789;
LABEL_15:
  AfdCleanupSuperAccept((__int64)Irp, v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140036dac  mov     [rsp+arg_18], r9b
0x140036db1  mov     [rsp+LockHandle], r8
0x140036db6  push    rbx
0x140036db7  push    rbp
0x140036db8  push    rdi
0x140036db9  push    r12
0x140036dbb  push    r13
0x140036dbd  push    r14
0x140036dbf  push    r15
0x140036dc1  sub     rsp, 50h
0x140036dc5  mov     r15, [rcx+0B8h]
0x140036dcc  mov     r13, r8
0x140036dcf  mov     rbp, rdx
0x140036dd2  mov     rbx, rcx
0x140036dd5  cmp     byte ptr [r15], 0Fh
0x140036dd9  mov     rax, [r15+30h]
0x140036ddd  mov     r14, [rax+18h]
0x140036de1  jnz     loc_140037250
0x140036de7  cmp     byte ptr [r15+1], 20h ; ' '
0x140036dec  jnz     loc_140037250
0x140036df2  mov     eax, [r14+8]
0x140036df6  bt      eax, 8
0x140036dfa  jb      short loc_140036E22
0x140036dfc  mov     eax, [r14+8]
0x140036e00  bt      eax, 16h
0x140036e04  jnb     short loc_140036E22
0x140036e06  mov     eax, [rdx+4]
0x140036e09  test    al, 2
0x140036e0b  jz      short loc_140036E17
0x140036e0d  lock dec dword ptr [r14+0B0h]
0x140036e15  jmp     short loc_140036E22
0x140036e17  mov     rax, [r14+118h]
0x140036e1e  lock dec dword ptr [rax+30h]
0x140036e22  mov     eax, [r14+8]
0x140036e26  bt      eax, 8
0x140036e2a  jb      short loc_140036E38
0x140036e2c  mov     eax, [r15+10h]
0x140036e30  cmp     [rdx+0A0h], eax
0x140036e36  ja      short loc_140036E70
0x140036e38  mov     eax, [r14+8]
0x140036e3c  bt      eax, 8
0x140036e40  jnb     short loc_140036E51
0x140036e42  mov     eax, [rdx+0A0h]
0x140036e48  add     eax, 6
0x140036e4b  cmp     eax, [r15+10h]
0x140036e4f  ja      short loc_140036E70
0x140036e51  mov     eax, [r14+8]
0x140036e55  bt      eax, 8
0x140036e59  jnb     short loc_140036E84
0x140036e5b  mov     ecx, [r15+18h]
0x140036e5f  test    ecx, ecx
0x140036e61  jz      short loc_140036E84
0x140036e63  mov     eax, [rdx+0A8h]
0x140036e69  add     eax, 6
0x140036e6c  cmp     eax, ecx
0x140036e6e  jbe     short loc_140036E84
0x140036e70  mov     edi, 0C0000023h
0x140036e75  mov     edx, edi
0x140036e77  mov     rcx, rbx
0x140036e7a  call    AfdCleanupSuperAccept
0x140036e7f  jmp     loc_14003735B
0x140036e84  mov     rcx, [rbx+8]; MemoryDescriptorList
0x140036e88  call    AfdMapMdlChain
0x140036e8d  mov     edi, eax
0x140036e8f  test    eax, eax
0x140036e91  js      short loc_140036E75
0x140036e93  test    dword ptr [rbp+4], 20000000h
0x140036e9a  jz      short loc_140036ED7
0x140036e9c  mov     rdx, [r15+20h]
0x140036ea0  mov     r9, r13
0x140036ea3  mov     r8, rbp
0x140036ea6  mov     rcx, rbx
0x140036ea9  call    AfdSanAcceptCore
0x140036eae  mov     r12d, 103h
0x140036eb4  mov     edi, eax
0x140036eb6  cmp     eax, r12d
0x140036eb9  jnz     short loc_140036EC2
0x140036ebb  xor     eax, eax
0x140036ebd  jmp     loc_14003735D
0x140036ec2  lea     rcx, [r14+38h]; SpinLock
0x140036ec6  mov     rdx, r13; LockHandle
0x140036ec9  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140036ed0  nop     dword ptr [rax+rax+00h]
0x140036ed5  jmp     short loc_140036E75
0x140036ed7  mov     eax, [r14+8]
0x140036edb  mov     r13d, 1
0x140036ee1  bt      eax, 8
0x140036ee5  jb      short loc_140036F1D
0x140036ee7  mov     edx, [r15+18h]; Length
0x140036eeb  test    edx, edx
0x140036eed  jz      short loc_140036F1D
0x140036eef  mov     ecx, [r15+8]
0x140036ef3  xor     r9d, r9d; ChargeQuota
0x140036ef6  add     rcx, [rbx+70h]; VirtualAddress
0x140036efa  mov     r8b, r13b; SecondaryBuffer
0x140036efd  mov     [rsp+88h+Irp], rbx; Irp
0x140036f02  call    cs:__imp_IoAllocateMdl
0x140036f09  nop     dword ptr [rax+rax+00h]
0x140036f0e  test    rax, rax
0x140036f11  jnz     short loc_140036F1D
0x140036f13  mov     edi, 0C000009Ah
0x140036f18  jmp     loc_140036E75
0x140036f1d  xor     r9d, r9d
0x140036f20  mov     r8, r14
0x140036f23  mov     edx, 184Dh
0x140036f28  mov     ecx, r13d
0x140036f2b  call    AFDETW_TRACEWAITLISTEN
0x140036f30  mov     rax, [r15+20h]
0x140036f34  mov     [rsp+88h+var_58], rax
0x140036f39  mov     rdi, [rax+18h]
0x140036f3d  mov     eax, [r14+8]
0x140036f41  bt      eax, 8
0x140036f45  mov     [rsp+88h+var_50], rdi
0x140036f4a  jnb     short loc_140036F7D
0x140036f4c  mov     eax, [rbp+0A0h]
0x140036f52  mov     rcx, rdi
0x140036f55  mov     r9, [rbp+98h]
0x140036f5c  mov     r8d, [rbp+0A8h]
0x140036f63  mov     rdx, [rbp+0E0h]
0x140036f6a  mov     [rsp+88h+var_60], rbx
0x140036f6f  mov     dword ptr [rsp+88h+Irp], eax
0x140036f73  call    AfdTLCopyRemoteAndLocalAddresses
0x140036f78  jmp     loc_140037068
0x140036f7d  cmp     byte ptr [rdi+0BCh], 0
0x140036f84  mov     rcx, [rbx+8]; MemoryDescriptorList
0x140036f88  jz      loc_14003702D
0x140036f8e  mov     rax, [rbp+98h]
0x140036f95  movzx   r12d, word ptr [rax+4]
0x140036f9a  add     r12w, 2
0x140036f9f  test    byte ptr [rcx+0Ah], 5
0x140036fa3  jz      short loc_140036FAB
0x140036fa5  mov     rax, [rcx+18h]
0x140036fa9  jmp     short loc_140036FB9
0x140036fab  xor     edx, edx; AccessMode
0x140036fad  call    cs:__imp_MmMapLockedPages
0x140036fb4  nop     dword ptr [rax+rax+00h]
0x140036fb9  mov     ecx, [r15+18h]
0x140036fbd  mov     edx, [r15+10h]
0x140036fc1  add     rdx, rax
0x140036fc4  mov     eax, [r15+8]
0x140036fc8  add     rdx, rcx
0x140036fcb  mov     [rsp+88h+var_48], rax
0x140036fd0  mov     rcx, [rbx+8]; MemoryDescriptorList
0x140036fd4  mov     [rsp+88h+Irql], rdx
0x140036fdc  test    byte ptr [rcx+0Ah], 5
0x140036fe0  jz      short loc_140036FE8
0x140036fe2  mov     rax, [rcx+18h]
0x140036fe6  jmp     short loc_140036FF6
0x140036fe8  xor     edx, edx; AccessMode
0x140036fea  call    cs:__imp_MmMapLockedPages
0x140036ff1  nop     dword ptr [rax+rax+00h]
0x140036ff6  mov     r9d, [r15+18h]
0x140036ffa  mov     rdx, [rbp+98h]
0x140037001  add     rax, r9
0x140037004  mov     ecx, [r15+8]
0x140037008  add     rdx, 6; Src
0x14003700c  add     rcx, rax; void *
0x14003700f  movzx   r8d, r12w; Size
0x140037013  call    RtlMoveVolatileMemory
0x140037018  mov     rax, [rsp+88h+Irql]
0x140037020  mov     rcx, [rsp+88h+var_48]
0x140037025  mov     [rcx+rax-2], r12w
0x14003702b  jmp     short loc_140037068
0x14003702d  test    byte ptr [rcx+0Ah], 5
0x140037031  jz      short loc_140037039
0x140037033  mov     rax, [rcx+18h]
0x140037037  jmp     short loc_140037047
0x140037039  xor     edx, edx; AccessMode
0x14003703b  call    cs:__imp_MmMapLockedPages
0x140037042  nop     dword ptr [rax+rax+00h]
0x140037047  mov     edx, [r15+18h]
0x14003704b  mov     ecx, [r15+8]
0x14003704f  add     rax, rdx
0x140037052  mov     r8d, [rbp+0A0h]; Size
0x140037059  add     rcx, rax; void *
0x14003705c  mov     rdx, [rbp+98h]; Src
0x140037063  call    RtlMoveVolatileMemory
0x140037068  mov     r8, rbp
0x14003706b  mov     rdx, rdi
0x14003706e  mov     rcx, rbx
0x140037071  call    AfdAcceptCore
0x140037076  mov     edi, eax
0x140037078  test    eax, eax
0x14003707a  js      loc_140036E75
0x140037080  mov     eax, [r14+8]
0x140037084  mov     r12d, 103h
0x14003708a  bt      eax, 8
0x14003708e  jnb     short loc_1400370D6
0x140037090  cmp     edi, r12d
0x140037093  jnz     short loc_1400370D6
0x140037095  mov     rax, r13
0x140037098  lock xadd [r14+40h], rax
0x14003709e  add     rax, r13
0x1400370a1  cmp     rax, r13
0x1400370a4  jg      short loc_1400370AD
0x1400370a6  mov     ecx, 0Eh
0x1400370ab  int     29h; Win8: RtlFailFast(ecx)
0x1400370ad  lea     rcx, [r14+90h]
0x1400370b4  mov     rdx, [rcx+8]
0x1400370b8  cmp     [rdx], rcx
0x1400370bb  jnz     loc_1400372BC
0x1400370c1  lea     rax, [rbp+0B0h]
0x1400370c8  mov     [rax], rcx
0x1400370cb  mov     [rax+8], rdx
0x1400370cf  mov     [rdx], rax
0x1400370d2  mov     [rcx+8], rax
0x1400370d6  mov     rcx, [rsp+88h+LockHandle]; LockHandle
0x1400370de  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400370e5  nop     dword ptr [rax+rax+00h]
0x1400370ea  mov     rcx, [rsp+88h+var_50]
0x1400370ef  mov     eax, [rcx+8]
0x1400370f2  bt      eax, 0Dh
0x1400370f6  jnb     short loc_1400370FD
0x1400370f8  call    AfdDerefTLBaseEndpoint
0x1400370fd  xor     eax, eax
0x1400370ff  xchg    rax, [rbx+68h]
0x140037103  test    rax, rax
0x140037106  jnz     short loc_140037136
0x140037108  lea     rcx, [rsp+88h+Irql]; Irql
0x140037110  mov     byte ptr [rsp+88h+Irql], al
0x140037117  call    cs:__imp_IoAcquireCancelSpinLock
0x14003711e  nop     dword ptr [rax+rax+00h]
0x140037123  mov     cl, byte ptr [rsp+88h+Irql]; Irql
0x14003712a  call    cs:__imp_IoReleaseCancelSpinLock
0x140037131  nop     dword ptr [rax+rax+00h]
0x140037136  cmp     edi, r12d
0x140037139  jz      short loc_14003717D
0x14003713b  mov     rax, [rbx+8]
0x14003713f  mov     rcx, [rsp+88h+var_58]
0x140037144  mov     dword ptr [rbx+30h], 0
0x14003714b  mov     [r15+20h], rax
0x14003714f  mov     qword ptr [rbx+8], 0
0x140037157  mov     [r15+30h], rcx
0x14003715b  mov     eax, [r14+8]
0x14003715f  bt      eax, 8
0x140037163  jnb     short loc_14003716D
0x140037165  mov     dword ptr [r15+18h], 0
0x14003716d  mov     rdx, rbp
0x140037170  mov     rcx, rbx; Irp
0x140037173  call    AfdRestartSuperAcceptListen
0x140037178  jmp     loc_140036EBB
0x14003717d  mov     eax, [r14+8]
0x140037181  bt      eax, 8
0x140037185  jnb     short loc_1400371F7
0x140037187  mov     [rbx+78h], rbp
0x14003718b  lea     rax, AfdTLCancelResumeDelayAccept
0x140037192  mov     [rbp+28h], rbx
0x140037196  xchg    rax, [rbx+68h]
0x14003719a  cmp     byte ptr [rbx+44h], 0
0x14003719e  jz      short loc_1400371D7
0x1400371a0  xor     eax, eax
0x1400371a2  xchg    rax, [rbx+68h]
0x1400371a6  test    rax, rax
0x1400371a9  jz      short loc_1400371D7
0x1400371ab  lea     rcx, [rbx+45h]; Irql
0x1400371af  call    cs:__imp_IoAcquireCancelSpinLock
0x1400371b6  nop     dword ptr [rax+rax+00h]
0x1400371bb  mov     rdx, rbx
0x1400371be  xor     ecx, ecx
0x1400371c0  call    AfdTLCancelResumeDelayAccept
0x1400371c5  cmp     [rsp+88h+arg_18], 0
0x1400371cd  jnz     short loc_1400371EF
0x1400371cf  mov     r8d, 2
0x1400371d5  jmp     short loc_1400371E4
0x1400371d7  cmp     [rsp+88h+arg_18], 0
0x1400371df  jnz     short loc_1400371EF
0x1400371e1  mov     r8d, r13d
0x1400371e4  mov     rdx, rbp
0x1400371e7  mov     rcx, r14
0x1400371ea  call    AfdTLResumeConnectionSetup
0x1400371ef  mov     eax, r12d
0x1400371f2  jmp     loc_14003735D
0x1400371f7  lock add [r14+0B4h], r13d
0x1400371ff  mov     rax, [rbx+8]
0x140037203  lea     rcx, AfdRestartDelayedSuperAccept
0x14003720a  mov     [r15+20h], rax
0x14003720e  mov     rax, [rbx+0B8h]
0x140037215  mov     qword ptr [rbx+8], 0
0x14003721d  mov     [rax-10h], rcx
0x140037221  mov     rcx, [rsp+88h+var_58]
0x140037226  mov     [rax-8], rcx
0x14003722a  mov     byte ptr [rax-45h], 0E0h
0x14003722e  mov     rax, [rsp+88h+var_50]
0x140037233  lock add [rax+0F8h], r13d
0x14003723b  mov     rcx, [rbp+18h]; DeviceObject
0x14003723f  mov     rdx, rbx; Irp
0x140037242  call    cs:__imp_IofCallDriver
0x140037249  nop     dword ptr [rax+rax+00h]
0x14003724e  jmp     short loc_1400371EF
0x140037250  mov     eax, [rdx+0A0h]
0x140037256  add     eax, 4
0x140037259  cmp     eax, [r15+8]
0x14003725d  jbe     short loc_14003726C
0x14003725f  mov     edi, 0C0000023h
0x140037264  mov     [rcx+30h], edi
0x140037267  jmp     loc_14003735B
0x14003726c  mov     rcx, [rcx+18h]
0x140037270  mov     eax, [r14+0B8h]
0x140037277  add     eax, 1
0x14003727a  mov     [r14+0B8h], eax
  ... truncated ...
```
