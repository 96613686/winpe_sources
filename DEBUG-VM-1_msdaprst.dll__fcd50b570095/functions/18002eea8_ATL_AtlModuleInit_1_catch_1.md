# _ATL::AtlModuleInit_::_1_::catch$1

- ea: `0x18002eea8`
- end: `0x18002eed4`
- name: `_ATL::AtlModuleInit_::_1_::catch$1`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `MSDART!MPDeleteCriticalSection` at `0x18002eebc`
- `MSDART!MPDeleteCriticalSection` at `0x18002eebc`

## pseudocode

```c
__int64 ATL::AtlModuleInit_::_1_::catch_1()
{
  MPDeleteCriticalSection(&qword_1800454F8);
  return 0;
}

```

## disassembly

```asm
0x18002eea8  mov     [rsp+arg_8], rdx
0x18002eead  push    rbp
0x18002eeae  sub     rsp, 20h
0x18002eeb2  mov     rbp, rdx
0x18002eeb5  lea     rcx, qword_1800454F8
0x18002eebc  call    cs:__imp_MPDeleteCriticalSection
0x18002eec2  nop
0x18002eec3  mov     rax, 0
0x18002eecd  add     rsp, 20h
0x18002eed1  pop     rbp
0x18002eed2  retn
```
