# _Windows::CopyFromPairWstringToLpolestr::copy_::_1_::catch$6

- ea: `0x14001244d`
- end: `0x140012472`
- name: `_Windows::CopyFromPairWstringToLpolestr::copy_::_1_::catch$6`
- size: `37`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall Windows::CopyFromPairWstringToLpolestr::copy_::_1_::catch_6(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 32) = -2147024882;
  return 0;
}

```

## disassembly

```asm
0x14001244d  mov     [rsp+arg_8], rdx
0x140012452  push    rbp
0x140012453  sub     rsp, 20h
0x140012457  mov     rbp, rdx
0x14001245a  mov     dword ptr [rbp+20h], 8007000Eh
0x140012461  mov     rax, 0
0x14001246b  add     rsp, 20h
0x14001246f  pop     rbp
0x140012470  retn
```
