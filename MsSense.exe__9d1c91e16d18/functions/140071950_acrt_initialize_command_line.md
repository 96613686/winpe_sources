# __acrt_initialize_command_line

- ea: `0x140071950`
- end: `0x140071975`
- name: `__acrt_initialize_command_line`
- size: `37`
- prototype: `char()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!GetCommandLineW` at `0x140071961`
- `KERNEL32!GetCommandLineW` at `0x140071961`
- `KERNEL32!GetCommandLineA` at `0x140071954`
- `KERNEL32!GetCommandLineA` at `0x140071954`

## pseudocode

```c
char _acrt_initialize_command_line()
{
  qword_1400C48F8 = (__int64)GetCommandLineA();
  qword_1400C4900 = (__int64)GetCommandLineW();
  return 1;
}

```

## disassembly

```asm
0x140071950  sub     rsp, 28h
0x140071954  call    cs:GetCommandLineA
0x14007195a  mov     cs:qword_1400C48F8, rax
0x140071961  call    cs:GetCommandLineW
0x140071967  mov     cs:qword_1400C4900, rax
0x14007196e  mov     al, 1
0x140071970  add     rsp, 28h
0x140071974  retn
```
