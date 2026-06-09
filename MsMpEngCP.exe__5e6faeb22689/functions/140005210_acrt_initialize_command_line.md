# __acrt_initialize_command_line

- ea: `0x140005210`
- end: `0x140005235`
- name: `__acrt_initialize_command_line`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!GetCommandLineA` at `0x140005214`
- `KERNEL32!GetCommandLineA` at `0x140005214`
- `KERNEL32!GetCommandLineW` at `0x140005221`
- `KERNEL32!GetCommandLineW` at `0x140005221`

## pseudocode

```c
char _acrt_initialize_command_line()
{
  qword_14001A468 = (__int64)GetCommandLineA();
  qword_14001A470 = (__int64)GetCommandLineW();
  return 1;
}

```

## disassembly

```asm
0x140005210  sub     rsp, 28h
0x140005214  call    cs:GetCommandLineA
0x14000521a  mov     cs:qword_14001A468, rax
0x140005221  call    cs:GetCommandLineW
0x140005227  mov     cs:qword_14001A470, rax
0x14000522e  mov     al, 1
0x140005230  add     rsp, 28h
0x140005234  retn
```
