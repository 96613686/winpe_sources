# __dcrt_lowio_ensure_console_output_initialized

- ea: `0x18002108c`
- end: `0x1800210de`
- name: `__dcrt_lowio_ensure_console_output_initialized`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18001c098`

## callees

- `0x18002108c`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x1800210c2`
- `KERNEL32!CreateFileW` at `0x1800210c2`

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
0x18002108c  push    rbx
0x18002108e  sub     rsp, 40h
0x180021092  mov     rax, cs:hObject
0x180021099  xor     ebx, ebx
0x18002109b  cmp     rax, 0FFFFFFFFFFFFFFFEh
0x18002109f  jnz     short loc_1800210CF
0x1800210a1  mov     [rsp+48h+hTemplateFile], rbx; hTemplateFile
0x1800210a6  lea     r8d, [rbx+3]; dwShareMode
0x1800210aa  mov     [rsp+48h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x1800210ae  lea     rcx, FileName; "CONOUT$"
0x1800210b5  xor     r9d, r9d; lpSecurityAttributes
0x1800210b8  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x1800210bd  mov     edx, 40000000h; dwDesiredAccess
0x1800210c2  call    cs:__imp_CreateFileW
0x1800210c8  mov     cs:hObject, rax
0x1800210cf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800210d3  setnz   bl
0x1800210d6  mov     eax, ebx
0x1800210d8  add     rsp, 40h
0x1800210dc  pop     rbx
0x1800210dd  retn
```
