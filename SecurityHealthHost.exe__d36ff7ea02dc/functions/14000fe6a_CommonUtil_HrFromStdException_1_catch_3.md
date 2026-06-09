# _CommonUtil::HrFromStdException_::_1_::catch$3

- ea: `0x14000fe6a`
- end: `0x14000fe8f`
- name: `_CommonUtil::HrFromStdException_::_1_::catch$3`
- size: `37`
- prototype: `__int64 __fastcall(__int64, __int64)`
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
0x14000fe6a  mov     [rsp+arg_8], rdx
0x14000fe6f  push    rbp
0x14000fe70  sub     rsp, 20h
0x14000fe74  mov     rbp, rdx
0x14000fe77  mov     dword ptr [rbp+60h], 80070585h
0x14000fe7e  mov     rax, 0
0x14000fe88  add     rsp, 20h
0x14000fe8c  pop     rbp
0x14000fe8d  retn
```
