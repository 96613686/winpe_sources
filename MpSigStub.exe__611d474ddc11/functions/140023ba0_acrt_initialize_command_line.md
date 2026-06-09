# __acrt_initialize_command_line

- ea: `0x140023ba0`
- end: `0x140023bc5`
- name: `__acrt_initialize_command_line`
- size: `37`
- prototype: `char()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!GetCommandLineW` at `0x140023bb1`
- `KERNEL32!GetCommandLineW` at `0x140023bb1`
- `KERNEL32!GetCommandLineA` at `0x140023ba4`
- `KERNEL32!GetCommandLineA` at `0x140023ba4`

## pseudocode

```c
char _acrt_initialize_command_line()
{
  qword_1400D7BF8 = (__int64)GetCommandLineA();
  qword_1400D7C00 = (__int64)GetCommandLineW();
  return 1;
}

```

## disassembly

```asm
0x140023ba0  sub     rsp, 28h
0x140023ba4  call    cs:GetCommandLineA
0x140023baa  mov     cs:qword_1400D7BF8, rax
0x140023bb1  call    cs:GetCommandLineW
0x140023bb7  mov     cs:qword_1400D7C00, rax
0x140023bbe  mov     al, 1
0x140023bc0  add     rsp, 28h
0x140023bc4  retn
```
