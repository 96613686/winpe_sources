# BfUpdateHeaderFlagsReverse

- ea: `0x1400063fc`
- end: `0x140006462`
- name: `BfUpdateHeaderFlagsReverse`
- size: `102`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x140001740`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x140006412`
- `ntoskrnl!ExAcquireFastMutex` at `0x140006422`
- `ntoskrnl!ExAcquireFastMutex` at `0x140006412`
- `ntoskrnl!ExAcquireFastMutex` at `0x140006422`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000643a`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000644a`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000643a`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000644a`

## pseudocode

```c
void __fastcall BfUpdateHeaderFlagsReverse(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rdi
  __int64 v4; // rbx
  struct _FAST_MUTEX *v5; // rcx

  v3 = *(_QWORD *)(a1 + 24);
  v4 = *(_QWORD *)(a3 + 24);
  ExAcquireFastMutex(*(PFAST_MUTEX *)(v3 + 48));
  ExAcquireFastMutex(*(PFAST_MUTEX *)(v4 + 48));
  v5 = *(struct _FAST_MUTEX **)(v4 + 48);
  *(_BYTE *)(v4 + 4) |= *(_BYTE *)(v3 + 4) & 0x20;
  ExReleaseFastMutex(v5);
  ExReleaseFastMutex(*(PFAST_MUTEX *)(v3 + 48));
}

```

## disassembly

```asm
0x1400063fc  mov     [rsp+arg_0], rbx
0x140006401  push    rdi
0x140006402  sub     rsp, 20h
0x140006406  mov     rdi, [rcx+18h]
0x14000640a  mov     rbx, [r8+18h]
0x14000640e  mov     rcx, [rdi+30h]; FastMutex
0x140006412  call    cs:__imp_ExAcquireFastMutex
0x140006419  nop     dword ptr [rax+rax+00h]
0x14000641e  mov     rcx, [rbx+30h]; FastMutex
0x140006422  call    cs:__imp_ExAcquireFastMutex
0x140006429  nop     dword ptr [rax+rax+00h]
0x14000642e  mov     al, [rdi+4]
0x140006431  mov     rcx, [rbx+30h]; FastMutex
0x140006435  and     al, 20h
0x140006437  or      [rbx+4], al
0x14000643a  call    cs:__imp_ExReleaseFastMutex
0x140006441  nop     dword ptr [rax+rax+00h]
0x140006446  mov     rcx, [rdi+30h]; FastMutex
0x14000644a  call    cs:__imp_ExReleaseFastMutex
0x140006451  nop     dword ptr [rax+rax+00h]
0x140006456  mov     rbx, [rsp+28h+arg_0]
0x14000645b  add     rsp, 20h
0x14000645f  pop     rdi
0x140006460  retn
```
