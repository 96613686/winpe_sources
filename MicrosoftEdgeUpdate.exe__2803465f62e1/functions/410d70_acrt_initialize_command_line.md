# ___acrt_initialize_command_line

- ea: `0x410d70`
- end: `0x410d89`
- name: `___acrt_initialize_command_line`
- size: `25`
- prototype: `char()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!GetCommandLineW` at `0x410d7b`
- `KERNEL32!GetCommandLineW` at `0x410d7b`
- `KERNEL32!GetCommandLineA` at `0x410d70`
- `KERNEL32!GetCommandLineA` at `0x410d70`

## pseudocode

```c
char __acrt_initialize_command_line()
{
  dword_4181A0 = (int)GetCommandLineA();
  dword_4181A4 = (int)GetCommandLineW();
  return 1;
}

```

## disassembly

```asm
0x410d70  call    ds:GetCommandLineA
0x410d76  mov     dword_4181A0, eax
0x410d7b  call    ds:GetCommandLineW
0x410d81  mov     dword_4181A4, eax
0x410d86  mov     al, 1
0x410d88  retn
```
