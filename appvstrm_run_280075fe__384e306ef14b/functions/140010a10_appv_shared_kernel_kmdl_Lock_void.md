# appv::shared::kernel::kmdl::Lock(void)

- ea: `0x140010a10`
- end: `0x140010b01`
- name: `?Lock@kmdl@kernel@shared@appv@@AEAAJXZ`
- size: `241`
- prototype: `__int64 __fastcall(appv::shared::kernel::kmdl *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140010270`
- `0x1400105d8`

## callees

- `0x140010a10`

## import_xrefs

- `ntoskrnl!MmProbeAndLockPages` at `0x140010aa6`
- `ntoskrnl!MmProbeAndLockPages` at `0x140010aa6`
- `ntoskrnl!IoAllocateMdl` at `0x140010a7c`
- `ntoskrnl!IoAllocateMdl` at `0x140010a7c`
- `ntoskrnl!IoGetCurrentProcess` at `0x140010a35`
- `ntoskrnl!IoGetCurrentProcess` at `0x140010a35`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140010ada`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140010ada`
- `ntoskrnl!ObfReferenceObject` at `0x140010a48`
- `ntoskrnl!ObfReferenceObject` at `0x140010a48`

## pseudocode

```c
__int64 __fastcall appv::shared::kernel::kmdl::Lock(appv::shared::kernel::kmdl *this)
{
  PEPROCESS CurrentProcess; // rax
  struct _MDL *Mdl; // rax
  void *v5; // rcx
  PVOID v6; // rax

  if ( !*((_QWORD *)this + 3) && !*((_QWORD *)this + 4) )
    return 3221225701LL;
  CurrentProcess = IoGetCurrentProcess();
  *((_QWORD *)this + 7) = CurrentProcess;
  ObfReferenceObject(CurrentProcess);
  Mdl = (struct _MDL *)*((_QWORD *)this + 1);
  if ( !Mdl )
  {
    v5 = (void *)*((_QWORD *)this + 3);
    if ( !v5 )
      v5 = (void *)*((_QWORD *)this + 4);
    Mdl = IoAllocateMdl(v5, *((_DWORD *)this + 12), 0, 0, 0);
    *((_QWORD *)this + 1) = Mdl;
    if ( !Mdl )
      return 3221225626LL;
  }
  if ( !*(_BYTE *)this )
  {
    MmProbeAndLockPages(Mdl, 0, IoWriteAccess);
    *(_BYTE *)this = 1;
  }
  if ( *((_QWORD *)this + 2) )
    return 0;
  v6 = MmMapLockedPagesSpecifyCache(*((PMDL *)this + 1), 1, MmCached, 0, 0, 0x10u);
  *((_QWORD *)this + 2) = v6;
  if ( v6 )
    return 0;
  else
    return 3221225626LL;
}

```

## disassembly

```asm
0x140010a10  push    rbx
0x140010a12  sub     rsp, 30h
0x140010a16  mov     rbx, rcx
0x140010a19  mov     rax, [rcx+18h]
0x140010a1d  test    rax, rax
0x140010a20  jnz     short loc_140010A35
0x140010a22  mov     rax, [rcx+20h]
0x140010a26  test    rax, rax
0x140010a29  jnz     short loc_140010A35
0x140010a2b  mov     eax, 0C00000E5h
0x140010a30  jmp     loc_140010AFA
0x140010a35  call    cs:__imp_IoGetCurrentProcess
0x140010a3c  nop     dword ptr [rax+rax+00h]
0x140010a41  mov     [rbx+38h], rax
0x140010a45  mov     rcx, rax; Object
0x140010a48  call    cs:__imp_ObfReferenceObject
0x140010a4f  nop     dword ptr [rax+rax+00h]
0x140010a54  mov     rax, [rbx+8]
0x140010a58  test    rax, rax
0x140010a5b  jnz     short loc_140010A98
0x140010a5d  mov     edx, [rbx+30h]; Length
0x140010a60  mov     rcx, [rbx+18h]
0x140010a64  test    rcx, rcx
0x140010a67  jnz     short loc_140010A6D
0x140010a69  mov     rcx, [rbx+20h]; VirtualAddress
0x140010a6d  mov     [rsp+38h+Irp], 0; Irp
0x140010a76  xor     r9d, r9d; ChargeQuota
0x140010a79  xor     r8d, r8d; SecondaryBuffer
0x140010a7c  call    cs:__imp_IoAllocateMdl
0x140010a83  nop     dword ptr [rax+rax+00h]
0x140010a88  mov     [rbx+8], rax
0x140010a8c  test    rax, rax
0x140010a8f  jnz     short loc_140010A98
0x140010a91  mov     eax, 0C000009Ah
0x140010a96  jmp     short loc_140010AFA
0x140010a98  cmp     byte ptr [rbx], 0
0x140010a9b  jnz     short loc_140010AB5
0x140010a9d  xor     edx, edx; AccessMode
0x140010a9f  lea     r8d, [rdx+1]; Operation
0x140010aa3  mov     rcx, rax; MemoryDescriptorList
0x140010aa6  call    cs:__imp_MmProbeAndLockPages
0x140010aad  nop     dword ptr [rax+rax+00h]
0x140010ab2  mov     byte ptr [rbx], 1
0x140010ab5  cmp     qword ptr [rbx+10h], 0
0x140010aba  jnz     short loc_140010AF6
0x140010abc  mov     [rsp+38h+Priority], 10h; Priority
0x140010ac4  mov     dword ptr [rsp+38h+Irp], 0; BugCheckOnFailure
0x140010acc  xor     r9d, r9d; RequestedAddress
0x140010acf  lea     r8d, [r9+1]; CacheType
0x140010ad3  mov     dl, r8b; AccessMode
0x140010ad6  mov     rcx, [rbx+8]; MemoryDescriptorList
0x140010ada  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140010ae1  nop     dword ptr [rax+rax+00h]
0x140010ae6  mov     [rbx+10h], rax
0x140010aea  test    rax, rax
0x140010aed  jnz     short loc_140010AF6
0x140010aef  mov     eax, 0C000009Ah
0x140010af4  jmp     short loc_140010AFA
0x140010af6  xor     eax, eax
0x140010af8  jmp     short $+2
0x140010afa  add     rsp, 30h
0x140010afe  pop     rbx
0x140010aff  retn
```
