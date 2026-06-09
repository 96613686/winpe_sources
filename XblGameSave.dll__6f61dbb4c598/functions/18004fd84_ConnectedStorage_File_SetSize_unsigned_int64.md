# ConnectedStorage::File::SetSize(unsigned __int64)

- ea: `0x18004fd84`
- end: `0x18004feaf`
- name: `?SetSize@File@ConnectedStorage@@QEAAX_K@Z`
- size: `299`
- prototype: `void(ConnectedStorage::File *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180044de0`
- `0x180069d80`

## callees

- `0x18000aae4`
- `0x18004fd84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fdca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fe0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fe41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fe83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fdca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fe0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fe41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fe83`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18004fdb7`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18004fdf7`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18004fe70`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18004fdb7`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18004fdf7`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18004fe70`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18004fe2e`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18004fe2e`

## string_xrefs

- `0x18004fddc`: `File::SetSize - SetFilePointerEx - FILE_CURRENT`
- `0x18004fe1c`: `File::SetSize - SetFilePointerEx - FILE_BEGIN`
- `0x18004fe95`: `File::SetSize - SetFilePointerEx - original location`

## pseudocode

```c
void __fastcall ConnectedStorage::File::SetSize(ConnectedStorage::File *this, LARGE_INTEGER a2)
{
  signed int LastError; // eax
  const unsigned __int16 *v5; // r8
  signed int v6; // eax
  const unsigned __int16 *v7; // r8
  signed int v8; // eax
  const unsigned __int16 *v9; // r8
  signed int v10; // eax
  const unsigned __int16 *v11; // r8
  LARGE_INTEGER liDistanceToMove; // [rsp+30h] [rbp+8h] BYREF
  __int64 v13; // [rsp+40h] [rbp+18h]

  v13 = 0;
  liDistanceToMove.QuadPart = 0;
  if ( !SetFilePointerEx(*(HANDLE *)this, 0, &liDistanceToMove, 1u) )
  {
    if ( *((_DWORD *)this + 2) == 1 )
      *((_DWORD *)this + 2) = 0;
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)(unsigned int)LastError,
      (int)L"File::SetSize - SetFilePointerEx - FILE_CURRENT",
      v5);
  }
  if ( !SetFilePointerEx(*(HANDLE *)this, a2, 0, 0) )
  {
    if ( *((_DWORD *)this + 2) == 1 )
      *((_DWORD *)this + 2) = 0;
    v6 = GetLastError();
    if ( v6 > 0 )
      v6 = (unsigned __int16)v6 | 0x80070000;
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)(unsigned int)v6,
      (int)L"File::SetSize - SetFilePointerEx - FILE_BEGIN",
      v7);
  }
  if ( !SetEndOfFile(*(HANDLE *)this) )
  {
    if ( *((_DWORD *)this + 2) == 1 )
      *((_DWORD *)this + 2) = 0;
    v8 = GetLastError();
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)(unsigned int)v8,
      (int)L"File::SetSize - SetEndOfFile",
      v9);
  }
  if ( !SetFilePointerEx(*(HANDLE *)this, liDistanceToMove, 0, 0) )
  {
    if ( *((_DWORD *)this + 2) == 1 )
      *((_DWORD *)this + 2) = 0;
    v10 = GetLastError();
    if ( v10 > 0 )
      v10 = (unsigned __int16)v10 | 0x80070000;
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)(unsigned int)v10,
      (int)L"File::SetSize - SetFilePointerEx - original location",
      v11);
  }
}

```

## disassembly

```asm
0x18004fd84  mov     rax, rsp
0x18004fd87  mov     [rax+10h], rbx
0x18004fd8b  push    rdi
0x18004fd8c  sub     rsp, 20h
0x18004fd90  mov     rdi, rdx
0x18004fd93  mov     qword ptr [rax+18h], 0
0x18004fd9b  mov     rdx, [rax+18h]; liDistanceToMove
0x18004fd9f  lea     r8, [rax+8]; lpNewFilePointer
0x18004fda3  mov     rbx, rcx
0x18004fda6  mov     qword ptr [rax+8], 0
0x18004fdae  mov     rcx, [rcx]; hFile
0x18004fdb1  mov     r9d, 1; dwMoveMethod
0x18004fdb7  call    cs:__imp_SetFilePointerEx
0x18004fdbd  test    eax, eax
0x18004fdbf  jnz     short loc_18004FDEB
0x18004fdc1  cmp     dword ptr [rbx+8], 1
0x18004fdc5  jnz     short loc_18004FDCA
0x18004fdc7  mov     [rbx+8], eax
0x18004fdca  call    cs:__imp_GetLastError
0x18004fdd0  test    eax, eax
0x18004fdd2  jle     short loc_18004FDDC
0x18004fdd4  movzx   eax, ax
0x18004fdd7  or      eax, 80070000h
0x18004fddc  lea     rdx, aFileSetsizeSet_0; "File::SetSize - SetFilePointerEx - FILE"...
0x18004fde3  mov     ecx, eax; this
0x18004fde5  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18004fdeb  mov     rcx, [rbx]; hFile
0x18004fdee  xor     r9d, r9d; dwMoveMethod
0x18004fdf1  xor     r8d, r8d; lpNewFilePointer
0x18004fdf4  mov     rdx, rdi; liDistanceToMove
0x18004fdf7  call    cs:__imp_SetFilePointerEx
0x18004fdfd  test    eax, eax
0x18004fdff  jnz     short loc_18004FE2B
0x18004fe01  cmp     dword ptr [rbx+8], 1
0x18004fe05  jnz     short loc_18004FE0A
0x18004fe07  mov     [rbx+8], eax
0x18004fe0a  call    cs:__imp_GetLastError
0x18004fe10  test    eax, eax
0x18004fe12  jle     short loc_18004FE1C
0x18004fe14  movzx   eax, ax
0x18004fe17  or      eax, 80070000h
0x18004fe1c  lea     rdx, aFileSetsizeSet_2; "File::SetSize - SetFilePointerEx - FILE"...
0x18004fe23  mov     ecx, eax; this
0x18004fe25  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18004fe2b  mov     rcx, [rbx]; hFile
0x18004fe2e  call    cs:__imp_SetEndOfFile
0x18004fe34  test    eax, eax
0x18004fe36  jnz     short loc_18004FE62
0x18004fe38  cmp     dword ptr [rbx+8], 1
0x18004fe3c  jnz     short loc_18004FE41
0x18004fe3e  mov     [rbx+8], eax
0x18004fe41  call    cs:__imp_GetLastError
0x18004fe47  test    eax, eax
0x18004fe49  jle     short loc_18004FE53
0x18004fe4b  movzx   eax, ax
0x18004fe4e  or      eax, 80070000h
0x18004fe53  lea     rdx, aFileSetsizeSet; "File::SetSize - SetEndOfFile"
0x18004fe5a  mov     ecx, eax; this
0x18004fe5c  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18004fe62  mov     rdx, qword ptr [rsp+28h+liDistanceToMove]; liDistanceToMove
0x18004fe67  xor     r9d, r9d; dwMoveMethod
0x18004fe6a  mov     rcx, [rbx]; hFile
0x18004fe6d  xor     r8d, r8d; lpNewFilePointer
0x18004fe70  call    cs:__imp_SetFilePointerEx
0x18004fe76  test    eax, eax
0x18004fe78  jnz     short loc_18004FEA4
0x18004fe7a  cmp     dword ptr [rbx+8], 1
0x18004fe7e  jnz     short loc_18004FE83
0x18004fe80  mov     [rbx+8], eax
0x18004fe83  call    cs:__imp_GetLastError
0x18004fe89  test    eax, eax
0x18004fe8b  jle     short loc_18004FE95
0x18004fe8d  movzx   eax, ax
0x18004fe90  or      eax, 80070000h
0x18004fe95  lea     rdx, aFileSetsizeSet_1; "File::SetSize - SetFilePointerEx - orig"...
0x18004fe9c  mov     ecx, eax; this
0x18004fe9e  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18004fea4  mov     rbx, [rsp+28h+arg_8]
0x18004fea9  add     rsp, 20h
0x18004fead  pop     rdi
0x18004feae  retn
```
