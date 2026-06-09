# AfdGetConnectData

- ea: `0x14004e3f0`
- end: `0x14004e899`
- name: `AfdGetConnectData`
- size: `1193`
- prototype: `__int64 __fastcall(__int64, int, KPROCESSOR_MODE, void *, unsigned int, PVOID VirtualAddress, ULONG Length, size_t *)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x14002fd7c`
- `0x1400445d8`
- `0x140047828`
- `0x14004e3f0`
- `0x140072840`
- `0x140072870`
- `0x140072980`
- `0x140092008`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004e5a5`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004e5a5`
- `ntoskrnl!IoFreeMdl` at `0x14004e85f`
- `ntoskrnl!IoFreeMdl` at `0x14004e85f`
- `ntoskrnl!MmUnlockPages` at `0x14004e850`
- `ntoskrnl!MmUnlockPages` at `0x14004e850`
- `ntoskrnl!MmProbeAndLockPages` at `0x14004e571`
- `ntoskrnl!MmProbeAndLockPages` at `0x14004e571`
- `ntoskrnl!IoAllocateMdl` at `0x14004e53e`
- `ntoskrnl!IoAllocateMdl` at `0x14004e53e`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14004e4ae`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14004e4ae`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004e633`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004e6ac`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004e719`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004e78d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004e7d7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004e823`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004e633`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004e6ac`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004e719`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004e78d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004e7d7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004e823`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004e5f1`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004e5f1`
- `ntoskrnl!ProbeForWrite` at `0x14004e5db`
- `ntoskrnl!ProbeForWrite` at `0x14004e5db`

## pseudocode

```c
__int64 __fastcall AfdGetConnectData(
        __int64 a1,
        int a2,
        KPROCESSOR_MODE a3,
        void *a4,
        unsigned int a5,
        PVOID VirtualAddress,
        ULONG Length,
        size_t *a8)
{
  KPROCESSOR_MODE v8; // al
  PVOID MappedSystemVa; // r15
  KSPIN_LOCK *v11; // r13
  struct _MDL *v12; // rdi
  struct _MDL *Mdl; // rax
  __int16 v14; // cx
  __int64 ReturnedConnection; // rax
  KSPIN_LOCK v16; // r14
  KSPIN_LOCK v17; // r14
  int v18; // esi
  int v19; // esi
  int v20; // esi
  __int64 v21; // rsi
  const void *v22; // rdx
  ULONG v23; // eax
  size_t v24; // r8
  size_t v25; // r8
  unsigned int v28; // [rsp+34h] [rbp-194h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+50h] [rbp-178h] BYREF
  PVOID v30; // [rsp+68h] [rbp-160h]
  size_t *v31; // [rsp+70h] [rbp-158h]
  __int64 Src; // [rsp+78h] [rbp-150h] BYREF
  int v33; // [rsp+80h] [rbp-148h]
  _BYTE v34[256]; // [rsp+90h] [rbp-138h] BYREF

  v8 = a3;
  MappedSystemVa = VirtualAddress;
  v30 = VirtualAddress;
  v31 = a8;
  Src = 0;
  v33 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  v11 = *(KSPIN_LOCK **)(a1 + 24);
  v12 = 0;
  v28 = 0;
  *a8 = 0;
  if ( a5 )
  {
    if ( a5 < 0xC )
    {
      v28 = -1073741811;
      goto LABEL_70;
    }
    if ( a3 )
    {
      if ( ((unsigned __int8)a4 & 3) != 0 )
        ExRaiseDatatypeMisalignment();
      RtlCopyFromUser(&Src, a4, 0xCu);
    }
    else
    {
      RtlCopyVolatileMemory(&Src, a4, 0xCu);
    }
    if ( (_BYTE)v33 && Length < 0xC )
    {
      v28 = -1073741811;
      goto LABEL_70;
    }
    v8 = a3;
  }
  else
  {
    LODWORD(Src) = 0;
    LOBYTE(v33) = 0;
  }
  if ( Length )
  {
    if ( Length <= 0x100 )
    {
      if ( v8 )
        ProbeForWrite(VirtualAddress, Length, 1u);
    }
    else
    {
      Mdl = IoAllocateMdl(VirtualAddress, Length, 0, 1u, 0);
      v12 = Mdl;
      if ( !Mdl )
      {
        v28 = -1073741670;
        goto LABEL_70;
      }
      MmProbeAndLockPages(Mdl, a3, IoWriteAccess);
      if ( (v12->MdlFlags & 5) != 0 )
        MappedSystemVa = v12->MappedSystemVa;
      else
        MappedSystemVa = MmMapLockedPagesSpecifyCache(v12, 0, MmCached, 0, 0, 0x40000000u);
      v30 = MappedSystemVa;
      if ( !MappedSystemVa )
      {
        v28 = -1073741670;
        goto LABEL_70;
      }
    }
  }
  KeAcquireInStackQueuedSpinLock(v11 + 7, &LockHandle);
  v14 = *(_WORD *)v11;
  if ( a5 )
  {
    if ( (v14 & 0xAFD4) == 0xAFD4 )
      ReturnedConnection = AfdFindReturnedConnection(v11, (unsigned int)Src);
    else
      ReturnedConnection = 0;
    if ( !ReturnedConnection )
      goto LABEL_30;
    v16 = *(_QWORD *)(ReturnedConnection + 224);
  }
  else
  {
    if ( (v14 & 0xAFD2) == 0xAFD2 )
      v17 = v11[24];
    else
      v17 = 0;
    if ( v17 )
    {
      v16 = *(_QWORD *)(v17 + 224);
    }
    else if ( ((v14 + 20528) & 0xFFF9) != 0 )
    {
      v16 = 0;
    }
    else
    {
      v16 = v11[26];
    }
  }
  if ( (v11[1] & 0x100) != 0 || !v16 )
  {
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    goto LABEL_70;
  }
  v18 = a2 - 73819;
  if ( v18 )
  {
    v19 = v18 - 4;
    if ( v19 )
    {
      v20 = v19 - 4;
      if ( v20 )
      {
        if ( v20 != 4 )
        {
LABEL_30:
          KeReleaseInStackQueuedSpinLock(&LockHandle);
          v28 = -1073741811;
          goto LABEL_70;
        }
        v21 = 112;
      }
      else
      {
        v21 = 96;
      }
    }
    else
    {
      v21 = 48;
    }
  }
  else
  {
    v21 = 32;
  }
  if ( a5 && (_BYTE)v33 )
  {
    HIDWORD(Src) = *(_DWORD *)(v21 + v16 + 8);
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    if ( v12 || !a3 )
      RtlCopyVolatileMemory(MappedSystemVa, &Src, 0xCu);
    else
      RtlCopyFromUser(MappedSystemVa, &Src, 0xCu);
    *a8 = 12;
LABEL_70:
    if ( !v12 )
      return v28;
    goto LABEL_71;
  }
  v22 = *(const void **)(v21 + v16);
  if ( !v22 || (v23 = *(_DWORD *)(v21 + v16 + 8)) == 0 )
  {
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    *a8 = 0;
    goto LABEL_70;
  }
  if ( Length < v23 )
  {
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    v28 = -1073741789;
    goto LABEL_70;
  }
  v24 = *(unsigned int *)(v21 + v16 + 8);
  if ( v12 )
    RtlCopyVolatileMemory(MappedSystemVa, v22, v24);
  else
    memmove(v34, v22, v24);
  *a8 = *(unsigned int *)(v21 + v16 + 8);
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( !v12 )
  {
    v25 = *a8;
    if ( a3 )
      RtlCopyToUser(MappedSystemVa, v34, v25);
    else
      RtlCopyVolatileMemory(MappedSystemVa, v34, v25);
    goto LABEL_70;
  }
LABEL_71:
  if ( (v12->MdlFlags & 2) != 0 )
    MmUnlockPages(v12);
  IoFreeMdl(v12);
  return v28;
}

```

## disassembly

```asm
0x14004e3f0  mov     [rsp+arg_8], rsi
0x14004e3f5  push    rdi
0x14004e3f6  push    r12
0x14004e3f8  push    r13
0x14004e3fa  push    r14
0x14004e3fc  push    r15
0x14004e3fe  sub     rsp, 1A0h
0x14004e405  mov     rax, cs:__security_cookie
0x14004e40c  xor     rax, rsp
0x14004e40f  mov     [rsp+1C8h+var_38], rax
0x14004e417  mov     al, r8b
0x14004e41a  mov     [rsp+1C8h+AccessMode], al
0x14004e41e  mov     esi, edx
0x14004e420  mov     r15, [rsp+1C8h+VirtualAddress]
0x14004e428  mov     [rsp+1C8h+var_160], r15
0x14004e42d  mov     r14d, [rsp+1C8h+Length]
0x14004e435  mov     [rsp+1C8h+var_188], r14d
0x14004e43a  mov     rdx, [rsp+1C8h+arg_38]
0x14004e442  mov     [rsp+1C8h+var_180], rdx
0x14004e447  mov     [rsp+1C8h+var_158], rdx
0x14004e44c  xor     r8d, r8d
0x14004e44f  mov     [rsp+1C8h+Src], r8
0x14004e454  mov     [rsp+1C8h+var_148], r8d
0x14004e45c  xorps   xmm0, xmm0
0x14004e45f  movups  xmmword ptr [rsp+1C8h+LockHandle.LockQueue.Next], xmm0
0x14004e464  mov     qword ptr [rsp+1C8h+LockHandle.OldIrql], r8
0x14004e469  mov     [rsp+1C8h+var_190], r8
0x14004e46e  mov     r13, [rcx+18h]
0x14004e472  xor     edi, edi
0x14004e474  mov     [rsp+1C8h+var_190], rdi
0x14004e479  mov     [rsp+1C8h+var_194], edi
0x14004e47d  mov     [rdx], rdi
0x14004e480  lea     r12d, [r8+0Ch]
0x14004e484  cmp     [rsp+1C8h+arg_20], edi
0x14004e48b  jbe     short loc_14004E4FD
0x14004e48d  cmp     [rsp+1C8h+arg_20], r12d
0x14004e495  jnb     short loc_14004E4A4
0x14004e497  mov     [rsp+1C8h+var_194], 0C000000Dh
0x14004e49f  jmp     loc_14004E842
0x14004e4a4  test    al, al
0x14004e4a6  jz      short loc_14004E4D1
0x14004e4a8  test    r9b, 3
0x14004e4ac  jz      short loc_14004E4BB
0x14004e4ae  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14004e4b5  nop     dword ptr [rax+rax+00h]
0x14004e4ba  int     3; Trap to Debugger
0x14004e4bb  test    al, al
0x14004e4bd  jz      short loc_14004E4D1
0x14004e4bf  mov     r8, r12; Size
0x14004e4c2  mov     rdx, r9; Src
0x14004e4c5  lea     rcx, [rsp+1C8h+Src]; void *
0x14004e4ca  call    RtlCopyFromUser
0x14004e4cf  jmp     short loc_14004E4E1
0x14004e4d1  mov     r8, r12; Size
0x14004e4d4  mov     rdx, r9; Src
0x14004e4d7  lea     rcx, [rsp+1C8h+Src]; void *
0x14004e4dc  call    RtlCopyVolatileMemory
0x14004e4e1  cmp     byte ptr [rsp+1C8h+var_148], 0
0x14004e4e9  jz      short loc_14004E50F
0x14004e4eb  cmp     r14d, r12d
0x14004e4ee  jnb     short loc_14004E50F
0x14004e4f0  mov     [rsp+1C8h+var_194], 0C000000Dh
0x14004e4f8  jmp     loc_14004E842
0x14004e4fd  mov     dword ptr [rsp+1C8h+Src], 0
0x14004e505  mov     byte ptr [rsp+1C8h+var_148], 0
0x14004e50d  jmp     short loc_14004E513
0x14004e50f  mov     al, [rsp+1C8h+AccessMode]
0x14004e513  test    r14d, r14d
0x14004e516  jz      loc_14004E5E8
0x14004e51c  cmp     r14d, 100h
0x14004e523  jbe     loc_14004E5CB
0x14004e529  mov     [rsp+1C8h+Irp], 0; Irp
0x14004e532  mov     r9b, 1; ChargeQuota
0x14004e535  xor     r8d, r8d; SecondaryBuffer
0x14004e538  mov     edx, r14d; Length
0x14004e53b  mov     rcx, r15; VirtualAddress
0x14004e53e  call    cs:__imp_IoAllocateMdl
0x14004e545  nop     dword ptr [rax+rax+00h]
0x14004e54a  mov     rdi, rax
0x14004e54d  mov     [rsp+1C8h+var_190], rax
0x14004e552  test    rax, rax
0x14004e555  jnz     short loc_14004E564
0x14004e557  mov     [rsp+1C8h+var_194], 0C000009Ah
0x14004e55f  jmp     loc_14004E842
0x14004e564  mov     r8d, 1; Operation
0x14004e56a  mov     dl, [rsp+1C8h+AccessMode]; AccessMode
0x14004e56e  mov     rcx, rdi; MemoryDescriptorList
0x14004e571  call    cs:__imp_MmProbeAndLockPages
0x14004e578  nop     dword ptr [rax+rax+00h]
0x14004e57d  test    byte ptr [rdi+0Ah], 5
0x14004e581  jz      short loc_14004E589
0x14004e583  mov     r15, [rdi+18h]
0x14004e587  jmp     short loc_14004E5B4
0x14004e589  mov     [rsp+1C8h+Priority], 40000000h; Priority
0x14004e591  mov     dword ptr [rsp+1C8h+Irp], 0; BugCheckOnFailure
0x14004e599  xor     r9d, r9d; RequestedAddress
0x14004e59c  xor     edx, edx; AccessMode
0x14004e59e  lea     r8d, [r9+1]; CacheType
0x14004e5a2  mov     rcx, rdi; MemoryDescriptorList
0x14004e5a5  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14004e5ac  nop     dword ptr [rax+rax+00h]
0x14004e5b1  mov     r15, rax
0x14004e5b4  mov     [rsp+1C8h+var_160], r15
0x14004e5b9  test    r15, r15
0x14004e5bc  jnz     short loc_14004E5E8
0x14004e5be  mov     [rsp+1C8h+var_194], 0C000009Ah
0x14004e5c6  jmp     loc_14004E842
0x14004e5cb  test    al, al
0x14004e5cd  jz      short loc_14004E5E8
0x14004e5cf  mov     rdx, r14; Length
0x14004e5d2  mov     r8d, 1; Alignment
0x14004e5d8  mov     rcx, r15; Address
0x14004e5db  call    cs:__imp_ProbeForWrite
0x14004e5e2  nop     dword ptr [rax+rax+00h]
0x14004e5e7  nop
0x14004e5e8  lea     rcx, [r13+38h]; SpinLock
0x14004e5ec  lea     rdx, [rsp+1C8h+LockHandle]; LockHandle
0x14004e5f1  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14004e5f8  nop     dword ptr [rax+rax+00h]
0x14004e5fd  movzx   ecx, word ptr [r13+0]
0x14004e602  cmp     [rsp+1C8h+arg_20], 0
0x14004e60a  jbe     short loc_14004E655
0x14004e60c  mov     eax, 0AFD4h
0x14004e611  and     cx, ax
0x14004e614  cmp     cx, ax
0x14004e617  jnz     short loc_14004E627
0x14004e619  mov     edx, dword ptr [rsp+1C8h+Src]
0x14004e61d  mov     rcx, r13
0x14004e620  call    AfdFindReturnedConnection
0x14004e625  jmp     short loc_14004E629
0x14004e627  xor     eax, eax
0x14004e629  test    rax, rax
0x14004e62c  jnz     short loc_14004E64C
0x14004e62e  lea     rcx, [rsp+1C8h+LockHandle]; LockHandle
0x14004e633  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004e63a  nop     dword ptr [rax+rax+00h]
0x14004e63f  mov     [rsp+1C8h+var_194], 0C000000Dh
0x14004e647  jmp     loc_14004E842
0x14004e64c  mov     r14, [rax+0E0h]
0x14004e653  jmp     short loc_14004E69D
0x14004e655  movzx   eax, cx
0x14004e658  mov     edx, 0AFD2h
0x14004e65d  and     ax, dx
0x14004e660  cmp     ax, dx
0x14004e663  jnz     short loc_14004E66E
0x14004e665  mov     r14, [r13+0C0h]
0x14004e66c  jmp     short loc_14004E671
0x14004e66e  xor     r14d, r14d
0x14004e671  test    r14, r14
0x14004e674  jz      short loc_14004E67F
0x14004e676  mov     r14, [r14+0E0h]
0x14004e67d  jmp     short loc_14004E69D
0x14004e67f  mov     eax, 5030h
0x14004e684  add     cx, ax
0x14004e687  mov     eax, 0FFF9h
0x14004e68c  test    ax, cx
0x14004e68f  jz      short loc_14004E696
0x14004e691  xor     r14d, r14d
0x14004e694  jmp     short loc_14004E69D
0x14004e696  mov     r14, [r13+0D0h]
0x14004e69d  mov     eax, [r13+8]
0x14004e6a1  bt      eax, 8
0x14004e6a5  jnb     short loc_14004E6BD
0x14004e6a7  lea     rcx, [rsp+1C8h+LockHandle]; LockHandle
0x14004e6ac  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004e6b3  nop     dword ptr [rax+rax+00h]
0x14004e6b8  jmp     loc_14004E842
0x14004e6bd  test    r14, r14
0x14004e6c0  jz      short loc_14004E6A7
0x14004e6c2  sub     esi, 1205Bh
0x14004e6c8  jz      short loc_14004E6F2
0x14004e6ca  sub     esi, 4
0x14004e6cd  jz      short loc_14004E6EB
0x14004e6cf  sub     esi, 4
0x14004e6d2  jz      short loc_14004E6E4
0x14004e6d4  cmp     esi, 4
0x14004e6d7  jnz     loc_14004E62E
0x14004e6dd  mov     esi, 70h ; 'p'
0x14004e6e2  jmp     short loc_14004E6F7
0x14004e6e4  mov     esi, 60h ; '`'
0x14004e6e9  jmp     short loc_14004E6F7
0x14004e6eb  mov     esi, 30h ; '0'
0x14004e6f0  jmp     short loc_14004E6F7
0x14004e6f2  mov     esi, 20h ; ' '
0x14004e6f7  cmp     [rsp+1C8h+arg_20], 0
0x14004e6ff  jbe     short loc_14004E768
0x14004e701  cmp     byte ptr [rsp+1C8h+var_148], 0
0x14004e709  jz      short loc_14004E768
0x14004e70b  mov     eax, [rsi+r14+8]
0x14004e710  mov     dword ptr [rsp+1C8h+Src+4], eax
0x14004e714  lea     rcx, [rsp+1C8h+LockHandle]; LockHandle
0x14004e719  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004e720  nop     dword ptr [rax+rax+00h]
0x14004e725  nop
0x14004e726  test    rdi, rdi
0x14004e729  jnz     short loc_14004E744
0x14004e72b  cmp     [rsp+1C8h+AccessMode], dil
0x14004e730  jz      short loc_14004E744
0x14004e732  mov     r8, r12; Size
0x14004e735  lea     rdx, [rsp+1C8h+Src]; Src
0x14004e73a  mov     rcx, r15; void *
0x14004e73d  call    RtlCopyFromUser
0x14004e742  jmp     short loc_14004E754
0x14004e744  mov     r8, r12; Size
0x14004e747  lea     rdx, [rsp+1C8h+Src]; Src
0x14004e74c  mov     rcx, r15; void *
0x14004e74f  call    RtlCopyVolatileMemory
0x14004e754  mov     rsi, [rsp+1C8h+var_180]
0x14004e759  mov     [rsi], r12
0x14004e75c  jmp     short loc_14004E763
0x14004e75e  mov     rdi, [rsp+1C8h+var_190]
0x14004e763  jmp     loc_14004E842
0x14004e768  mov     rdx, [rsi+r14]; Src
0x14004e76c  test    rdx, rdx
0x14004e76f  jz      loc_14004E81E
0x14004e775  mov     eax, [rsi+r14+8]
0x14004e77a  test    eax, eax
0x14004e77c  jz      loc_14004E81E
0x14004e782  cmp     [rsp+1C8h+var_188], eax
0x14004e786  jnb     short loc_14004E7A6
0x14004e788  lea     rcx, [rsp+1C8h+LockHandle]; LockHandle
0x14004e78d  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004e794  nop     dword ptr [rax+rax+00h]
0x14004e799  mov     [rsp+1C8h+var_194], 0C0000023h
0x14004e7a1  jmp     loc_14004E842
0x14004e7a6  mov     r8, rax; Size
0x14004e7a9  test    rdi, rdi
0x14004e7ac  jz      short loc_14004E7B8
0x14004e7ae  mov     rcx, r15; void *
0x14004e7b1  call    RtlCopyVolatileMemory
0x14004e7b6  jmp     short loc_14004E7C5
0x14004e7b8  lea     rcx, [rsp+1C8h+var_138]; void *
0x14004e7c0  call    memmove
0x14004e7c5  mov     eax, [rsi+r14+8]
0x14004e7ca  mov     rsi, [rsp+1C8h+var_180]
0x14004e7cf  mov     [rsi], rax
0x14004e7d2  lea     rcx, [rsp+1C8h+LockHandle]; LockHandle
0x14004e7d7  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004e7de  nop     dword ptr [rax+rax+00h]
0x14004e7e3  test    rdi, rdi
0x14004e7e6  jnz     short loc_14004E847
0x14004e7e8  mov     r8, [rsi]; Size
0x14004e7eb  lea     rdx, [rsp+1C8h+var_138]; Src
0x14004e7f3  mov     rcx, r15; void *
0x14004e7f6  cmp     [rsp+1C8h+AccessMode], dil
0x14004e7fb  jz      short loc_14004E804
0x14004e7fd  call    RtlCopyToUser
0x14004e802  jmp     short loc_14004E809
0x14004e804  call    RtlCopyVolatileMemory
0x14004e809  jmp     short loc_14004E842
0x14004e80b  mov     rax, [rsp+1C8h+var_158]
0x14004e810  mov     qword ptr [rax], 0
0x14004e817  mov     rdi, [rsp+1C8h+var_190]
0x14004e81c  jmp     short loc_14004E842
0x14004e81e  lea     rcx, [rsp+1C8h+LockHandle]; LockHandle
0x14004e823  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004e82a  nop     dword ptr [rax+rax+00h]
0x14004e82f  mov     rsi, [rsp+1C8h+var_180]
0x14004e834  mov     qword ptr [rsi], 0
0x14004e83b  jmp     short loc_14004E842
0x14004e83d  mov     rdi, [rsp+1C8h+var_190]
0x14004e842  test    rdi, rdi
0x14004e845  jz      short loc_14004E86B
0x14004e847  test    byte ptr [rdi+0Ah], 2
0x14004e84b  jz      short loc_14004E85C
0x14004e84d  mov     rcx, rdi; MemoryDescriptorList
0x14004e850  call    cs:__imp_MmUnlockPages
0x14004e857  nop     dword ptr [rax+rax+00h]
0x14004e85c  mov     rcx, rdi; Mdl
0x14004e85f  call    cs:__imp_IoFreeMdl
0x14004e866  nop     dword ptr [rax+rax+00h]
0x14004e86b  mov     eax, [rsp+1C8h+var_194]
0x14004e86f  mov     rcx, [rsp+1C8h+var_38]
0x14004e877  xor     rcx, rsp; StackCookie
0x14004e87a  call    __security_check_cookie
0x14004e87f  mov     rsi, [rsp+1C8h+arg_8]
0x14004e887  add     rsp, 1A0h
0x14004e88e  pop     r15
0x14004e890  pop     r14
0x14004e892  pop     r13
0x14004e894  pop     r12
0x14004e896  pop     rdi
0x14004e897  retn
0x140073f05  push    rbp
0x140073f07  sub     rsp, 30h
0x140073f0b  mov     rbp, rdx
0x140073f0e  mov     r8, rcx
0x140073f11  lea     r9, [rbp+34h]
0x140073f15  mov     edx, 104Dh
0x140073f1a  lea     rcx, aMinioSocketsWi_6; "minio\\sockets\\winsock2\\wsp\\afdsys\\"...
0x140073f21  call    AfdExceptionFilter
0x140073f26  nop
0x140073f27  add     rsp, 30h
0x140073f2b  pop     rbp
0x140073f2c  retn
0x140073f2e  push    rbp
0x140073f30  sub     rsp, 30h
0x140073f34  mov     rbp, rdx
0x140073f37  mov     r8, rcx
0x140073f3a  lea     r9, [rbp+34h]
  ... truncated ...
```
