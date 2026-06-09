# BfUpdateFileSizes

- ea: `0x140006380`
- end: `0x1400063f6`
- name: `BfUpdateFileSizes`
- size: `118`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x140001500`
- `0x140006360`
- `0x1400157a0`
- `0x140023be0`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x140006396`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400063a6`
- `ntoskrnl!ExAcquireFastMutex` at `0x140006396`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400063a6`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400063ce`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400063de`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400063ce`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400063de`

## pseudocode

```c
void __fastcall BfUpdateFileSizes(__int64 a1, __int64 a2)
{
  __int64 v2; // rdi
  __int64 v3; // rbx

  v2 = *(_QWORD *)(a2 + 24);
  v3 = *(_QWORD *)(a1 + 24);
  ExAcquireFastMutex(*(PFAST_MUTEX *)(v2 + 48));
  ExAcquireFastMutex(*(PFAST_MUTEX *)(v3 + 48));
  *(_QWORD *)(v2 + 24) = *(_QWORD *)(v3 + 24);
  *(_QWORD *)(v2 + 32) = *(_QWORD *)(v3 + 32);
  *(_QWORD *)(v2 + 40) = *(_QWORD *)(v3 + 40);
  ExReleaseFastMutex(*(PFAST_MUTEX *)(v3 + 48));
  ExReleaseFastMutex(*(PFAST_MUTEX *)(v2 + 48));
}

```

## disassembly

```asm
0x140006380  mov     [rsp+arg_0], rbx
0x140006385  push    rdi
0x140006386  sub     rsp, 20h
0x14000638a  mov     rdi, [rdx+18h]
0x14000638e  mov     rbx, [rcx+18h]
0x140006392  mov     rcx, [rdi+30h]; FastMutex
0x140006396  call    cs:__imp_ExAcquireFastMutex
0x14000639d  nop     dword ptr [rax+rax+00h]
0x1400063a2  mov     rcx, [rbx+30h]; FastMutex
0x1400063a6  call    cs:__imp_ExAcquireFastMutex
0x1400063ad  nop     dword ptr [rax+rax+00h]
0x1400063b2  mov     rax, [rbx+18h]
0x1400063b6  mov     [rdi+18h], rax
0x1400063ba  mov     rax, [rbx+20h]
0x1400063be  mov     [rdi+20h], rax
0x1400063c2  mov     rax, [rbx+28h]
0x1400063c6  mov     [rdi+28h], rax
0x1400063ca  mov     rcx, [rbx+30h]; FastMutex
0x1400063ce  call    cs:__imp_ExReleaseFastMutex
0x1400063d5  nop     dword ptr [rax+rax+00h]
0x1400063da  mov     rcx, [rdi+30h]; FastMutex
0x1400063de  call    cs:__imp_ExReleaseFastMutex
0x1400063e5  nop     dword ptr [rax+rax+00h]
0x1400063ea  mov     rbx, [rsp+28h+arg_0]
0x1400063ef  add     rsp, 20h
0x1400063f3  pop     rdi
0x1400063f4  retn
```
