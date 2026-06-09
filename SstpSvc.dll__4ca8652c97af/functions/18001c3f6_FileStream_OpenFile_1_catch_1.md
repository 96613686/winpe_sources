# _FileStream::OpenFile_::_1_::catch$1

- ea: `0x18001c3f6`
- end: `0x18001c41b`
- name: `_FileStream::OpenFile_::_1_::catch$1`
- size: `37`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall FileStream::OpenFile_::_1_::catch_1(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 96) = 8;
  return 0;
}

```

## disassembly

```asm
0x18001c3f6  mov     [rsp+arg_8], rdx
0x18001c3fb  push    rbp
0x18001c3fc  sub     rsp, 60h
0x18001c400  mov     rbp, rdx
0x18001c403  mov     dword ptr [rbp+60h], 8
0x18001c40a  mov     rax, 0
0x18001c414  add     rsp, 60h
0x18001c418  pop     rbp
0x18001c419  retn
```
