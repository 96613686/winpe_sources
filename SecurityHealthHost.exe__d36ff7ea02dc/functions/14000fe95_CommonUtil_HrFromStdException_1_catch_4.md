# _CommonUtil::HrFromStdException_::_1_::catch$4

- ea: `0x14000fe95`
- end: `0x14000feba`
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
0x14000fe95  mov     [rsp+arg_8], rdx
0x14000fe9a  push    rbp
0x14000fe9b  sub     rsp, 20h
0x14000fe9f  mov     rbp, rdx
0x14000fea2  mov     dword ptr [rbp+60h], 80004005h
0x14000fea9  mov     rax, 0
0x14000feb3  add     rsp, 20h
0x14000feb7  pop     rbp
0x14000feb8  retn
```
