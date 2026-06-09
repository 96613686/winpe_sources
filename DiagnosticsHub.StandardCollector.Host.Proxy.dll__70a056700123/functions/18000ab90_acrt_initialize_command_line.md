# __acrt_initialize_command_line

- ea: `0x18000ab90`
- end: `0x18000abb5`
- name: `__acrt_initialize_command_line`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!GetCommandLineA` at `0x18000ab94`
- `KERNEL32!GetCommandLineA` at `0x18000ab94`
- `KERNEL32!GetCommandLineW` at `0x18000aba1`
- `KERNEL32!GetCommandLineW` at `0x18000aba1`

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
0x18000ab90  sub     rsp, 28h
0x18000ab94  call    cs:__imp_GetCommandLineA
0x18000ab9a  mov     cs:_acmdln, rax
0x18000aba1  call    cs:__imp_GetCommandLineW
0x18000aba7  mov     cs:_wcmdln, rax
0x18000abae  mov     al, 1
0x18000abb0  add     rsp, 28h
0x18000abb4  retn
```
