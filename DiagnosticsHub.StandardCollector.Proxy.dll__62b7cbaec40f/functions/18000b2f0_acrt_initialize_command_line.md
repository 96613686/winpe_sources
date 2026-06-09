# __acrt_initialize_command_line

- ea: `0x18000b2f0`
- end: `0x18000b315`
- name: `__acrt_initialize_command_line`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!GetCommandLineA` at `0x18000b2f4`
- `KERNEL32!GetCommandLineA` at `0x18000b2f4`
- `KERNEL32!GetCommandLineW` at `0x18000b301`
- `KERNEL32!GetCommandLineW` at `0x18000b301`

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
0x18000b2f0  sub     rsp, 28h
0x18000b2f4  call    cs:__imp_GetCommandLineA
0x18000b2fa  mov     cs:_acmdln, rax
0x18000b301  call    cs:__imp_GetCommandLineW
0x18000b307  mov     cs:_wcmdln, rax
0x18000b30e  mov     al, 1
0x18000b310  add     rsp, 28h
0x18000b314  retn
```
