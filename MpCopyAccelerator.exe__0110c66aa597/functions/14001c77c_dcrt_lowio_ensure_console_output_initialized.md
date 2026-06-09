# __dcrt_lowio_ensure_console_output_initialized

- ea: `0x14001c77c`
- end: `0x14001c7ce`
- name: `__dcrt_lowio_ensure_console_output_initialized`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14001bf40`

## callees

- `0x14001c77c`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x14001c7b2`
- `KERNEL32!CreateFileW` at `0x14001c7b2`

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
0x14001c77c  push    rbx
0x14001c77e  sub     rsp, 40h
0x14001c782  mov     rax, cs:hObject
0x14001c789  xor     ebx, ebx
0x14001c78b  cmp     rax, 0FFFFFFFFFFFFFFFEh
0x14001c78f  jnz     short loc_14001C7BF
0x14001c791  mov     [rsp+48h+hTemplateFile], rbx; hTemplateFile
0x14001c796  lea     r8d, [rbx+3]; dwShareMode
0x14001c79a  mov     [rsp+48h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x14001c79e  lea     rcx, FileName
0x14001c7a5  xor     r9d, r9d; lpSecurityAttributes
0x14001c7a8  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x14001c7ad  mov     edx, 40000000h; dwDesiredAccess
0x14001c7b2  call    cs:__imp_CreateFileW
0x14001c7b8  mov     cs:hObject, rax
0x14001c7bf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001c7c3  setnz   bl
0x14001c7c6  mov     eax, ebx
0x14001c7c8  add     rsp, 40h
0x14001c7cc  pop     rbx
0x14001c7cd  retn
```
