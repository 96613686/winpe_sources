# __dcrt_lowio_ensure_console_output_initialized

- ea: `0x1800217ec`
- end: `0x18002183e`
- name: `__dcrt_lowio_ensure_console_output_initialized`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18001c7f8`

## callees

- `0x1800217ec`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180021822`
- `KERNEL32!CreateFileW` at `0x180021822`

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
0x1800217ec  push    rbx
0x1800217ee  sub     rsp, 40h
0x1800217f2  mov     rax, cs:hObject
0x1800217f9  xor     ebx, ebx
0x1800217fb  cmp     rax, 0FFFFFFFFFFFFFFFEh
0x1800217ff  jnz     short loc_18002182F
0x180021801  mov     [rsp+48h+hTemplateFile], rbx; hTemplateFile
0x180021806  lea     r8d, [rbx+3]; dwShareMode
0x18002180a  mov     [rsp+48h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x18002180e  lea     rcx, FileName; "CONOUT$"
0x180021815  xor     r9d, r9d; lpSecurityAttributes
0x180021818  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x18002181d  mov     edx, 40000000h; dwDesiredAccess
0x180021822  call    cs:__imp_CreateFileW
0x180021828  mov     cs:hObject, rax
0x18002182f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180021833  setnz   bl
0x180021836  mov     eax, ebx
0x180021838  add     rsp, 40h
0x18002183c  pop     rbx
0x18002183d  retn
```
