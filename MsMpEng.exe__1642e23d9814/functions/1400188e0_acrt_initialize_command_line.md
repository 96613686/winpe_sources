# __acrt_initialize_command_line

- ea: `0x1400188e0`
- end: `0x140018905`
- name: `__acrt_initialize_command_line`
- size: `37`
- prototype: `char()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!GetCommandLineW` at `0x1400188f1`
- `KERNEL32!GetCommandLineW` at `0x1400188f1`
- `KERNEL32!GetCommandLineA` at `0x1400188e4`
- `KERNEL32!GetCommandLineA` at `0x1400188e4`

## pseudocode

```c
char _acrt_initialize_command_line()
{
  qword_14003E548 = (__int64)GetCommandLineA();
  qword_14003E550 = (__int64)GetCommandLineW();
  return 1;
}

```

## disassembly

```asm
0x1400188e0  sub     rsp, 28h
0x1400188e4  call    cs:GetCommandLineA
0x1400188ea  mov     cs:qword_14003E548, rax
0x1400188f1  call    cs:GetCommandLineW
0x1400188f7  mov     cs:qword_14003E550, rax
0x1400188fe  mov     al, 1
0x140018900  add     rsp, 28h
0x140018904  retn
```
