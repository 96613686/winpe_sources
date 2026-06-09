# _CommonUtil::HrFromStdException_::_1_::catch$3

- ea: `0x140012547`
- end: `0x14001256c`
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
0x140012547  mov     [rsp+arg_8], rdx
0x14001254c  push    rbp
0x14001254d  sub     rsp, 20h
0x140012551  mov     rbp, rdx
0x140012554  mov     dword ptr [rbp+60h], 80070585h
0x14001255b  mov     rax, 0
0x140012565  add     rsp, 20h
0x140012569  pop     rbp
0x14001256a  retn
```
