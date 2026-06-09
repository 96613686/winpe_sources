# File::Flush(void)

- ea: `0x1800027c4`
- end: `0x1800027f6`
- name: `?Flush@File@@QEAAJXZ`
- size: `50`
- prototype: `__int64 __fastcall(HANDLE *this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800019d4`
- `0x18000228c`
- `0x180002474`

## callees

- `0x1800027c4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800027d9`
- `KERNEL32!GetLastError` at `0x1800027d9`
- `KERNEL32!FlushFileBuffers` at `0x1800027cf`
- `KERNEL32!FlushFileBuffers` at `0x1800027cf`

## pseudocode

```c
__int64 __fastcall File::Flush(HANDLE *this)
{
  unsigned int v1; // ebx
  signed int LastError; // eax

  v1 = 0;
  if ( !FlushFileBuffers(*this) )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v1;
}

```

## disassembly

```asm
0x1800027c4  push    rbx
0x1800027c6  sub     rsp, 20h
0x1800027ca  mov     rcx, [rcx]; hFile
0x1800027cd  xor     ebx, ebx
0x1800027cf  call    cs:__imp_FlushFileBuffers
0x1800027d5  test    eax, eax
0x1800027d7  jnz     short loc_1800027EE
0x1800027d9  call    cs:__imp_GetLastError
0x1800027df  mov     ebx, eax
0x1800027e1  test    eax, eax
0x1800027e3  jle     short loc_1800027EE
0x1800027e5  movzx   ebx, ax
0x1800027e8  or      ebx, 80070000h
0x1800027ee  mov     eax, ebx
0x1800027f0  add     rsp, 20h
0x1800027f4  pop     rbx
0x1800027f5  retn
```
