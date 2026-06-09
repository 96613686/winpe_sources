# __acrt_initialize_command_line

- ea: `0x140012dd0`
- end: `0x140012df5`
- name: `__acrt_initialize_command_line`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!GetCommandLineW` at `0x140012de1`
- `KERNEL32!GetCommandLineW` at `0x140012de1`
- `KERNEL32!GetCommandLineA` at `0x140012dd4`
- `KERNEL32!GetCommandLineA` at `0x140012dd4`

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
0x140012dd0  sub     rsp, 28h
0x140012dd4  call    cs:__imp_GetCommandLineA
0x140012dda  mov     cs:_acmdln, rax
0x140012de1  call    cs:__imp_GetCommandLineW
0x140012de7  mov     cs:_wcmdln, rax
0x140012dee  mov     al, 1
0x140012df0  add     rsp, 28h
0x140012df4  retn
```
