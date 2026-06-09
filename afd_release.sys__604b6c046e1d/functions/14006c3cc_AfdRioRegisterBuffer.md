# AfdRioRegisterBuffer

- ea: `0x14006c3cc`
- end: `0x14006c758`
- name: `AfdRioRegisterBuffer`
- size: `908`
- prototype: `__int64 __fastcall(__int64, void *, unsigned int, void *, unsigned int, KPROCESSOR_MODE AccessMode)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1400064f0`

## callees

- `0x14002fd5c`
- `0x14003eb88`
- `0x14003edf4`
- `0x1400445b8`
- `0x14006976c`
- `0x14006c3cc`
- `0x1400726a0`
- `0x1400726d0`
- `0x140092254`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x14006c44f`
- `ntoskrnl!ExRaiseStatus` at `0x14006c515`
- `ntoskrnl!ExRaiseStatus` at `0x14006c637`
- `ntoskrnl!ExRaiseStatus` at `0x14006c44f`
- `ntoskrnl!ExRaiseStatus` at `0x14006c515`
- `ntoskrnl!ExRaiseStatus` at `0x14006c637`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006c562`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006c562`
- `ntoskrnl!IoFreeMdl` at `0x14006c720`
- `ntoskrnl!IoFreeMdl` at `0x14006c720`
- `ntoskrnl!MmUnlockPages` at `0x14006c711`
- `ntoskrnl!MmUnlockPages` at `0x14006c711`
- `ntoskrnl!MmProbeAndLockPages` at `0x14006c52a`
- `ntoskrnl!MmProbeAndLockPages` at `0x14006c52a`
- `ntoskrnl!IoAllocateMdl` at `0x14006c4f4`
- `ntoskrnl!IoAllocateMdl` at `0x14006c4f4`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14006c488`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14006c659`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14006c488`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14006c659`

## pseudocode

```c
__int64 __fastcall AfdRioRegisterBuffer(
        __int64 a1,
        void *a2,
        unsigned int a3,
        void *a4,
        unsigned int a5,
        KPROCESSOR_MODE AccessMode)
{
  struct _MDL *Mdl; // rax
  __int64 v7; // rsi
  PVOID v8; // r13
  unsigned int v9; // edi
  char v10; // r15
  char v11; // al
  int v12; // r8d
  unsigned int v14; // [rsp+48h] [rbp-A0h] BYREF
  ULONG v15; // [rsp+4Ch] [rbp-9Ch]
  ULONG v16; // [rsp+50h] [rbp-98h]
  __int64 v17; // [rsp+58h] [rbp-90h]
  void *v18; // [rsp+60h] [rbp-88h]
  PVOID v19; // [rsp+68h] [rbp-80h]
  PVOID v20; // [rsp+70h] [rbp-78h]
  PVOID v21; // [rsp+78h] [rbp-70h]
  void *Src; // [rsp+80h] [rbp-68h] BYREF
  struct _MDL *v23; // [rsp+88h] [rbp-60h]
  __int64 v24; // [rsp+90h] [rbp-58h]
  __int64 v25; // [rsp+98h] [rbp-50h] BYREF
  PVOID VirtualAddress[2]; // [rsp+A0h] [rbp-48h] BYREF
  ULONG Length; // [rsp+B0h] [rbp-38h]

  v18 = a4;
  v17 = a1;
  v24 = a1;
  Src = a4;
  v23 = 0;
  v19 = 0;
  v14 = 0;
  v16 = 0;
  v25 = 0;
  v20 = 0;
  if ( a3 < 0x18 )
    ExRaiseStatus(-1073741811);
  *(_OWORD *)VirtualAddress = 0;
  Length = 0;
  if ( AccessMode )
  {
    if ( ((unsigned __int8)a2 & 3) != 0 )
      ExRaiseDatatypeMisalignment();
    RtlCopyFromUser(VirtualAddress, a2, 0x18u);
  }
  else
  {
    RtlCopyVolatileMemory(VirtualAddress, a2, 0x18u);
  }
  v15 = Length;
  v16 = Length;
  v21 = VirtualAddress[1];
  v20 = VirtualAddress[1];
  Mdl = IoAllocateMdl(VirtualAddress[1], Length, 0, 1u, 0);
  v7 = (__int64)Mdl;
  v23 = Mdl;
  if ( !Mdl )
    ExRaiseStatus(-1073741801);
  MmProbeAndLockPages(Mdl, AccessMode, IoWriteAccess);
  if ( (*(_BYTE *)(v7 + 10) & 5) != 0 )
    v8 = *(PVOID *)(v7 + 24);
  else
    v8 = MmMapLockedPagesSpecifyCache((PMDL)v7, 0, MmCached, 0, 0, 0x40000010u);
  v19 = v8;
  v9 = AfdRioCreateRegisteredBuffer(v17, v7, (__int64)v8, v15, &v14, &v25);
  v10 = v14;
  if ( v9 )
  {
    v11 = v15;
    v12 = (int)v21;
  }
  else
  {
    if ( a5 < 4 )
      ExRaiseStatus(-1073741811);
    LODWORD(Src) = v14;
    if ( AccessMode && ((unsigned __int8)v18 & 3) != 0 )
      ExRaiseDatatypeMisalignment();
    if ( AccessMode )
      RtlWriteULongToUser(v18, v14);
    else
      RtlCopyVolatileMemory(v18, &Src, 4u);
    v9 = 0;
    v11 = v15;
    v12 = (int)v21;
  }
  AFDETW_RIO_TRACE_BUFFER_REGISTER(v25, v17, v12, (_DWORD)v8, v11, v10, v9);
  if ( v9 && v7 )
  {
    MmUnlockPages((PMDL)v7);
    IoFreeMdl((PMDL)v7);
  }
  return v9;
}

```

## disassembly

```asm
0x14006c3cc  mov     r11, rsp
0x14006c3cf  mov     [r11+18h], rsi
0x14006c3d3  push    rdi
0x14006c3d4  push    r12
0x14006c3d6  push    r13
0x14006c3d8  push    r14
0x14006c3da  push    r15
0x14006c3dc  sub     rsp, 0C0h
0x14006c3e3  mov     rax, cs:__security_cookie
0x14006c3ea  xor     rax, rsp
0x14006c3ed  mov     [rsp+0E8h+var_30], rax
0x14006c3f5  mov     [rsp+0E8h+var_88], r9
0x14006c3fa  mov     [rsp+0E8h+var_90], rcx
0x14006c3ff  mov     [rsp+0E8h+var_58], rcx
0x14006c407  mov     [rsp+0E8h+Src], r9
0x14006c40f  mov     qword ptr [r11-60h], 0
0x14006c417  mov     qword ptr [r11-80h], 0
0x14006c41f  mov     [rsp+0E8h+var_A8], 0
0x14006c424  xor     r15d, r15d
0x14006c427  mov     [rsp+0E8h+var_A0], r15d
0x14006c42c  mov     [rsp+0E8h+var_98], r15d
0x14006c431  mov     [rsp+0E8h+var_A4], 0C0000100h
0x14006c439  mov     [r11-50h], r15
0x14006c43d  mov     [r11-78h], r15
0x14006c441  lea     ecx, [r15+18h]
0x14006c445  cmp     r8d, ecx
0x14006c448  jnb     short loc_14006C45B
0x14006c44a  mov     ecx, 0C000000Dh; Status
0x14006c44f  call    cs:__imp_ExRaiseStatus
0x14006c45b  xor     eax, eax
0x14006c45d  mov     dword ptr [rsp+0E8h+VirtualAddress+4], eax
0x14006c464  xorps   xmm0, xmm0
0x14006c467  movups  xmmword ptr [rsp+0E8h+VirtualAddress], xmm0
0x14006c46f  mov     [rsp+0E8h+Length], eax
0x14006c476  mov     r14b, [rsp+0E8h+AccessMode]
0x14006c47e  test    r14b, r14b
0x14006c481  jz      short loc_14006C4AC
0x14006c483  test    dl, 3
0x14006c486  jz      short loc_14006C495
0x14006c488  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14006c48f  nop     dword ptr [rax+rax+00h]
0x14006c494  int     3; Trap to Debugger
0x14006c495  test    r14b, r14b
0x14006c498  jz      short loc_14006C4AC
0x14006c49a  mov     r8, rcx; Size
0x14006c49d  lea     rcx, [rsp+0E8h+VirtualAddress]; void *
0x14006c4a5  call    RtlCopyFromUser
0x14006c4aa  jmp     short loc_14006C4BC
0x14006c4ac  mov     r8, rcx; Size
0x14006c4af  lea     rcx, [rsp+0E8h+VirtualAddress]; void *
0x14006c4b7  call    RtlCopyVolatileMemory
0x14006c4bc  mov     eax, [rsp+0E8h+Length]
0x14006c4c3  mov     [rsp+0E8h+var_9C], eax
0x14006c4c7  mov     [rsp+0E8h+var_98], eax
0x14006c4cb  mov     rcx, [rsp+0E8h+VirtualAddress+8]; VirtualAddress
0x14006c4d3  mov     [rsp+0E8h+var_70], rcx
0x14006c4d8  mov     [rsp+0E8h+var_78], rcx
0x14006c4dd  mov     [rsp+0E8h+Irp], 0; Irp
0x14006c4e6  mov     r12d, 1
0x14006c4ec  mov     r9b, r12b; ChargeQuota
0x14006c4ef  xor     r8d, r8d; SecondaryBuffer
0x14006c4f2  mov     edx, eax; Length
0x14006c4f4  call    cs:__imp_IoAllocateMdl
0x14006c4fb  nop     dword ptr [rax+rax+00h]
0x14006c500  mov     rsi, rax
0x14006c503  mov     [rsp+0E8h+var_60], rax
0x14006c50b  test    rax, rax
0x14006c50e  jnz     short loc_14006C521
0x14006c510  mov     ecx, 0C0000017h; Status
0x14006c515  call    cs:__imp_ExRaiseStatus
0x14006c521  mov     r8d, r12d; Operation
0x14006c524  mov     dl, r14b; AccessMode
0x14006c527  mov     rcx, rsi; MemoryDescriptorList
0x14006c52a  call    cs:__imp_MmProbeAndLockPages
0x14006c531  nop     dword ptr [rax+rax+00h]
0x14006c536  mov     [rsp+0E8h+var_A8], r12b
0x14006c53b  test    byte ptr [rsi+0Ah], 5
0x14006c53f  jz      short loc_14006C547
0x14006c541  mov     r13, [rsi+18h]
0x14006c545  jmp     short loc_14006C571
0x14006c547  mov     [rsp+0E8h+Priority], 40000010h; Priority
0x14006c54f  mov     dword ptr [rsp+0E8h+Irp], 0; BugCheckOnFailure
0x14006c557  xor     r9d, r9d; RequestedAddress
0x14006c55a  mov     r8d, r12d; CacheType
0x14006c55d  xor     edx, edx; AccessMode
0x14006c55f  mov     rcx, rsi; MemoryDescriptorList
0x14006c562  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14006c569  nop     dword ptr [rax+rax+00h]
0x14006c56e  mov     r13, rax
0x14006c571  mov     [rsp+0E8h+var_80], r13
0x14006c576  mov     [rsp+0E8h+var_A4], 0
0x14006c57e  mov     edi, [rsp+0E8h+var_A4]
0x14006c582  mov     rax, [rsp+0E8h+var_90]
0x14006c587  mov     ecx, [rsp+0E8h+var_9C]
0x14006c58b  jmp     short loc_14006C5E1
0x14006c58d  mov     edi, 0C00000E8h
0x14006c592  mov     [rsp+0E8h+var_A4], edi
0x14006c596  mov     r14b, [rsp+0E8h+AccessMode]
0x14006c59e  mov     rsi, [rsp+0E8h+var_60]
0x14006c5a6  mov     r13, [rsp+0E8h+var_80]
0x14006c5ab  mov     r12b, [rsp+0E8h+var_A8]
0x14006c5b0  mov     r15d, [rsp+0E8h+var_A0]
0x14006c5b5  mov     ecx, [rsp+0E8h+var_98]
0x14006c5b9  mov     [rsp+0E8h+var_9C], ecx
0x14006c5bd  mov     rax, [rsp+0E8h+var_78]
0x14006c5c2  mov     [rsp+0E8h+var_70], rax
0x14006c5c7  mov     rax, [rsp+0E8h+var_58]
0x14006c5cf  mov     [rsp+0E8h+var_90], rax
0x14006c5d4  mov     r9, [rsp+0E8h+Src]
0x14006c5dc  mov     [rsp+0E8h+var_88], r9
0x14006c5e1  test    edi, edi
0x14006c5e3  jnz     loc_14006C6D5
0x14006c5e9  lea     rdx, [rsp+0E8h+var_50]
0x14006c5f1  mov     qword ptr [rsp+0E8h+Priority], rdx
0x14006c5f6  lea     rdx, [rsp+0E8h+var_A0]
0x14006c5fb  mov     [rsp+0E8h+Irp], rdx
0x14006c600  mov     r9d, ecx
0x14006c603  mov     r8, r13
0x14006c606  mov     rdx, rsi
0x14006c609  mov     rcx, rax
0x14006c60c  call    AfdRioCreateRegisteredBuffer
0x14006c611  mov     edi, eax
0x14006c613  mov     [rsp+0E8h+var_A4], eax
0x14006c617  mov     r15d, [rsp+0E8h+var_A0]
0x14006c61c  test    eax, eax
0x14006c61e  jnz     loc_14006C6D5
0x14006c624  lea     r8d, [rax+4]
0x14006c628  cmp     [rsp+0E8h+arg_20], r8d
0x14006c630  jnb     short loc_14006C643
0x14006c632  mov     ecx, 0C000000Dh; Status
0x14006c637  call    cs:__imp_ExRaiseStatus
0x14006c643  mov     dword ptr [rsp+0E8h+Src], r15d
0x14006c64b  mov     rax, [rsp+0E8h+var_88]
0x14006c650  test    r14b, r14b
0x14006c653  jz      short loc_14006C666
0x14006c655  test    al, 3
0x14006c657  jz      short loc_14006C666
0x14006c659  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14006c660  nop     dword ptr [rax+rax+00h]
0x14006c665  int     3; Trap to Debugger
0x14006c666  mov     rcx, rax; void *
0x14006c669  test    r14b, r14b
0x14006c66c  jz      short loc_14006C678
0x14006c66e  mov     edx, r15d
0x14006c671  call    RtlWriteULongToUser
0x14006c676  jmp     short loc_14006C685
0x14006c678  lea     rdx, [rsp+0E8h+Src]; Src
0x14006c680  call    RtlCopyVolatileMemory
0x14006c685  mov     [rsp+0E8h+var_A4], 0
0x14006c68d  mov     edi, [rsp+0E8h+var_A4]
0x14006c691  mov     eax, [rsp+0E8h+var_9C]
0x14006c695  mov     r8, [rsp+0E8h+var_70]
0x14006c69a  jmp     short loc_14006C6DE
0x14006c69c  xor     r8d, r8d
0x14006c69f  mov     r15d, [rsp+0E8h+var_A0]
0x14006c6a4  mov     edx, r15d
0x14006c6a7  mov     rax, [rsp+0E8h+var_58]
0x14006c6af  mov     [rsp+0E8h+var_90], rax
0x14006c6b4  mov     rcx, rax
0x14006c6b7  call    AfdRioInvalidateBuffer
0x14006c6bc  xor     esi, esi
0x14006c6be  xor     r12b, r12b
0x14006c6c1  mov     r13, [rsp+0E8h+var_80]
0x14006c6c6  mov     eax, [rsp+0E8h+var_98]
0x14006c6ca  mov     edi, [rsp+0E8h+var_A4]
0x14006c6ce  mov     r8, [rsp+0E8h+var_78]
0x14006c6d3  jmp     short loc_14006C6DE
0x14006c6d5  mov     eax, [rsp+0E8h+var_9C]
0x14006c6d9  mov     r8, [rsp+0E8h+var_70]
0x14006c6de  mov     [rsp+0E8h+var_B8], edi
0x14006c6e2  mov     [rsp+0E8h+Priority], r15d
0x14006c6e7  mov     dword ptr [rsp+0E8h+Irp], eax
0x14006c6eb  mov     r9, r13
0x14006c6ee  mov     rdx, [rsp+0E8h+var_90]
0x14006c6f3  mov     rcx, [rsp+0E8h+var_50]
0x14006c6fb  call    AFDETW_RIO_TRACE_BUFFER_REGISTER
0x14006c700  test    edi, edi
0x14006c702  jz      short loc_14006C72C
0x14006c704  test    rsi, rsi
0x14006c707  jz      short loc_14006C72C
0x14006c709  test    r12b, r12b
0x14006c70c  jz      short loc_14006C71D
0x14006c70e  mov     rcx, rsi; MemoryDescriptorList
0x14006c711  call    cs:__imp_MmUnlockPages
0x14006c718  nop     dword ptr [rax+rax+00h]
0x14006c71d  mov     rcx, rsi; Mdl
0x14006c720  call    cs:__imp_IoFreeMdl
0x14006c727  nop     dword ptr [rax+rax+00h]
0x14006c72c  mov     eax, edi
0x14006c72e  mov     rcx, [rsp+0E8h+var_30]
0x14006c736  xor     rcx, rsp; StackCookie
0x14006c739  call    __security_check_cookie
0x14006c73e  mov     rsi, [rsp+0E8h+arg_10]
0x14006c746  add     rsp, 0C0h
0x14006c74d  pop     r15
0x14006c74f  pop     r14
0x14006c751  pop     r13
0x14006c753  pop     r12
0x14006c755  pop     rdi
0x14006c756  retn
0x140074693  push    rbp
0x140074695  sub     rsp, 40h
0x140074699  mov     rbp, rdx
0x14007469c  mov     r8, rcx
0x14007469f  lea     r9, [rbp+44h]
0x1400746a3  mov     edx, 0F98h
0x1400746a8  lea     rcx, aMinioSocketsWi_2; "minio\\sockets\\winsock2\\wsp\\afdsys\\"...
0x1400746af  call    AfdExceptionFilter
0x1400746b4  nop
0x1400746b5  add     rsp, 40h
0x1400746b9  pop     rbp
0x1400746ba  retn
0x1400746bc  push    rbp
0x1400746be  sub     rsp, 40h
0x1400746c2  mov     rbp, rdx
0x1400746c5  mov     r8, rcx
0x1400746c8  lea     r9, [rbp+44h]
0x1400746cc  mov     edx, 0FB8h
0x1400746d1  lea     rcx, aMinioSocketsWi_2; "minio\\sockets\\winsock2\\wsp\\afdsys\\"...
0x1400746d8  call    AfdExceptionFilter
0x1400746dd  nop
0x1400746de  add     rsp, 40h
0x1400746e2  pop     rbp
0x1400746e3  retn
```
