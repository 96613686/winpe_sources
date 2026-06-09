# __dcrt_lowio_initialize_console_output

- ea: `0x18035746c`
- end: `0x1803574a7`
- name: `__dcrt_lowio_initialize_console_output`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x18034eeec`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180357495`
- `KERNEL32!CreateFileW` at `0x180357495`

## pseudocode

```c
HANDLE _dcrt_lowio_initialize_console_output()
{
  HANDLE result; // rax

  result = CreateFileW(L"CONOUT$", 0x40000000u, 3u, 0, 3u, 0, 0);
  _dcrt_lowio_console_output_handle = result;
  return result;
}

```

## disassembly

```asm
0x18035746c  sub     rsp, 48h
0x180357470  and     [rsp+48h+var_18], 0
0x180357476  lea     rcx, aConout
0x18035747d  and     [rsp+48h+var_20], 0
0x180357482  mov     r8d, 3; dwShareMode
0x180357488  xor     r9d, r9d; lpSecurityAttributes
0x18035748b  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x180357490  mov     edx, 40000000h; dwDesiredAccess
0x180357495  call    cs:__imp_CreateFileW
0x18035749b  mov     cs:__dcrt_lowio_console_output_handle, rax
0x1803574a2  add     rsp, 48h
0x1803574a6  retn
```
