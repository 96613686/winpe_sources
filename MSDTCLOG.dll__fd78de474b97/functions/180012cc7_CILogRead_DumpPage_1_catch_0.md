# _CILogRead::DumpPage_::_1_::catch$0

- ea: `0x180012cc7`
- end: `0x180012ceb`
- name: `_CILogRead::DumpPage_::_1_::catch$0`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall CILogRead::DumpPage_::_1_::catch_0(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 120) = *(_DWORD *)(a2 + 72);
  return 0;
}

```

## disassembly

```asm
0x180012cc7  mov     [rsp+arg_8], rdx
0x180012ccc  push    rbp
0x180012ccd  sub     rsp, 40h
0x180012cd1  mov     rbp, rdx
0x180012cd4  mov     eax, [rbp+48h]
0x180012cd7  mov     [rbp+78h], eax
0x180012cda  mov     rax, 0
0x180012ce4  add     rsp, 40h
0x180012ce8  pop     rbp
0x180012ce9  retn
```
