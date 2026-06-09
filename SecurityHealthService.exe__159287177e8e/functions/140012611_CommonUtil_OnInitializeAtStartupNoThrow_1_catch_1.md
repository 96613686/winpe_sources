# _CommonUtil::OnInitializeAtStartupNoThrow_::_1_::catch$1

- ea: `0x140012611`
- end: `0x140012636`
- name: `_CommonUtil::OnInitializeAtStartupNoThrow_::_1_::catch$1`
- size: `37`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CommonUtil::OnInitializeAtStartupNoThrow_::_1_::catch_1(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 64) = -2147467259;
  return 0;
}

```

## disassembly

```asm
0x140012611  mov     [rsp+arg_8], rdx
0x140012616  push    rbp
0x140012617  sub     rsp, 20h
0x14001261b  mov     rbp, rdx
0x14001261e  mov     dword ptr [rbp+40h], 80004005h
0x140012625  mov     rax, 0
0x14001262f  add     rsp, 20h
0x140012633  pop     rbp
0x140012634  retn
```
