# AfdServiceWaitForListen

- ea: `0x140036dcc`
- end: `0x14003738e`
- name: `AfdServiceWaitForListen`
- size: `1474`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `5`
- callee_count: `13`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x14002d8d0`
- `0x14002f800`
- `0x14004c770`
- `0x14004d5b0`
- `0x140059ab0`

## callees

- `0x1400049b0`
- `0x140004c10`
- `0x140009fb0`
- `0x14000dc90`
- `0x14001a030`
- `0x14001aabc`
- `0x14002e7a8`
- `0x140036708`
- `0x140036d2c`
- `0x140036dcc`
- `0x14004d400`
- `0x140072880`
- `0x140072980`

## import_xrefs

- `ntoskrnl!MmMapLockedPages` at `0x140036fcd`
- `ntoskrnl!MmMapLockedPages` at `0x14003700a`
- `ntoskrnl!MmMapLockedPages` at `0x14003705b`
- `ntoskrnl!MmMapLockedPages` at `0x140036fcd`
- `ntoskrnl!MmMapLockedPages` at `0x14003700a`
- `ntoskrnl!MmMapLockedPages` at `0x14003705b`
- `ntoskrnl!IoAllocateMdl` at `0x140036f22`
- `ntoskrnl!IoAllocateMdl` at `0x140036f22`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14003714a`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140037343`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14003714a`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140037343`
- `ntoskrnl!IofCompleteRequest` at `0x14003736f`
- `ntoskrnl!IofCompleteRequest` at `0x14003736f`
- `ntoskrnl!IofCallDriver` at `0x140037262`
- `ntoskrnl!IofCallDriver` at `0x140037262`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140037137`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400371cf`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140037330`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140037137`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400371cf`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x140037330`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400370fe`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140037303`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400370fe`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140037303`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140036ee9`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140036ee9`

## pseudocode

```c
__int64 __fastcall AfdServiceWaitForListen(PIRP Irp, __int64 a2, struct _KLOCK_QUEUE_HANDLE *a3, char a4)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r15
  char *FsContext; // r14
  unsigned int v9; // ecx
  int v10; // edi
  ULONG LowPart; // edx
  _BYTE *v13; // rdi
  PMDL MdlAddress; // rcx
  unsigned __int16 v15; // r12
  char *MappedSystemVa; // rax
  PMDL v17; // rcx
  char *v18; // rax
  char *v19; // rax
  PVOID *v20; // rdx
  PMDL v21; // rax
  __int64 v22; // r8
  struct _IO_STACK_LOCATION *v23; // rax
  struct _IRP *MasterIrp; // rcx
  int v25; // eax
  bool v26; // zf
  int v27; // eax
  PVOID *v28; // rdx
  CCHAR v29; // dl
  struct _FILE_OBJECT *Parameters; // [rsp+30h] [rbp-58h]
  _BYTE *v31; // [rsp+38h] [rbp-50h]
  __int64 Length; // [rsp+40h] [rbp-48h]
  char *Irql; // [rsp+90h] [rbp+8h] BYREF
  PKLOCK_QUEUE_HANDLE LockHandle; // [rsp+A0h] [rbp+18h]
  char v35; // [rsp+A8h] [rbp+20h]

  v35 = a4;
  LockHandle = a3;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  FsContext = (char *)CurrentStackLocation->FileObject->FsContext;
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
      v25 = *((_DWORD *)FsContext + 46);
      v26 = v25 == -1;
      v27 = v25 + 1;
      *((_DWORD *)FsContext + 46) = v27;
      *(_DWORD *)(a2 + 164) = v27;
    }
    while ( v26 );
    *(_DWORD *)&MasterIrp->Type = v27;
    memmove(&MasterIrp->Size + 1, *(const void **)(a2 + 152), *(unsigned int *)(a2 + 160));
    Irp->IoStatus.Information = (unsigned int)(*(_DWORD *)(a2 + 160) + 4);
    v28 = (PVOID *)*((_QWORD *)FsContext + 15);
    if ( *v28 == FsContext + 112 )
    {
      v10 = 0;
      *(_QWORD *)(a2 + 176) = FsContext + 112;
      *(_QWORD *)(a2 + 184) = v28;
      *v28 = (PVOID)(a2 + 176);
      *((_QWORD *)FsContext + 15) = a2 + 176;
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
  if ( (*((_DWORD *)FsContext + 2) & 0x100) == 0 && (*((_DWORD *)FsContext + 2) & 0x400000) != 0 )
  {
    if ( (*(_DWORD *)(a2 + 4) & 2) != 0 )
      _InterlockedDecrement((volatile signed __int32 *)FsContext + 44);
    else
      _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)FsContext + 35) + 48LL));
  }
  if ( ((*((_DWORD *)FsContext + 2) & 0x100) != 0
     || *(_DWORD *)(a2 + 160) <= CurrentStackLocation->Parameters.Create.Options)
    && ((*((_DWORD *)FsContext + 2) & 0x100) == 0
     || *(_DWORD *)(a2 + 160) + 6 <= CurrentStackLocation->Parameters.Create.Options)
    && ((*((_DWORD *)FsContext + 2) & 0x100) == 0
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
        KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)FsContext + 7, a3);
        goto LABEL_15;
      }
      return 0;
    }
    if ( (*((_DWORD *)FsContext + 2) & 0x100) == 0 )
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
    Parameters = (struct _FILE_OBJECT *)CurrentStackLocation->Parameters.CreatePipe.Parameters;
    v13 = Parameters->FsContext;
    v31 = v13;
    if ( (*((_DWORD *)FsContext + 2) & 0x100) != 0 )
    {
      AfdTLCopyRemoteAndLocalAddresses(
        v13,
        *(_QWORD *)(a2 + 224),
        *(unsigned int *)(a2 + 168),
        *(_QWORD *)(a2 + 152),
        *(_DWORD *)(a2 + 160),
        Irp);
    }
    else
    {
      MdlAddress = Irp->MdlAddress;
      if ( v13[188] )
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
    v10 = AfdAcceptCore(Irp, v13, a2);
    if ( v10 < 0 )
      goto LABEL_15;
    if ( (*((_DWORD *)FsContext + 2) & 0x100) == 0 || v10 != 259 )
    {
LABEL_46:
      KeReleaseInStackQueuedSpinLock(LockHandle);
      if ( (*((_DWORD *)v31 + 2) & 0x2000) != 0 )
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
        CurrentStackLocation->FileObject = Parameters;
        if ( (*((_DWORD *)FsContext + 2) & 0x100) != 0 )
          CurrentStackLocation->Parameters.Read.ByteOffset.LowPart = 0;
        AfdRestartSuperAcceptListen(Irp);
        return 0;
      }
      if ( (*((_DWORD *)FsContext + 2) & 0x100) == 0 )
      {
        _InterlockedAdd((volatile signed __int32 *)FsContext + 45, 1u);
        CurrentStackLocation->Parameters.CreatePipe.Parameters = (PNAMED_PIPE_CREATE_PARAMETERS)Irp->MdlAddress;
        v23 = Irp->Tail.Overlay.CurrentStackLocation;
        Irp->MdlAddress = 0;
        v23[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&AfdRestartDelayedSuperAccept;
        v23[-1].Context = Parameters;
        v23[-1].Control = -32;
        _InterlockedAdd((volatile signed __int32 *)v31 + 62, 1u);
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
    if ( _InterlockedIncrement64((volatile signed __int64 *)FsContext + 8) <= 1 )
      __fastfail(0xEu);
    v20 = (PVOID *)*((_QWORD *)FsContext + 19);
    if ( *v20 == FsContext + 144 )
    {
      *(_QWORD *)(a2 + 176) = FsContext + 144;
      *(_QWORD *)(a2 + 184) = v20;
      *v20 = (PVOID)(a2 + 176);
      *((_QWORD *)FsContext + 19) = a2 + 176;
      goto LABEL_46;
    }
LABEL_69:
    __fastfail(3u);
  }
  v10 = -1073741789;
LABEL_15:
  AfdCleanupSuperAccept(Irp, (unsigned int)v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140036dcc  mov     [rsp+arg_18], r9b
0x140036dd1  mov     [rsp+LockHandle], r8
0x140036dd6  push    rbx
0x140036dd7  push    rbp
0x140036dd8  push    rdi
0x140036dd9  push    r12
0x140036ddb  push    r13
0x140036ddd  push    r14
0x140036ddf  push    r15
0x140036de1  sub     rsp, 50h
0x140036de5  mov     r15, [rcx+0B8h]
0x140036dec  mov     r13, r8
0x140036def  mov     rbp, rdx
0x140036df2  mov     rbx, rcx
0x140036df5  cmp     byte ptr [r15], 0Fh
0x140036df9  mov     rax, [r15+30h]
0x140036dfd  mov     r14, [rax+18h]
0x140036e01  jnz     loc_140037270
0x140036e07  cmp     byte ptr [r15+1], 20h ; ' '
0x140036e0c  jnz     loc_140037270
0x140036e12  mov     eax, [r14+8]
0x140036e16  bt      eax, 8
0x140036e1a  jb      short loc_140036E42
0x140036e1c  mov     eax, [r14+8]
0x140036e20  bt      eax, 16h
0x140036e24  jnb     short loc_140036E42
0x140036e26  mov     eax, [rdx+4]
0x140036e29  test    al, 2
0x140036e2b  jz      short loc_140036E37
0x140036e2d  lock dec dword ptr [r14+0B0h]
0x140036e35  jmp     short loc_140036E42
0x140036e37  mov     rax, [r14+118h]
0x140036e3e  lock dec dword ptr [rax+30h]
0x140036e42  mov     eax, [r14+8]
0x140036e46  bt      eax, 8
0x140036e4a  jb      short loc_140036E58
0x140036e4c  mov     eax, [r15+10h]
0x140036e50  cmp     [rdx+0A0h], eax
0x140036e56  ja      short loc_140036E90
0x140036e58  mov     eax, [r14+8]
0x140036e5c  bt      eax, 8
0x140036e60  jnb     short loc_140036E71
0x140036e62  mov     eax, [rdx+0A0h]
0x140036e68  add     eax, 6
0x140036e6b  cmp     eax, [r15+10h]
0x140036e6f  ja      short loc_140036E90
0x140036e71  mov     eax, [r14+8]
0x140036e75  bt      eax, 8
0x140036e79  jnb     short loc_140036EA4
0x140036e7b  mov     ecx, [r15+18h]
0x140036e7f  test    ecx, ecx
0x140036e81  jz      short loc_140036EA4
0x140036e83  mov     eax, [rdx+0A8h]
0x140036e89  add     eax, 6
0x140036e8c  cmp     eax, ecx
0x140036e8e  jbe     short loc_140036EA4
0x140036e90  mov     edi, 0C0000023h
0x140036e95  mov     edx, edi
0x140036e97  mov     rcx, rbx
0x140036e9a  call    AfdCleanupSuperAccept
0x140036e9f  jmp     loc_14003737B
0x140036ea4  mov     rcx, [rbx+8]; MemoryDescriptorList
0x140036ea8  call    AfdMapMdlChain
0x140036ead  mov     edi, eax
0x140036eaf  test    eax, eax
0x140036eb1  js      short loc_140036E95
0x140036eb3  test    dword ptr [rbp+4], 20000000h
0x140036eba  jz      short loc_140036EF7
0x140036ebc  mov     rdx, [r15+20h]
0x140036ec0  mov     r9, r13
0x140036ec3  mov     r8, rbp
0x140036ec6  mov     rcx, rbx
0x140036ec9  call    AfdSanAcceptCore
0x140036ece  mov     r12d, 103h
0x140036ed4  mov     edi, eax
0x140036ed6  cmp     eax, r12d
0x140036ed9  jnz     short loc_140036EE2
0x140036edb  xor     eax, eax
0x140036edd  jmp     loc_14003737D
0x140036ee2  lea     rcx, [r14+38h]; SpinLock
0x140036ee6  mov     rdx, r13; LockHandle
0x140036ee9  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140036ef0  nop     dword ptr [rax+rax+00h]
0x140036ef5  jmp     short loc_140036E95
0x140036ef7  mov     eax, [r14+8]
0x140036efb  mov     r13d, 1
0x140036f01  bt      eax, 8
0x140036f05  jb      short loc_140036F3D
0x140036f07  mov     edx, [r15+18h]; Length
0x140036f0b  test    edx, edx
0x140036f0d  jz      short loc_140036F3D
0x140036f0f  mov     ecx, [r15+8]
0x140036f13  xor     r9d, r9d; ChargeQuota
0x140036f16  add     rcx, [rbx+70h]; VirtualAddress
0x140036f1a  mov     r8b, r13b; SecondaryBuffer
0x140036f1d  mov     [rsp+88h+Irp], rbx; Irp
0x140036f22  call    cs:__imp_IoAllocateMdl
0x140036f29  nop     dword ptr [rax+rax+00h]
0x140036f2e  test    rax, rax
0x140036f31  jnz     short loc_140036F3D
0x140036f33  mov     edi, 0C000009Ah
0x140036f38  jmp     loc_140036E95
0x140036f3d  xor     r9d, r9d
0x140036f40  mov     r8, r14
0x140036f43  mov     edx, 184Dh
0x140036f48  mov     ecx, r13d
0x140036f4b  call    AFDETW_TRACEWAITLISTEN
0x140036f50  mov     rax, [r15+20h]
0x140036f54  mov     [rsp+88h+var_58], rax
0x140036f59  mov     rdi, [rax+18h]
0x140036f5d  mov     eax, [r14+8]
0x140036f61  bt      eax, 8
0x140036f65  mov     [rsp+88h+var_50], rdi
0x140036f6a  jnb     short loc_140036F9D
0x140036f6c  mov     eax, [rbp+0A0h]
0x140036f72  mov     rcx, rdi
0x140036f75  mov     r9, [rbp+98h]
0x140036f7c  mov     r8d, [rbp+0A8h]
0x140036f83  mov     rdx, [rbp+0E0h]
0x140036f8a  mov     [rsp+88h+var_60], rbx
0x140036f8f  mov     dword ptr [rsp+88h+Irp], eax
0x140036f93  call    AfdTLCopyRemoteAndLocalAddresses
0x140036f98  jmp     loc_140037088
0x140036f9d  cmp     byte ptr [rdi+0BCh], 0
0x140036fa4  mov     rcx, [rbx+8]; MemoryDescriptorList
0x140036fa8  jz      loc_14003704D
0x140036fae  mov     rax, [rbp+98h]
0x140036fb5  movzx   r12d, word ptr [rax+4]
0x140036fba  add     r12w, 2
0x140036fbf  test    byte ptr [rcx+0Ah], 5
0x140036fc3  jz      short loc_140036FCB
0x140036fc5  mov     rax, [rcx+18h]
0x140036fc9  jmp     short loc_140036FD9
0x140036fcb  xor     edx, edx; AccessMode
0x140036fcd  call    cs:__imp_MmMapLockedPages
0x140036fd4  nop     dword ptr [rax+rax+00h]
0x140036fd9  mov     ecx, [r15+18h]
0x140036fdd  mov     edx, [r15+10h]
0x140036fe1  add     rdx, rax
0x140036fe4  mov     eax, [r15+8]
0x140036fe8  add     rdx, rcx
0x140036feb  mov     [rsp+88h+var_48], rax
0x140036ff0  mov     rcx, [rbx+8]; MemoryDescriptorList
0x140036ff4  mov     [rsp+88h+Irql], rdx
0x140036ffc  test    byte ptr [rcx+0Ah], 5
0x140037000  jz      short loc_140037008
0x140037002  mov     rax, [rcx+18h]
0x140037006  jmp     short loc_140037016
0x140037008  xor     edx, edx; AccessMode
0x14003700a  call    cs:__imp_MmMapLockedPages
0x140037011  nop     dword ptr [rax+rax+00h]
0x140037016  mov     r9d, [r15+18h]
0x14003701a  mov     rdx, [rbp+98h]
0x140037021  add     rax, r9
0x140037024  mov     ecx, [r15+8]
0x140037028  add     rdx, 6; Src
0x14003702c  add     rcx, rax; void *
0x14003702f  movzx   r8d, r12w; Size
0x140037033  call    RtlMoveVolatileMemory
0x140037038  mov     rax, [rsp+88h+Irql]
0x140037040  mov     rcx, [rsp+88h+var_48]
0x140037045  mov     [rcx+rax-2], r12w
0x14003704b  jmp     short loc_140037088
0x14003704d  test    byte ptr [rcx+0Ah], 5
0x140037051  jz      short loc_140037059
0x140037053  mov     rax, [rcx+18h]
0x140037057  jmp     short loc_140037067
0x140037059  xor     edx, edx; AccessMode
0x14003705b  call    cs:__imp_MmMapLockedPages
0x140037062  nop     dword ptr [rax+rax+00h]
0x140037067  mov     edx, [r15+18h]
0x14003706b  mov     ecx, [r15+8]
0x14003706f  add     rax, rdx
0x140037072  mov     r8d, [rbp+0A0h]; Size
0x140037079  add     rcx, rax; void *
0x14003707c  mov     rdx, [rbp+98h]; Src
0x140037083  call    RtlMoveVolatileMemory
0x140037088  mov     r8, rbp
0x14003708b  mov     rdx, rdi
0x14003708e  mov     rcx, rbx
0x140037091  call    AfdAcceptCore
0x140037096  mov     edi, eax
0x140037098  test    eax, eax
0x14003709a  js      loc_140036E95
0x1400370a0  mov     eax, [r14+8]
0x1400370a4  mov     r12d, 103h
0x1400370aa  bt      eax, 8
0x1400370ae  jnb     short loc_1400370F6
0x1400370b0  cmp     edi, r12d
0x1400370b3  jnz     short loc_1400370F6
0x1400370b5  mov     rax, r13
0x1400370b8  lock xadd [r14+40h], rax
0x1400370be  add     rax, r13
0x1400370c1  cmp     rax, r13
0x1400370c4  jg      short loc_1400370CD
0x1400370c6  mov     ecx, 0Eh
0x1400370cb  int     29h; Win8: RtlFailFast(ecx)
0x1400370cd  lea     rcx, [r14+90h]
0x1400370d4  mov     rdx, [rcx+8]
0x1400370d8  cmp     [rdx], rcx
0x1400370db  jnz     loc_1400372DC
0x1400370e1  lea     rax, [rbp+0B0h]
0x1400370e8  mov     [rax], rcx
0x1400370eb  mov     [rax+8], rdx
0x1400370ef  mov     [rdx], rax
0x1400370f2  mov     [rcx+8], rax
0x1400370f6  mov     rcx, [rsp+88h+LockHandle]; LockHandle
0x1400370fe  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140037105  nop     dword ptr [rax+rax+00h]
0x14003710a  mov     rcx, [rsp+88h+var_50]
0x14003710f  mov     eax, [rcx+8]
0x140037112  bt      eax, 0Dh
0x140037116  jnb     short loc_14003711D
0x140037118  call    AfdDerefTLBaseEndpoint
0x14003711d  xor     eax, eax
0x14003711f  xchg    rax, [rbx+68h]
0x140037123  test    rax, rax
0x140037126  jnz     short loc_140037156
0x140037128  lea     rcx, [rsp+88h+Irql]; Irql
0x140037130  mov     byte ptr [rsp+88h+Irql], al
0x140037137  call    cs:__imp_IoAcquireCancelSpinLock
0x14003713e  nop     dword ptr [rax+rax+00h]
0x140037143  mov     cl, byte ptr [rsp+88h+Irql]; Irql
0x14003714a  call    cs:__imp_IoReleaseCancelSpinLock
0x140037151  nop     dword ptr [rax+rax+00h]
0x140037156  cmp     edi, r12d
0x140037159  jz      short loc_14003719D
0x14003715b  mov     rax, [rbx+8]
0x14003715f  mov     rcx, [rsp+88h+var_58]
0x140037164  mov     dword ptr [rbx+30h], 0
0x14003716b  mov     [r15+20h], rax
0x14003716f  mov     qword ptr [rbx+8], 0
0x140037177  mov     [r15+30h], rcx
0x14003717b  mov     eax, [r14+8]
0x14003717f  bt      eax, 8
0x140037183  jnb     short loc_14003718D
0x140037185  mov     dword ptr [r15+18h], 0
0x14003718d  mov     rdx, rbp
0x140037190  mov     rcx, rbx; Irp
0x140037193  call    AfdRestartSuperAcceptListen
0x140037198  jmp     loc_140036EDB
0x14003719d  mov     eax, [r14+8]
0x1400371a1  bt      eax, 8
0x1400371a5  jnb     short loc_140037217
0x1400371a7  mov     [rbx+78h], rbp
0x1400371ab  lea     rax, AfdTLCancelResumeDelayAccept
0x1400371b2  mov     [rbp+28h], rbx
0x1400371b6  xchg    rax, [rbx+68h]
0x1400371ba  cmp     byte ptr [rbx+44h], 0
0x1400371be  jz      short loc_1400371F7
0x1400371c0  xor     eax, eax
0x1400371c2  xchg    rax, [rbx+68h]
0x1400371c6  test    rax, rax
0x1400371c9  jz      short loc_1400371F7
0x1400371cb  lea     rcx, [rbx+45h]; Irql
0x1400371cf  call    cs:__imp_IoAcquireCancelSpinLock
0x1400371d6  nop     dword ptr [rax+rax+00h]
0x1400371db  mov     rdx, rbx
0x1400371de  xor     ecx, ecx
0x1400371e0  call    AfdTLCancelResumeDelayAccept
0x1400371e5  cmp     [rsp+88h+arg_18], 0
0x1400371ed  jnz     short loc_14003720F
0x1400371ef  mov     r8d, 2
0x1400371f5  jmp     short loc_140037204
0x1400371f7  cmp     [rsp+88h+arg_18], 0
0x1400371ff  jnz     short loc_14003720F
0x140037201  mov     r8d, r13d
0x140037204  mov     rdx, rbp
0x140037207  mov     rcx, r14
0x14003720a  call    AfdTLResumeConnectionSetup
0x14003720f  mov     eax, r12d
0x140037212  jmp     loc_14003737D
0x140037217  lock add [r14+0B4h], r13d
0x14003721f  mov     rax, [rbx+8]
0x140037223  lea     rcx, AfdRestartDelayedSuperAccept
0x14003722a  mov     [r15+20h], rax
0x14003722e  mov     rax, [rbx+0B8h]
0x140037235  mov     qword ptr [rbx+8], 0
0x14003723d  mov     [rax-10h], rcx
0x140037241  mov     rcx, [rsp+88h+var_58]
0x140037246  mov     [rax-8], rcx
0x14003724a  mov     byte ptr [rax-45h], 0E0h
0x14003724e  mov     rax, [rsp+88h+var_50]
0x140037253  lock add [rax+0F8h], r13d
0x14003725b  mov     rcx, [rbp+18h]; DeviceObject
0x14003725f  mov     rdx, rbx; Irp
0x140037262  call    cs:__imp_IofCallDriver
0x140037269  nop     dword ptr [rax+rax+00h]
0x14003726e  jmp     short loc_14003720F
0x140037270  mov     eax, [rdx+0A0h]
0x140037276  add     eax, 4
0x140037279  cmp     eax, [r15+8]
0x14003727d  jbe     short loc_14003728C
0x14003727f  mov     edi, 0C0000023h
0x140037284  mov     [rcx+30h], edi
0x140037287  jmp     loc_14003737B
0x14003728c  mov     rcx, [rcx+18h]
0x140037290  mov     eax, [r14+0B8h]
0x140037297  add     eax, 1
0x14003729a  mov     [r14+0B8h], eax
  ... truncated ...
```
