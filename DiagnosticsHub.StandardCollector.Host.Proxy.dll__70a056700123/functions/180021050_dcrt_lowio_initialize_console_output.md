# __dcrt_lowio_initialize_console_output

- ea: `0x180021050`
- end: `0x18002108b`
- name: `__dcrt_lowio_initialize_console_output`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180021079`
- `KERNEL32!CreateFileW` at `0x180021079`

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
0x180021050  sub     rsp, 48h
0x180021054  and     [rsp+48h+var_18], 0
0x18002105a  lea     rcx, FileName; "CONOUT$"
0x180021061  and     [rsp+48h+var_20], 0
0x180021066  mov     r8d, 3; dwShareMode
0x18002106c  xor     r9d, r9d; lpSecurityAttributes
0x18002106f  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x180021074  mov     edx, 40000000h; dwDesiredAccess
0x180021079  call    cs:__imp_CreateFileW
0x18002107f  mov     cs:hObject, rax
0x180021086  add     rsp, 48h
0x18002108a  retn
```
