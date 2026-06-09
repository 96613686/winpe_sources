# AfdGetUnacceptedConnectData

- ea: `0x14004ea50`
- end: `0x14004edd5`
- name: `AfdGetUnacceptedConnectData`
- size: `901`
- prototype: `__int64 __fastcall(__int64, __int64, KPROCESSOR_MODE, void *, unsigned int, PVOID VirtualAddress, ULONG Length, size_t *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x14002fd5c`
- `0x1400445b8`
- `0x1400477a8`
- `0x14004ea50`
- `0x1400726a0`
- `0x1400726d0`
- `0x140092008`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004ebcd`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004ebcd`
- `ntoskrnl!IoFreeMdl` at `0x14004ed9a`
- `ntoskrnl!IoFreeMdl` at `0x14004ed9a`
- `ntoskrnl!MmUnlockPages` at `0x14004ed8b`
- `ntoskrnl!MmUnlockPages` at `0x14004ed8b`
- `ntoskrnl!MmProbeAndLockPages` at `0x14004eb9a`
- `ntoskrnl!MmProbeAndLockPages` at `0x14004eb9a`
- `ntoskrnl!IoAllocateMdl` at `0x14004eb66`
- `ntoskrnl!IoAllocateMdl` at `0x14004eb66`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14004eaf1`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14004eaf1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004ec3f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004ec8d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004ecde`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004ecf8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004ed33`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004ec3f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004ec8d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004ecde`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004ecf8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004ed33`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004ec1a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004ec1a`
- `ntoskrnl!ProbeForWrite` at `0x14004ec04`
- `ntoskrnl!ProbeForWrite` at `0x14004ec04`

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
0x14004ea50  push    rbx
0x14004ea52  push    rsi
0x14004ea53  push    rdi
0x14004ea54  push    r12
0x14004ea56  push    r13
0x14004ea58  push    r14
0x14004ea5a  push    r15
0x14004ea5c  sub     rsp, 190h
0x14004ea63  mov     rax, cs:__security_cookie
0x14004ea6a  xor     rax, rsp
0x14004ea6d  mov     [rsp+1C8h+var_48], rax
0x14004ea75  mov     r14b, r8b
0x14004ea78  mov     rsi, [rsp+1C8h+VirtualAddress]
0x14004ea80  mov     [rsp+1C8h+var_170], rsi
0x14004ea85  mov     ebx, [rsp+1C8h+Length]
0x14004ea8c  mov     r15, [rsp+1C8h+arg_38]
0x14004ea94  mov     [rsp+1C8h+var_168], r15
0x14004ea99  xor     eax, eax
0x14004ea9b  mov     [rsp+1C8h+Src], rax
0x14004eaa0  mov     [rsp+1C8h+var_158], eax
0x14004eaa4  xorps   xmm0, xmm0
0x14004eaa7  movups  xmmword ptr [rsp+1C8h+LockHandle.LockQueue.Next], xmm0
0x14004eaac  mov     qword ptr [rsp+1C8h+LockHandle.OldIrql], rax
0x14004eab1  mov     [rsp+1C8h+var_190], rax
0x14004eab6  mov     r13, [rcx+18h]
0x14004eaba  mov     [rsp+1C8h+var_198], eax
0x14004eabe  xor     edi, edi
0x14004eac0  mov     [rsp+1C8h+var_190], rdi
0x14004eac5  mov     [r15], rax
0x14004eac8  mov     eax, [r13+8]
0x14004eacc  test    al, 1
0x14004eace  jz      loc_14004EDAC
0x14004ead4  lea     r12d, [rdi+0Ch]
0x14004ead8  cmp     [rsp+1C8h+arg_20], r12d
0x14004eae0  jb      loc_14004EDAC
0x14004eae6  test    r8b, r8b
0x14004eae9  jz      short loc_14004EB15
0x14004eaeb  test    r9b, 3
0x14004eaef  jz      short loc_14004EAFE
0x14004eaf1  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14004eaf8  nop     dword ptr [rax+rax+00h]
0x14004eafd  int     3; Trap to Debugger
0x14004eafe  test    r14b, r14b
0x14004eb01  jz      short loc_14004EB15
0x14004eb03  mov     r8, r12; Size
0x14004eb06  mov     rdx, r9; Src
0x14004eb09  lea     rcx, [rsp+1C8h+Src]; void *
0x14004eb0e  call    RtlCopyFromUser
0x14004eb13  jmp     short loc_14004EB25
0x14004eb15  mov     r8, r12; Size
0x14004eb18  mov     rdx, r9; Src
0x14004eb1b  lea     rcx, [rsp+1C8h+Src]; void *
0x14004eb20  call    RtlCopyVolatileMemory
0x14004eb25  cmp     byte ptr [rsp+1C8h+var_158], 0
0x14004eb2a  jz      short loc_14004EB3E
0x14004eb2c  cmp     ebx, r12d
0x14004eb2f  jnb     short loc_14004EB3E
0x14004eb31  mov     [rsp+1C8h+var_198], 0C000000Dh
0x14004eb39  jmp     loc_14004ED7D
0x14004eb3e  test    ebx, ebx
0x14004eb40  jz      loc_14004EC11
0x14004eb46  cmp     ebx, 100h
0x14004eb4c  jbe     loc_14004EBF3
0x14004eb52  mov     [rsp+1C8h+Irp], 0; Irp
0x14004eb5b  mov     r9b, 1; ChargeQuota
0x14004eb5e  xor     r8d, r8d; SecondaryBuffer
0x14004eb61  mov     edx, ebx; Length
0x14004eb63  mov     rcx, rsi; VirtualAddress
0x14004eb66  call    cs:__imp_IoAllocateMdl
0x14004eb6d  nop     dword ptr [rax+rax+00h]
0x14004eb72  mov     rdi, rax
0x14004eb75  mov     [rsp+1C8h+var_190], rax
0x14004eb7a  test    rax, rax
0x14004eb7d  jnz     short loc_14004EB8C
0x14004eb7f  mov     [rsp+1C8h+var_198], 0C000009Ah
0x14004eb87  jmp     loc_14004ED7D
0x14004eb8c  mov     esi, 1
0x14004eb91  mov     r8d, esi; Operation
0x14004eb94  mov     dl, r14b; AccessMode
0x14004eb97  mov     rcx, rdi; MemoryDescriptorList
0x14004eb9a  call    cs:__imp_MmProbeAndLockPages
0x14004eba1  nop     dword ptr [rax+rax+00h]
0x14004eba6  test    byte ptr [rdi+0Ah], 5
0x14004ebaa  jz      short loc_14004EBB2
0x14004ebac  mov     rsi, [rdi+18h]
0x14004ebb0  jmp     short loc_14004EBDC
0x14004ebb2  mov     [rsp+1C8h+Priority], 40000000h; Priority
0x14004ebba  mov     dword ptr [rsp+1C8h+Irp], 0; BugCheckOnFailure
0x14004ebc2  xor     r9d, r9d; RequestedAddress
0x14004ebc5  mov     r8d, esi; CacheType
0x14004ebc8  xor     edx, edx; AccessMode
0x14004ebca  mov     rcx, rdi; MemoryDescriptorList
0x14004ebcd  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14004ebd4  nop     dword ptr [rax+rax+00h]
0x14004ebd9  mov     rsi, rax
0x14004ebdc  mov     [rsp+1C8h+var_170], rsi
0x14004ebe1  test    rsi, rsi
0x14004ebe4  jnz     short loc_14004EC11
0x14004ebe6  mov     [rsp+1C8h+var_198], 0C000009Ah
0x14004ebee  jmp     loc_14004ED7D
0x14004ebf3  test    r14b, r14b
0x14004ebf6  jz      short loc_14004EC11
0x14004ebf8  mov     rdx, rbx; Length
0x14004ebfb  mov     r8d, 1; Alignment
0x14004ec01  mov     rcx, rsi; Address
0x14004ec04  call    cs:__imp_ProbeForWrite
0x14004ec0b  nop     dword ptr [rax+rax+00h]
0x14004ec10  nop
0x14004ec11  lea     rcx, [r13+38h]; SpinLock
0x14004ec15  lea     rdx, [rsp+1C8h+LockHandle]; LockHandle
0x14004ec1a  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14004ec21  nop     dword ptr [rax+rax+00h]
0x14004ec26  mov     edx, dword ptr [rsp+1C8h+Src]
0x14004ec2a  mov     rcx, r13
0x14004ec2d  call    AfdFindReturnedConnection
0x14004ec32  mov     rcx, rax
0x14004ec35  test    rax, rax
0x14004ec38  jnz     short loc_14004EC58
0x14004ec3a  lea     rcx, [rsp+1C8h+LockHandle]; LockHandle
0x14004ec3f  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004ec46  nop     dword ptr [rax+rax+00h]
0x14004ec4b  mov     [rsp+1C8h+var_198], 0C000000Dh
0x14004ec53  jmp     loc_14004ED7D
0x14004ec58  xor     edx, edx
0x14004ec5a  mov     eax, [r13+8]
0x14004ec5e  bt      eax, 8
0x14004ec62  jb      short loc_14004EC7B
0x14004ec64  mov     rax, [rcx+0E0h]
0x14004ec6b  test    rax, rax
0x14004ec6e  jz      short loc_14004EC7D
0x14004ec70  cmp     [rax+20h], rdx
0x14004ec74  jz      short loc_14004EC7D
0x14004ec76  mov     edx, [rax+28h]
0x14004ec79  jmp     short loc_14004EC7D
0x14004ec7b  xor     eax, eax
0x14004ec7d  cmp     byte ptr [rsp+1C8h+var_158], 0
0x14004ec82  jz      short loc_14004ECD5
0x14004ec84  mov     dword ptr [rsp+1C8h+Src+4], edx
0x14004ec88  lea     rcx, [rsp+1C8h+LockHandle]; LockHandle
0x14004ec8d  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004ec94  nop     dword ptr [rax+rax+00h]
0x14004ec99  nop
0x14004ec9a  test    rdi, rdi
0x14004ec9d  jnz     short loc_14004ECB6
0x14004ec9f  test    r14b, r14b
0x14004eca2  jz      short loc_14004ECB6
0x14004eca4  mov     r8, r12; Size
0x14004eca7  lea     rdx, [rsp+1C8h+Src]; Src
0x14004ecac  mov     rcx, rsi; void *
0x14004ecaf  call    RtlCopyToUser
0x14004ecb4  jmp     short loc_14004ECC6
0x14004ecb6  mov     r8, r12; Size
0x14004ecb9  lea     rdx, [rsp+1C8h+Src]; Src
0x14004ecbe  mov     rcx, rsi; void *
0x14004ecc1  call    RtlCopyVolatileMemory
0x14004ecc6  mov     [r15], r12
0x14004ecc9  jmp     short loc_14004ECD0
0x14004eccb  mov     rdi, [rsp+1C8h+var_190]
0x14004ecd0  jmp     loc_14004ED7D
0x14004ecd5  test    edx, edx
0x14004ecd7  jnz     short loc_14004ECEF
0x14004ecd9  lea     rcx, [rsp+1C8h+LockHandle]; LockHandle
0x14004ecde  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004ece5  nop     dword ptr [rax+rax+00h]
0x14004ecea  jmp     loc_14004ED7D
0x14004ecef  cmp     ebx, edx
0x14004ecf1  jnb     short loc_14004ED0E
0x14004ecf3  lea     rcx, [rsp+1C8h+LockHandle]; LockHandle
0x14004ecf8  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004ecff  nop     dword ptr [rax+rax+00h]
0x14004ed04  mov     [rsp+1C8h+var_198], 0C0000023h
0x14004ed0c  jmp     short loc_14004ED7D
0x14004ed0e  lea     rcx, [rsp+1C8h+var_148]
0x14004ed16  test    rdi, rdi
0x14004ed19  cmovnz  rcx, rsi; void *
0x14004ed1d  mov     ebx, edx
0x14004ed1f  mov     r8d, edx; Size
0x14004ed22  mov     rdx, [rax+20h]; Src
0x14004ed26  call    RtlCopyVolatileMemory
0x14004ed2b  mov     [r15], rbx
0x14004ed2e  lea     rcx, [rsp+1C8h+LockHandle]; LockHandle
0x14004ed33  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004ed3a  nop     dword ptr [rax+rax+00h]
0x14004ed3f  test    rdi, rdi
0x14004ed42  jnz     short loc_14004ED82
0x14004ed44  mov     r8, [r15]; Size
0x14004ed47  lea     rdx, [rsp+1C8h+var_148]; Src
0x14004ed4f  mov     rcx, rsi; void *
0x14004ed52  test    r14b, r14b
0x14004ed55  jz      short loc_14004ED5E
0x14004ed57  call    RtlCopyToUser
0x14004ed5c  jmp     short loc_14004ED63
0x14004ed5e  call    RtlCopyVolatileMemory
0x14004ed63  jmp     short loc_14004ED7D
0x14004ed65  mov     rax, [rsp+1C8h+var_168]
0x14004ed6a  mov     qword ptr [rax], 0
0x14004ed71  mov     rdi, [rsp+1C8h+var_190]
0x14004ed76  jmp     short loc_14004ED7D
0x14004ed78  mov     rdi, [rsp+1C8h+var_190]
0x14004ed7d  test    rdi, rdi
0x14004ed80  jz      short loc_14004EDA6
0x14004ed82  test    byte ptr [rdi+0Ah], 2
0x14004ed86  jz      short loc_14004ED97
0x14004ed88  mov     rcx, rdi; MemoryDescriptorList
0x14004ed8b  call    cs:__imp_MmUnlockPages
0x14004ed92  nop     dword ptr [rax+rax+00h]
0x14004ed97  mov     rcx, rdi; Mdl
0x14004ed9a  call    cs:__imp_IoFreeMdl
0x14004eda1  nop     dword ptr [rax+rax+00h]
0x14004eda6  mov     eax, [rsp+1C8h+var_198]
0x14004edaa  jmp     short loc_14004EDB1
0x14004edac  mov     eax, 0C000000Dh
0x14004edb1  mov     rcx, [rsp+1C8h+var_48]
0x14004edb9  xor     rcx, rsp; StackCookie
0x14004edbc  call    __security_check_cookie
0x14004edc1  add     rsp, 190h
0x14004edc8  pop     r15
0x14004edca  pop     r14
0x14004edcc  pop     r13
0x14004edce  pop     r12
0x14004edd0  pop     rdi
0x14004edd1  pop     rsi
0x14004edd2  pop     rbx
0x14004edd3  retn
0x140073e87  push    rbp
0x140073e89  sub     rsp, 30h
0x140073e8d  mov     rbp, rdx
0x140073e90  mov     r8, rcx
0x140073e93  lea     r9, [rbp+30h]
0x140073e97  mov     edx, 1DECh
0x140073e9c  lea     rcx, aMinioSocketsWi_6; "minio\\sockets\\winsock2\\wsp\\afdsys\\"...
0x140073ea3  call    AfdExceptionFilter
0x140073ea8  nop
0x140073ea9  add     rsp, 30h
0x140073ead  pop     rbp
0x140073eae  retn
0x140073eb0  push    rbp
0x140073eb2  sub     rsp, 30h
0x140073eb6  mov     rbp, rdx
0x140073eb9  mov     r8, rcx
0x140073ebc  lea     r9, [rbp+30h]
0x140073ec0  mov     edx, 1E31h
0x140073ec5  lea     rcx, aMinioSocketsWi_6; "minio\\sockets\\winsock2\\wsp\\afdsys\\"...
0x140073ecc  call    AfdExceptionFilter
0x140073ed1  nop
0x140073ed2  add     rsp, 30h
0x140073ed6  pop     rbp
0x140073ed7  retn
0x140073ed9  push    rbp
0x140073edb  sub     rsp, 30h
0x140073edf  mov     rbp, rdx
0x140073ee2  mov     r8, rcx
0x140073ee5  lea     r9, [rbp+30h]
0x140073ee9  mov     edx, 1E5Dh
0x140073eee  lea     rcx, aMinioSocketsWi_6; "minio\\sockets\\winsock2\\wsp\\afdsys\\"...
0x140073ef5  call    AfdExceptionFilter
0x140073efa  nop
0x140073efb  add     rsp, 30h
0x140073eff  pop     rbp
0x140073f00  retn
```
