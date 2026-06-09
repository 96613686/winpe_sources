# _CILogWrite::Append_::_1_::catch$1

- ea: `0x180013160`
- end: `0x18001318e`
- name: `_CILogWrite::Append_::_1_::catch$1`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall CILogWrite::Append_::_1_::catch_1(__int64 a1, _DWORD *a2)
{
  a2[18] = a2[27];
  a2[50] = 0;
  return 0;
}

```

## disassembly

```asm
0x180013160  mov     [rsp+arg_8], rdx
0x180013165  push    rbp
0x180013166  sub     rsp, 40h
0x18001316a  mov     rbp, rdx
0x18001316d  mov     eax, [rbp+6Ch]
0x180013170  mov     [rbp+48h], eax
0x180013173  mov     dword ptr [rbp+0C8h], 0
0x18001317d  mov     rax, 0
0x180013187  add     rsp, 40h
0x18001318b  pop     rbp
0x18001318c  retn
```
