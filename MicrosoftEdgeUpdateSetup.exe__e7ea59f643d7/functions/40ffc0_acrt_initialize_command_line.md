# ___acrt_initialize_command_line

- ea: `0x40ffc0`
- end: `0x40ffd9`
- name: `___acrt_initialize_command_line`
- size: `25`
- prototype: `char()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!GetCommandLineA` at `0x40ffc0`
- `KERNEL32!GetCommandLineA` at `0x40ffc0`
- `KERNEL32!GetCommandLineW` at `0x40ffcb`
- `KERNEL32!GetCommandLineW` at `0x40ffcb`

## pseudocode

```c
char __acrt_initialize_command_line()
{
  dword_426EB4 = (int)GetCommandLineA();
  dword_426EB8 = (int)GetCommandLineW();
  return 1;
}

```

## disassembly

```asm
0x40ffc0  call    ds:GetCommandLineA
0x40ffc6  mov     dword_426EB4, eax
0x40ffcb  call    ds:GetCommandLineW
0x40ffd1  mov     dword_426EB8, eax
0x40ffd6  mov     al, 1
0x40ffd8  retn
```
