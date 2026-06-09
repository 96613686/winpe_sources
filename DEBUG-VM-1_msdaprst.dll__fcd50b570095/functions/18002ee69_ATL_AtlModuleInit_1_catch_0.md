# _ATL::AtlModuleInit_::_1_::catch$0

- ea: `0x18002ee69`
- end: `0x18002eea2`
- name: `_ATL::AtlModuleInit_::_1_::catch$0`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `MSDART!MPDeleteCriticalSection` at `0x18002ee7d`
- `MSDART!MPDeleteCriticalSection` at `0x18002ee8a`
- `MSDART!MPDeleteCriticalSection` at `0x18002ee7d`
- `MSDART!MPDeleteCriticalSection` at `0x18002ee8a`

## pseudocode

```c
__int64 ATL::AtlModuleInit_::_1_::catch_0()
{
  MPDeleteCriticalSection(&qword_1800454F8);
  MPDeleteCriticalSection(&qword_180045500);
  return 0;
}

```

## disassembly

```asm
0x18002ee69  mov     [rsp+arg_8], rdx
0x18002ee6e  push    rbp
0x18002ee6f  sub     rsp, 20h
0x18002ee73  mov     rbp, rdx
0x18002ee76  lea     rcx, qword_1800454F8
0x18002ee7d  call    cs:__imp_MPDeleteCriticalSection
0x18002ee83  lea     rcx, qword_180045500
0x18002ee8a  call    cs:__imp_MPDeleteCriticalSection
0x18002ee90  nop
0x18002ee91  mov     rax, 0
0x18002ee9b  add     rsp, 20h
0x18002ee9f  pop     rbp
0x18002eea0  retn
```
