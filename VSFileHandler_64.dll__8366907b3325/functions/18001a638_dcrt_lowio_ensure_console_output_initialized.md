# __dcrt_lowio_ensure_console_output_initialized

- ea: `0x18001a638`
- end: `0x18001a68a`
- name: `__dcrt_lowio_ensure_console_output_initialized`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180019c84`

## callees

- `0x18001a638`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18001a66e`
- `KERNEL32!CreateFileW` at `0x18001a66e`

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
0x18001a638  push    rbx
0x18001a63a  sub     rsp, 40h
0x18001a63e  mov     rax, cs:hObject
0x18001a645  xor     ebx, ebx
0x18001a647  cmp     rax, 0FFFFFFFFFFFFFFFEh
0x18001a64b  jnz     short loc_18001A67B
0x18001a64d  mov     [rsp+48h+hTemplateFile], rbx; hTemplateFile
0x18001a652  lea     r8d, [rbx+3]; dwShareMode
0x18001a656  mov     [rsp+48h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x18001a65a  lea     rcx, FileName; "CONOUT$"
0x18001a661  xor     r9d, r9d; lpSecurityAttributes
0x18001a664  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x18001a669  mov     edx, 40000000h; dwDesiredAccess
0x18001a66e  call    cs:__imp_CreateFileW
0x18001a674  mov     cs:hObject, rax
0x18001a67b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001a67f  setnz   bl
0x18001a682  mov     eax, ebx
0x18001a684  add     rsp, 40h
0x18001a688  pop     rbx
0x18001a689  retn
```
