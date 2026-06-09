# __dcrt_lowio_initialize_console_output(void)

- ea: `0x41be61`
- end: `0x41be80`
- name: `?__dcrt_lowio_initialize_console_output@@YAXXZ`
- size: `31`
- prototype: `void __cdecl()`
- caller_count: `2`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x41be80`
- `0x41beb7`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x41be74`
- `KERNEL32!CreateFileW` at `0x41be74`

## pseudocode

```c
void __cdecl __dcrt_lowio_initialize_console_output()
{
  hConsoleOutput = CreateFileW(L"CONOUT$", 0x40000000u, 3u, 0, 3u, 0, 0);
}

```

## disassembly

```asm
0x41be61  xor     eax, eax
0x41be63  push    eax; hTemplateFile
0x41be64  push    eax; dwFlagsAndAttributes
0x41be65  push    3; dwCreationDisposition
0x41be67  push    eax; lpSecurityAttributes
0x41be68  push    3; dwShareMode
0x41be6a  push    40000000h; dwDesiredAccess
0x41be6f  push    offset FileName
0x41be74  call    ds:CreateFileW
0x41be7a  mov     hConsoleOutput, eax
0x41be7f  retn
```
