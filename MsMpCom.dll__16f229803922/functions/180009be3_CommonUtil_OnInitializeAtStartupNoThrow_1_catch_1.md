# _CommonUtil::OnInitializeAtStartupNoThrow_::_1_::catch$1

- ea: `0x180009be3`
- end: `0x180009c08`
- name: `_CommonUtil::OnInitializeAtStartupNoThrow_::_1_::catch$1`
- size: `37`
- prototype: ``
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
0x180009be3  mov     [rsp+arg_8], rdx
0x180009be8  push    rbp
0x180009be9  sub     rsp, 20h
0x180009bed  mov     rbp, rdx
0x180009bf0  mov     dword ptr [rbp+40h], 80004005h
0x180009bf7  mov     rax, 0
0x180009c01  add     rsp, 20h
0x180009c05  pop     rbp
0x180009c06  retn
```
