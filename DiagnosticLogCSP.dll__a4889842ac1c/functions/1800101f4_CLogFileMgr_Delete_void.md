# CLogFileMgr::Delete(void)

- ea: `0x1800101f4`
- end: `0x18001022a`
- name: `?Delete@CLogFileMgr@@QEAAJXZ`
- size: `54`
- prototype: `__int64 __fastcall(const WCHAR *this)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180009260`
- `0x18000eaf8`
- `0x18000f924`

## callees

- `0x1800101f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010206`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010206`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800101fc`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800101fc`

## pseudocode

```c
__int64 __fastcall CLogFileMgr::Delete(const WCHAR *this)
{
  unsigned int v1; // ebx
  signed int LastError; // eax

  v1 = 0;
  if ( !DeleteFileW(this) )
  {
    LastError = GetLastError();
    if ( LastError != 2 )
    {
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
      else
        return (unsigned int)LastError;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x1800101f4  push    rbx
0x1800101f6  sub     rsp, 20h
0x1800101fa  xor     ebx, ebx
0x1800101fc  call    cs:__imp_DeleteFileW
0x180010202  test    eax, eax
0x180010204  jnz     short loc_180010222
0x180010206  call    cs:__imp_GetLastError
0x18001020c  cmp     eax, 2
0x18001020f  jz      short loc_180010222
0x180010211  test    eax, eax
0x180010213  jg      short loc_180010219
0x180010215  mov     ebx, eax
0x180010217  jmp     short loc_180010222
0x180010219  movzx   ebx, ax
0x18001021c  or      ebx, 80070000h
0x180010222  mov     eax, ebx
0x180010224  add     rsp, 20h
0x180010228  pop     rbx
0x180010229  retn
```
