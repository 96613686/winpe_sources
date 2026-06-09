# __acrt_initialize_command_line

- ea: `0x140066690`
- end: `0x1400666b5`
- name: `__acrt_initialize_command_line`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!GetCommandLineW` at `0x1400666a1`
- `KERNEL32!GetCommandLineW` at `0x1400666a1`
- `KERNEL32!GetCommandLineA` at `0x140066694`
- `KERNEL32!GetCommandLineA` at `0x140066694`

## pseudocode

```c
char _acrt_initialize_command_line()
{
  acmdln = GetCommandLineA();
  wcmdln = GetCommandLineW();
  return 1;
}

```

## disassembly

```asm
0x140066690  sub     rsp, 28h
0x140066694  call    cs:__imp_GetCommandLineA
0x14006669a  mov     cs:_acmdln, rax
0x1400666a1  call    cs:__imp_GetCommandLineW
0x1400666a7  mov     cs:_wcmdln, rax
0x1400666ae  mov     al, 1
0x1400666b0  add     rsp, 28h
0x1400666b4  retn
```
