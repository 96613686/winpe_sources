# BfInitializeMappingContext

- ea: `0x140003098`
- end: `0x1400030f6`
- name: `BfInitializeMappingContext`
- size: `94`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140003074`
- `0x140012570`
- `0x140022950`

## callees

- `0x140003098`

## import_xrefs

- `ntoskrnl!ExInitializeResourceLite` at `0x1400030d2`
- `ntoskrnl!ExInitializeResourceLite` at `0x1400030d2`
- `ntoskrnl!ExAllocatePool2` at `0x1400030b3`
- `ntoskrnl!ExAllocatePool2` at `0x1400030b3`

## pseudocode

```c
__int64 __fastcall BfInitializeMappingContext(__int64 *a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 Pool2; // rax
  __int64 v6; // rbx
  __int64 result; // rax

  Pool2 = ExAllocatePool2(64, 120, 1668105794, a4);
  v6 = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  *(_QWORD *)(Pool2 + 8) = Pool2;
  *(_QWORD *)Pool2 = Pool2;
  ExInitializeResourceLite((PERESOURCE)(Pool2 + 16));
  result = 0;
  *a1 = v6;
  return result;
}

```

## disassembly

```asm
0x140003098  mov     [rsp+arg_0], rbx
0x14000309d  push    rdi
0x14000309e  sub     rsp, 20h
0x1400030a2  mov     edx, 78h ; 'x'
0x1400030a7  mov     rdi, rcx
0x1400030aa  mov     r8d, 636D4642h
0x1400030b0  lea     ecx, [rdx-38h]
0x1400030b3  call    cs:__imp_ExAllocatePool2
0x1400030ba  nop     dword ptr [rax+rax+00h]
0x1400030bf  mov     rbx, rax
0x1400030c2  test    rax, rax
0x1400030c5  jz      short loc_1400030EF
0x1400030c7  lea     rcx, [rax+10h]; Resource
0x1400030cb  mov     [rax+8], rax
0x1400030cf  mov     [rax], rax
0x1400030d2  call    cs:__imp_ExInitializeResourceLite
0x1400030d9  nop     dword ptr [rax+rax+00h]
0x1400030de  xor     eax, eax
0x1400030e0  mov     [rdi], rbx
0x1400030e3  mov     rbx, [rsp+28h+arg_0]
0x1400030e8  add     rsp, 20h
0x1400030ec  pop     rdi
0x1400030ed  retn
0x1400030ef  mov     eax, 0C000009Ah
0x1400030f4  jmp     short loc_1400030E3
```
