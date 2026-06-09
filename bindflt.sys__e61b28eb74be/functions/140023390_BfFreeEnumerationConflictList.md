# BfFreeEnumerationConflictList

- ea: `0x140023390`
- end: `0x1400233da`
- name: `BfFreeEnumerationConflictList`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140024a58`

## callees

- `0x140023390`

## import_xrefs

- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400233cc`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400233cc`

## pseudocode

```c
void __fastcall BfFreeEnumerationConflictList(_QWORD *a1)
{
  _QWORD *v2; // rdx
  _QWORD *v3; // rax

  while ( (_QWORD *)*a1 != a1 )
  {
    v2 = (_QWORD *)a1[1];
    if ( (_QWORD *)*v2 != a1 || (v3 = (_QWORD *)v2[1], (_QWORD *)*v3 != v2) )
      __fastfail(3u);
    a1[1] = v3;
    *v3 = a1;
    ExFreeToPagedLookasideList(&stru_14000B500, v2);
  }
}

```

## disassembly

```asm
0x140023390  push    rbx
0x140023392  sub     rsp, 20h
0x140023396  mov     rbx, rcx
0x140023399  cmp     [rbx], rbx
0x14002339c  jz      short loc_1400233B7
0x14002339e  mov     rdx, [rbx+8]; Entry
0x1400233a2  cmp     [rdx], rbx
0x1400233a5  jnz     short loc_1400233B0
0x1400233a7  mov     rax, [rdx+8]
0x1400233ab  cmp     [rax], rdx
0x1400233ae  jz      short loc_1400233BE
0x1400233b0  mov     ecx, 3
0x1400233b5  int     29h; Win8: RtlFailFast(ecx)
0x1400233b7  add     rsp, 20h
0x1400233bb  pop     rbx
0x1400233bc  retn
0x1400233be  mov     [rbx+8], rax
0x1400233c2  lea     rcx, stru_14000B500; Lookaside
0x1400233c9  mov     [rax], rbx
0x1400233cc  call    cs:__imp_ExFreeToPagedLookasideList
0x1400233d3  nop     dword ptr [rax+rax+00h]
0x1400233d8  jmp     short loc_140023399
```
