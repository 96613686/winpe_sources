# __dcrt_lowio_ensure_console_output_initialized

- ea: `0x140024d5c`
- end: `0x140024dae`
- name: `__dcrt_lowio_ensure_console_output_initialized`
- size: `82`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14002457c`

## callees

- `0x140024d5c`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x140024d92`
- `KERNEL32!CreateFileW` at `0x140024d92`

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
0x140024d5c  push    rbx
0x140024d5e  sub     rsp, 40h
0x140024d62  mov     rax, cs:hObject
0x140024d69  xor     ebx, ebx
0x140024d6b  cmp     rax, 0FFFFFFFFFFFFFFFEh
0x140024d6f  jnz     short loc_140024D9F
0x140024d71  mov     [rsp+48h+hTemplateFile], rbx; hTemplateFile
0x140024d76  lea     r8d, [rbx+3]; dwShareMode
0x140024d7a  mov     [rsp+48h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x140024d7e  lea     rcx, FileName
0x140024d85  xor     r9d, r9d; lpSecurityAttributes
0x140024d88  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x140024d8d  mov     edx, 40000000h; dwDesiredAccess
0x140024d92  call    cs:CreateFileW
0x140024d98  mov     cs:hObject, rax
0x140024d9f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140024da3  setnz   bl
0x140024da6  mov     eax, ebx
0x140024da8  add     rsp, 40h
0x140024dac  pop     rbx
0x140024dad  retn
```
