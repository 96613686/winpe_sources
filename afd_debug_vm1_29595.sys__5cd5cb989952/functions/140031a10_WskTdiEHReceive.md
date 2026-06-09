# WskTdiEHReceive

- ea: `0x140031a10`
- end: `0x140031d7b`
- name: `WskTdiEHReceive`
- size: `875`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140063900`

## callees

- `0x140031a10`
- `0x14004f070`
- `0x140064160`
- `0x140072920`
- `0x140072c80`

## import_xrefs

- `ntoskrnl!PsChargeProcessPoolQuota` at `0x14007904f`
- `ntoskrnl!PsChargeProcessPoolQuota` at `0x14007904f`
- `ntoskrnl!PsReturnPoolQuota` at `0x140031d5b`
- `ntoskrnl!PsReturnPoolQuota` at `0x140079090`
- `ntoskrnl!PsReturnPoolQuota` at `0x140031d5b`
- `ntoskrnl!PsReturnPoolQuota` at `0x140079090`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140031b23`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140031b23`
- `ntoskrnl!IoAllocateIrp` at `0x1400790ce`
- `ntoskrnl!IoAllocateIrp` at `0x1400790ce`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140031a8b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140031a8b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140031c0d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400790a6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140031c0d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400790a6`
- `ntoskrnl!IoFreeMdl` at `0x140031be3`
- `ntoskrnl!IoFreeMdl` at `0x140031be3`
- `ntoskrnl!ObfReferenceObject` at `0x140031d25`
- `ntoskrnl!ObfReferenceObject` at `0x140031d25`
- `ntoskrnl!IoAllocateMdl` at `0x140031b04`
- `ntoskrnl!IoAllocateMdl` at `0x140031b04`
- `ntoskrnl!ObfDereferenceObject` at `0x140031d6a`
- `ntoskrnl!ObfDereferenceObject` at `0x140031d6a`
- `ntoskrnl!IofCallDriver` at `0x1400791af`
- `ntoskrnl!IofCallDriver` at `0x1400791af`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140031aa7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140031c8f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400790e6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140031aa7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140031c8f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400790e6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140079032`
- `ntoskrnl!KeReleaseSpinLock` at `0x14007912b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400791c8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140079032`
- `ntoskrnl!KeReleaseSpinLock` at `0x14007912b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400791c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031bf7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031d08`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031bf7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031d08`
- `ntoskrnl!ExAllocatePool2` at `0x140031cda`
- `ntoskrnl!ExAllocatePool2` at `0x14007906d`
- `ntoskrnl!ExAllocatePool2` at `0x140031cda`
- `ntoskrnl!ExAllocatePool2` at `0x14007906d`
- `TDI!TdiCopyBufferToMdl` at `0x140031b4c`
- `TDI!TdiCopyBufferToMdl` at `0x140031b4c`

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
0x140031a10  mov     [rsp-38h+arg_0], rbx
0x140031a15  mov     [rsp-38h+arg_10], r8d
0x140031a1a  push    rbp
0x140031a1b  push    rsi
0x140031a1c  push    rdi
0x140031a1d  push    r12
0x140031a1f  push    r13
0x140031a21  push    r14
0x140031a23  push    r15
0x140031a25  mov     rbp, rsp
0x140031a28  sub     rsp, 70h
0x140031a2c  mov     rcx, [rbp+arg_28]
0x140031a30  xor     r13d, r13d
0x140031a33  xor     eax, eax
0x140031a35  mov     r12d, r9d
0x140031a38  xorps   xmm0, xmm0
0x140031a3b  mov     [rbp+var_10], rax
0x140031a3f  mov     rax, [rbp+Mdl]
0x140031a43  mov     rbx, rdx
0x140031a46  mov     [rcx], r13d
0x140031a49  movups  [rbp+var_40], xmm0
0x140031a4d  mov     [rbp+arg_8], r13d
0x140031a51  mov     [rax], r13
0x140031a54  movups  [rbp+var_30], xmm0
0x140031a58  mov     [rdx+0D8h], r13d
0x140031a5f  movups  [rbp+var_20], xmm0
0x140031a63  cmp     [rdx+0D0h], r13
0x140031a6a  jnz     loc_140031C7F
0x140031a70  mov     rdi, [rdx+110h]
0x140031a77  cmp     [rdx+120h], r13
0x140031a7e  jz      loc_140031C88
0x140031a84  lea     rcx, Lookaside; Lookaside
0x140031a8b  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140031a92  nop     dword ptr [rax+rax+00h]
0x140031a97  mov     r14, rax
0x140031a9a  test    rax, rax
0x140031a9d  jnz     loc_140031CB7
0x140031aa3  lea     rcx, [rbx+8]; SpinLock
0x140031aa7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140031aae  nop     dword ptr [rax+rax+00h]
0x140031ab3  mov     r8d, 8000h
0x140031ab9  mov     sil, al
0x140031abc  test    [rbx+10h], r8d
0x140031ac0  jnz     loc_1400791C1
0x140031ac6  mov     rcx, rbx
0x140031ac9  call    WskTdiRetainTDIEndpoint
0x140031ace  test    al, al
0x140031ad0  jz      loc_1400791C1
0x140031ad6  or      [rbx+10h], r8d
0x140031ada  lea     rcx, [rbx+0E0h]; ListEntry
0x140031ae1  lea     rdx, WskTdiLRPost0Receive
0x140031ae8  call    AfdLRListAddItem
0x140031aed  nop
0x140031aee  jmp     loc_1400791C1
0x140031af3  xor     r9d, r9d; ChargeQuota
0x140031af6  mov     [rsp+70h+Irp], r13; Irp
0x140031afb  xor     r8d, r8d; SecondaryBuffer
0x140031afe  mov     edx, r12d; Length
0x140031b01  mov     rcx, r15; VirtualAddress
0x140031b04  call    cs:__imp_IoAllocateMdl
0x140031b0b  nop     dword ptr [rax+rax+00h]
0x140031b10  mov     [rbp+Mdl], rax
0x140031b14  mov     r13, rax
0x140031b17  test    rax, rax
0x140031b1a  jz      loc_140031CF7
0x140031b20  mov     rcx, rax; MemoryDescriptorList
0x140031b23  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140031b2a  nop     dword ptr [rax+rax+00h]
0x140031b2f  mov     rcx, [rbp+SourceBuffer]; SourceBuffer
0x140031b33  lea     rax, [rbp+arg_8]
0x140031b37  mov     [rsp+70h+BytesCopied], rax; BytesCopied
0x140031b3c  mov     r9, r13; DestinationMdlChain
0x140031b3f  mov     r8d, r12d; SourceBytesToCopy
0x140031b42  mov     dword ptr [rsp+70h+Irp], 0; DestinationOffset
0x140031b4a  xor     edx, edx; SourceOffset
0x140031b4c  call    cs:__imp_TdiCopyBufferToMdl
0x140031b53  nop     dword ptr [rax+rax+00h]
0x140031b58  mov     [r14+10h], r13
0x140031b5c  lea     rax, [r14+8]
0x140031b60  mov     qword ptr [rax], 0
0x140031b67  mov     dword ptr [r14+18h], 0
0x140031b6f  mov     [r14+20h], r12
0x140031b73  test    rdi, rdi
0x140031b76  jnz     loc_140031D22
0x140031b7c  mov     ecx, [rbp+arg_10]
0x140031b7f  mov     [r14+50h], rdi
0x140031b83  mov     [r14+58h], r15
0x140031b87  mov     qword ptr [rbp+var_30], rax
0x140031b8b  mov     eax, dword ptr [rbp+var_40]
0x140031b8e  mov     qword ptr [rbp+var_30+8], r12
0x140031b92  mov     qword ptr [rbp+var_20], 0FFFFFFFFFFFFFFFFh
0x140031b9a  test    cl, 40h
0x140031b9d  jnz     loc_140031D3A
0x140031ba3  bt      ecx, 0Ah
0x140031ba7  jb      loc_140031D45
0x140031bad  mov     rax, [rbx+120h]
0x140031bb4  lea     rdx, [rbp+var_40]
0x140031bb8  mov     rcx, [rbx+118h]
0x140031bbf  mov     rax, [rax+10h]
0x140031bc3  call    _guard_dispatch_icall
0x140031bc8  xor     r13d, r13d
0x140031bcb  cmp     eax, 0C0000016h
0x140031bd0  cmovnz  r13d, eax
0x140031bd4  cmp     qword ptr [rbp+var_30], 0
0x140031bd9  jz      loc_140031C6F
0x140031bdf  mov     rcx, [rbp+Mdl]; Mdl
0x140031be3  call    cs:__imp_IoFreeMdl
0x140031bea  nop     dword ptr [rax+rax+00h]
0x140031bef  mov     edx, 724B5357h; Tag
0x140031bf4  mov     rcx, r15; P
0x140031bf7  call    cs:__imp_ExFreePoolWithTag
0x140031bfe  nop     dword ptr [rax+rax+00h]
0x140031c03  mov     rdx, r14; Entry
0x140031c06  lea     rcx, Lookaside; Lookaside
0x140031c0d  call    cs:__imp_ExFreeToNPagedLookasideList
0x140031c14  nop     dword ptr [rax+rax+00h]
0x140031c19  xor     r14d, r14d
0x140031c1c  test    rdi, rdi
0x140031c1f  jnz     loc_140031D50
0x140031c25  test    r13d, r13d
0x140031c28  jnz     short loc_140031C74
0x140031c2a  mov     rcx, qword ptr [rbp+var_20]
0x140031c2e  mov     rax, [rbp+arg_28]
0x140031c32  cmp     rcx, r12
0x140031c35  cmova   rcx, r12
0x140031c39  mov     qword ptr [rbp+var_20], rcx
0x140031c3d  mov     [rax], ecx
0x140031c3f  cmp     ecx, r12d
0x140031c42  jnb     loc_1400790B8
0x140031c48  mov     eax, [rbp+arg_20]
0x140031c4b  sub     eax, ecx
0x140031c4d  mov     [rbx+0D8h], eax
0x140031c53  mov     eax, r13d
0x140031c56  mov     rbx, [rsp+70h+arg_0]
0x140031c5e  add     rsp, 70h
0x140031c62  pop     r15
0x140031c64  pop     r14
0x140031c66  pop     r13
0x140031c68  pop     r12
0x140031c6a  pop     rdi
0x140031c6b  pop     rsi
0x140031c6c  pop     rbp
0x140031c6d  retn
0x140031c6f  xor     r14d, r14d
0x140031c72  jmp     short loc_140031C25
0x140031c74  mov     ecx, [rbp+arg_20]
0x140031c77  mov     [rbx+0D8h], ecx
0x140031c7d  jmp     short loc_140031C53
0x140031c7f  mov     eax, [rbp+arg_20]
0x140031c82  mov     [rcx], eax
0x140031c84  xor     eax, eax
0x140031c86  jmp     short loc_140031C56
0x140031c88  lea     rsi, [rdx+8]
0x140031c8c  mov     rcx, rsi; SpinLock
0x140031c8f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140031c96  nop     dword ptr [rax+rax+00h]
0x140031c9b  mov     rcx, rsi; SpinLock
0x140031c9e  mov     dl, al; NewIrql
0x140031ca0  cmp     [rbx+120h], r13
0x140031ca7  jnz     loc_140079032
0x140031cad  bts     dword ptr [rbx+10h], 0Eh
0x140031cb2  jmp     loc_1400791C8
0x140031cb7  xor     edx, edx; Val
0x140031cb9  mov     rcx, r14; void *
0x140031cbc  lea     r8d, [rdx+68h]; Size
0x140031cc0  call    memset
0x140031cc5  test    rdi, rdi
0x140031cc8  jnz     loc_140079044
0x140031cce  mov     r8d, 724B5357h
0x140031cd4  lea     ecx, [rdi+40h]
0x140031cd7  mov     rdx, r12
0x140031cda  call    cs:__imp_ExAllocatePool2
0x140031ce1  nop     dword ptr [rax+rax+00h]
0x140031ce6  mov     r15, rax
0x140031ce9  test    rax, rax
0x140031cec  jz      loc_14007909C
0x140031cf2  jmp     loc_140031AF3
0x140031cf7  test    r15, r15
0x140031cfa  jz      loc_14007909C
0x140031d00  mov     edx, 724B5357h; Tag
0x140031d05  mov     rcx, r15; P
0x140031d08  call    cs:__imp_ExFreePoolWithTag
0x140031d0f  nop     dword ptr [rax+rax+00h]
0x140031d14  test    rdi, rdi
0x140031d17  jnz     loc_140079085
0x140031d1d  jmp     loc_14007909C
0x140031d22  mov     rcx, rdi; Object
0x140031d25  call    cs:__imp_ObfReferenceObject
0x140031d2c  nop     dword ptr [rax+rax+00h]
0x140031d31  lea     rax, [r14+8]
0x140031d35  jmp     loc_140031B7C
0x140031d3a  or      eax, 1
0x140031d3d  mov     dword ptr [rbp+var_40], eax
0x140031d40  jmp     loc_140031BA3
0x140031d45  or      eax, 2
0x140031d48  mov     dword ptr [rbp+var_40], eax
0x140031d4b  jmp     loc_140031BAD
0x140031d50  mov     r8, r12; Amount
0x140031d53  mov     edx, 200h; PoolType
0x140031d58  mov     rcx, rdi; Process
0x140031d5b  call    cs:__imp_PsReturnPoolQuota
0x140031d62  nop     dword ptr [rax+rax+00h]
0x140031d67  mov     rcx, rdi; Object
0x140031d6a  call    cs:__imp_ObfDereferenceObject
0x140031d71  nop     dword ptr [rax+rax+00h]
0x140031d76  jmp     loc_140031C25
0x140079032  call    cs:__imp_KeReleaseSpinLock
0x140079039  nop     dword ptr [rax+rax+00h]
0x14007903e  nop
0x14007903f  jmp     loc_140031A84
0x140079044  mov     r8, r12; Amount
0x140079047  mov     edx, 200h; PoolType
0x14007904c  mov     rcx, rdi; Process
0x14007904f  call    cs:__imp_PsChargeProcessPoolQuota
0x140079056  nop     dword ptr [rax+rax+00h]
0x14007905b  test    eax, eax
0x14007905d  js      short loc_14007909C
0x14007905f  mov     r8d, 724B5357h
0x140079065  mov     rdx, r12
0x140079068  mov     ecx, 40h ; '@'
0x14007906d  call    cs:__imp_ExAllocatePool2
0x140079074  nop     dword ptr [rax+rax+00h]
0x140079079  mov     r15, rax
0x14007907c  test    rax, rax
0x14007907f  jnz     loc_140031AF3
0x140079085  mov     r8, r12; Amount
0x140079088  mov     edx, 200h; PoolType
0x14007908d  mov     rcx, rdi; Process
0x140079090  call    cs:__imp_PsReturnPoolQuota
0x140079097  nop     dword ptr [rax+rax+00h]
0x14007909c  mov     rdx, r14; Entry
0x14007909f  lea     rcx, Lookaside; Lookaside
0x1400790a6  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400790ad  nop     dword ptr [rax+rax+00h]
0x1400790b2  nop
0x1400790b3  jmp     loc_140031AA3
0x1400790b8  cmp     r12d, [rbp+arg_20]
0x1400790bc  jnb     loc_140031C53
0x1400790c2  mov     rcx, [rbx+0A0h]
0x1400790c9  xor     edx, edx; ChargeQuota
0x1400790cb  mov     cl, [rcx+4Ch]; StackSize
0x1400790ce  call    cs:__imp_IoAllocateIrp
0x1400790d5  nop     dword ptr [rax+rax+00h]
0x1400790da  mov     rdx, rax; Irp
0x1400790dd  test    rax, rax
0x1400790e0  jnz     short loc_14007913D
0x1400790e2  lea     rcx, [rbx+8]; SpinLock
0x1400790e6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400790ed  nop     dword ptr [rax+rax+00h]
0x1400790f2  mov     r8d, 8000h
0x1400790f8  mov     sil, al
0x1400790fb  test    [rbx+10h], r8d
0x1400790ff  jnz     short loc_140079124
0x140079101  mov     rcx, rbx
0x140079104  call    WskTdiRetainTDIEndpoint
0x140079109  test    al, al
0x14007910b  jz      short loc_140079124
0x14007910d  or      [rbx+10h], r8d
0x140079111  lea     rcx, [rbx+0E0h]; ListEntry
0x140079118  lea     rdx, WskTdiLRPost0Receive
0x14007911f  call    AfdLRListAddItem
0x140079124  mov     dl, sil; NewIrql
0x140079127  lea     rcx, [rbx+8]; SpinLock
0x14007912b  call    cs:__imp_KeReleaseSpinLock
0x140079132  nop     dword ptr [rax+rax+00h]
0x140079137  nop
0x140079138  jmp     loc_140031C53
0x14007913d  mov     [rax+40h], r14b
0x140079141  lea     rcx, WskTdiCOMPReceive
0x140079148  mov     rax, gs:188h
0x140079151  mov     [rdx+98h], rax
0x140079158  mov     rax, [rbx+98h]
0x14007915f  mov     [rdx+0C0h], rax
0x140079166  mov     rax, [rdx+0B8h]
0x14007916d  mov     [rax-10h], rcx
0x140079171  mov     [rax-8], r14
0x140079175  mov     byte ptr [rax-45h], 0E0h
0x140079179  mov     rcx, [rdx+0B8h]
0x140079180  mov     word ptr [rcx-48h], 80Fh
0x140079186  mov     rax, [rbx+0A0h]
0x14007918d  mov     [rcx-20h], rax
0x140079191  mov     rax, [rbx+98h]
0x140079198  mov     [rcx-18h], rax
0x14007919c  mov     qword ptr [rcx-40h], 0
0x1400791a4  mov     [rdx+8], r14
0x1400791a8  mov     rcx, [rbx+0A0h]; DeviceObject
0x1400791af  call    cs:__imp_IofCallDriver
0x1400791b6  nop     dword ptr [rax+rax+00h]
0x1400791bb  nop
0x1400791bc  jmp     loc_140031C53
0x1400791c1  mov     dl, sil; NewIrql
0x1400791c4  lea     rcx, [rbx+8]; SpinLock
0x1400791c8  call    cs:__imp_KeReleaseSpinLock
0x1400791cf  nop     dword ptr [rax+rax+00h]
0x1400791d4  mov     eax, 0C000021Bh
0x1400791d9  jmp     loc_140031C56
```
