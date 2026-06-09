# _CommonUtil::HrFromStdException_::_1_::catch$1

- ea: `0x180009a0f`
- end: `0x180009a34`
- name: `_CommonUtil::HrFromStdException_::_1_::catch$1`
- size: `37`
- prototype: ``
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
0x180009a0f  mov     [rsp+arg_8], rdx
0x180009a14  push    rbp
0x180009a15  sub     rsp, 20h
0x180009a19  mov     rbp, rdx
0x180009a1c  mov     dword ptr [rbp+60h], 8007000Eh
0x180009a23  mov     rax, 0
0x180009a2d  add     rsp, 20h
0x180009a31  pop     rbp
0x180009a32  retn
```
