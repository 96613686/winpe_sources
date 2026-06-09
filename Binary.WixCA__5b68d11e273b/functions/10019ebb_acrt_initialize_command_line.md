# ___acrt_initialize_command_line

- ea: `0x10019ebb`
- end: `0x10019ed4`
- name: `___acrt_initialize_command_line`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!GetCommandLineW` at `0x10019ec6`
- `KERNEL32!GetCommandLineW` at `0x10019ec6`
- `KERNEL32!GetCommandLineA` at `0x10019ebb`
- `KERNEL32!GetCommandLineA` at `0x10019ebb`

## pseudocode

```c
char __acrt_initialize_command_line()
{
  dword_100352B0 = (int)GetCommandLineA();
  dword_100352B4 = (int)GetCommandLineW();
  return 1;
}

```

## disassembly

```asm
0x10019ebb  call    ds:GetCommandLineA
0x10019ec1  mov     dword_100352B0, eax
0x10019ec6  call    ds:GetCommandLineW
0x10019ecc  mov     dword_100352B4, eax
0x10019ed1  mov     al, 1
0x10019ed3  retn
```
