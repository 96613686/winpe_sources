# __dcrt_lowio_ensure_console_output_initialized

- ea: `0x180228c2c`
- end: `0x180228c7e`
- name: `__dcrt_lowio_ensure_console_output_initialized`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1802285ec`

## callees

- `0x180228c2c`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180228c62`
- `KERNEL32!CreateFileW` at `0x180228c62`

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
0x180228c2c  push    rbx
0x180228c2e  sub     rsp, 40h
0x180228c32  mov     rax, cs:hObject
0x180228c39  xor     ebx, ebx
0x180228c3b  cmp     rax, 0FFFFFFFFFFFFFFFEh
0x180228c3f  jnz     short loc_180228C6F
0x180228c41  mov     [rsp+48h+hTemplateFile], rbx; hTemplateFile
0x180228c46  lea     r8d, [rbx+3]; dwShareMode
0x180228c4a  mov     [rsp+48h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x180228c4e  lea     rcx, aConout; "CONOUT$"
0x180228c55  xor     r9d, r9d; lpSecurityAttributes
0x180228c58  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x180228c5d  mov     edx, 40000000h; dwDesiredAccess
0x180228c62  call    cs:__imp_CreateFileW
0x180228c68  mov     cs:hObject, rax
0x180228c6f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180228c73  setnz   bl
0x180228c76  mov     eax, ebx
0x180228c78  add     rsp, 40h
0x180228c7c  pop     rbx
0x180228c7d  retn
```
