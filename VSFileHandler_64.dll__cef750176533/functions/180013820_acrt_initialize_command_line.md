# __acrt_initialize_command_line

- ea: `0x180013820`
- end: `0x180013845`
- name: `__acrt_initialize_command_line`
- size: `37`
- prototype: `char()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!GetCommandLineA` at `0x180013824`
- `KERNEL32!GetCommandLineA` at `0x180013824`
- `KERNEL32!GetCommandLineW` at `0x180013831`
- `KERNEL32!GetCommandLineW` at `0x180013831`

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
0x180013820  sub     rsp, 28h
0x180013824  call    cs:__imp_GetCommandLineA
0x18001382a  mov     cs:_acmdln, rax
0x180013831  call    cs:__imp_GetCommandLineW
0x180013837  mov     cs:_wcmdln, rax
0x18001383e  mov     al, 1
0x180013840  add     rsp, 28h
0x180013844  retn
```
