# NormDelete

- ea: `0x180080740`
- end: `0x180080775`
- name: `NormDelete`
- size: `53`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x18000b1b0`
- `0x180080740`

## pseudocode

```c
void __fastcall NormDelete(_QWORD *Block)
{
  void *v2; // rcx
  void *v3; // rcx

  v2 = (void *)Block[1];
  if ( v2 )
    operator delete(v2);
  v3 = (void *)Block[16];
  if ( v3 )
    operator delete(v3);
  operator delete(Block);
}

```

## disassembly

```asm
0x180080740  push    rbx
0x180080742  sub     rsp, 20h
0x180080746  mov     rbx, rcx
0x180080749  mov     rcx, [rcx+8]; Block
0x18008074d  test    rcx, rcx
0x180080750  jz      short loc_180080757
0x180080752  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180080757  mov     rcx, [rbx+80h]; Block
0x18008075e  test    rcx, rcx
0x180080761  jz      short loc_180080768
0x180080763  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180080768  mov     rcx, rbx; Block
0x18008076b  add     rsp, 20h
0x18008076f  pop     rbx
0x180080770  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
