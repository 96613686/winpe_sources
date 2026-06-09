# AfdRioCreateCompletionQueue

- ea: `0x14006a5a0`
- end: `0x14006a9db`
- name: `AfdRioCreateCompletionQueue`
- size: `1083`
- prototype: `__int64 __fastcall(int, int, int, int, int, KPROCESSOR_MODE AccessMode, int, HANDLE Handle, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14006a9e4`

## callees

- `0x14002fd5c`
- `0x14006a5a0`
- `0x14006c0b8`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x14006a75a`
- `ntoskrnl!ExRaiseStatus` at `0x14006a7d1`
- `ntoskrnl!ExRaiseStatus` at `0x14006a75a`
- `ntoskrnl!ExRaiseStatus` at `0x14006a7d1`
- `ntoskrnl!ExEventObjectType` at `0x14006a6fc`
- `ntoskrnl!ExGetPreviousMode` at `0x14006a766`
- `ntoskrnl!ExGetPreviousMode` at `0x14006a766`
- `ntoskrnl!IoCompletionObjectType` at `0x14006a68c`
- `ntoskrnl!IoInitializeMiniCompletionPacket` at `0x14006a863`
- `ntoskrnl!IoInitializeMiniCompletionPacket` at `0x14006a863`
- `ntoskrnl!KeInitializeSpinLock` at `0x14006a82f`
- `ntoskrnl!KeInitializeSpinLock` at `0x14006a82f`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006a7b3`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006a7b3`
- `ntoskrnl!IoFreeMdl` at `0x14006a97c`
- `ntoskrnl!IoFreeMdl` at `0x14006a97c`
- `ntoskrnl!MmUnlockPages` at `0x14006a96d`
- `ntoskrnl!MmUnlockPages` at `0x14006a96d`
- `ntoskrnl!MmProbeAndLockPages` at `0x14006a77a`
- `ntoskrnl!MmProbeAndLockPages` at `0x14006a77a`
- `ntoskrnl!IoAllocateMdl` at `0x14006a73c`
- `ntoskrnl!IoAllocateMdl` at `0x14006a73c`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14006a6b5`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14006a6b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a995`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a9ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a995`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006a9ae`
- `ntoskrnl!ExAllocatePool2` at `0x14006a666`
- `ntoskrnl!ExAllocatePool2` at `0x14006a7f3`
- `ntoskrnl!ExAllocatePool2` at `0x14006a666`
- `ntoskrnl!ExAllocatePool2` at `0x14006a7f3`
- `NDIS!NdisAcquireRWLockWrite` at `0x14006a8d8`
- `NDIS!NdisAcquireRWLockWrite` at `0x14006a8d8`
- `NDIS!NdisReleaseRWLock` at `0x14006a915`
- `NDIS!NdisReleaseRWLock` at `0x14006a915`

## pseudocode

```c
__int64 __fastcall AfdRioCreateCompletionQueue(
        __int64 a1,
        __int64 *a2,
        void *a3,
        int a4,
        int a5,
        KPROCESSOR_MODE AccessMode,
        int a7,
        HANDLE Handle,
        __int64 a9,
        __int64 a10)
{
  void *v11; // r10
  PMDL Mdl; // r14
  void *Pool2; // r15
  __int64 v14; // rdi
  ULONG v15; // edx
  int v16; // r12d
  int v17; // esi
  NTSTATUS v18; // eax
  PVOID v19; // rcx
  KPROCESSOR_MODE PreviousMode; // al
  PVOID MappedSystemVa; // rsi
  int v22; // r12d
  char v24; // [rsp+30h] [rbp-78h]
  ULONG v25; // [rsp+38h] [rbp-70h]
  PVOID Object; // [rsp+40h] [rbp-68h] BYREF
  PMDL v27; // [rsp+48h] [rbp-60h]
  void *v28; // [rsp+50h] [rbp-58h]
  __int64 v29; // [rsp+58h] [rbp-50h]
  PVOID v30; // [rsp+60h] [rbp-48h]
  struct _LOCK_STATE_EX LockState; // [rsp+C8h] [rbp+20h] BYREF

  v11 = a3;
  Mdl = 0;
  v27 = 0;
  v24 = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  Pool2 = 0;
  v28 = 0;
  v14 = 0;
  v29 = 0;
  if ( !a4 || (unsigned int)(a4 - 1) > 0x8000000 )
  {
    v17 = -1073741811;
    goto LABEL_32;
  }
  v15 = 24 * a4 + 16;
  v25 = v15;
  if ( v15 != a5 || !a3 )
  {
    v17 = -1073741811;
    goto LABEL_33;
  }
  v16 = a7;
  switch ( a7 )
  {
    case 0:
      v18 = 0;
      v17 = -1073741811;
      goto LABEL_13;
    case 1:
      Object = 0;
      v18 = ObReferenceObjectByHandle(Handle, 2u, (POBJECT_TYPE)ExEventObjectType, AccessMode, &Object, 0);
      goto LABEL_10;
    case 2:
      Pool2 = (void *)ExAllocatePool2(97, 80, 1364150610);
      v28 = Pool2;
      Object = 0;
      v18 = ObReferenceObjectByHandle(Handle, 2u, IoCompletionObjectType, AccessMode, &Object, 0);
LABEL_10:
      v19 = Object;
      v17 = -1073741811;
      v15 = v25;
      v11 = a3;
      goto LABEL_14;
  }
  v17 = -1073741811;
  v18 = -1073741811;
LABEL_13:
  v19 = Handle;
LABEL_14:
  Object = v19;
  if ( v18 >= 0 )
  {
    Mdl = IoAllocateMdl(v11, v15, 0, 1u, 0);
    v27 = Mdl;
    if ( !Mdl )
      ExRaiseStatus(-1073741801);
    PreviousMode = ExGetPreviousMode();
    MmProbeAndLockPages(Mdl, PreviousMode, IoWriteAccess);
    v24 = 1;
    if ( (Mdl->MdlFlags & 5) != 0 )
      MappedSystemVa = Mdl->MappedSystemVa;
    else
      MappedSystemVa = MmMapLockedPagesSpecifyCache(Mdl, 0, MmCached, 0, 0, 0x40000010u);
    v30 = MappedSystemVa;
    if ( !MappedSystemVa )
      ExRaiseStatus(-1073741670);
    v14 = ExAllocatePool2(97, 88, 1364150610);
    v29 = v14;
    *(_QWORD *)(v14 + 16) = MappedSystemVa;
    *(_QWORD *)(v14 + 8) = Mdl;
    *(_DWORD *)(v14 + 28) = a4;
    *(_DWORD *)(v14 + 36) = a4;
    *(_DWORD *)(v14 + 80) = 0;
    *(_DWORD *)(v14 + 24) = 2;
    *(_DWORD *)(v14 + 32) = 0;
    KeInitializeSpinLock((PKSPIN_LOCK)v14);
    *(_DWORD *)(v14 + 44) = 0;
    *(_QWORD *)(v14 + 72) = 0;
    v22 = v16 - 1;
    if ( v22 )
    {
      if ( v22 == 1 )
      {
        IoInitializeMiniCompletionPacket(Pool2, AfdRioMiniPacketCompletion, v14);
        *(_QWORD *)(v14 + 48) = Object;
        *(_QWORD *)(v14 + 56) = a9;
        *(_QWORD *)(v14 + 64) = a10;
        *(_QWORD *)(v14 + 72) = Pool2;
        *(_DWORD *)(v14 + 80) |= 4u;
      }
    }
    else
    {
      *(_QWORD *)(v14 + 48) = Object;
      *(_DWORD *)(v14 + 80) = *(_DWORD *)(v14 + 80) & 0xFFFFFFF7 | (a9 != 0 ? 8 : 0) | 2;
    }
    NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(a1 + 96), &LockState, 0);
    if ( (unsigned __int8)AfdRioInsertCompletionQueue(a1, v14) )
    {
      *a2 = v14;
      v17 = 0;
    }
    else
    {
      v17 = -1073741801;
    }
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 96), &LockState);
LABEL_32:
    if ( v17 >= 0 )
      return (unsigned int)v17;
  }
LABEL_33:
  if ( Mdl )
  {
    if ( v24 )
      MmUnlockPages(Mdl);
    IoFreeMdl(Mdl);
  }
  if ( v14 )
    ExFreePoolWithTag((PVOID)v14, 0x514F4952u);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x514F4952u);
  *a2 = 0;
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x14006a5a0  mov     r11, rsp
0x14006a5a3  mov     [r11+18h], r8
0x14006a5a7  mov     [r11+10h], rdx
0x14006a5ab  mov     [r11+8], rcx
0x14006a5af  push    rsi
0x14006a5b0  push    rdi
0x14006a5b1  push    r12
0x14006a5b3  push    r13
0x14006a5b5  push    r14
0x14006a5b7  push    r15
0x14006a5b9  sub     rsp, 78h
0x14006a5bd  mov     r13d, r9d
0x14006a5c0  mov     r10, r8
0x14006a5c3  xor     r14d, r14d
0x14006a5c6  mov     [r11-60h], r14
0x14006a5ca  mov     [r11-78h], r14b
0x14006a5ce  xor     eax, eax
0x14006a5d0  mov     [r11+20h], ax
0x14006a5d5  mov     [r11+22h], al
0x14006a5d9  xor     r15d, r15d
0x14006a5dc  mov     [r11-58h], r15
0x14006a5e0  xor     edi, edi
0x14006a5e2  mov     [r11-50h], rdi
0x14006a5e6  test    r9d, r9d
0x14006a5e9  jz      loc_14006A955
0x14006a5ef  lea     eax, [r9-1]
0x14006a5f3  cmp     eax, 8000000h
0x14006a5f8  ja      loc_14006A955
0x14006a5fe  lea     eax, ds:0[r9*2]
0x14006a606  add     eax, r9d
0x14006a609  lea     edx, ds:10h[rax*8]; Length
0x14006a610  mov     [rsp+0A8h+var_70], edx
0x14006a614  cmp     edx, [rsp+0A8h+arg_20]
0x14006a61b  jnz     loc_14006A94E
0x14006a621  test    r8, r8
0x14006a624  jz      loc_14006A94E
0x14006a62a  mov     r12d, [rsp+0A8h+arg_30]
0x14006a632  mov     ecx, r12d
0x14006a635  test    r12d, r12d
0x14006a638  jz      loc_14006A705
0x14006a63e  sub     ecx, 1
0x14006a641  jz      loc_14006A6F2
0x14006a647  cmp     ecx, 1
0x14006a64a  jz      short loc_14006A658
0x14006a64c  mov     esi, 0C000000Dh
0x14006a651  mov     eax, esi
0x14006a653  jmp     loc_14006A70C
0x14006a658  mov     edx, 50h ; 'P'
0x14006a65d  lea     ecx, [rdx+11h]
0x14006a660  mov     r8d, 514F4952h
0x14006a666  call    cs:__imp_ExAllocatePool2
0x14006a66d  nop     dword ptr [rax+rax+00h]
0x14006a672  mov     r15, rax
0x14006a675  mov     [rsp+0A8h+var_58], rax
0x14006a67a  mov     [rsp+0A8h+var_68], 0
0x14006a683  mov     [rsp+0A8h+HandleInformation], 0; HandleInformation
0x14006a68c  mov     r8, cs:__imp_IoCompletionObjectType
0x14006a693  lea     rax, [rsp+0A8h+var_68]
0x14006a698  mov     r9b, [rsp+0A8h+AccessMode]; AccessMode
0x14006a6a0  mov     [rsp+0A8h+Object], rax; Object
0x14006a6a5  mov     r8, [r8]; ObjectType
0x14006a6a8  mov     edx, 2; DesiredAccess
0x14006a6ad  mov     rcx, [rsp+0A8h+Handle]; Handle
0x14006a6b5  call    cs:__imp_ObReferenceObjectByHandle
0x14006a6bc  nop     dword ptr [rax+rax+00h]
0x14006a6c1  mov     rcx, [rsp+0A8h+var_68]
0x14006a6c6  mov     esi, 0C000000Dh
0x14006a6cb  mov     edx, [rsp+0A8h+var_70]
0x14006a6cf  mov     r10, [rsp+0A8h+VirtualAddress]
0x14006a6d7  jmp     short loc_14006A714
0x14006a6d9  mov     esi, 0C0000017h
0x14006a6de  mov     r14, [rsp+0A8h+var_60]
0x14006a6e3  mov     r15, [rsp+0A8h+var_58]
0x14006a6e8  mov     rdi, [rsp+0A8h+var_50]
0x14006a6ed  jmp     loc_14006A95A
0x14006a6f2  mov     [rsp+0A8h+var_68], rdi
0x14006a6f7  mov     [rsp+0A8h+HandleInformation], rdi
0x14006a6fc  mov     r8, cs:ExEventObjectType
0x14006a703  jmp     short loc_14006A693
0x14006a705  xor     eax, eax
0x14006a707  mov     esi, 0C000000Dh
0x14006a70c  mov     rcx, [rsp+0A8h+Handle]
0x14006a714  mov     [rsp+0A8h+var_68], rcx
0x14006a719  mov     [rsp+0A8h+var_74], eax
0x14006a71d  test    eax, eax
0x14006a71f  js      loc_14006A95E
0x14006a725  mov     [rsp+0A8h+Object], 0; Irp
0x14006a72e  mov     edi, 1
0x14006a733  mov     r9b, dil; ChargeQuota
0x14006a736  xor     r8d, r8d; SecondaryBuffer
0x14006a739  mov     rcx, r10; VirtualAddress
0x14006a73c  call    cs:__imp_IoAllocateMdl
0x14006a743  nop     dword ptr [rax+rax+00h]
0x14006a748  mov     r14, rax
0x14006a74b  mov     [rsp+0A8h+var_60], rax
0x14006a750  test    rax, rax
0x14006a753  jnz     short loc_14006A766
0x14006a755  mov     ecx, 0C0000017h; Status
0x14006a75a  call    cs:__imp_ExRaiseStatus
0x14006a766  call    cs:__imp_ExGetPreviousMode
0x14006a76d  nop     dword ptr [rax+rax+00h]
0x14006a772  mov     dl, al; AccessMode
0x14006a774  mov     r8d, edi; Operation
0x14006a777  mov     rcx, r14; MemoryDescriptorList
0x14006a77a  call    cs:__imp_MmProbeAndLockPages
0x14006a781  nop     dword ptr [rax+rax+00h]
0x14006a786  mov     [rsp+0A8h+var_78], dil
0x14006a78b  test    byte ptr [r14+0Ah], 5
0x14006a790  jz      short loc_14006A798
0x14006a792  mov     rsi, [r14+18h]
0x14006a796  jmp     short loc_14006A7C2
0x14006a798  mov     dword ptr [rsp+0A8h+HandleInformation], 40000010h; Priority
0x14006a7a0  mov     dword ptr [rsp+0A8h+Object], 0; BugCheckOnFailure
0x14006a7a8  xor     r9d, r9d; RequestedAddress
0x14006a7ab  mov     r8d, edi; CacheType
0x14006a7ae  xor     edx, edx; AccessMode
0x14006a7b0  mov     rcx, r14; MemoryDescriptorList
0x14006a7b3  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14006a7ba  nop     dword ptr [rax+rax+00h]
0x14006a7bf  mov     rsi, rax
0x14006a7c2  mov     [rsp+0A8h+var_48], rsi
0x14006a7c7  test    rsi, rsi
0x14006a7ca  jnz     short loc_14006A7DD
0x14006a7cc  mov     ecx, 0C000009Ah; Status
0x14006a7d1  call    cs:__imp_ExRaiseStatus
0x14006a7dd  mov     [rsp+0A8h+var_74], 0
0x14006a7e5  mov     edx, 58h ; 'X'
0x14006a7ea  lea     ecx, [rdx+9]
0x14006a7ed  mov     r8d, 514F4952h
0x14006a7f3  call    cs:__imp_ExAllocatePool2
0x14006a7fa  nop     dword ptr [rax+rax+00h]
0x14006a7ff  mov     rdi, rax
0x14006a802  mov     [rsp+0A8h+var_50], rax
0x14006a807  mov     [rax+10h], rsi
0x14006a80b  mov     [rax+8], r14
0x14006a80f  mov     [rax+1Ch], r13d
0x14006a813  mov     [rax+24h], r13d
0x14006a817  mov     dword ptr [rax+50h], 0
0x14006a81e  mov     dword ptr [rax+18h], 2
0x14006a825  mov     dword ptr [rax+20h], 0
0x14006a82c  mov     rcx, rdi; SpinLock
0x14006a82f  call    cs:__imp_KeInitializeSpinLock
0x14006a836  nop     dword ptr [rax+rax+00h]
0x14006a83b  mov     dword ptr [rdi+2Ch], 0
0x14006a842  mov     qword ptr [rdi+48h], 0
0x14006a84a  sub     r12d, 1
0x14006a84e  jz      short loc_14006A89A
0x14006a850  cmp     r12d, 1
0x14006a854  jnz     short loc_14006A8C1
0x14006a856  mov     r8, rdi
0x14006a859  lea     rdx, AfdRioMiniPacketCompletion
0x14006a860  mov     rcx, r15
0x14006a863  call    cs:__imp_IoInitializeMiniCompletionPacket
0x14006a86a  nop     dword ptr [rax+rax+00h]
0x14006a86f  mov     rax, [rsp+0A8h+var_68]
0x14006a874  mov     [rdi+30h], rax
0x14006a878  mov     rax, [rsp+0A8h+arg_40]
0x14006a880  mov     [rdi+38h], rax
0x14006a884  mov     rax, [rsp+0A8h+arg_48]
0x14006a88c  mov     [rdi+40h], rax
0x14006a890  mov     [rdi+48h], r15
0x14006a894  or      dword ptr [rdi+50h], 4
0x14006a898  jmp     short loc_14006A8C1
0x14006a89a  mov     rax, [rsp+0A8h+var_68]
0x14006a89f  mov     [rdi+30h], rax
0x14006a8a3  mov     rax, [rsp+0A8h+arg_40]
0x14006a8ab  neg     rax
0x14006a8ae  sbb     ecx, ecx
0x14006a8b0  and     ecx, 8
0x14006a8b3  mov     eax, [rdi+50h]
0x14006a8b6  and     eax, 0FFFFFFF7h
0x14006a8b9  or      ecx, eax
0x14006a8bb  or      ecx, 2
0x14006a8be  mov     [rdi+50h], ecx
0x14006a8c1  xor     r8d, r8d; Flags
0x14006a8c4  lea     rdx, [rsp+0A8h+LockState]; LockState
0x14006a8cc  mov     r13, [rsp+0A8h+arg_0]
0x14006a8d4  mov     rcx, [r13+60h]; Lock
0x14006a8d8  call    cs:__imp_NdisAcquireRWLockWrite
0x14006a8df  nop     dword ptr [rax+rax+00h]
0x14006a8e4  mov     rdx, rdi
0x14006a8e7  mov     rcx, r13
0x14006a8ea  call    AfdRioInsertCompletionQueue
0x14006a8ef  test    al, al
0x14006a8f1  jz      short loc_14006A904
0x14006a8f3  mov     rax, [rsp+0A8h+arg_8]
0x14006a8fb  mov     [rax], rdi
0x14006a8fe  mov     esi, [rsp+0A8h+var_74]
0x14006a902  jmp     short loc_14006A909
0x14006a904  mov     esi, 0C0000017h
0x14006a909  lea     rdx, [rsp+0A8h+LockState]; LockState
0x14006a911  mov     rcx, [r13+60h]; Lock
0x14006a915  call    cs:__imp_NdisReleaseRWLock
0x14006a91c  nop     dword ptr [rax+rax+00h]
0x14006a921  jmp     short loc_14006A95A
0x14006a923  mov     esi, 0C0000017h
0x14006a928  mov     r14, [rsp+0A8h+var_60]
0x14006a92d  mov     r15, [rsp+0A8h+var_58]
0x14006a932  mov     rdi, [rsp+0A8h+var_50]
0x14006a937  jmp     short loc_14006A95A
0x14006a939  mov     r14, [rsp+0A8h+var_60]
0x14006a93e  mov     esi, [rsp+0A8h+var_74]
0x14006a942  mov     r15, [rsp+0A8h+var_58]
0x14006a947  mov     rdi, [rsp+0A8h+var_50]
0x14006a94c  jmp     short loc_14006A95A
0x14006a94e  mov     esi, 0C000000Dh
0x14006a953  jmp     short loc_14006A95E
0x14006a955  mov     esi, 0C000000Dh
0x14006a95a  test    esi, esi
0x14006a95c  jns     short loc_14006A9C9
0x14006a95e  test    r14, r14
0x14006a961  jz      short loc_14006A988
0x14006a963  cmp     [rsp+0A8h+var_78], 0
0x14006a968  jz      short loc_14006A979
0x14006a96a  mov     rcx, r14; MemoryDescriptorList
0x14006a96d  call    cs:__imp_MmUnlockPages
0x14006a974  nop     dword ptr [rax+rax+00h]
0x14006a979  mov     rcx, r14; Mdl
0x14006a97c  call    cs:__imp_IoFreeMdl
0x14006a983  nop     dword ptr [rax+rax+00h]
0x14006a988  test    rdi, rdi
0x14006a98b  jz      short loc_14006A9A1
0x14006a98d  mov     edx, 514F4952h; Tag
0x14006a992  mov     rcx, rdi; P
0x14006a995  call    cs:__imp_ExFreePoolWithTag
0x14006a99c  nop     dword ptr [rax+rax+00h]
0x14006a9a1  test    r15, r15
0x14006a9a4  jz      short loc_14006A9BA
0x14006a9a6  mov     edx, 514F4952h; Tag
0x14006a9ab  mov     rcx, r15; P
0x14006a9ae  call    cs:__imp_ExFreePoolWithTag
0x14006a9b5  nop     dword ptr [rax+rax+00h]
0x14006a9ba  mov     rcx, [rsp+0A8h+arg_8]
0x14006a9c2  mov     qword ptr [rcx], 0
0x14006a9c9  mov     eax, esi
0x14006a9cb  add     rsp, 78h
0x14006a9cf  pop     r15
0x14006a9d1  pop     r14
0x14006a9d3  pop     r13
0x14006a9d5  pop     r12
0x14006a9d7  pop     rdi
0x14006a9d8  pop     rsi
0x14006a9d9  retn
0x14007457c  push    rbp
0x14007457e  sub     rsp, 30h
0x140074582  mov     rbp, rdx
0x140074585  mov     r8, rcx
0x140074588  lea     r9, [rbp+34h]
0x14007458c  mov     edx, 707h
0x140074591  lea     rcx, aMinioSocketsWi_2; "minio\\sockets\\winsock2\\wsp\\afdsys\\"...
0x140074598  call    AfdExceptionFilter
0x14007459d  nop
0x14007459e  add     rsp, 30h
0x1400745a2  pop     rbp
0x1400745a3  retn
```
