# __dcrt_lowio_initialize_console_output(void)

- ea: `0x414bf1`
- end: `0x414c10`
- name: `?__dcrt_lowio_initialize_console_output@@YAXXZ`
- size: `31`
- prototype: `void __cdecl()`
- caller_count: `2`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x414c10`
- `0x414c47`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x414c04`
- `KERNEL32!CreateFileW` at `0x414c04`

## pseudocode

```c
void __cdecl __dcrt_lowio_initialize_console_output()
{
  hConsoleOutput = CreateFileW(L"CONOUT$", 0x40000000u, 3u, 0, 3u, 0, 0);
}

```

## disassembly

```asm
0x414bf1  xor     eax, eax
0x414bf3  push    eax; hTemplateFile
0x414bf4  push    eax; dwFlagsAndAttributes
0x414bf5  push    3; dwCreationDisposition
0x414bf7  push    eax; lpSecurityAttributes
0x414bf8  push    3; dwShareMode
0x414bfa  push    40000000h; dwDesiredAccess
0x414bff  push    offset FileName
0x414c04  call    ds:CreateFileW
0x414c0a  mov     hConsoleOutput, eax
0x414c0f  retn
```
