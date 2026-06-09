# File::MoveFilePointer(_LARGE_INTEGER)

- ea: `0x1800029bc`
- end: `0x1800029f4`
- name: `?MoveFilePointer@File@@QEAAJT_LARGE_INTEGER@@@Z`
- size: `56`
- prototype: `__int64 __fastcall(HANDLE *this, LARGE_INTEGER)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800019d4`
- `0x180001e9c`
- `0x180002474`

## callees

- `0x1800029bc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800029d7`
- `KERNEL32!GetLastError` at `0x1800029d7`
- `KERNEL32!SetFilePointerEx` at `0x1800029cd`
- `KERNEL32!SetFilePointerEx` at `0x1800029cd`

## pseudocode

```c
__int64 __fastcall File::MoveFilePointer(HANDLE *this, LARGE_INTEGER a2)
{
  unsigned int v2; // ebx
  signed int LastError; // eax

  v2 = 0;
  if ( !SetFilePointerEx(*this, a2, 0, 0) )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v2;
}

```

## disassembly

```asm
0x1800029bc  push    rbx
0x1800029be  sub     rsp, 20h
0x1800029c2  mov     rcx, [rcx]; hFile
0x1800029c5  xor     r9d, r9d; dwMoveMethod
0x1800029c8  xor     r8d, r8d; lpNewFilePointer
0x1800029cb  xor     ebx, ebx
0x1800029cd  call    cs:__imp_SetFilePointerEx
0x1800029d3  test    eax, eax
0x1800029d5  jnz     short loc_1800029EC
0x1800029d7  call    cs:__imp_GetLastError
0x1800029dd  mov     ebx, eax
0x1800029df  test    eax, eax
0x1800029e1  jle     short loc_1800029EC
0x1800029e3  movzx   ebx, ax
0x1800029e6  or      ebx, 80070000h
0x1800029ec  mov     eax, ebx
0x1800029ee  add     rsp, 20h
0x1800029f2  pop     rbx
0x1800029f3  retn
```
