# _CILogWrite::Append_::_1_::catch$0

- ea: `0x18001312c`
- end: `0x18001315a`
- name: `_CILogWrite::Append_::_1_::catch$0`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall CILogWrite::Append_::_1_::catch_0(__int64 a1, _DWORD *a2)
{
  a2[18] = a2[26];
  a2[50] = 0;
  return 0;
}

```

## disassembly

```asm
0x18001312c  mov     [rsp+arg_8], rdx
0x180013131  push    rbp
0x180013132  sub     rsp, 40h
0x180013136  mov     rbp, rdx
0x180013139  mov     eax, [rbp+68h]
0x18001313c  mov     [rbp+48h], eax
0x18001313f  mov     dword ptr [rbp+0C8h], 0
0x180013149  mov     rax, 0
0x180013153  add     rsp, 40h
0x180013157  pop     rbp
0x180013158  retn
```
