# __dcrt_lowio_ensure_console_output_initialized

- ea: `0x14000c820`
- end: `0x14000c872`
- name: `__dcrt_lowio_ensure_console_output_initialized`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14000c620`

## callees

- `0x14000c820`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x14000c856`
- `KERNEL32!CreateFileW` at `0x14000c856`

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
0x14000c820  push    rbx
0x14000c822  sub     rsp, 40h
0x14000c826  mov     rax, cs:hObject
0x14000c82d  xor     ebx, ebx
0x14000c82f  cmp     rax, 0FFFFFFFFFFFFFFFEh
0x14000c833  jnz     short loc_14000C863
0x14000c835  mov     [rsp+48h+hTemplateFile], rbx; hTemplateFile
0x14000c83a  lea     r8d, [rbx+3]; dwShareMode
0x14000c83e  mov     [rsp+48h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x14000c842  lea     rcx, FileName
0x14000c849  xor     r9d, r9d; lpSecurityAttributes
0x14000c84c  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x14000c851  mov     edx, 40000000h; dwDesiredAccess
0x14000c856  call    cs:CreateFileW
0x14000c85c  mov     cs:hObject, rax
0x14000c863  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000c867  setnz   bl
0x14000c86a  mov     eax, ebx
0x14000c86c  add     rsp, 40h
0x14000c870  pop     rbx
0x14000c871  retn
```
