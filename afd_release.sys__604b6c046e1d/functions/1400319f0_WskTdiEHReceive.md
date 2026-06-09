# WskTdiEHReceive

- ea: `0x1400319f0`
- end: `0x140031d5b`
- name: `WskTdiEHReceive`
- size: `875`
- prototype: `__int64 __fastcall(__int64, __int64, int, unsigned int, unsigned int, unsigned int *, PVOID SourceBuffer, PMDL Mdl)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140063760`

## callees

- `0x1400319f0`
- `0x14004efd0`
- `0x140063fc0`
- `0x140072780`
- `0x140072b00`

## import_xrefs

- `ntoskrnl!PsChargeProcessPoolQuota` at `0x140078ecf`
- `ntoskrnl!PsChargeProcessPoolQuota` at `0x140078ecf`
- `ntoskrnl!PsReturnPoolQuota` at `0x140031d3b`
- `ntoskrnl!PsReturnPoolQuota` at `0x140078f10`
- `ntoskrnl!PsReturnPoolQuota` at `0x140031d3b`
- `ntoskrnl!PsReturnPoolQuota` at `0x140078f10`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140031b03`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140031b03`
- `ntoskrnl!IoAllocateIrp` at `0x140078f4e`
- `ntoskrnl!IoAllocateIrp` at `0x140078f4e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140031a6b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140031a6b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140031bed`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140078f26`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140031bed`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140078f26`
- `ntoskrnl!IoFreeMdl` at `0x140031bc3`
- `ntoskrnl!IoFreeMdl` at `0x140031bc3`
- `ntoskrnl!ObfReferenceObject` at `0x140031d05`
- `ntoskrnl!ObfReferenceObject` at `0x140031d05`
- `ntoskrnl!IoAllocateMdl` at `0x140031ae4`
- `ntoskrnl!IoAllocateMdl` at `0x140031ae4`
- `ntoskrnl!ObfDereferenceObject` at `0x140031d4a`
- `ntoskrnl!ObfDereferenceObject` at `0x140031d4a`
- `ntoskrnl!IofCallDriver` at `0x14007902f`
- `ntoskrnl!IofCallDriver` at `0x14007902f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140031a87`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140031c6f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140078f66`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140031a87`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140031c6f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140078f66`
- `ntoskrnl!KeReleaseSpinLock` at `0x140078eb2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140078fab`
- `ntoskrnl!KeReleaseSpinLock` at `0x140079048`
- `ntoskrnl!KeReleaseSpinLock` at `0x140078eb2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140078fab`
- `ntoskrnl!KeReleaseSpinLock` at `0x140079048`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031bd7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031ce8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031bd7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031ce8`
- `ntoskrnl!ExAllocatePool2` at `0x140031cba`
- `ntoskrnl!ExAllocatePool2` at `0x140078eed`
- `ntoskrnl!ExAllocatePool2` at `0x140031cba`
- `ntoskrnl!ExAllocatePool2` at `0x140078eed`
- `TDI!TdiCopyBufferToMdl` at `0x140031b2c`
- `TDI!TdiCopyBufferToMdl` at `0x140031b2c`

## pseudocode

```c
__int64 __fastcall WskTdiEHReceive(
        __int64 a1,
        __int64 a2,
        int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int *a6,
        PVOID SourceBuffer,
        PMDL Mdl)
{
  unsigned int *v8; // rcx
  unsigned __int64 v9; // r12
  PMDL v10; // rax
  struct _KPROCESS *v12; // rdi
  char *v13; // rax
  char *v14; // r14
  KIRQL v15; // si
  int v16; // r8d
  struct _MDL *v17; // rax
  struct _MDL *v18; // r13
  char *v19; // rax
  __int16 v20; // cx
  int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // r13d
  unsigned __int64 v24; // rcx
  KSPIN_LOCK *v26; // rsi
  KIRQL v27; // al
  KSPIN_LOCK *v28; // rcx
  KIRQL v29; // dl
  void *Pool2; // r15
  PIRP Irp; // rax
  IRP *v32; // rdx
  KIRQL v33; // si
  int v34; // r8d
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v36; // rcx
  __int128 v37; // [rsp+30h] [rbp-40h] BYREF
  __int128 v38; // [rsp+40h] [rbp-30h]
  __int128 v39; // [rsp+50h] [rbp-20h]
  __int64 v40; // [rsp+60h] [rbp-10h]
  ULONG BytesCopied; // [rsp+B8h] [rbp+48h] BYREF
  int v42; // [rsp+C0h] [rbp+50h]

  v42 = a3;
  v8 = a6;
  v9 = a4;
  v40 = 0;
  v10 = Mdl;
  *a6 = 0;
  v37 = 0;
  BytesCopied = 0;
  v10->Next = 0;
  v38 = 0;
  *(_DWORD *)(a2 + 216) = 0;
  v39 = 0;
  if ( *(_QWORD *)(a2 + 208) )
  {
    *v8 = a5;
    return 0;
  }
  v12 = *(struct _KPROCESS **)(a2 + 272);
  if ( !*(_QWORD *)(a2 + 288) )
  {
    v26 = (KSPIN_LOCK *)(a2 + 8);
    v27 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 8));
    v28 = v26;
    v29 = v27;
    if ( !*(_QWORD *)(a2 + 288) )
    {
      *(_DWORD *)(a2 + 16) |= 0x4000u;
LABEL_48:
      KeReleaseSpinLock(v28, v29);
      return 3221226011LL;
    }
    KeReleaseSpinLock(v26, v27);
  }
  v13 = (char *)ExAllocateFromNPagedLookasideList(&Lookaside);
  v14 = v13;
  if ( !v13 )
  {
LABEL_4:
    v15 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 8));
    if ( (*(_DWORD *)(a2 + 16) & 0x8000) == 0 )
    {
      if ( (unsigned __int8)WskTdiRetainTDIEndpoint(a2) )
      {
        *(_DWORD *)(a2 + 16) |= v16;
        AfdLRListAddItem((PSLIST_ENTRY)(a2 + 224));
      }
    }
    v29 = v15;
    v28 = (KSPIN_LOCK *)(a2 + 8);
    goto LABEL_48;
  }
  memset(v13, 0, 0x68u);
  if ( !v12 )
  {
    Pool2 = (void *)ExAllocatePool2(64, v9, 1917539159);
    if ( Pool2 )
      goto LABEL_7;
LABEL_39:
    ExFreeToNPagedLookasideList(&Lookaside, v14);
    goto LABEL_4;
  }
  if ( PsChargeProcessPoolQuota(v12, (POOL_TYPE)512, v9) < 0 )
    goto LABEL_39;
  Pool2 = (void *)ExAllocatePool2(64, v9, 1917539159);
  if ( !Pool2 )
  {
LABEL_38:
    PsReturnPoolQuota(v12, (POOL_TYPE)512, v9);
    goto LABEL_39;
  }
LABEL_7:
  v17 = IoAllocateMdl(Pool2, v9, 0, 0, 0);
  Mdl = v17;
  v18 = v17;
  if ( !v17 )
  {
    ExFreePoolWithTag(Pool2, 0x724B5357u);
    if ( !v12 )
      goto LABEL_39;
    goto LABEL_38;
  }
  MmBuildMdlForNonPagedPool(v17);
  TdiCopyBufferToMdl(SourceBuffer, 0, v9, v18, 0, &BytesCopied);
  *((_QWORD *)v14 + 2) = v18;
  v19 = v14 + 8;
  *((_QWORD *)v14 + 1) = 0;
  *((_DWORD *)v14 + 6) = 0;
  *((_QWORD *)v14 + 4) = v9;
  if ( v12 )
  {
    ObfReferenceObject(v12);
    v19 = v14 + 8;
  }
  v20 = v42;
  *((_QWORD *)v14 + 10) = v12;
  *((_QWORD *)v14 + 11) = Pool2;
  *(_QWORD *)&v38 = v19;
  v21 = v37;
  *((_QWORD *)&v38 + 1) = v9;
  *(_QWORD *)&v39 = -1;
  if ( (v20 & 0x40) != 0 )
  {
    v21 = v37 | 1;
    LODWORD(v37) = v37 | 1;
  }
  if ( (v20 & 0x400) != 0 )
    LODWORD(v37) = v21 | 2;
  v22 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)(a2 + 288) + 16LL))(*(_QWORD *)(a2 + 280), &v37);
  v23 = 0;
  if ( v22 != -1073741802 )
    v23 = v22;
  if ( (_QWORD)v38 )
  {
    IoFreeMdl(Mdl);
    ExFreePoolWithTag(Pool2, 0x724B5357u);
    ExFreeToNPagedLookasideList(&Lookaside, v14);
    if ( v12 )
    {
      PsReturnPoolQuota(v12, (POOL_TYPE)512, v9);
      ObfDereferenceObject(v12);
    }
  }
  if ( v23 )
  {
    *(_DWORD *)(a2 + 216) = a5;
  }
  else
  {
    v24 = v39;
    if ( (unsigned __int64)v39 > v9 )
      v24 = v9;
    *(_QWORD *)&v39 = v24;
    *a6 = v24;
    if ( (unsigned int)v24 >= (unsigned int)v9 )
    {
      if ( (unsigned int)v9 < a5 )
      {
        Irp = IoAllocateIrp(*(_BYTE *)(*(_QWORD *)(a2 + 160) + 76LL), 0);
        v32 = Irp;
        if ( Irp )
        {
          Irp->RequestorMode = 0;
          Irp->Tail.Overlay.Thread = KeGetCurrentThread();
          Irp->Tail.Overlay.OriginalFileObject = *(PFILE_OBJECT *)(a2 + 152);
          CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
          CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&WskTdiCOMPReceive;
          CurrentStackLocation[-1].Context = 0;
          CurrentStackLocation[-1].Control = -32;
          v36 = v32->Tail.Overlay.CurrentStackLocation;
          *(_WORD *)&v36[-1].MajorFunction = 2063;
          v36[-1].DeviceObject = *(PDEVICE_OBJECT *)(a2 + 160);
          v36[-1].FileObject = *(PFILE_OBJECT *)(a2 + 152);
          v36[-1].Parameters.WMI.ProviderId = 0;
          v32->MdlAddress = 0;
          IofCallDriver(*(PDEVICE_OBJECT *)(a2 + 160), v32);
        }
        else
        {
          v33 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 8));
          if ( (*(_DWORD *)(a2 + 16) & 0x8000) == 0 && (unsigned __int8)WskTdiRetainTDIEndpoint(a2) )
          {
            *(_DWORD *)(a2 + 16) |= v34;
            AfdLRListAddItem((PSLIST_ENTRY)(a2 + 224));
          }
          KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 8), v33);
        }
      }
    }
    else
    {
      *(_DWORD *)(a2 + 216) = a5 - v24;
    }
  }
  return v23;
}

```

## disassembly

```asm
0x1400319f0  mov     [rsp-38h+arg_0], rbx
0x1400319f5  mov     [rsp-38h+arg_10], r8d
0x1400319fa  push    rbp
0x1400319fb  push    rsi
0x1400319fc  push    rdi
0x1400319fd  push    r12
0x1400319ff  push    r13
0x140031a01  push    r14
0x140031a03  push    r15
0x140031a05  mov     rbp, rsp
0x140031a08  sub     rsp, 70h
0x140031a0c  mov     rcx, [rbp+arg_28]
0x140031a10  xor     r13d, r13d
0x140031a13  xor     eax, eax
0x140031a15  mov     r12d, r9d
0x140031a18  xorps   xmm0, xmm0
0x140031a1b  mov     [rbp+var_10], rax
0x140031a1f  mov     rax, [rbp+Mdl]
0x140031a23  mov     rbx, rdx
0x140031a26  mov     [rcx], r13d
0x140031a29  movups  [rbp+var_40], xmm0
0x140031a2d  mov     [rbp+arg_8], r13d
0x140031a31  mov     [rax], r13
0x140031a34  movups  [rbp+var_30], xmm0
0x140031a38  mov     [rdx+0D8h], r13d
0x140031a3f  movups  [rbp+var_20], xmm0
0x140031a43  cmp     [rdx+0D0h], r13
0x140031a4a  jnz     loc_140031C5F
0x140031a50  mov     rdi, [rdx+110h]
0x140031a57  cmp     [rdx+120h], r13
0x140031a5e  jz      loc_140031C68
0x140031a64  lea     rcx, Lookaside; Lookaside
0x140031a6b  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140031a72  nop     dword ptr [rax+rax+00h]
0x140031a77  mov     r14, rax
0x140031a7a  test    rax, rax
0x140031a7d  jnz     loc_140031C97
0x140031a83  lea     rcx, [rbx+8]; SpinLock
0x140031a87  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140031a8e  nop     dword ptr [rax+rax+00h]
0x140031a93  mov     r8d, 8000h
0x140031a99  mov     sil, al
0x140031a9c  test    [rbx+10h], r8d
0x140031aa0  jnz     loc_140079041
0x140031aa6  mov     rcx, rbx
0x140031aa9  call    WskTdiRetainTDIEndpoint
0x140031aae  test    al, al
0x140031ab0  jz      loc_140079041
0x140031ab6  or      [rbx+10h], r8d
0x140031aba  lea     rcx, [rbx+0E0h]; ListEntry
0x140031ac1  lea     rdx, WskTdiLRPost0Receive
0x140031ac8  call    AfdLRListAddItem
0x140031acd  nop
0x140031ace  jmp     loc_140079041
0x140031ad3  xor     r9d, r9d; ChargeQuota
0x140031ad6  mov     [rsp+70h+Irp], r13; Irp
0x140031adb  xor     r8d, r8d; SecondaryBuffer
0x140031ade  mov     edx, r12d; Length
0x140031ae1  mov     rcx, r15; VirtualAddress
0x140031ae4  call    cs:__imp_IoAllocateMdl
0x140031aeb  nop     dword ptr [rax+rax+00h]
0x140031af0  mov     [rbp+Mdl], rax
0x140031af4  mov     r13, rax
0x140031af7  test    rax, rax
0x140031afa  jz      loc_140031CD7
0x140031b00  mov     rcx, rax; MemoryDescriptorList
0x140031b03  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140031b0a  nop     dword ptr [rax+rax+00h]
0x140031b0f  mov     rcx, [rbp+SourceBuffer]; SourceBuffer
0x140031b13  lea     rax, [rbp+arg_8]
0x140031b17  mov     [rsp+70h+BytesCopied], rax; BytesCopied
0x140031b1c  mov     r9, r13; DestinationMdlChain
0x140031b1f  mov     r8d, r12d; SourceBytesToCopy
0x140031b22  mov     dword ptr [rsp+70h+Irp], 0; DestinationOffset
0x140031b2a  xor     edx, edx; SourceOffset
0x140031b2c  call    cs:__imp_TdiCopyBufferToMdl
0x140031b33  nop     dword ptr [rax+rax+00h]
0x140031b38  mov     [r14+10h], r13
0x140031b3c  lea     rax, [r14+8]
0x140031b40  mov     qword ptr [rax], 0
0x140031b47  mov     dword ptr [r14+18h], 0
0x140031b4f  mov     [r14+20h], r12
0x140031b53  test    rdi, rdi
0x140031b56  jnz     loc_140031D02
0x140031b5c  mov     ecx, [rbp+arg_10]
0x140031b5f  mov     [r14+50h], rdi
0x140031b63  mov     [r14+58h], r15
0x140031b67  mov     qword ptr [rbp+var_30], rax
0x140031b6b  mov     eax, dword ptr [rbp+var_40]
0x140031b6e  mov     qword ptr [rbp+var_30+8], r12
0x140031b72  mov     qword ptr [rbp+var_20], 0FFFFFFFFFFFFFFFFh
0x140031b7a  test    cl, 40h
0x140031b7d  jnz     loc_140031D1A
0x140031b83  bt      ecx, 0Ah
0x140031b87  jb      loc_140031D25
0x140031b8d  mov     rax, [rbx+120h]
0x140031b94  lea     rdx, [rbp+var_40]
0x140031b98  mov     rcx, [rbx+118h]
0x140031b9f  mov     rax, [rax+10h]
0x140031ba3  call    _guard_dispatch_icall
0x140031ba8  xor     r13d, r13d
0x140031bab  cmp     eax, 0C0000016h
0x140031bb0  cmovnz  r13d, eax
0x140031bb4  cmp     qword ptr [rbp+var_30], 0
0x140031bb9  jz      loc_140031C4F
0x140031bbf  mov     rcx, [rbp+Mdl]; Mdl
0x140031bc3  call    cs:__imp_IoFreeMdl
0x140031bca  nop     dword ptr [rax+rax+00h]
0x140031bcf  mov     edx, 724B5357h; Tag
0x140031bd4  mov     rcx, r15; P
0x140031bd7  call    cs:__imp_ExFreePoolWithTag
0x140031bde  nop     dword ptr [rax+rax+00h]
0x140031be3  mov     rdx, r14; Entry
0x140031be6  lea     rcx, Lookaside; Lookaside
0x140031bed  call    cs:__imp_ExFreeToNPagedLookasideList
0x140031bf4  nop     dword ptr [rax+rax+00h]
0x140031bf9  xor     r14d, r14d
0x140031bfc  test    rdi, rdi
0x140031bff  jnz     loc_140031D30
0x140031c05  test    r13d, r13d
0x140031c08  jnz     short loc_140031C54
0x140031c0a  mov     rcx, qword ptr [rbp+var_20]
0x140031c0e  mov     rax, [rbp+arg_28]
0x140031c12  cmp     rcx, r12
0x140031c15  cmova   rcx, r12
0x140031c19  mov     qword ptr [rbp+var_20], rcx
0x140031c1d  mov     [rax], ecx
0x140031c1f  cmp     ecx, r12d
0x140031c22  jnb     loc_140078F38
0x140031c28  mov     eax, [rbp+arg_20]
0x140031c2b  sub     eax, ecx
0x140031c2d  mov     [rbx+0D8h], eax
0x140031c33  mov     eax, r13d
0x140031c36  mov     rbx, [rsp+70h+arg_0]
0x140031c3e  add     rsp, 70h
0x140031c42  pop     r15
0x140031c44  pop     r14
0x140031c46  pop     r13
0x140031c48  pop     r12
0x140031c4a  pop     rdi
0x140031c4b  pop     rsi
0x140031c4c  pop     rbp
0x140031c4d  retn
0x140031c4f  xor     r14d, r14d
0x140031c52  jmp     short loc_140031C05
0x140031c54  mov     ecx, [rbp+arg_20]
0x140031c57  mov     [rbx+0D8h], ecx
0x140031c5d  jmp     short loc_140031C33
0x140031c5f  mov     eax, [rbp+arg_20]
0x140031c62  mov     [rcx], eax
0x140031c64  xor     eax, eax
0x140031c66  jmp     short loc_140031C36
0x140031c68  lea     rsi, [rdx+8]
0x140031c6c  mov     rcx, rsi; SpinLock
0x140031c6f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140031c76  nop     dword ptr [rax+rax+00h]
0x140031c7b  mov     rcx, rsi; SpinLock
0x140031c7e  mov     dl, al; NewIrql
0x140031c80  cmp     [rbx+120h], r13
0x140031c87  jnz     loc_140078EB2
0x140031c8d  bts     dword ptr [rbx+10h], 0Eh
0x140031c92  jmp     loc_140079048
0x140031c97  xor     edx, edx; Val
0x140031c99  mov     rcx, r14; void *
0x140031c9c  lea     r8d, [rdx+68h]; Size
0x140031ca0  call    memset
0x140031ca5  test    rdi, rdi
0x140031ca8  jnz     loc_140078EC4
0x140031cae  mov     r8d, 724B5357h
0x140031cb4  lea     ecx, [rdi+40h]
0x140031cb7  mov     rdx, r12
0x140031cba  call    cs:__imp_ExAllocatePool2
0x140031cc1  nop     dword ptr [rax+rax+00h]
0x140031cc6  mov     r15, rax
0x140031cc9  test    rax, rax
0x140031ccc  jz      loc_140078F1C
0x140031cd2  jmp     loc_140031AD3
0x140031cd7  test    r15, r15
0x140031cda  jz      loc_140078F1C
0x140031ce0  mov     edx, 724B5357h; Tag
0x140031ce5  mov     rcx, r15; P
0x140031ce8  call    cs:__imp_ExFreePoolWithTag
0x140031cef  nop     dword ptr [rax+rax+00h]
0x140031cf4  test    rdi, rdi
0x140031cf7  jnz     loc_140078F05
0x140031cfd  jmp     loc_140078F1C
0x140031d02  mov     rcx, rdi; Object
0x140031d05  call    cs:__imp_ObfReferenceObject
0x140031d0c  nop     dword ptr [rax+rax+00h]
0x140031d11  lea     rax, [r14+8]
0x140031d15  jmp     loc_140031B5C
0x140031d1a  or      eax, 1
0x140031d1d  mov     dword ptr [rbp+var_40], eax
0x140031d20  jmp     loc_140031B83
0x140031d25  or      eax, 2
0x140031d28  mov     dword ptr [rbp+var_40], eax
0x140031d2b  jmp     loc_140031B8D
0x140031d30  mov     r8, r12; Amount
0x140031d33  mov     edx, 200h; PoolType
0x140031d38  mov     rcx, rdi; Process
0x140031d3b  call    cs:__imp_PsReturnPoolQuota
0x140031d42  nop     dword ptr [rax+rax+00h]
0x140031d47  mov     rcx, rdi; Object
0x140031d4a  call    cs:__imp_ObfDereferenceObject
0x140031d51  nop     dword ptr [rax+rax+00h]
0x140031d56  jmp     loc_140031C05
0x140078eb2  call    cs:__imp_KeReleaseSpinLock
0x140078eb9  nop     dword ptr [rax+rax+00h]
0x140078ebe  nop
0x140078ebf  jmp     loc_140031A64
0x140078ec4  mov     r8, r12; Amount
0x140078ec7  mov     edx, 200h; PoolType
0x140078ecc  mov     rcx, rdi; Process
0x140078ecf  call    cs:__imp_PsChargeProcessPoolQuota
0x140078ed6  nop     dword ptr [rax+rax+00h]
0x140078edb  test    eax, eax
0x140078edd  js      short loc_140078F1C
0x140078edf  mov     r8d, 724B5357h
0x140078ee5  mov     rdx, r12
0x140078ee8  mov     ecx, 40h ; '@'
0x140078eed  call    cs:__imp_ExAllocatePool2
0x140078ef4  nop     dword ptr [rax+rax+00h]
0x140078ef9  mov     r15, rax
0x140078efc  test    rax, rax
0x140078eff  jnz     loc_140031AD3
0x140078f05  mov     r8, r12; Amount
0x140078f08  mov     edx, 200h; PoolType
0x140078f0d  mov     rcx, rdi; Process
0x140078f10  call    cs:__imp_PsReturnPoolQuota
0x140078f17  nop     dword ptr [rax+rax+00h]
0x140078f1c  mov     rdx, r14; Entry
0x140078f1f  lea     rcx, Lookaside; Lookaside
0x140078f26  call    cs:__imp_ExFreeToNPagedLookasideList
0x140078f2d  nop     dword ptr [rax+rax+00h]
0x140078f32  nop
0x140078f33  jmp     loc_140031A83
0x140078f38  cmp     r12d, [rbp+arg_20]
0x140078f3c  jnb     loc_140031C33
0x140078f42  mov     rcx, [rbx+0A0h]
0x140078f49  xor     edx, edx; ChargeQuota
0x140078f4b  mov     cl, [rcx+4Ch]; StackSize
0x140078f4e  call    cs:__imp_IoAllocateIrp
0x140078f55  nop     dword ptr [rax+rax+00h]
0x140078f5a  mov     rdx, rax; Irp
0x140078f5d  test    rax, rax
0x140078f60  jnz     short loc_140078FBD
0x140078f62  lea     rcx, [rbx+8]; SpinLock
0x140078f66  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140078f6d  nop     dword ptr [rax+rax+00h]
0x140078f72  mov     r8d, 8000h
0x140078f78  mov     sil, al
0x140078f7b  test    [rbx+10h], r8d
0x140078f7f  jnz     short loc_140078FA4
0x140078f81  mov     rcx, rbx
0x140078f84  call    WskTdiRetainTDIEndpoint
0x140078f89  test    al, al
0x140078f8b  jz      short loc_140078FA4
0x140078f8d  or      [rbx+10h], r8d
0x140078f91  lea     rcx, [rbx+0E0h]; ListEntry
0x140078f98  lea     rdx, WskTdiLRPost0Receive
0x140078f9f  call    AfdLRListAddItem
0x140078fa4  mov     dl, sil; NewIrql
0x140078fa7  lea     rcx, [rbx+8]; SpinLock
0x140078fab  call    cs:__imp_KeReleaseSpinLock
0x140078fb2  nop     dword ptr [rax+rax+00h]
0x140078fb7  nop
0x140078fb8  jmp     loc_140031C33
0x140078fbd  mov     [rax+40h], r14b
0x140078fc1  lea     rcx, WskTdiCOMPReceive
0x140078fc8  mov     rax, gs:188h
0x140078fd1  mov     [rdx+98h], rax
0x140078fd8  mov     rax, [rbx+98h]
0x140078fdf  mov     [rdx+0C0h], rax
0x140078fe6  mov     rax, [rdx+0B8h]
0x140078fed  mov     [rax-10h], rcx
0x140078ff1  mov     [rax-8], r14
0x140078ff5  mov     byte ptr [rax-45h], 0E0h
0x140078ff9  mov     rcx, [rdx+0B8h]
0x140079000  mov     word ptr [rcx-48h], 80Fh
0x140079006  mov     rax, [rbx+0A0h]
0x14007900d  mov     [rcx-20h], rax
0x140079011  mov     rax, [rbx+98h]
0x140079018  mov     [rcx-18h], rax
0x14007901c  mov     qword ptr [rcx-40h], 0
0x140079024  mov     [rdx+8], r14
0x140079028  mov     rcx, [rbx+0A0h]; DeviceObject
0x14007902f  call    cs:__imp_IofCallDriver
0x140079036  nop     dword ptr [rax+rax+00h]
0x14007903b  nop
0x14007903c  jmp     loc_140031C33
0x140079041  mov     dl, sil; NewIrql
0x140079044  lea     rcx, [rbx+8]; SpinLock
0x140079048  call    cs:__imp_KeReleaseSpinLock
0x14007904f  nop     dword ptr [rax+rax+00h]
0x140079054  mov     eax, 0C000021Bh
0x140079059  jmp     loc_140031C36
```
