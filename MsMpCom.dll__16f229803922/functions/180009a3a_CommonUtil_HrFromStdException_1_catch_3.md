# _CommonUtil::HrFromStdException_::_1_::catch$3

- ea: `0x180009a3a`
- end: `0x180009a5f`
- name: `_CommonUtil::HrFromStdException_::_1_::catch$3`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CommonUtil::HrFromStdException_::_1_::catch_3(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 96) = -2147023483;
  return 0;
}

```

## disassembly

```asm
0x180009a3a  mov     [rsp+arg_8], rdx
0x180009a3f  push    rbp
0x180009a40  sub     rsp, 20h
0x180009a44  mov     rbp, rdx
0x180009a47  mov     dword ptr [rbp+60h], 80070585h
0x180009a4e  mov     rax, 0
0x180009a58  add     rsp, 20h
0x180009a5c  pop     rbp
0x180009a5d  retn
```
