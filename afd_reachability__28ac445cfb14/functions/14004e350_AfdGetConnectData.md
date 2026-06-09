# AfdGetConnectData

- ea: `0x14004e350`
- end: `0x14004e7f9`
- name: `AfdGetConnectData`
- size: `1193`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x14002fd5c`
- `0x1400445b8`
- `0x1400477a8`
- `0x14004e350`
- `0x1400726a0`
- `0x1400726d0`
- `0x140072800`
- `0x140092008`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004e505`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004e505`
- `ntoskrnl!IoFreeMdl` at `0x14004e7bf`
- `ntoskrnl!IoFreeMdl` at `0x14004e7bf`
- `ntoskrnl!MmUnlockPages` at `0x14004e7b0`
- `ntoskrnl!MmUnlockPages` at `0x14004e7b0`
- `ntoskrnl!MmProbeAndLockPages` at `0x14004e4d1`
- `ntoskrnl!MmProbeAndLockPages` at `0x14004e4d1`
- `ntoskrnl!IoAllocateMdl` at `0x14004e49e`
- `ntoskrnl!IoAllocateMdl` at `0x14004e49e`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14004e40e`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14004e40e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004e593`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004e60c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004e679`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004e6ed`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004e737`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004e783`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004e593`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004e60c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004e679`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004e6ed`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004e737`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004e783`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004e551`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004e551`
- `ntoskrnl!ProbeForWrite` at `0x14004e53b`
- `ntoskrnl!ProbeForWrite` at `0x14004e53b`

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
0x14004e350  mov     [rsp+arg_8], rsi
0x14004e355  push    rdi
0x14004e356  push    r12
0x14004e358  push    r13
0x14004e35a  push    r14
0x14004e35c  push    r15
0x14004e35e  sub     rsp, 1A0h
0x14004e365  mov     rax, cs:__security_cookie
0x14004e36c  xor     rax, rsp
0x14004e36f  mov     [rsp+1C8h+var_38], rax
0x14004e377  mov     al, r8b
0x14004e37a  mov     [rsp+1C8h+AccessMode], al
0x14004e37e  mov     esi, edx
0x14004e380  mov     r15, [rsp+1C8h+VirtualAddress]
0x14004e388  mov     [rsp+1C8h+var_160], r15
0x14004e38d  mov     r14d, [rsp+1C8h+Length]
0x14004e395  mov     [rsp+1C8h+var_188], r14d
0x14004e39a  mov     rdx, [rsp+1C8h+arg_38]
0x14004e3a2  mov     [rsp+1C8h+var_180], rdx
0x14004e3a7  mov     [rsp+1C8h+var_158], rdx
0x14004e3ac  xor     r8d, r8d
0x14004e3af  mov     [rsp+1C8h+Src], r8
0x14004e3b4  mov     [rsp+1C8h+var_148], r8d
0x14004e3bc  xorps   xmm0, xmm0
0x14004e3bf  movups  xmmword ptr [rsp+1C8h+LockHandle.LockQueue.Next], xmm0
0x14004e3c4  mov     qword ptr [rsp+1C8h+LockHandle.OldIrql], r8
0x14004e3c9  mov     [rsp+1C8h+var_190], r8
0x14004e3ce  mov     r13, [rcx+18h]
0x14004e3d2  xor     edi, edi
0x14004e3d4  mov     [rsp+1C8h+var_190], rdi
0x14004e3d9  mov     [rsp+1C8h+var_194], edi
0x14004e3dd  mov     [rdx], rdi
0x14004e3e0  lea     r12d, [r8+0Ch]
0x14004e3e4  cmp     [rsp+1C8h+arg_20], edi
0x14004e3eb  jbe     short loc_14004E45D
0x14004e3ed  cmp     [rsp+1C8h+arg_20], r12d
0x14004e3f5  jnb     short loc_14004E404
0x14004e3f7  mov     [rsp+1C8h+var_194], 0C000000Dh
0x14004e3ff  jmp     loc_14004E7A2
0x14004e404  test    al, al
0x14004e406  jz      short loc_14004E431
0x14004e408  test    r9b, 3
0x14004e40c  jz      short loc_14004E41B
0x14004e40e  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14004e415  nop     dword ptr [rax+rax+00h]
0x14004e41a  int     3; Trap to Debugger
0x14004e41b  test    al, al
0x14004e41d  jz      short loc_14004E431
0x14004e41f  mov     r8, r12; Size
0x14004e422  mov     rdx, r9; Src
0x14004e425  lea     rcx, [rsp+1C8h+Src]; void *
0x14004e42a  call    RtlCopyFromUser
0x14004e42f  jmp     short loc_14004E441
0x14004e431  mov     r8, r12; Size
0x14004e434  mov     rdx, r9; Src
0x14004e437  lea     rcx, [rsp+1C8h+Src]; void *
0x14004e43c  call    RtlCopyVolatileMemory
0x14004e441  cmp     byte ptr [rsp+1C8h+var_148], 0
0x14004e449  jz      short loc_14004E46F
0x14004e44b  cmp     r14d, r12d
0x14004e44e  jnb     short loc_14004E46F
0x14004e450  mov     [rsp+1C8h+var_194], 0C000000Dh
0x14004e458  jmp     loc_14004E7A2
0x14004e45d  mov     dword ptr [rsp+1C8h+Src], 0
0x14004e465  mov     byte ptr [rsp+1C8h+var_148], 0
0x14004e46d  jmp     short loc_14004E473
0x14004e46f  mov     al, [rsp+1C8h+AccessMode]
0x14004e473  test    r14d, r14d
0x14004e476  jz      loc_14004E548
0x14004e47c  cmp     r14d, 100h
0x14004e483  jbe     loc_14004E52B
0x14004e489  mov     [rsp+1C8h+Irp], 0; Irp
0x14004e492  mov     r9b, 1; ChargeQuota
0x14004e495  xor     r8d, r8d; SecondaryBuffer
0x14004e498  mov     edx, r14d; Length
0x14004e49b  mov     rcx, r15; VirtualAddress
0x14004e49e  call    cs:__imp_IoAllocateMdl
0x14004e4a5  nop     dword ptr [rax+rax+00h]
0x14004e4aa  mov     rdi, rax
0x14004e4ad  mov     [rsp+1C8h+var_190], rax
0x14004e4b2  test    rax, rax
0x14004e4b5  jnz     short loc_14004E4C4
0x14004e4b7  mov     [rsp+1C8h+var_194], 0C000009Ah
0x14004e4bf  jmp     loc_14004E7A2
0x14004e4c4  mov     r8d, 1; Operation
0x14004e4ca  mov     dl, [rsp+1C8h+AccessMode]; AccessMode
0x14004e4ce  mov     rcx, rdi; MemoryDescriptorList
0x14004e4d1  call    cs:__imp_MmProbeAndLockPages
0x14004e4d8  nop     dword ptr [rax+rax+00h]
0x14004e4dd  test    byte ptr [rdi+0Ah], 5
0x14004e4e1  jz      short loc_14004E4E9
0x14004e4e3  mov     r15, [rdi+18h]
0x14004e4e7  jmp     short loc_14004E514
0x14004e4e9  mov     [rsp+1C8h+Priority], 40000000h; Priority
0x14004e4f1  mov     dword ptr [rsp+1C8h+Irp], 0; BugCheckOnFailure
0x14004e4f9  xor     r9d, r9d; RequestedAddress
0x14004e4fc  xor     edx, edx; AccessMode
0x14004e4fe  lea     r8d, [r9+1]; CacheType
0x14004e502  mov     rcx, rdi; MemoryDescriptorList
0x14004e505  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14004e50c  nop     dword ptr [rax+rax+00h]
0x14004e511  mov     r15, rax
0x14004e514  mov     [rsp+1C8h+var_160], r15
0x14004e519  test    r15, r15
0x14004e51c  jnz     short loc_14004E548
0x14004e51e  mov     [rsp+1C8h+var_194], 0C000009Ah
0x14004e526  jmp     loc_14004E7A2
0x14004e52b  test    al, al
0x14004e52d  jz      short loc_14004E548
0x14004e52f  mov     rdx, r14; Length
0x14004e532  mov     r8d, 1; Alignment
0x14004e538  mov     rcx, r15; Address
0x14004e53b  call    cs:__imp_ProbeForWrite
0x14004e542  nop     dword ptr [rax+rax+00h]
0x14004e547  nop
0x14004e548  lea     rcx, [r13+38h]; SpinLock
0x14004e54c  lea     rdx, [rsp+1C8h+LockHandle]; LockHandle
0x14004e551  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14004e558  nop     dword ptr [rax+rax+00h]
0x14004e55d  movzx   ecx, word ptr [r13+0]
0x14004e562  cmp     [rsp+1C8h+arg_20], 0
0x14004e56a  jbe     short loc_14004E5B5
0x14004e56c  mov     eax, 0AFD4h
0x14004e571  and     cx, ax
0x14004e574  cmp     cx, ax
0x14004e577  jnz     short loc_14004E587
0x14004e579  mov     edx, dword ptr [rsp+1C8h+Src]
0x14004e57d  mov     rcx, r13
0x14004e580  call    AfdFindReturnedConnection
0x14004e585  jmp     short loc_14004E589
0x14004e587  xor     eax, eax
0x14004e589  test    rax, rax
0x14004e58c  jnz     short loc_14004E5AC
0x14004e58e  lea     rcx, [rsp+1C8h+LockHandle]; LockHandle
0x14004e593  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004e59a  nop     dword ptr [rax+rax+00h]
0x14004e59f  mov     [rsp+1C8h+var_194], 0C000000Dh
0x14004e5a7  jmp     loc_14004E7A2
0x14004e5ac  mov     r14, [rax+0E0h]
0x14004e5b3  jmp     short loc_14004E5FD
0x14004e5b5  movzx   eax, cx
0x14004e5b8  mov     edx, 0AFD2h
0x14004e5bd  and     ax, dx
0x14004e5c0  cmp     ax, dx
0x14004e5c3  jnz     short loc_14004E5CE
0x14004e5c5  mov     r14, [r13+0C0h]
0x14004e5cc  jmp     short loc_14004E5D1
0x14004e5ce  xor     r14d, r14d
0x14004e5d1  test    r14, r14
0x14004e5d4  jz      short loc_14004E5DF
0x14004e5d6  mov     r14, [r14+0E0h]
0x14004e5dd  jmp     short loc_14004E5FD
0x14004e5df  mov     eax, 5030h
0x14004e5e4  add     cx, ax
0x14004e5e7  mov     eax, 0FFF9h
0x14004e5ec  test    ax, cx
0x14004e5ef  jz      short loc_14004E5F6
0x14004e5f1  xor     r14d, r14d
0x14004e5f4  jmp     short loc_14004E5FD
0x14004e5f6  mov     r14, [r13+0D0h]
0x14004e5fd  mov     eax, [r13+8]
0x14004e601  bt      eax, 8
0x14004e605  jnb     short loc_14004E61D
0x14004e607  lea     rcx, [rsp+1C8h+LockHandle]; LockHandle
0x14004e60c  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004e613  nop     dword ptr [rax+rax+00h]
0x14004e618  jmp     loc_14004E7A2
0x14004e61d  test    r14, r14
0x14004e620  jz      short loc_14004E607
0x14004e622  sub     esi, 1205Bh
0x14004e628  jz      short loc_14004E652
0x14004e62a  sub     esi, 4
0x14004e62d  jz      short loc_14004E64B
0x14004e62f  sub     esi, 4
0x14004e632  jz      short loc_14004E644
0x14004e634  cmp     esi, 4
0x14004e637  jnz     loc_14004E58E
0x14004e63d  mov     esi, 70h ; 'p'
0x14004e642  jmp     short loc_14004E657
0x14004e644  mov     esi, 60h ; '`'
0x14004e649  jmp     short loc_14004E657
0x14004e64b  mov     esi, 30h ; '0'
0x14004e650  jmp     short loc_14004E657
0x14004e652  mov     esi, 20h ; ' '
0x14004e657  cmp     [rsp+1C8h+arg_20], 0
0x14004e65f  jbe     short loc_14004E6C8
0x14004e661  cmp     byte ptr [rsp+1C8h+var_148], 0
0x14004e669  jz      short loc_14004E6C8
0x14004e66b  mov     eax, [rsi+r14+8]
0x14004e670  mov     dword ptr [rsp+1C8h+Src+4], eax
0x14004e674  lea     rcx, [rsp+1C8h+LockHandle]; LockHandle
0x14004e679  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004e680  nop     dword ptr [rax+rax+00h]
0x14004e685  nop
0x14004e686  test    rdi, rdi
0x14004e689  jnz     short loc_14004E6A4
0x14004e68b  cmp     [rsp+1C8h+AccessMode], dil
0x14004e690  jz      short loc_14004E6A4
0x14004e692  mov     r8, r12; Size
0x14004e695  lea     rdx, [rsp+1C8h+Src]; Src
0x14004e69a  mov     rcx, r15; void *
0x14004e69d  call    RtlCopyFromUser
0x14004e6a2  jmp     short loc_14004E6B4
0x14004e6a4  mov     r8, r12; Size
0x14004e6a7  lea     rdx, [rsp+1C8h+Src]; Src
0x14004e6ac  mov     rcx, r15; void *
0x14004e6af  call    RtlCopyVolatileMemory
0x14004e6b4  mov     rsi, [rsp+1C8h+var_180]
0x14004e6b9  mov     [rsi], r12
0x14004e6bc  jmp     short loc_14004E6C3
0x14004e6be  mov     rdi, [rsp+1C8h+var_190]
0x14004e6c3  jmp     loc_14004E7A2
0x14004e6c8  mov     rdx, [rsi+r14]; Src
0x14004e6cc  test    rdx, rdx
0x14004e6cf  jz      loc_14004E77E
0x14004e6d5  mov     eax, [rsi+r14+8]
0x14004e6da  test    eax, eax
0x14004e6dc  jz      loc_14004E77E
0x14004e6e2  cmp     [rsp+1C8h+var_188], eax
0x14004e6e6  jnb     short loc_14004E706
0x14004e6e8  lea     rcx, [rsp+1C8h+LockHandle]; LockHandle
0x14004e6ed  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004e6f4  nop     dword ptr [rax+rax+00h]
0x14004e6f9  mov     [rsp+1C8h+var_194], 0C0000023h
0x14004e701  jmp     loc_14004E7A2
0x14004e706  mov     r8, rax; Size
0x14004e709  test    rdi, rdi
0x14004e70c  jz      short loc_14004E718
0x14004e70e  mov     rcx, r15; void *
0x14004e711  call    RtlCopyVolatileMemory
0x14004e716  jmp     short loc_14004E725
0x14004e718  lea     rcx, [rsp+1C8h+var_138]; void *
0x14004e720  call    memmove
0x14004e725  mov     eax, [rsi+r14+8]
0x14004e72a  mov     rsi, [rsp+1C8h+var_180]
0x14004e72f  mov     [rsi], rax
0x14004e732  lea     rcx, [rsp+1C8h+LockHandle]; LockHandle
0x14004e737  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004e73e  nop     dword ptr [rax+rax+00h]
0x14004e743  test    rdi, rdi
0x14004e746  jnz     short loc_14004E7A7
0x14004e748  mov     r8, [rsi]; Size
0x14004e74b  lea     rdx, [rsp+1C8h+var_138]; Src
0x14004e753  mov     rcx, r15; void *
0x14004e756  cmp     [rsp+1C8h+AccessMode], dil
0x14004e75b  jz      short loc_14004E764
0x14004e75d  call    RtlCopyToUser
0x14004e762  jmp     short loc_14004E769
0x14004e764  call    RtlCopyVolatileMemory
0x14004e769  jmp     short loc_14004E7A2
0x14004e76b  mov     rax, [rsp+1C8h+var_158]
0x14004e770  mov     qword ptr [rax], 0
0x14004e777  mov     rdi, [rsp+1C8h+var_190]
0x14004e77c  jmp     short loc_14004E7A2
0x14004e77e  lea     rcx, [rsp+1C8h+LockHandle]; LockHandle
0x14004e783  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004e78a  nop     dword ptr [rax+rax+00h]
0x14004e78f  mov     rsi, [rsp+1C8h+var_180]
0x14004e794  mov     qword ptr [rsi], 0
0x14004e79b  jmp     short loc_14004E7A2
0x14004e79d  mov     rdi, [rsp+1C8h+var_190]
0x14004e7a2  test    rdi, rdi
0x14004e7a5  jz      short loc_14004E7CB
0x14004e7a7  test    byte ptr [rdi+0Ah], 2
0x14004e7ab  jz      short loc_14004E7BC
0x14004e7ad  mov     rcx, rdi; MemoryDescriptorList
0x14004e7b0  call    cs:__imp_MmUnlockPages
0x14004e7b7  nop     dword ptr [rax+rax+00h]
0x14004e7bc  mov     rcx, rdi; Mdl
0x14004e7bf  call    cs:__imp_IoFreeMdl
0x14004e7c6  nop     dword ptr [rax+rax+00h]
0x14004e7cb  mov     eax, [rsp+1C8h+var_194]
0x14004e7cf  mov     rcx, [rsp+1C8h+var_38]
0x14004e7d7  xor     rcx, rsp; StackCookie
0x14004e7da  call    __security_check_cookie
0x14004e7df  mov     rsi, [rsp+1C8h+arg_8]
0x14004e7e7  add     rsp, 1A0h
0x14004e7ee  pop     r15
0x14004e7f0  pop     r14
0x14004e7f2  pop     r13
0x14004e7f4  pop     r12
0x14004e7f6  pop     rdi
0x14004e7f7  retn
0x140073d85  push    rbp
0x140073d87  sub     rsp, 30h
0x140073d8b  mov     rbp, rdx
0x140073d8e  mov     r8, rcx
0x140073d91  lea     r9, [rbp+34h]
0x140073d95  mov     edx, 104Dh
0x140073d9a  lea     rcx, aMinioSocketsWi_6; "minio\\sockets\\winsock2\\wsp\\afdsys\\"...
0x140073da1  call    AfdExceptionFilter
0x140073da6  nop
0x140073da7  add     rsp, 30h
0x140073dab  pop     rbp
0x140073dac  retn
0x140073dae  push    rbp
0x140073db0  sub     rsp, 30h
0x140073db4  mov     rbp, rdx
0x140073db7  mov     r8, rcx
0x140073dba  lea     r9, [rbp+34h]
  ... truncated ...
```
