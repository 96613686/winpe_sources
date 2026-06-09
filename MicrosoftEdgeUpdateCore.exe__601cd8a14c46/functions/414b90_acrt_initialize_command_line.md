# ___acrt_initialize_command_line

- ea: `0x414b90`
- end: `0x414ba9`
- name: `___acrt_initialize_command_line`
- size: `25`
- prototype: `char()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!GetCommandLineA` at `0x414b90`
- `KERNEL32!GetCommandLineA` at `0x414b90`
- `KERNEL32!GetCommandLineW` at `0x414b9b`
- `KERNEL32!GetCommandLineW` at `0x414b9b`

## pseudocode

```c
char __acrt_initialize_command_line()
{
  dword_43E4A0 = (int)GetCommandLineA();
  dword_43E4A4 = (int)GetCommandLineW();
  return 1;
}

```

## disassembly

```asm
0x414b90  call    ds:GetCommandLineA
0x414b96  mov     dword_43E4A0, eax
0x414b9b  call    ds:GetCommandLineW
0x414ba1  mov     dword_43E4A4, eax
0x414ba6  mov     al, 1
0x414ba8  retn
```
