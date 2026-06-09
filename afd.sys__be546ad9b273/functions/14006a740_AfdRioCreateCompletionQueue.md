# AfdRioCreateCompletionQueue

- ea: `0x14006a740`
- end: `0x14006ab7b`
- name: `AfdRioCreateCompletionQueue`
- size: `1083`
- prototype: `__int64 __fastcall(__int64, __int64 *, void *, int, int, KPROCESSOR_MODE AccessMode, int, HANDLE Handle, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14006ab84`

## callees

- `0x14002fd7c`
- `0x14006a740`
- `0x14006c258`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x14006a8fa`
- `ntoskrnl!ExRaiseStatus` at `0x14006a971`
- `ntoskrnl!ExRaiseStatus` at `0x14006a8fa`
- `ntoskrnl!ExRaiseStatus` at `0x14006a971`
- `ntoskrnl!ExEventObjectType` at `0x14006a89c`
- `ntoskrnl!ExGetPreviousMode` at `0x14006a906`
- `ntoskrnl!ExGetPreviousMode` at `0x14006a906`
- `ntoskrnl!IoCompletionObjectType` at `0x14006a82c`
- `ntoskrnl!IoInitializeMiniCompletionPacket` at `0x14006aa03`
- `ntoskrnl!IoInitializeMiniCompletionPacket` at `0x14006aa03`
- `ntoskrnl!KeInitializeSpinLock` at `0x14006a9cf`
- `ntoskrnl!KeInitializeSpinLock` at `0x14006a9cf`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006a953`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006a953`
- `ntoskrnl!IoFreeMdl` at `0x14006ab1c`
- `ntoskrnl!IoFreeMdl` at `0x14006ab1c`
- `ntoskrnl!MmUnlockPages` at `0x14006ab0d`
- `ntoskrnl!MmUnlockPages` at `0x14006ab0d`
- `ntoskrnl!MmProbeAndLockPages` at `0x14006a91a`
- `ntoskrnl!MmProbeAndLockPages` at `0x14006a91a`
- `ntoskrnl!IoAllocateMdl` at `0x14006a8dc`
- `ntoskrnl!IoAllocateMdl` at `0x14006a8dc`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14006a855`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14006a855`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ab35`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ab4e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ab35`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ab4e`
- `ntoskrnl!ExAllocatePool2` at `0x14006a806`
- `ntoskrnl!ExAllocatePool2` at `0x14006a993`
- `ntoskrnl!ExAllocatePool2` at `0x14006a806`
- `ntoskrnl!ExAllocatePool2` at `0x14006a993`
- `NDIS!NdisAcquireRWLockWrite` at `0x14006aa78`
- `NDIS!NdisAcquireRWLockWrite` at `0x14006aa78`
- `NDIS!NdisReleaseRWLock` at `0x14006aab5`
- `NDIS!NdisReleaseRWLock` at `0x14006aab5`

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
0x14006a740  mov     r11, rsp
0x14006a743  mov     [r11+18h], r8
0x14006a747  mov     [r11+10h], rdx
0x14006a74b  mov     [r11+8], rcx
0x14006a74f  push    rsi
0x14006a750  push    rdi
0x14006a751  push    r12
0x14006a753  push    r13
0x14006a755  push    r14
0x14006a757  push    r15
0x14006a759  sub     rsp, 78h
0x14006a75d  mov     r13d, r9d
0x14006a760  mov     r10, r8
0x14006a763  xor     r14d, r14d
0x14006a766  mov     [r11-60h], r14
0x14006a76a  mov     [r11-78h], r14b
0x14006a76e  xor     eax, eax
0x14006a770  mov     [r11+20h], ax
0x14006a775  mov     [r11+22h], al
0x14006a779  xor     r15d, r15d
0x14006a77c  mov     [r11-58h], r15
0x14006a780  xor     edi, edi
0x14006a782  mov     [r11-50h], rdi
0x14006a786  test    r9d, r9d
0x14006a789  jz      loc_14006AAF5
0x14006a78f  lea     eax, [r9-1]
0x14006a793  cmp     eax, 8000000h
0x14006a798  ja      loc_14006AAF5
0x14006a79e  lea     eax, ds:0[r9*2]
0x14006a7a6  add     eax, r9d
0x14006a7a9  lea     edx, ds:10h[rax*8]; Length
0x14006a7b0  mov     [rsp+0A8h+var_70], edx
0x14006a7b4  cmp     edx, [rsp+0A8h+arg_20]
0x14006a7bb  jnz     loc_14006AAEE
0x14006a7c1  test    r8, r8
0x14006a7c4  jz      loc_14006AAEE
0x14006a7ca  mov     r12d, [rsp+0A8h+arg_30]
0x14006a7d2  mov     ecx, r12d
0x14006a7d5  test    r12d, r12d
0x14006a7d8  jz      loc_14006A8A5
0x14006a7de  sub     ecx, 1
0x14006a7e1  jz      loc_14006A892
0x14006a7e7  cmp     ecx, 1
0x14006a7ea  jz      short loc_14006A7F8
0x14006a7ec  mov     esi, 0C000000Dh
0x14006a7f1  mov     eax, esi
0x14006a7f3  jmp     loc_14006A8AC
0x14006a7f8  mov     edx, 50h ; 'P'
0x14006a7fd  lea     ecx, [rdx+11h]
0x14006a800  mov     r8d, 514F4952h
0x14006a806  call    cs:__imp_ExAllocatePool2
0x14006a80d  nop     dword ptr [rax+rax+00h]
0x14006a812  mov     r15, rax
0x14006a815  mov     [rsp+0A8h+var_58], rax
0x14006a81a  mov     [rsp+0A8h+var_68], 0
0x14006a823  mov     [rsp+0A8h+HandleInformation], 0; HandleInformation
0x14006a82c  mov     r8, cs:__imp_IoCompletionObjectType
0x14006a833  lea     rax, [rsp+0A8h+var_68]
0x14006a838  mov     r9b, [rsp+0A8h+AccessMode]; AccessMode
0x14006a840  mov     [rsp+0A8h+Object], rax; Object
0x14006a845  mov     r8, [r8]; ObjectType
0x14006a848  mov     edx, 2; DesiredAccess
0x14006a84d  mov     rcx, [rsp+0A8h+Handle]; Handle
0x14006a855  call    cs:__imp_ObReferenceObjectByHandle
0x14006a85c  nop     dword ptr [rax+rax+00h]
0x14006a861  mov     rcx, [rsp+0A8h+var_68]
0x14006a866  mov     esi, 0C000000Dh
0x14006a86b  mov     edx, [rsp+0A8h+var_70]
0x14006a86f  mov     r10, [rsp+0A8h+VirtualAddress]
0x14006a877  jmp     short loc_14006A8B4
0x14006a879  mov     esi, 0C0000017h
0x14006a87e  mov     r14, [rsp+0A8h+var_60]
0x14006a883  mov     r15, [rsp+0A8h+var_58]
0x14006a888  mov     rdi, [rsp+0A8h+var_50]
0x14006a88d  jmp     loc_14006AAFA
0x14006a892  mov     [rsp+0A8h+var_68], rdi
0x14006a897  mov     [rsp+0A8h+HandleInformation], rdi
0x14006a89c  mov     r8, cs:ExEventObjectType
0x14006a8a3  jmp     short loc_14006A833
0x14006a8a5  xor     eax, eax
0x14006a8a7  mov     esi, 0C000000Dh
0x14006a8ac  mov     rcx, [rsp+0A8h+Handle]
0x14006a8b4  mov     [rsp+0A8h+var_68], rcx
0x14006a8b9  mov     [rsp+0A8h+var_74], eax
0x14006a8bd  test    eax, eax
0x14006a8bf  js      loc_14006AAFE
0x14006a8c5  mov     [rsp+0A8h+Object], 0; Irp
0x14006a8ce  mov     edi, 1
0x14006a8d3  mov     r9b, dil; ChargeQuota
0x14006a8d6  xor     r8d, r8d; SecondaryBuffer
0x14006a8d9  mov     rcx, r10; VirtualAddress
0x14006a8dc  call    cs:__imp_IoAllocateMdl
0x14006a8e3  nop     dword ptr [rax+rax+00h]
0x14006a8e8  mov     r14, rax
0x14006a8eb  mov     [rsp+0A8h+var_60], rax
0x14006a8f0  test    rax, rax
0x14006a8f3  jnz     short loc_14006A906
0x14006a8f5  mov     ecx, 0C0000017h; Status
0x14006a8fa  call    cs:__imp_ExRaiseStatus
0x14006a906  call    cs:__imp_ExGetPreviousMode
0x14006a90d  nop     dword ptr [rax+rax+00h]
0x14006a912  mov     dl, al; AccessMode
0x14006a914  mov     r8d, edi; Operation
0x14006a917  mov     rcx, r14; MemoryDescriptorList
0x14006a91a  call    cs:__imp_MmProbeAndLockPages
0x14006a921  nop     dword ptr [rax+rax+00h]
0x14006a926  mov     [rsp+0A8h+var_78], dil
0x14006a92b  test    byte ptr [r14+0Ah], 5
0x14006a930  jz      short loc_14006A938
0x14006a932  mov     rsi, [r14+18h]
0x14006a936  jmp     short loc_14006A962
0x14006a938  mov     dword ptr [rsp+0A8h+HandleInformation], 40000010h; Priority
0x14006a940  mov     dword ptr [rsp+0A8h+Object], 0; BugCheckOnFailure
0x14006a948  xor     r9d, r9d; RequestedAddress
0x14006a94b  mov     r8d, edi; CacheType
0x14006a94e  xor     edx, edx; AccessMode
0x14006a950  mov     rcx, r14; MemoryDescriptorList
0x14006a953  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14006a95a  nop     dword ptr [rax+rax+00h]
0x14006a95f  mov     rsi, rax
0x14006a962  mov     [rsp+0A8h+var_48], rsi
0x14006a967  test    rsi, rsi
0x14006a96a  jnz     short loc_14006A97D
0x14006a96c  mov     ecx, 0C000009Ah; Status
0x14006a971  call    cs:__imp_ExRaiseStatus
0x14006a97d  mov     [rsp+0A8h+var_74], 0
0x14006a985  mov     edx, 58h ; 'X'
0x14006a98a  lea     ecx, [rdx+9]
0x14006a98d  mov     r8d, 514F4952h
0x14006a993  call    cs:__imp_ExAllocatePool2
0x14006a99a  nop     dword ptr [rax+rax+00h]
0x14006a99f  mov     rdi, rax
0x14006a9a2  mov     [rsp+0A8h+var_50], rax
0x14006a9a7  mov     [rax+10h], rsi
0x14006a9ab  mov     [rax+8], r14
0x14006a9af  mov     [rax+1Ch], r13d
0x14006a9b3  mov     [rax+24h], r13d
0x14006a9b7  mov     dword ptr [rax+50h], 0
0x14006a9be  mov     dword ptr [rax+18h], 2
0x14006a9c5  mov     dword ptr [rax+20h], 0
0x14006a9cc  mov     rcx, rdi; SpinLock
0x14006a9cf  call    cs:__imp_KeInitializeSpinLock
0x14006a9d6  nop     dword ptr [rax+rax+00h]
0x14006a9db  mov     dword ptr [rdi+2Ch], 0
0x14006a9e2  mov     qword ptr [rdi+48h], 0
0x14006a9ea  sub     r12d, 1
0x14006a9ee  jz      short loc_14006AA3A
0x14006a9f0  cmp     r12d, 1
0x14006a9f4  jnz     short loc_14006AA61
0x14006a9f6  mov     r8, rdi
0x14006a9f9  lea     rdx, AfdRioMiniPacketCompletion
0x14006aa00  mov     rcx, r15
0x14006aa03  call    cs:__imp_IoInitializeMiniCompletionPacket
0x14006aa0a  nop     dword ptr [rax+rax+00h]
0x14006aa0f  mov     rax, [rsp+0A8h+var_68]
0x14006aa14  mov     [rdi+30h], rax
0x14006aa18  mov     rax, [rsp+0A8h+arg_40]
0x14006aa20  mov     [rdi+38h], rax
0x14006aa24  mov     rax, [rsp+0A8h+arg_48]
0x14006aa2c  mov     [rdi+40h], rax
0x14006aa30  mov     [rdi+48h], r15
0x14006aa34  or      dword ptr [rdi+50h], 4
0x14006aa38  jmp     short loc_14006AA61
0x14006aa3a  mov     rax, [rsp+0A8h+var_68]
0x14006aa3f  mov     [rdi+30h], rax
0x14006aa43  mov     rax, [rsp+0A8h+arg_40]
0x14006aa4b  neg     rax
0x14006aa4e  sbb     ecx, ecx
0x14006aa50  and     ecx, 8
0x14006aa53  mov     eax, [rdi+50h]
0x14006aa56  and     eax, 0FFFFFFF7h
0x14006aa59  or      ecx, eax
0x14006aa5b  or      ecx, 2
0x14006aa5e  mov     [rdi+50h], ecx
0x14006aa61  xor     r8d, r8d; Flags
0x14006aa64  lea     rdx, [rsp+0A8h+LockState]; LockState
0x14006aa6c  mov     r13, [rsp+0A8h+arg_0]
0x14006aa74  mov     rcx, [r13+60h]; Lock
0x14006aa78  call    cs:__imp_NdisAcquireRWLockWrite
0x14006aa7f  nop     dword ptr [rax+rax+00h]
0x14006aa84  mov     rdx, rdi
0x14006aa87  mov     rcx, r13
0x14006aa8a  call    AfdRioInsertCompletionQueue
0x14006aa8f  test    al, al
0x14006aa91  jz      short loc_14006AAA4
0x14006aa93  mov     rax, [rsp+0A8h+arg_8]
0x14006aa9b  mov     [rax], rdi
0x14006aa9e  mov     esi, [rsp+0A8h+var_74]
0x14006aaa2  jmp     short loc_14006AAA9
0x14006aaa4  mov     esi, 0C0000017h
0x14006aaa9  lea     rdx, [rsp+0A8h+LockState]; LockState
0x14006aab1  mov     rcx, [r13+60h]; Lock
0x14006aab5  call    cs:__imp_NdisReleaseRWLock
0x14006aabc  nop     dword ptr [rax+rax+00h]
0x14006aac1  jmp     short loc_14006AAFA
0x14006aac3  mov     esi, 0C0000017h
0x14006aac8  mov     r14, [rsp+0A8h+var_60]
0x14006aacd  mov     r15, [rsp+0A8h+var_58]
0x14006aad2  mov     rdi, [rsp+0A8h+var_50]
0x14006aad7  jmp     short loc_14006AAFA
0x14006aad9  mov     r14, [rsp+0A8h+var_60]
0x14006aade  mov     esi, [rsp+0A8h+var_74]
0x14006aae2  mov     r15, [rsp+0A8h+var_58]
0x14006aae7  mov     rdi, [rsp+0A8h+var_50]
0x14006aaec  jmp     short loc_14006AAFA
0x14006aaee  mov     esi, 0C000000Dh
0x14006aaf3  jmp     short loc_14006AAFE
0x14006aaf5  mov     esi, 0C000000Dh
0x14006aafa  test    esi, esi
0x14006aafc  jns     short loc_14006AB69
0x14006aafe  test    r14, r14
0x14006ab01  jz      short loc_14006AB28
0x14006ab03  cmp     [rsp+0A8h+var_78], 0
0x14006ab08  jz      short loc_14006AB19
0x14006ab0a  mov     rcx, r14; MemoryDescriptorList
0x14006ab0d  call    cs:__imp_MmUnlockPages
0x14006ab14  nop     dword ptr [rax+rax+00h]
0x14006ab19  mov     rcx, r14; Mdl
0x14006ab1c  call    cs:__imp_IoFreeMdl
0x14006ab23  nop     dword ptr [rax+rax+00h]
0x14006ab28  test    rdi, rdi
0x14006ab2b  jz      short loc_14006AB41
0x14006ab2d  mov     edx, 514F4952h; Tag
0x14006ab32  mov     rcx, rdi; P
0x14006ab35  call    cs:__imp_ExFreePoolWithTag
0x14006ab3c  nop     dword ptr [rax+rax+00h]
0x14006ab41  test    r15, r15
0x14006ab44  jz      short loc_14006AB5A
0x14006ab46  mov     edx, 514F4952h; Tag
0x14006ab4b  mov     rcx, r15; P
0x14006ab4e  call    cs:__imp_ExFreePoolWithTag
0x14006ab55  nop     dword ptr [rax+rax+00h]
0x14006ab5a  mov     rcx, [rsp+0A8h+arg_8]
0x14006ab62  mov     qword ptr [rcx], 0
0x14006ab69  mov     eax, esi
0x14006ab6b  add     rsp, 78h
0x14006ab6f  pop     r15
0x14006ab71  pop     r14
0x14006ab73  pop     r13
0x14006ab75  pop     r12
0x14006ab77  pop     rdi
0x14006ab78  pop     rsi
0x14006ab79  retn
0x1400746fc  push    rbp
0x1400746fe  sub     rsp, 30h
0x140074702  mov     rbp, rdx
0x140074705  mov     r8, rcx
0x140074708  lea     r9, [rbp+34h]
0x14007470c  mov     edx, 707h
0x140074711  lea     rcx, aMinioSocketsWi_2; "minio\\sockets\\winsock2\\wsp\\afdsys\\"...
0x140074718  call    AfdExceptionFilter
0x14007471d  nop
0x14007471e  add     rsp, 30h
0x140074722  pop     rbp
0x140074723  retn
```
