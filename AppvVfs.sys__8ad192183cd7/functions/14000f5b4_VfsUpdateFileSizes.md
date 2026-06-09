# VfsUpdateFileSizes

- ea: `0x14000f5b4`
- end: `0x14000f62a`
- name: `VfsUpdateFileSizes`
- size: `118`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x14000aa20`
- `0x14000b1d0`
- `0x14000f188`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x14000f602`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000f612`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000f602`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000f612`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000f5ca`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000f5da`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000f5ca`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000f5da`

## pseudocode

```c
void __fastcall VfsUpdateFileSizes(__int64 a1, __int64 a2)
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
0x14000f5b4  mov     [rsp+arg_0], rbx
0x14000f5b9  push    rdi
0x14000f5ba  sub     rsp, 20h
0x14000f5be  mov     rdi, [rdx+18h]
0x14000f5c2  mov     rbx, [rcx+18h]
0x14000f5c6  mov     rcx, [rdi+30h]; FastMutex
0x14000f5ca  call    cs:__imp_ExAcquireFastMutex
0x14000f5d1  nop     dword ptr [rax+rax+00h]
0x14000f5d6  mov     rcx, [rbx+30h]; FastMutex
0x14000f5da  call    cs:__imp_ExAcquireFastMutex
0x14000f5e1  nop     dword ptr [rax+rax+00h]
0x14000f5e6  mov     rax, [rbx+18h]
0x14000f5ea  mov     [rdi+18h], rax
0x14000f5ee  mov     rax, [rbx+20h]
0x14000f5f2  mov     [rdi+20h], rax
0x14000f5f6  mov     rax, [rbx+28h]
0x14000f5fa  mov     [rdi+28h], rax
0x14000f5fe  mov     rcx, [rbx+30h]; FastMutex
0x14000f602  call    cs:__imp_ExReleaseFastMutex
0x14000f609  nop     dword ptr [rax+rax+00h]
0x14000f60e  mov     rcx, [rdi+30h]; FastMutex
0x14000f612  call    cs:__imp_ExReleaseFastMutex
0x14000f619  nop     dword ptr [rax+rax+00h]
0x14000f61e  mov     rbx, [rsp+28h+arg_0]
0x14000f623  add     rsp, 20h
0x14000f627  pop     rdi
0x14000f628  retn
```
