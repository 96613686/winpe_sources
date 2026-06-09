# CFileStream::Write(void const *,ulong,ulong *)

- ea: `0x14004dbb0`
- end: `0x14004dc15`
- name: `?Write@CFileStream@@UEAAJPEBXKPEAK@Z`
- size: `101`
- prototype: `__int64 __fastcall(CFileStream *__hidden this, const void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x14004dbb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004dbee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004dbee`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14004dbe4`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14004dbe4`

## pseudocode

```c
signed int __fastcall CFileStream::Write(HANDLE *this, const void *a2, DWORD a3, unsigned int *a4)
{
  signed int result; // eax
  DWORD NumberOfBytesWritten; // [rsp+50h] [rbp+18h] BYREF

  NumberOfBytesWritten = 0;
  if ( !a3 )
    return 0;
  if ( !a2 )
    return -2147467261;
  if ( WriteFile(this[3], a2, a3, &NumberOfBytesWritten, 0) )
  {
    if ( a4 )
      *a4 = NumberOfBytesWritten;
    return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x14004dbb0  push    rbx
0x14004dbb2  sub     rsp, 30h
0x14004dbb6  mov     [rsp+38h+NumberOfBytesWritten], 0
0x14004dbbe  mov     rbx, r9
0x14004dbc1  test    r8d, r8d
0x14004dbc4  jz      short loc_14004DC0D
0x14004dbc6  test    rdx, rdx
0x14004dbc9  jnz     short loc_14004DBD2
0x14004dbcb  mov     eax, 80004003h
0x14004dbd0  jmp     short loc_14004DC0F
0x14004dbd2  mov     rcx, [rcx+18h]; hFile
0x14004dbd6  lea     r9, [rsp+38h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14004dbdb  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x14004dbe4  call    cs:__imp_WriteFile
0x14004dbea  test    eax, eax
0x14004dbec  jnz     short loc_14004DC02
0x14004dbee  call    cs:__imp_GetLastError
0x14004dbf4  test    eax, eax
0x14004dbf6  jle     short loc_14004DC0F
0x14004dbf8  movzx   eax, ax
0x14004dbfb  or      eax, 80070000h
0x14004dc00  jmp     short loc_14004DC0F
0x14004dc02  test    rbx, rbx
0x14004dc05  jz      short loc_14004DC0D
0x14004dc07  mov     eax, [rsp+38h+NumberOfBytesWritten]
0x14004dc0b  mov     [rbx], eax
0x14004dc0d  xor     eax, eax
0x14004dc0f  add     rsp, 30h
0x14004dc13  pop     rbx
0x14004dc14  retn
```
