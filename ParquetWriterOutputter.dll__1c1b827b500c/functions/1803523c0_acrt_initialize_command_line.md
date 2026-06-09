# __acrt_initialize_command_line

- ea: `0x1803523c0`
- end: `0x1803523e5`
- name: `__acrt_initialize_command_line`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!GetCommandLineA` at `0x1803523c4`
- `KERNEL32!GetCommandLineA` at `0x1803523c4`
- `KERNEL32!GetCommandLineW` at `0x1803523d1`
- `KERNEL32!GetCommandLineW` at `0x1803523d1`

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
0x1803523c0  sub     rsp, 28h
0x1803523c4  call    cs:__imp_GetCommandLineA
0x1803523ca  mov     cs:_acmdln, rax
0x1803523d1  call    cs:__imp_GetCommandLineW
0x1803523d7  mov     cs:_wcmdln, rax
0x1803523de  mov     al, 1
0x1803523e0  add     rsp, 28h
0x1803523e4  retn
```
