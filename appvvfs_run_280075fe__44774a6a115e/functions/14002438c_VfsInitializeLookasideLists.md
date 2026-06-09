# VfsInitializeLookasideLists

- ea: `0x14002438c`
- end: `0x1400245fc`
- name: `VfsInitializeLookasideLists`
- size: `624`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x140008100`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140024482`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140024482`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400243b9`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400243ec`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140024420`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140024453`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400244b6`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400244e5`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140024518`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14002454b`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14002457e`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400245b1`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400245e4`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400243b9`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400243ec`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140024420`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140024453`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400244b6`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400244e5`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140024518`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14002454b`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14002457e`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400245b1`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400245e4`

## pseudocode

```c
void __fastcall VfsInitializeLookasideLists(__int64 a1)
{
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)a1, 0, 0, 0, 0x60u, 0x63504656u, 0);
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)(a1 + 128), 0, 0, 0, 0x110u, 0x63554656u, 0);
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)(a1 + 256), 0, 0, 0, 0xA0u, 0x74534656u, 0);
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)(a1 + 384), 0, 0, 0, 0x198u, 0x62534656u, 0);
  ExInitializeNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 512), 0, 0, 0, 0xA0u, 0x6E534656u, 0);
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)(a1 + 640), 0, 0, 0, 0x88u, 0x62434656u, 0);
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)(a1 + 768), 0, 0, 0, 0x88u, 0x72434656u, 0);
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)(a1 + 896), 0, 0, 0, 0x18u, 0x6C434656u, 0);
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)(a1 + 1024), 0, 0, 0, 8u, 0x6E4E4656u, 0);
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)(a1 + 1152), 0, 0, 0, 0x38u, 0x71444656u, 0);
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)(a1 + 1280), 0, 0, 0, 0x78u, 0x73444656u, 0);
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)(a1 + 1408), 0, 0, 0, 0x28u, 0x704D4656u, 0);
}

```

## disassembly

```asm
0x14002438c  mov     [rsp+arg_0], rbx
0x140024391  push    rdi
0x140024392  sub     rsp, 40h
0x140024396  xor     eax, eax
0x140024398  xor     r9d, r9d; Flags
0x14002439b  mov     [rsp+48h+Depth], ax; Depth
0x1400243a0  xor     r8d, r8d; Free
0x1400243a3  mov     [rsp+48h+Tag], 63504656h; Tag
0x1400243ab  xor     edx, edx; Allocate
0x1400243ad  mov     [rsp+48h+Size], 60h ; '`'; Size
0x1400243b6  mov     rbx, rcx
0x1400243b9  call    cs:__imp_ExInitializePagedLookasideList
0x1400243c0  nop     dword ptr [rax+rax+00h]
0x1400243c5  xor     eax, eax
0x1400243c7  lea     rcx, [rbx+80h]; Lookaside
0x1400243ce  mov     [rsp+48h+Depth], ax; Depth
0x1400243d3  xor     r9d, r9d; Flags
0x1400243d6  mov     [rsp+48h+Tag], 63554656h; Tag
0x1400243de  xor     r8d, r8d; Free
0x1400243e1  xor     edx, edx; Allocate
0x1400243e3  mov     [rsp+48h+Size], 110h; Size
0x1400243ec  call    cs:__imp_ExInitializePagedLookasideList
0x1400243f3  nop     dword ptr [rax+rax+00h]
0x1400243f8  xor     eax, eax
0x1400243fa  lea     rcx, [rbx+100h]; Lookaside
0x140024401  mov     [rsp+48h+Depth], ax; Depth
0x140024406  mov     edi, 0A0h
0x14002440b  mov     [rsp+48h+Tag], 74534656h; Tag
0x140024413  xor     r9d, r9d; Flags
0x140024416  xor     r8d, r8d; Free
0x140024419  mov     [rsp+48h+Size], rdi; Size
0x14002441e  xor     edx, edx; Allocate
0x140024420  call    cs:__imp_ExInitializePagedLookasideList
0x140024427  nop     dword ptr [rax+rax+00h]
0x14002442c  xor     eax, eax
0x14002442e  lea     rcx, [rbx+180h]; Lookaside
0x140024435  mov     [rsp+48h+Depth], ax; Depth
0x14002443a  xor     r9d, r9d; Flags
0x14002443d  mov     [rsp+48h+Tag], 62534656h; Tag
0x140024445  xor     r8d, r8d; Free
0x140024448  xor     edx, edx; Allocate
0x14002444a  mov     [rsp+48h+Size], 198h; Size
0x140024453  call    cs:__imp_ExInitializePagedLookasideList
0x14002445a  nop     dword ptr [rax+rax+00h]
0x14002445f  xor     eax, eax
0x140024461  lea     rcx, [rbx+200h]; Lookaside
0x140024468  mov     [rsp+48h+Depth], ax; Depth
0x14002446d  xor     r9d, r9d; Flags
0x140024470  mov     [rsp+48h+Tag], 6E534656h; Tag
0x140024478  xor     r8d, r8d; Free
0x14002447b  xor     edx, edx; Allocate
0x14002447d  mov     [rsp+48h+Size], rdi; Size
0x140024482  call    cs:__imp_ExInitializeNPagedLookasideList
0x140024489  nop     dword ptr [rax+rax+00h]
0x14002448e  xor     eax, eax
0x140024490  lea     rcx, [rbx+280h]; Lookaside
0x140024497  mov     [rsp+48h+Depth], ax; Depth
0x14002449c  mov     edi, 88h
0x1400244a1  mov     [rsp+48h+Tag], 62434656h; Tag
0x1400244a9  xor     r9d, r9d; Flags
0x1400244ac  xor     r8d, r8d; Free
0x1400244af  mov     [rsp+48h+Size], rdi; Size
0x1400244b4  xor     edx, edx; Allocate
0x1400244b6  call    cs:__imp_ExInitializePagedLookasideList
0x1400244bd  nop     dword ptr [rax+rax+00h]
0x1400244c2  xor     eax, eax
0x1400244c4  lea     rcx, [rbx+300h]; Lookaside
0x1400244cb  mov     [rsp+48h+Depth], ax; Depth
0x1400244d0  xor     r9d, r9d; Flags
0x1400244d3  mov     [rsp+48h+Tag], 72434656h; Tag
0x1400244db  xor     r8d, r8d; Free
0x1400244de  xor     edx, edx; Allocate
0x1400244e0  mov     [rsp+48h+Size], rdi; Size
0x1400244e5  call    cs:__imp_ExInitializePagedLookasideList
0x1400244ec  nop     dword ptr [rax+rax+00h]
0x1400244f1  xor     eax, eax
0x1400244f3  lea     rcx, [rbx+380h]; Lookaside
0x1400244fa  mov     [rsp+48h+Depth], ax; Depth
0x1400244ff  xor     r9d, r9d; Flags
0x140024502  mov     [rsp+48h+Tag], 6C434656h; Tag
0x14002450a  xor     r8d, r8d; Free
0x14002450d  xor     edx, edx; Allocate
0x14002450f  mov     [rsp+48h+Size], 18h; Size
0x140024518  call    cs:__imp_ExInitializePagedLookasideList
0x14002451f  nop     dword ptr [rax+rax+00h]
0x140024524  xor     eax, eax
0x140024526  lea     rcx, [rbx+400h]; Lookaside
0x14002452d  mov     [rsp+48h+Depth], ax; Depth
0x140024532  xor     r9d, r9d; Flags
0x140024535  mov     [rsp+48h+Tag], 6E4E4656h; Tag
0x14002453d  xor     r8d, r8d; Free
0x140024540  mov     [rsp+48h+Size], 8; Size
0x140024549  xor     edx, edx; Allocate
0x14002454b  call    cs:__imp_ExInitializePagedLookasideList
0x140024552  nop     dword ptr [rax+rax+00h]
0x140024557  xor     eax, eax
0x140024559  lea     rcx, [rbx+480h]; Lookaside
0x140024560  mov     [rsp+48h+Depth], ax; Depth
0x140024565  xor     r9d, r9d; Flags
0x140024568  mov     [rsp+48h+Tag], 71444656h; Tag
0x140024570  xor     r8d, r8d; Free
0x140024573  xor     edx, edx; Allocate
0x140024575  mov     [rsp+48h+Size], 38h ; '8'; Size
0x14002457e  call    cs:__imp_ExInitializePagedLookasideList
0x140024585  nop     dword ptr [rax+rax+00h]
0x14002458a  xor     eax, eax
0x14002458c  lea     rcx, [rbx+500h]; Lookaside
0x140024593  mov     [rsp+48h+Depth], ax; Depth
0x140024598  xor     r9d, r9d; Flags
0x14002459b  mov     [rsp+48h+Tag], 73444656h; Tag
0x1400245a3  xor     r8d, r8d; Free
0x1400245a6  xor     edx, edx; Allocate
0x1400245a8  mov     [rsp+48h+Size], 78h ; 'x'; Size
0x1400245b1  call    cs:__imp_ExInitializePagedLookasideList
0x1400245b8  nop     dword ptr [rax+rax+00h]
0x1400245bd  xor     eax, eax
0x1400245bf  lea     rcx, [rbx+580h]; Lookaside
0x1400245c6  mov     [rsp+48h+Depth], ax; Depth
0x1400245cb  xor     r9d, r9d; Flags
0x1400245ce  mov     [rsp+48h+Tag], 704D4656h; Tag
0x1400245d6  xor     r8d, r8d; Free
0x1400245d9  xor     edx, edx; Allocate
0x1400245db  mov     [rsp+48h+Size], 28h ; '('; Size
0x1400245e4  call    cs:__imp_ExInitializePagedLookasideList
0x1400245eb  nop     dword ptr [rax+rax+00h]
0x1400245f0  mov     rbx, [rsp+48h+arg_0]
0x1400245f5  add     rsp, 40h
0x1400245f9  pop     rdi
0x1400245fa  retn
```
