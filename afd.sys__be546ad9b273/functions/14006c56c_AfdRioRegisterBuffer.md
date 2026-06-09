# AfdRioRegisterBuffer

- ea: `0x14006c56c`
- end: `0x14006c8f8`
- name: `AfdRioRegisterBuffer`
- size: `908`
- prototype: `__int64 __fastcall(__int64, void *, unsigned int, void *, unsigned int, KPROCESSOR_MODE AccessMode)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1400064f0`

## callees

- `0x14002fd7c`
- `0x14003eba8`
- `0x14003ee14`
- `0x1400445d8`
- `0x14006990c`
- `0x14006c56c`
- `0x140072840`
- `0x140072870`
- `0x140092254`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x14006c5ef`
- `ntoskrnl!ExRaiseStatus` at `0x14006c6b5`
- `ntoskrnl!ExRaiseStatus` at `0x14006c7d7`
- `ntoskrnl!ExRaiseStatus` at `0x14006c5ef`
- `ntoskrnl!ExRaiseStatus` at `0x14006c6b5`
- `ntoskrnl!ExRaiseStatus` at `0x14006c7d7`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006c702`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006c702`
- `ntoskrnl!IoFreeMdl` at `0x14006c8c0`
- `ntoskrnl!IoFreeMdl` at `0x14006c8c0`
- `ntoskrnl!MmUnlockPages` at `0x14006c8b1`
- `ntoskrnl!MmUnlockPages` at `0x14006c8b1`
- `ntoskrnl!MmProbeAndLockPages` at `0x14006c6ca`
- `ntoskrnl!MmProbeAndLockPages` at `0x14006c6ca`
- `ntoskrnl!IoAllocateMdl` at `0x14006c694`
- `ntoskrnl!IoAllocateMdl` at `0x14006c694`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14006c628`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14006c7f9`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14006c628`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14006c7f9`

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
  struct _MDL *v7; // rsi
  PVOID MappedSystemVa; // r13
  unsigned int RegisteredBuffer; // edi
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
  v7 = Mdl;
  v23 = Mdl;
  if ( !Mdl )
    ExRaiseStatus(-1073741801);
  MmProbeAndLockPages(Mdl, AccessMode, IoWriteAccess);
  if ( (v7->MdlFlags & 5) != 0 )
    MappedSystemVa = v7->MappedSystemVa;
  else
    MappedSystemVa = MmMapLockedPagesSpecifyCache(v7, 0, MmCached, 0, 0, 0x40000010u);
  v19 = MappedSystemVa;
  RegisteredBuffer = AfdRioCreateRegisteredBuffer(
                       v17,
                       (_DWORD)v7,
                       (_DWORD)MappedSystemVa,
                       v15,
                       (__int64)&v14,
                       (__int64)&v25);
  v10 = v14;
  if ( RegisteredBuffer )
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
    RegisteredBuffer = 0;
    v11 = v15;
    v12 = (int)v21;
  }
  AFDETW_RIO_TRACE_BUFFER_REGISTER(v25, v17, v12, (_DWORD)MappedSystemVa, v11, v10, RegisteredBuffer);
  if ( RegisteredBuffer && v7 )
  {
    MmUnlockPages(v7);
    IoFreeMdl(v7);
  }
  return RegisteredBuffer;
}

```

## disassembly

```asm
0x14006c56c  mov     r11, rsp
0x14006c56f  mov     [r11+18h], rsi
0x14006c573  push    rdi
0x14006c574  push    r12
0x14006c576  push    r13
0x14006c578  push    r14
0x14006c57a  push    r15
0x14006c57c  sub     rsp, 0C0h
0x14006c583  mov     rax, cs:__security_cookie
0x14006c58a  xor     rax, rsp
0x14006c58d  mov     [rsp+0E8h+var_30], rax
0x14006c595  mov     [rsp+0E8h+var_88], r9
0x14006c59a  mov     [rsp+0E8h+var_90], rcx
0x14006c59f  mov     [rsp+0E8h+var_58], rcx
0x14006c5a7  mov     [rsp+0E8h+Src], r9
0x14006c5af  mov     qword ptr [r11-60h], 0
0x14006c5b7  mov     qword ptr [r11-80h], 0
0x14006c5bf  mov     [rsp+0E8h+var_A8], 0
0x14006c5c4  xor     r15d, r15d
0x14006c5c7  mov     [rsp+0E8h+var_A0], r15d
0x14006c5cc  mov     [rsp+0E8h+var_98], r15d
0x14006c5d1  mov     [rsp+0E8h+var_A4], 0C0000100h
0x14006c5d9  mov     [r11-50h], r15
0x14006c5dd  mov     [r11-78h], r15
0x14006c5e1  lea     ecx, [r15+18h]
0x14006c5e5  cmp     r8d, ecx
0x14006c5e8  jnb     short loc_14006C5FB
0x14006c5ea  mov     ecx, 0C000000Dh; Status
0x14006c5ef  call    cs:__imp_ExRaiseStatus
0x14006c5fb  xor     eax, eax
0x14006c5fd  mov     dword ptr [rsp+0E8h+VirtualAddress+4], eax
0x14006c604  xorps   xmm0, xmm0
0x14006c607  movups  xmmword ptr [rsp+0E8h+VirtualAddress], xmm0
0x14006c60f  mov     [rsp+0E8h+Length], eax
0x14006c616  mov     r14b, [rsp+0E8h+AccessMode]
0x14006c61e  test    r14b, r14b
0x14006c621  jz      short loc_14006C64C
0x14006c623  test    dl, 3
0x14006c626  jz      short loc_14006C635
0x14006c628  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14006c62f  nop     dword ptr [rax+rax+00h]
0x14006c634  int     3; Trap to Debugger
0x14006c635  test    r14b, r14b
0x14006c638  jz      short loc_14006C64C
0x14006c63a  mov     r8, rcx; Size
0x14006c63d  lea     rcx, [rsp+0E8h+VirtualAddress]; void *
0x14006c645  call    RtlCopyFromUser
0x14006c64a  jmp     short loc_14006C65C
0x14006c64c  mov     r8, rcx; Size
0x14006c64f  lea     rcx, [rsp+0E8h+VirtualAddress]; void *
0x14006c657  call    RtlCopyVolatileMemory
0x14006c65c  mov     eax, [rsp+0E8h+Length]
0x14006c663  mov     [rsp+0E8h+var_9C], eax
0x14006c667  mov     [rsp+0E8h+var_98], eax
0x14006c66b  mov     rcx, [rsp+0E8h+VirtualAddress+8]; VirtualAddress
0x14006c673  mov     [rsp+0E8h+var_70], rcx
0x14006c678  mov     [rsp+0E8h+var_78], rcx
0x14006c67d  mov     [rsp+0E8h+Irp], 0; Irp
0x14006c686  mov     r12d, 1
0x14006c68c  mov     r9b, r12b; ChargeQuota
0x14006c68f  xor     r8d, r8d; SecondaryBuffer
0x14006c692  mov     edx, eax; Length
0x14006c694  call    cs:__imp_IoAllocateMdl
0x14006c69b  nop     dword ptr [rax+rax+00h]
0x14006c6a0  mov     rsi, rax
0x14006c6a3  mov     [rsp+0E8h+var_60], rax
0x14006c6ab  test    rax, rax
0x14006c6ae  jnz     short loc_14006C6C1
0x14006c6b0  mov     ecx, 0C0000017h; Status
0x14006c6b5  call    cs:__imp_ExRaiseStatus
0x14006c6c1  mov     r8d, r12d; Operation
0x14006c6c4  mov     dl, r14b; AccessMode
0x14006c6c7  mov     rcx, rsi; MemoryDescriptorList
0x14006c6ca  call    cs:__imp_MmProbeAndLockPages
0x14006c6d1  nop     dword ptr [rax+rax+00h]
0x14006c6d6  mov     [rsp+0E8h+var_A8], r12b
0x14006c6db  test    byte ptr [rsi+0Ah], 5
0x14006c6df  jz      short loc_14006C6E7
0x14006c6e1  mov     r13, [rsi+18h]
0x14006c6e5  jmp     short loc_14006C711
0x14006c6e7  mov     [rsp+0E8h+Priority], 40000010h; Priority
0x14006c6ef  mov     dword ptr [rsp+0E8h+Irp], 0; BugCheckOnFailure
0x14006c6f7  xor     r9d, r9d; RequestedAddress
0x14006c6fa  mov     r8d, r12d; CacheType
0x14006c6fd  xor     edx, edx; AccessMode
0x14006c6ff  mov     rcx, rsi; MemoryDescriptorList
0x14006c702  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14006c709  nop     dword ptr [rax+rax+00h]
0x14006c70e  mov     r13, rax
0x14006c711  mov     [rsp+0E8h+var_80], r13
0x14006c716  mov     [rsp+0E8h+var_A4], 0
0x14006c71e  mov     edi, [rsp+0E8h+var_A4]
0x14006c722  mov     rax, [rsp+0E8h+var_90]
0x14006c727  mov     ecx, [rsp+0E8h+var_9C]
0x14006c72b  jmp     short loc_14006C781
0x14006c72d  mov     edi, 0C00000E8h
0x14006c732  mov     [rsp+0E8h+var_A4], edi
0x14006c736  mov     r14b, [rsp+0E8h+AccessMode]
0x14006c73e  mov     rsi, [rsp+0E8h+var_60]
0x14006c746  mov     r13, [rsp+0E8h+var_80]
0x14006c74b  mov     r12b, [rsp+0E8h+var_A8]
0x14006c750  mov     r15d, [rsp+0E8h+var_A0]
0x14006c755  mov     ecx, [rsp+0E8h+var_98]
0x14006c759  mov     [rsp+0E8h+var_9C], ecx
0x14006c75d  mov     rax, [rsp+0E8h+var_78]
0x14006c762  mov     [rsp+0E8h+var_70], rax
0x14006c767  mov     rax, [rsp+0E8h+var_58]
0x14006c76f  mov     [rsp+0E8h+var_90], rax
0x14006c774  mov     r9, [rsp+0E8h+Src]
0x14006c77c  mov     [rsp+0E8h+var_88], r9
0x14006c781  test    edi, edi
0x14006c783  jnz     loc_14006C875
0x14006c789  lea     rdx, [rsp+0E8h+var_50]
0x14006c791  mov     qword ptr [rsp+0E8h+Priority], rdx
0x14006c796  lea     rdx, [rsp+0E8h+var_A0]
0x14006c79b  mov     [rsp+0E8h+Irp], rdx
0x14006c7a0  mov     r9d, ecx
0x14006c7a3  mov     r8, r13
0x14006c7a6  mov     rdx, rsi
0x14006c7a9  mov     rcx, rax
0x14006c7ac  call    AfdRioCreateRegisteredBuffer
0x14006c7b1  mov     edi, eax
0x14006c7b3  mov     [rsp+0E8h+var_A4], eax
0x14006c7b7  mov     r15d, [rsp+0E8h+var_A0]
0x14006c7bc  test    eax, eax
0x14006c7be  jnz     loc_14006C875
0x14006c7c4  lea     r8d, [rax+4]
0x14006c7c8  cmp     [rsp+0E8h+arg_20], r8d
0x14006c7d0  jnb     short loc_14006C7E3
0x14006c7d2  mov     ecx, 0C000000Dh; Status
0x14006c7d7  call    cs:__imp_ExRaiseStatus
0x14006c7e3  mov     dword ptr [rsp+0E8h+Src], r15d
0x14006c7eb  mov     rax, [rsp+0E8h+var_88]
0x14006c7f0  test    r14b, r14b
0x14006c7f3  jz      short loc_14006C806
0x14006c7f5  test    al, 3
0x14006c7f7  jz      short loc_14006C806
0x14006c7f9  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14006c800  nop     dword ptr [rax+rax+00h]
0x14006c805  int     3; Trap to Debugger
0x14006c806  mov     rcx, rax; void *
0x14006c809  test    r14b, r14b
0x14006c80c  jz      short loc_14006C818
0x14006c80e  mov     edx, r15d
0x14006c811  call    RtlWriteULongToUser
0x14006c816  jmp     short loc_14006C825
0x14006c818  lea     rdx, [rsp+0E8h+Src]; Src
0x14006c820  call    RtlCopyVolatileMemory
0x14006c825  mov     [rsp+0E8h+var_A4], 0
0x14006c82d  mov     edi, [rsp+0E8h+var_A4]
0x14006c831  mov     eax, [rsp+0E8h+var_9C]
0x14006c835  mov     r8, [rsp+0E8h+var_70]
0x14006c83a  jmp     short loc_14006C87E
0x14006c83c  xor     r8d, r8d
0x14006c83f  mov     r15d, [rsp+0E8h+var_A0]
0x14006c844  mov     edx, r15d
0x14006c847  mov     rax, [rsp+0E8h+var_58]
0x14006c84f  mov     [rsp+0E8h+var_90], rax
0x14006c854  mov     rcx, rax
0x14006c857  call    AfdRioInvalidateBuffer
0x14006c85c  xor     esi, esi
0x14006c85e  xor     r12b, r12b
0x14006c861  mov     r13, [rsp+0E8h+var_80]
0x14006c866  mov     eax, [rsp+0E8h+var_98]
0x14006c86a  mov     edi, [rsp+0E8h+var_A4]
0x14006c86e  mov     r8, [rsp+0E8h+var_78]
0x14006c873  jmp     short loc_14006C87E
0x14006c875  mov     eax, [rsp+0E8h+var_9C]
0x14006c879  mov     r8, [rsp+0E8h+var_70]
0x14006c87e  mov     [rsp+0E8h+var_B8], edi
0x14006c882  mov     [rsp+0E8h+Priority], r15d
0x14006c887  mov     dword ptr [rsp+0E8h+Irp], eax
0x14006c88b  mov     r9, r13
0x14006c88e  mov     rdx, [rsp+0E8h+var_90]
0x14006c893  mov     rcx, [rsp+0E8h+var_50]
0x14006c89b  call    AFDETW_RIO_TRACE_BUFFER_REGISTER
0x14006c8a0  test    edi, edi
0x14006c8a2  jz      short loc_14006C8CC
0x14006c8a4  test    rsi, rsi
0x14006c8a7  jz      short loc_14006C8CC
0x14006c8a9  test    r12b, r12b
0x14006c8ac  jz      short loc_14006C8BD
0x14006c8ae  mov     rcx, rsi; MemoryDescriptorList
0x14006c8b1  call    cs:__imp_MmUnlockPages
0x14006c8b8  nop     dword ptr [rax+rax+00h]
0x14006c8bd  mov     rcx, rsi; Mdl
0x14006c8c0  call    cs:__imp_IoFreeMdl
0x14006c8c7  nop     dword ptr [rax+rax+00h]
0x14006c8cc  mov     eax, edi
0x14006c8ce  mov     rcx, [rsp+0E8h+var_30]
0x14006c8d6  xor     rcx, rsp; StackCookie
0x14006c8d9  call    __security_check_cookie
0x14006c8de  mov     rsi, [rsp+0E8h+arg_10]
0x14006c8e6  add     rsp, 0C0h
0x14006c8ed  pop     r15
0x14006c8ef  pop     r14
0x14006c8f1  pop     r13
0x14006c8f3  pop     r12
0x14006c8f5  pop     rdi
0x14006c8f6  retn
0x140074813  push    rbp
0x140074815  sub     rsp, 40h
0x140074819  mov     rbp, rdx
0x14007481c  mov     r8, rcx
0x14007481f  lea     r9, [rbp+44h]
0x140074823  mov     edx, 0F98h
0x140074828  lea     rcx, aMinioSocketsWi_2; "minio\\sockets\\winsock2\\wsp\\afdsys\\"...
0x14007482f  call    AfdExceptionFilter
0x140074834  nop
0x140074835  add     rsp, 40h
0x140074839  pop     rbp
0x14007483a  retn
0x14007483c  push    rbp
0x14007483e  sub     rsp, 40h
0x140074842  mov     rbp, rdx
0x140074845  mov     r8, rcx
0x140074848  lea     r9, [rbp+44h]
0x14007484c  mov     edx, 0FB8h
0x140074851  lea     rcx, aMinioSocketsWi_2; "minio\\sockets\\winsock2\\wsp\\afdsys\\"...
0x140074858  call    AfdExceptionFilter
0x14007485d  nop
0x14007485e  add     rsp, 40h
0x140074862  pop     rbp
0x140074863  retn
```
