# _CommonUtil::HrFromStdException_::_1_::catch$4

- ea: `0x140012572`
- end: `0x140012597`
- name: `_CommonUtil::HrFromStdException_::_1_::catch$4`
- size: `37`
- prototype: `__int64 __fastcall(__int64, __int64)`
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
0x140012572  mov     [rsp+arg_8], rdx
0x140012577  push    rbp
0x140012578  sub     rsp, 20h
0x14001257c  mov     rbp, rdx
0x14001257f  mov     dword ptr [rbp+60h], 80004005h
0x140012586  mov     rax, 0
0x140012590  add     rsp, 20h
0x140012594  pop     rbp
0x140012595  retn
```
