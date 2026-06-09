# __dcrt_lowio_initialize_console_output(void)

- ea: `0x417501`
- end: `0x417520`
- name: `?__dcrt_lowio_initialize_console_output@@YAXXZ`
- size: `31`
- prototype: `void __cdecl()`
- caller_count: `2`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x417520`
- `0x417557`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x417514`
- `KERNEL32!CreateFileW` at `0x417514`

## pseudocode

```c
void __cdecl __dcrt_lowio_initialize_console_output()
{
  hConsoleOutput = CreateFileW(L"CONOUT$", 0x40000000u, 3u, 0, 3u, 0, 0);
}

```

## disassembly

```asm
0x417501  xor     eax, eax
0x417503  push    eax; hTemplateFile
0x417504  push    eax; dwFlagsAndAttributes
0x417505  push    3; dwCreationDisposition
0x417507  push    eax; lpSecurityAttributes
0x417508  push    3; dwShareMode
0x41750a  push    40000000h; dwDesiredAccess
0x41750f  push    offset FileName
0x417514  call    ds:CreateFileW
0x41751a  mov     hConsoleOutput, eax
0x41751f  retn
```
