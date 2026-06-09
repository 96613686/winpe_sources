# __dcrt_lowio_ensure_console_output_initialized

- ea: `0x14001b6a0`
- end: `0x14001b6f2`
- name: `__dcrt_lowio_ensure_console_output_initialized`
- size: `82`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14001ad74`

## callees

- `0x14001b6a0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x14001b6d6`
- `KERNEL32!CreateFileW` at `0x14001b6d6`

## pseudocode

```c
__int64 _dcrt_lowio_ensure_console_output_initialized()
{
  char *FileW; // rax
  unsigned int v1; // ebx

  FileW = (char *)hObject;
  v1 = 0;
  if ( hObject == (HANDLE)-2LL )
  {
    FileW = (char *)CreateFileW(L"CONOUT$", 0x40000000u, 3u, 0, 3u, 0, 0);
    hObject = FileW;
  }
  LOBYTE(v1) = FileW + 1 != 0;
  return v1;
}

```

## disassembly

```asm
0x14001b6a0  push    rbx
0x14001b6a2  sub     rsp, 40h
0x14001b6a6  mov     rax, cs:hObject
0x14001b6ad  xor     ebx, ebx
0x14001b6af  cmp     rax, 0FFFFFFFFFFFFFFFEh
0x14001b6b3  jnz     short loc_14001B6E3
0x14001b6b5  mov     [rsp+48h+hTemplateFile], rbx; hTemplateFile
0x14001b6ba  lea     r8d, [rbx+3]; dwShareMode
0x14001b6be  mov     [rsp+48h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x14001b6c2  lea     rcx, FileName
0x14001b6c9  xor     r9d, r9d; lpSecurityAttributes
0x14001b6cc  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x14001b6d1  mov     edx, 40000000h; dwDesiredAccess
0x14001b6d6  call    cs:CreateFileW
0x14001b6dc  mov     cs:hObject, rax
0x14001b6e3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001b6e7  setnz   bl
0x14001b6ea  mov     eax, ebx
0x14001b6ec  add     rsp, 40h
0x14001b6f0  pop     rbx
0x14001b6f1  retn
```
