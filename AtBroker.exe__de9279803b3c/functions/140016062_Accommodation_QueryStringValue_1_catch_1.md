# _Accommodation::QueryStringValue_::_1_::catch$1

- ea: `0x140016062`
- end: `0x140016087`
- name: `_Accommodation::QueryStringValue_::_1_::catch$1`
- size: `37`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall Accommodation::QueryStringValue_::_1_::catch_1(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 64) = 0;
  return 0;
}

```

## disassembly

```asm
0x140016062  mov     [rsp+arg_8], rdx
0x140016067  push    rbp
0x140016068  sub     rsp, 40h
0x14001606c  mov     rbp, rdx
0x14001606f  mov     dword ptr [rbp+40h], 0
0x140016076  mov     rax, 0
0x140016080  add     rsp, 40h
0x140016084  pop     rbp
0x140016085  retn
```
