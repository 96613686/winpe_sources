# AfdGetUnacceptedConnectData

- ea: `0x14004eaf0`
- end: `0x14004ee75`
- name: `AfdGetUnacceptedConnectData`
- size: `901`
- prototype: `__int64 __fastcall(__int64, __int64, KPROCESSOR_MODE, void *, unsigned int, PVOID VirtualAddress, ULONG Length, size_t *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x14002fd7c`
- `0x1400445d8`
- `0x140047828`
- `0x14004eaf0`
- `0x140072840`
- `0x140072870`
- `0x140092008`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004ec6d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004ec6d`
- `ntoskrnl!IoFreeMdl` at `0x14004ee3a`
- `ntoskrnl!IoFreeMdl` at `0x14004ee3a`
- `ntoskrnl!MmUnlockPages` at `0x14004ee2b`
- `ntoskrnl!MmUnlockPages` at `0x14004ee2b`
- `ntoskrnl!MmProbeAndLockPages` at `0x14004ec3a`
- `ntoskrnl!MmProbeAndLockPages` at `0x14004ec3a`
- `ntoskrnl!IoAllocateMdl` at `0x14004ec06`
- `ntoskrnl!IoAllocateMdl` at `0x14004ec06`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14004eb91`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14004eb91`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004ecdf`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004ed2d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004ed7e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004ed98`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004edd3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004ecdf`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004ed2d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004ed7e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004ed98`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004edd3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004ecba`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004ecba`
- `ntoskrnl!ProbeForWrite` at `0x14004eca4`
- `ntoskrnl!ProbeForWrite` at `0x14004eca4`

## pseudocode

```c
__int64 __fastcall AfdGetUnacceptedConnectData(
        __int64 a1,
        __int64 a2,
        KPROCESSOR_MODE a3,
        void *a4,
        unsigned int a5,
        PVOID VirtualAddress,
        ULONG Length,
        size_t *a8)
{
  PVOID MappedSystemVa; // rsi
  __int64 v10; // r13
  struct _MDL *v11; // rdi
  struct _MDL *Mdl; // rax
  __int64 ReturnedConnection; // rcx
  ULONG v14; // edx
  __int64 v15; // rax
  _BYTE *v16; // rcx
  size_t v17; // rbx
  size_t v18; // r8
  unsigned int v20; // [rsp+30h] [rbp-198h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+40h] [rbp-188h] BYREF
  PVOID v22; // [rsp+58h] [rbp-170h]
  size_t *v23; // [rsp+60h] [rbp-168h]
  __int64 Src; // [rsp+68h] [rbp-160h] BYREF
  int v25; // [rsp+70h] [rbp-158h]
  _BYTE v26[256]; // [rsp+80h] [rbp-148h] BYREF

  MappedSystemVa = VirtualAddress;
  v22 = VirtualAddress;
  v23 = a8;
  Src = 0;
  v25 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  v10 = *(_QWORD *)(a1 + 24);
  v20 = 0;
  v11 = 0;
  *a8 = 0;
  if ( (*(_DWORD *)(v10 + 8) & 1) != 0 && a5 >= 0xC )
  {
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
    if ( (_BYTE)v25 && Length < 0xC )
    {
      v20 = -1073741811;
      goto LABEL_45;
    }
    if ( Length )
    {
      if ( Length <= 0x100 )
      {
        if ( a3 )
          ProbeForWrite(VirtualAddress, Length, 1u);
      }
      else
      {
        Mdl = IoAllocateMdl(VirtualAddress, Length, 0, 1u, 0);
        v11 = Mdl;
        if ( !Mdl )
        {
          v20 = -1073741670;
          goto LABEL_45;
        }
        MmProbeAndLockPages(Mdl, a3, IoWriteAccess);
        if ( (v11->MdlFlags & 5) != 0 )
          MappedSystemVa = v11->MappedSystemVa;
        else
          MappedSystemVa = MmMapLockedPagesSpecifyCache(v11, 0, MmCached, 0, 0, 0x40000000u);
        v22 = MappedSystemVa;
        if ( !MappedSystemVa )
        {
          v20 = -1073741670;
          goto LABEL_45;
        }
      }
    }
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v10 + 56), &LockHandle);
    ReturnedConnection = AfdFindReturnedConnection(v10, (unsigned int)Src);
    if ( ReturnedConnection )
    {
      v14 = 0;
      if ( (*(_DWORD *)(v10 + 8) & 0x100) != 0 )
      {
        v15 = 0;
      }
      else
      {
        v15 = *(_QWORD *)(ReturnedConnection + 224);
        if ( v15 && *(_QWORD *)(v15 + 32) )
          v14 = *(_DWORD *)(v15 + 40);
      }
      if ( (_BYTE)v25 )
      {
        HIDWORD(Src) = v14;
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        if ( v11 || !a3 )
          RtlCopyVolatileMemory(MappedSystemVa, &Src, 0xCu);
        else
          RtlCopyToUser(MappedSystemVa, &Src, 0xCu);
        *a8 = 12;
      }
      else if ( v14 )
      {
        if ( Length >= v14 )
        {
          v16 = v26;
          if ( v11 )
            v16 = MappedSystemVa;
          v17 = v14;
          RtlCopyVolatileMemory(v16, *(const void **)(v15 + 32), v14);
          *a8 = v17;
          KeReleaseInStackQueuedSpinLock(&LockHandle);
          if ( v11 )
            goto LABEL_46;
          v18 = *a8;
          if ( a3 )
            RtlCopyToUser(MappedSystemVa, v26, v18);
          else
            RtlCopyVolatileMemory(MappedSystemVa, v26, v18);
        }
        else
        {
          KeReleaseInStackQueuedSpinLock(&LockHandle);
          v20 = -1073741789;
        }
      }
      else
      {
        KeReleaseInStackQueuedSpinLock(&LockHandle);
      }
    }
    else
    {
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      v20 = -1073741811;
    }
LABEL_45:
    if ( !v11 )
      return v20;
LABEL_46:
    if ( (v11->MdlFlags & 2) != 0 )
      MmUnlockPages(v11);
    IoFreeMdl(v11);
    return v20;
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x14004eaf0  push    rbx
0x14004eaf2  push    rsi
0x14004eaf3  push    rdi
0x14004eaf4  push    r12
0x14004eaf6  push    r13
0x14004eaf8  push    r14
0x14004eafa  push    r15
0x14004eafc  sub     rsp, 190h
0x14004eb03  mov     rax, cs:__security_cookie
0x14004eb0a  xor     rax, rsp
0x14004eb0d  mov     [rsp+1C8h+var_48], rax
0x14004eb15  mov     r14b, r8b
0x14004eb18  mov     rsi, [rsp+1C8h+VirtualAddress]
0x14004eb20  mov     [rsp+1C8h+var_170], rsi
0x14004eb25  mov     ebx, [rsp+1C8h+Length]
0x14004eb2c  mov     r15, [rsp+1C8h+arg_38]
0x14004eb34  mov     [rsp+1C8h+var_168], r15
0x14004eb39  xor     eax, eax
0x14004eb3b  mov     [rsp+1C8h+Src], rax
0x14004eb40  mov     [rsp+1C8h+var_158], eax
0x14004eb44  xorps   xmm0, xmm0
0x14004eb47  movups  xmmword ptr [rsp+1C8h+LockHandle.LockQueue.Next], xmm0
0x14004eb4c  mov     qword ptr [rsp+1C8h+LockHandle.OldIrql], rax
0x14004eb51  mov     [rsp+1C8h+var_190], rax
0x14004eb56  mov     r13, [rcx+18h]
0x14004eb5a  mov     [rsp+1C8h+var_198], eax
0x14004eb5e  xor     edi, edi
0x14004eb60  mov     [rsp+1C8h+var_190], rdi
0x14004eb65  mov     [r15], rax
0x14004eb68  mov     eax, [r13+8]
0x14004eb6c  test    al, 1
0x14004eb6e  jz      loc_14004EE4C
0x14004eb74  lea     r12d, [rdi+0Ch]
0x14004eb78  cmp     [rsp+1C8h+arg_20], r12d
0x14004eb80  jb      loc_14004EE4C
0x14004eb86  test    r8b, r8b
0x14004eb89  jz      short loc_14004EBB5
0x14004eb8b  test    r9b, 3
0x14004eb8f  jz      short loc_14004EB9E
0x14004eb91  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14004eb98  nop     dword ptr [rax+rax+00h]
0x14004eb9d  int     3; Trap to Debugger
0x14004eb9e  test    r14b, r14b
0x14004eba1  jz      short loc_14004EBB5
0x14004eba3  mov     r8, r12; Size
0x14004eba6  mov     rdx, r9; Src
0x14004eba9  lea     rcx, [rsp+1C8h+Src]; void *
0x14004ebae  call    RtlCopyFromUser
0x14004ebb3  jmp     short loc_14004EBC5
0x14004ebb5  mov     r8, r12; Size
0x14004ebb8  mov     rdx, r9; Src
0x14004ebbb  lea     rcx, [rsp+1C8h+Src]; void *
0x14004ebc0  call    RtlCopyVolatileMemory
0x14004ebc5  cmp     byte ptr [rsp+1C8h+var_158], 0
0x14004ebca  jz      short loc_14004EBDE
0x14004ebcc  cmp     ebx, r12d
0x14004ebcf  jnb     short loc_14004EBDE
0x14004ebd1  mov     [rsp+1C8h+var_198], 0C000000Dh
0x14004ebd9  jmp     loc_14004EE1D
0x14004ebde  test    ebx, ebx
0x14004ebe0  jz      loc_14004ECB1
0x14004ebe6  cmp     ebx, 100h
0x14004ebec  jbe     loc_14004EC93
0x14004ebf2  mov     [rsp+1C8h+Irp], 0; Irp
0x14004ebfb  mov     r9b, 1; ChargeQuota
0x14004ebfe  xor     r8d, r8d; SecondaryBuffer
0x14004ec01  mov     edx, ebx; Length
0x14004ec03  mov     rcx, rsi; VirtualAddress
0x14004ec06  call    cs:__imp_IoAllocateMdl
0x14004ec0d  nop     dword ptr [rax+rax+00h]
0x14004ec12  mov     rdi, rax
0x14004ec15  mov     [rsp+1C8h+var_190], rax
0x14004ec1a  test    rax, rax
0x14004ec1d  jnz     short loc_14004EC2C
0x14004ec1f  mov     [rsp+1C8h+var_198], 0C000009Ah
0x14004ec27  jmp     loc_14004EE1D
0x14004ec2c  mov     esi, 1
0x14004ec31  mov     r8d, esi; Operation
0x14004ec34  mov     dl, r14b; AccessMode
0x14004ec37  mov     rcx, rdi; MemoryDescriptorList
0x14004ec3a  call    cs:__imp_MmProbeAndLockPages
0x14004ec41  nop     dword ptr [rax+rax+00h]
0x14004ec46  test    byte ptr [rdi+0Ah], 5
0x14004ec4a  jz      short loc_14004EC52
0x14004ec4c  mov     rsi, [rdi+18h]
0x14004ec50  jmp     short loc_14004EC7C
0x14004ec52  mov     [rsp+1C8h+Priority], 40000000h; Priority
0x14004ec5a  mov     dword ptr [rsp+1C8h+Irp], 0; BugCheckOnFailure
0x14004ec62  xor     r9d, r9d; RequestedAddress
0x14004ec65  mov     r8d, esi; CacheType
0x14004ec68  xor     edx, edx; AccessMode
0x14004ec6a  mov     rcx, rdi; MemoryDescriptorList
0x14004ec6d  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14004ec74  nop     dword ptr [rax+rax+00h]
0x14004ec79  mov     rsi, rax
0x14004ec7c  mov     [rsp+1C8h+var_170], rsi
0x14004ec81  test    rsi, rsi
0x14004ec84  jnz     short loc_14004ECB1
0x14004ec86  mov     [rsp+1C8h+var_198], 0C000009Ah
0x14004ec8e  jmp     loc_14004EE1D
0x14004ec93  test    r14b, r14b
0x14004ec96  jz      short loc_14004ECB1
0x14004ec98  mov     rdx, rbx; Length
0x14004ec9b  mov     r8d, 1; Alignment
0x14004eca1  mov     rcx, rsi; Address
0x14004eca4  call    cs:__imp_ProbeForWrite
0x14004ecab  nop     dword ptr [rax+rax+00h]
0x14004ecb0  nop
0x14004ecb1  lea     rcx, [r13+38h]; SpinLock
0x14004ecb5  lea     rdx, [rsp+1C8h+LockHandle]; LockHandle
0x14004ecba  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14004ecc1  nop     dword ptr [rax+rax+00h]
0x14004ecc6  mov     edx, dword ptr [rsp+1C8h+Src]
0x14004ecca  mov     rcx, r13
0x14004eccd  call    AfdFindReturnedConnection
0x14004ecd2  mov     rcx, rax
0x14004ecd5  test    rax, rax
0x14004ecd8  jnz     short loc_14004ECF8
0x14004ecda  lea     rcx, [rsp+1C8h+LockHandle]; LockHandle
0x14004ecdf  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004ece6  nop     dword ptr [rax+rax+00h]
0x14004eceb  mov     [rsp+1C8h+var_198], 0C000000Dh
0x14004ecf3  jmp     loc_14004EE1D
0x14004ecf8  xor     edx, edx
0x14004ecfa  mov     eax, [r13+8]
0x14004ecfe  bt      eax, 8
0x14004ed02  jb      short loc_14004ED1B
0x14004ed04  mov     rax, [rcx+0E0h]
0x14004ed0b  test    rax, rax
0x14004ed0e  jz      short loc_14004ED1D
0x14004ed10  cmp     [rax+20h], rdx
0x14004ed14  jz      short loc_14004ED1D
0x14004ed16  mov     edx, [rax+28h]
0x14004ed19  jmp     short loc_14004ED1D
0x14004ed1b  xor     eax, eax
0x14004ed1d  cmp     byte ptr [rsp+1C8h+var_158], 0
0x14004ed22  jz      short loc_14004ED75
0x14004ed24  mov     dword ptr [rsp+1C8h+Src+4], edx
0x14004ed28  lea     rcx, [rsp+1C8h+LockHandle]; LockHandle
0x14004ed2d  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004ed34  nop     dword ptr [rax+rax+00h]
0x14004ed39  nop
0x14004ed3a  test    rdi, rdi
0x14004ed3d  jnz     short loc_14004ED56
0x14004ed3f  test    r14b, r14b
0x14004ed42  jz      short loc_14004ED56
0x14004ed44  mov     r8, r12; Size
0x14004ed47  lea     rdx, [rsp+1C8h+Src]; Src
0x14004ed4c  mov     rcx, rsi; void *
0x14004ed4f  call    RtlCopyToUser
0x14004ed54  jmp     short loc_14004ED66
0x14004ed56  mov     r8, r12; Size
0x14004ed59  lea     rdx, [rsp+1C8h+Src]; Src
0x14004ed5e  mov     rcx, rsi; void *
0x14004ed61  call    RtlCopyVolatileMemory
0x14004ed66  mov     [r15], r12
0x14004ed69  jmp     short loc_14004ED70
0x14004ed6b  mov     rdi, [rsp+1C8h+var_190]
0x14004ed70  jmp     loc_14004EE1D
0x14004ed75  test    edx, edx
0x14004ed77  jnz     short loc_14004ED8F
0x14004ed79  lea     rcx, [rsp+1C8h+LockHandle]; LockHandle
0x14004ed7e  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004ed85  nop     dword ptr [rax+rax+00h]
0x14004ed8a  jmp     loc_14004EE1D
0x14004ed8f  cmp     ebx, edx
0x14004ed91  jnb     short loc_14004EDAE
0x14004ed93  lea     rcx, [rsp+1C8h+LockHandle]; LockHandle
0x14004ed98  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004ed9f  nop     dword ptr [rax+rax+00h]
0x14004eda4  mov     [rsp+1C8h+var_198], 0C0000023h
0x14004edac  jmp     short loc_14004EE1D
0x14004edae  lea     rcx, [rsp+1C8h+var_148]
0x14004edb6  test    rdi, rdi
0x14004edb9  cmovnz  rcx, rsi; void *
0x14004edbd  mov     ebx, edx
0x14004edbf  mov     r8d, edx; Size
0x14004edc2  mov     rdx, [rax+20h]; Src
0x14004edc6  call    RtlCopyVolatileMemory
0x14004edcb  mov     [r15], rbx
0x14004edce  lea     rcx, [rsp+1C8h+LockHandle]; LockHandle
0x14004edd3  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004edda  nop     dword ptr [rax+rax+00h]
0x14004eddf  test    rdi, rdi
0x14004ede2  jnz     short loc_14004EE22
0x14004ede4  mov     r8, [r15]; Size
0x14004ede7  lea     rdx, [rsp+1C8h+var_148]; Src
0x14004edef  mov     rcx, rsi; void *
0x14004edf2  test    r14b, r14b
0x14004edf5  jz      short loc_14004EDFE
0x14004edf7  call    RtlCopyToUser
0x14004edfc  jmp     short loc_14004EE03
0x14004edfe  call    RtlCopyVolatileMemory
0x14004ee03  jmp     short loc_14004EE1D
0x14004ee05  mov     rax, [rsp+1C8h+var_168]
0x14004ee0a  mov     qword ptr [rax], 0
0x14004ee11  mov     rdi, [rsp+1C8h+var_190]
0x14004ee16  jmp     short loc_14004EE1D
0x14004ee18  mov     rdi, [rsp+1C8h+var_190]
0x14004ee1d  test    rdi, rdi
0x14004ee20  jz      short loc_14004EE46
0x14004ee22  test    byte ptr [rdi+0Ah], 2
0x14004ee26  jz      short loc_14004EE37
0x14004ee28  mov     rcx, rdi; MemoryDescriptorList
0x14004ee2b  call    cs:__imp_MmUnlockPages
0x14004ee32  nop     dword ptr [rax+rax+00h]
0x14004ee37  mov     rcx, rdi; Mdl
0x14004ee3a  call    cs:__imp_IoFreeMdl
0x14004ee41  nop     dword ptr [rax+rax+00h]
0x14004ee46  mov     eax, [rsp+1C8h+var_198]
0x14004ee4a  jmp     short loc_14004EE51
0x14004ee4c  mov     eax, 0C000000Dh
0x14004ee51  mov     rcx, [rsp+1C8h+var_48]
0x14004ee59  xor     rcx, rsp; StackCookie
0x14004ee5c  call    __security_check_cookie
0x14004ee61  add     rsp, 190h
0x14004ee68  pop     r15
0x14004ee6a  pop     r14
0x14004ee6c  pop     r13
0x14004ee6e  pop     r12
0x14004ee70  pop     rdi
0x14004ee71  pop     rsi
0x14004ee72  pop     rbx
0x14004ee73  retn
0x140074007  push    rbp
0x140074009  sub     rsp, 30h
0x14007400d  mov     rbp, rdx
0x140074010  mov     r8, rcx
0x140074013  lea     r9, [rbp+30h]
0x140074017  mov     edx, 1DECh
0x14007401c  lea     rcx, aMinioSocketsWi_6; "minio\\sockets\\winsock2\\wsp\\afdsys\\"...
0x140074023  call    AfdExceptionFilter
0x140074028  nop
0x140074029  add     rsp, 30h
0x14007402d  pop     rbp
0x14007402e  retn
0x140074030  push    rbp
0x140074032  sub     rsp, 30h
0x140074036  mov     rbp, rdx
0x140074039  mov     r8, rcx
0x14007403c  lea     r9, [rbp+30h]
0x140074040  mov     edx, 1E31h
0x140074045  lea     rcx, aMinioSocketsWi_6; "minio\\sockets\\winsock2\\wsp\\afdsys\\"...
0x14007404c  call    AfdExceptionFilter
0x140074051  nop
0x140074052  add     rsp, 30h
0x140074056  pop     rbp
0x140074057  retn
0x140074059  push    rbp
0x14007405b  sub     rsp, 30h
0x14007405f  mov     rbp, rdx
0x140074062  mov     r8, rcx
0x140074065  lea     r9, [rbp+30h]
0x140074069  mov     edx, 1E5Dh
0x14007406e  lea     rcx, aMinioSocketsWi_6; "minio\\sockets\\winsock2\\wsp\\afdsys\\"...
0x140074075  call    AfdExceptionFilter
0x14007407a  nop
0x14007407b  add     rsp, 30h
0x14007407f  pop     rbp
0x140074080  retn
```
