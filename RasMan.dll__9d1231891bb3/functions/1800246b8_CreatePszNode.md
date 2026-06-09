# CreatePszNode

- ea: `0x1800246b8`
- end: `0x1800246ee`
- name: `CreatePszNode`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180025d98`

## callees

- `0x1800246b8`
- `0x180025040`
- `0x180026058`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800246e0`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800246e0`

## pseudocode

```c
_QWORD *__fastcall CreatePszNode(const wchar_t *a1)
{
  wchar_t *v1; // rbx
  _QWORD *result; // rax

  v1 = StrDup(a1);
  if ( v1 )
  {
    result = DtlCreateSizedNode(0);
    if ( result )
    {
      result[2] = v1;
      return result;
    }
    GlobalFree(v1);
  }
  return 0;
}

```

## disassembly

```asm
0x1800246b8  push    rbx
0x1800246ba  sub     rsp, 20h
0x1800246be  call    StrDup
0x1800246c3  mov     rbx, rax
0x1800246c6  test    rax, rax
0x1800246c9  jz      short loc_1800246E6
0x1800246cb  xor     ecx, ecx
0x1800246cd  call    DtlCreateSizedNode
0x1800246d2  test    rax, rax
0x1800246d5  jz      short loc_1800246DD
0x1800246d7  mov     [rax+10h], rbx
0x1800246db  jmp     short loc_1800246E8
0x1800246dd  mov     rcx, rbx; hMem
0x1800246e0  call    cs:__imp_GlobalFree
0x1800246e6  xor     eax, eax
0x1800246e8  add     rsp, 20h
0x1800246ec  pop     rbx
0x1800246ed  retn
```
