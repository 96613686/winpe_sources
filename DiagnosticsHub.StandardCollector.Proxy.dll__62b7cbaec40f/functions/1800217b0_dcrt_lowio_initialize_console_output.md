# __dcrt_lowio_initialize_console_output

- ea: `0x1800217b0`
- end: `0x1800217eb`
- name: `__dcrt_lowio_initialize_console_output`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x1800217d9`
- `KERNEL32!CreateFileW` at `0x1800217d9`

## pseudocode

```c
HANDLE _dcrt_lowio_initialize_console_output()
{
  HANDLE result; // rax

  result = CreateFileW(L"CONOUT$", 0x40000000u, 3u, 0, 3u, 0, 0);
  hObject = result;
  return result;
}

```

## disassembly

```asm
0x1800217b0  sub     rsp, 48h
0x1800217b4  and     [rsp+48h+var_18], 0
0x1800217ba  lea     rcx, FileName; "CONOUT$"
0x1800217c1  and     [rsp+48h+var_20], 0
0x1800217c6  mov     r8d, 3; dwShareMode
0x1800217cc  xor     r9d, r9d; lpSecurityAttributes
0x1800217cf  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x1800217d4  mov     edx, 40000000h; dwDesiredAccess
0x1800217d9  call    cs:__imp_CreateFileW
0x1800217df  mov     cs:hObject, rax
0x1800217e6  add     rsp, 48h
0x1800217ea  retn
```
