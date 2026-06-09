# CFileReadStream::Reset(void)

- ea: `0x180031800`
- end: `0x180031845`
- name: `?Reset@CFileReadStream@@UEAAJXZ`
- size: `69`
- prototype: `__int64 __fastcall(CFileReadStream *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180031800`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003181b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031825`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003181b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031825`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180031810`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180031810`

## pseudocode

```c
signed int __fastcall CFileReadStream::Reset(HANDLE *this)
{
  signed int result; // eax

  if ( SetFilePointer(this[1], 0, 0, 0) == -1 || (result = GetLastError()) != 0 )
  {
    result = GetLastError();
    if ( result )
    {
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
    else
    {
      return -2143748092;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180031800  sub     rsp, 28h
0x180031804  mov     rcx, [rcx+8]; hFile
0x180031808  xor     r9d, r9d; dwMoveMethod
0x18003180b  xor     r8d, r8d; lpDistanceToMoveHigh
0x18003180e  xor     edx, edx; lDistanceToMove
0x180031810  call    cs:__imp_SetFilePointer
0x180031816  cmp     eax, 0FFFFFFFFh
0x180031819  jz      short loc_180031825
0x18003181b  call    cs:__imp_GetLastError
0x180031821  test    eax, eax
0x180031823  jz      short loc_180031840
0x180031825  call    cs:__imp_GetLastError
0x18003182b  test    eax, eax
0x18003182d  jz      short loc_18003183B
0x18003182f  jle     short loc_180031840
0x180031831  movzx   eax, ax
0x180031834  or      eax, 80070000h
0x180031839  jmp     short loc_180031840
0x18003183b  mov     eax, 80390004h
0x180031840  add     rsp, 28h
0x180031844  retn
```
