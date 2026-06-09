# __dcrt_lowio_initialize_console_output(void)

- ea: `0x10020281`
- end: `0x100202a0`
- name: `?__dcrt_lowio_initialize_console_output@@YAXXZ`
- size: `31`
- prototype: `void __cdecl()`
- caller_count: `2`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x100202a0`
- `0x100202d6`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x10020294`
- `KERNEL32!CreateFileW` at `0x10020294`

## pseudocode

```c
void __cdecl __dcrt_lowio_initialize_console_output()
{
  hConsoleOutput = CreateFileW(L"CONOUT$", 0x40000000u, 3u, 0, 3u, 0, 0);
}

```

## disassembly

```asm
0x10020281  xor     eax, eax
0x10020283  push    eax; hTemplateFile
0x10020284  push    eax; dwFlagsAndAttributes
0x10020285  push    3; dwCreationDisposition
0x10020287  push    eax; lpSecurityAttributes
0x10020288  push    3; dwShareMode
0x1002028a  push    40000000h; dwDesiredAccess
0x1002028f  push    offset FileName
0x10020294  call    ds:CreateFileW
0x1002029a  mov     hConsoleOutput, eax
0x1002029f  retn
```
