# CLogFileMgr::Delete(void)

- ea: `0x180010a30`
- end: `0x180010a73`
- name: `?Delete@CLogFileMgr@@QEAAJXZ`
- size: `67`
- prototype: `__int64 __fastcall(CLogFileMgr *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800094c8`
- `0x18000f228`
- `0x180010118`

## callees

- `0x180010a30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010a48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010a48`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180010a38`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180010a38`

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
0x180010a30  push    rbx
0x180010a32  sub     rsp, 20h
0x180010a36  xor     ebx, ebx
0x180010a38  call    cs:__imp_DeleteFileW
0x180010a3f  nop     dword ptr [rax+rax+00h]
0x180010a44  test    eax, eax
0x180010a46  jnz     short loc_180010A6A
0x180010a48  call    cs:__imp_GetLastError
0x180010a4f  nop     dword ptr [rax+rax+00h]
0x180010a54  cmp     eax, 2
0x180010a57  jz      short loc_180010A6A
0x180010a59  test    eax, eax
0x180010a5b  jg      short loc_180010A61
0x180010a5d  mov     ebx, eax
0x180010a5f  jmp     short loc_180010A6A
0x180010a61  movzx   ebx, ax
0x180010a64  or      ebx, 80070000h
0x180010a6a  mov     eax, ebx
0x180010a6c  add     rsp, 20h
0x180010a70  pop     rbx
0x180010a71  retn
```
