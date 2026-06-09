# __acrt_initialize_command_line

- ea: `0x180039960`
- end: `0x180039985`
- name: `__acrt_initialize_command_line`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!GetCommandLineW` at `0x180039971`
- `KERNEL32!GetCommandLineW` at `0x180039971`
- `KERNEL32!GetCommandLineA` at `0x180039964`
- `KERNEL32!GetCommandLineA` at `0x180039964`

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
0x180039960  sub     rsp, 28h
0x180039964  call    cs:__imp_GetCommandLineA
0x18003996a  mov     cs:_acmdln, rax
0x180039971  call    cs:__imp_GetCommandLineW
0x180039977  mov     cs:_wcmdln, rax
0x18003997e  mov     al, 1
0x180039980  add     rsp, 28h
0x180039984  retn
```
