# BfFreeEnumerationConflictList

- ea: `0x1400232a0`
- end: `0x1400232ea`
- name: `BfFreeEnumerationConflictList`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140024a64`

## callees

- `0x1400232a0`

## import_xrefs

- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400232dc`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400232dc`

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
0x1400232a0  push    rbx
0x1400232a2  sub     rsp, 20h
0x1400232a6  mov     rbx, rcx
0x1400232a9  cmp     [rbx], rbx
0x1400232ac  jz      short loc_1400232C7
0x1400232ae  mov     rdx, [rbx+8]; Entry
0x1400232b2  cmp     [rdx], rbx
0x1400232b5  jnz     short loc_1400232C0
0x1400232b7  mov     rax, [rdx+8]
0x1400232bb  cmp     [rax], rdx
0x1400232be  jz      short loc_1400232CE
0x1400232c0  mov     ecx, 3
0x1400232c5  int     29h; Win8: RtlFailFast(ecx)
0x1400232c7  add     rsp, 20h
0x1400232cb  pop     rbx
0x1400232cc  retn
0x1400232ce  mov     [rbx+8], rax
0x1400232d2  lea     rcx, stru_14000B500; Lookaside
0x1400232d9  mov     [rax], rbx
0x1400232dc  call    cs:__imp_ExFreeToPagedLookasideList
0x1400232e3  nop     dword ptr [rax+rax+00h]
0x1400232e8  jmp     short loc_1400232A9
```
