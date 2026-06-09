# __std_exception_destroy

- ea: `0x180008a4c`
- end: `0x180008a74`
- name: `__std_exception_destroy`
- size: `40`
- prototype: `void __fastcall(__int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180001110`
- `0x180001190`
- `0x180003690`
- `0x180003780`

## callees

- `0x180008a4c`
- `0x18000b604`

## pseudocode

```c
void __fastcall _std_exception_destroy(__int64 a1)
{
  if ( *(_BYTE *)(a1 + 8) )
    free_0(*(void **)a1);
  *(_BYTE *)(a1 + 8) = 0;
  *(_QWORD *)a1 = 0;
}

```

## disassembly

```asm
0x180008a4c  push    rbx
0x180008a4e  sub     rsp, 20h
0x180008a52  cmp     byte ptr [rcx+8], 0
0x180008a56  mov     rbx, rcx
0x180008a59  jz      short loc_180008A63
0x180008a5b  mov     rcx, [rcx]; Block
0x180008a5e  call    free_0
0x180008a63  mov     byte ptr [rbx+8], 0
0x180008a67  mov     qword ptr [rbx], 0
0x180008a6e  add     rsp, 20h
0x180008a72  pop     rbx
0x180008a73  retn
```
