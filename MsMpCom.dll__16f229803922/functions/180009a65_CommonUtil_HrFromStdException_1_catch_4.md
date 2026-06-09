# _CommonUtil::HrFromStdException_::_1_::catch$4

- ea: `0x180009a65`
- end: `0x180009a8a`
- name: `_CommonUtil::HrFromStdException_::_1_::catch$4`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CommonUtil::HrFromStdException_::_1_::catch_4(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 96) = -2147467259;
  return 0;
}

```

## disassembly

```asm
0x180009a65  mov     [rsp+arg_8], rdx
0x180009a6a  push    rbp
0x180009a6b  sub     rsp, 20h
0x180009a6f  mov     rbp, rdx
0x180009a72  mov     dword ptr [rbp+60h], 80004005h
0x180009a79  mov     rax, 0
0x180009a83  add     rsp, 20h
0x180009a87  pop     rbp
0x180009a88  retn
```
