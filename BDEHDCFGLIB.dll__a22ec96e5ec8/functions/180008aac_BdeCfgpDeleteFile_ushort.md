# BdeCfgpDeleteFile(ushort *)

- ea: `0x180008aac`
- end: `0x180008af9`
- name: `?BdeCfgpDeleteFile@@YAJPEAG@Z`
- size: `77`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180007070`
- `0x1800083c4`
- `0x180008968`
- `0x1800093e0`

## callees

- `0x180008aac`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180008ad7`
- `KERNEL32!GetLastError` at `0x180008ad7`
- `KERNEL32!SetFileAttributesW` at `0x180008abe`
- `KERNEL32!SetFileAttributesW` at `0x180008abe`
- `KERNEL32!DeleteFileW` at `0x180008acd`
- `KERNEL32!DeleteFileW` at `0x180008acd`

## pseudocode

```c
__int64 __fastcall BdeCfgpDeleteFile(LPCWSTR lpFileName)
{
  unsigned int v2; // ebx
  signed int LastError; // eax

  if ( !SetFileAttributesW(lpFileName, 0x80u) || (v2 = 0, !DeleteFileW(lpFileName)) )
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
0x180008aac  mov     [rsp+arg_0], rbx
0x180008ab1  push    rdi
0x180008ab2  sub     rsp, 20h
0x180008ab6  mov     edx, 80h; dwFileAttributes
0x180008abb  mov     rdi, rcx
0x180008abe  call    cs:__imp_SetFileAttributesW
0x180008ac4  test    eax, eax
0x180008ac6  jz      short loc_180008AD7
0x180008ac8  mov     rcx, rdi; lpFileName
0x180008acb  xor     ebx, ebx
0x180008acd  call    cs:__imp_DeleteFileW
0x180008ad3  test    eax, eax
0x180008ad5  jnz     short loc_180008AEC
0x180008ad7  call    cs:__imp_GetLastError
0x180008add  mov     ebx, eax
0x180008adf  test    eax, eax
0x180008ae1  jle     short loc_180008AEC
0x180008ae3  movzx   ebx, ax
0x180008ae6  or      ebx, 80070000h
0x180008aec  mov     eax, ebx
0x180008aee  mov     rbx, [rsp+28h+arg_0]
0x180008af3  add     rsp, 20h
0x180008af7  pop     rdi
0x180008af8  retn
```
