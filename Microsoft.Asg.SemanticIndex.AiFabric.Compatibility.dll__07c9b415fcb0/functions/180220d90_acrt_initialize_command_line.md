# __acrt_initialize_command_line

- ea: `0x180220d90`
- end: `0x180220db5`
- name: `__acrt_initialize_command_line`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!GetCommandLineW` at `0x180220da1`
- `KERNEL32!GetCommandLineW` at `0x180220da1`
- `KERNEL32!GetCommandLineA` at `0x180220d94`
- `KERNEL32!GetCommandLineA` at `0x180220d94`

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
0x180220d90  sub     rsp, 28h
0x180220d94  call    cs:__imp_GetCommandLineA
0x180220d9a  mov     cs:_acmdln, rax
0x180220da1  call    cs:__imp_GetCommandLineW
0x180220da7  mov     cs:_wcmdln, rax
0x180220dae  mov     al, 1
0x180220db0  add     rsp, 28h
0x180220db4  retn
```
