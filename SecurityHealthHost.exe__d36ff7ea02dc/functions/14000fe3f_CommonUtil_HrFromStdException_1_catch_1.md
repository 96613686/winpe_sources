# _CommonUtil::HrFromStdException_::_1_::catch$1

- ea: `0x14000fe3f`
- end: `0x14000fe64`
- name: `_CommonUtil::HrFromStdException_::_1_::catch$1`
- size: `37`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CommonUtil::HrFromStdException_::_1_::catch_1(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 96) = -2147024882;
  return 0;
}

```

## disassembly

```asm
0x14000fe3f  mov     [rsp+arg_8], rdx
0x14000fe44  push    rbp
0x14000fe45  sub     rsp, 20h
0x14000fe49  mov     rbp, rdx
0x14000fe4c  mov     dword ptr [rbp+60h], 8007000Eh
0x14000fe53  mov     rax, 0
0x14000fe5d  add     rsp, 20h
0x14000fe61  pop     rbp
0x14000fe62  retn
```
