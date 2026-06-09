# __dcrt_lowio_ensure_console_output_initialized

- ea: `0x14007e22c`
- end: `0x14007e27e`
- name: `__dcrt_lowio_ensure_console_output_initialized`
- size: `82`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14007d8b4`

## callees

- `0x14007e22c`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x14007e262`
- `KERNEL32!CreateFileW` at `0x14007e262`

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
0x14007e22c  push    rbx
0x14007e22e  sub     rsp, 40h
0x14007e232  mov     rax, cs:hObject
0x14007e239  xor     ebx, ebx
0x14007e23b  cmp     rax, 0FFFFFFFFFFFFFFFEh
0x14007e23f  jnz     short loc_14007E26F
0x14007e241  mov     [rsp+48h+hTemplateFile], rbx; hTemplateFile
0x14007e246  lea     r8d, [rbx+3]; dwShareMode
0x14007e24a  mov     [rsp+48h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x14007e24e  lea     rcx, FileName
0x14007e255  xor     r9d, r9d; lpSecurityAttributes
0x14007e258  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x14007e25d  mov     edx, 40000000h; dwDesiredAccess
0x14007e262  call    cs:CreateFileW
0x14007e268  mov     cs:hObject, rax
0x14007e26f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14007e273  setnz   bl
0x14007e276  mov     eax, ebx
0x14007e278  add     rsp, 40h
0x14007e27c  pop     rbx
0x14007e27d  retn
```
