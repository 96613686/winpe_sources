# _anonymous_namespace_::_Set_delete_flag

- ea: `0x140003968`
- end: `0x1400039df`
- name: `_anonymous_namespace_::_Set_delete_flag`
- size: `119`
- prototype: `DWORD __fastcall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140004058`

## callees

- `0x140003968`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003992`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400039cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003992`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400039cf`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x140003988`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1400039c5`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x140003988`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1400039c5`

## pseudocode

```c
DWORD __fastcall anonymous_namespace_::_Set_delete_flag(HANDLE hFile)
{
  DWORD result; // eax
  char v3; // [rsp+38h] [rbp+10h] BYREF
  int FileInformation; // [rsp+40h] [rbp+18h] BYREF

  FileInformation = 3;
  if ( SetFileInformationByHandle(hFile, FileRenameInfoEx|FileDispositionInfo, &FileInformation, 4u) )
    return 0;
  result = GetLastError();
  if ( result == 1 || result != 5 && (result == 50 || result == 87) )
  {
    v3 = 1;
    if ( !SetFileInformationByHandle(hFile, FileDispositionInfo, &v3, 1u) )
      return GetLastError();
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140003968  push    rbx
0x14000396a  sub     rsp, 20h
0x14000396e  mov     r9d, 4; dwBufferSize
0x140003974  mov     [rsp+28h+FileInformation], 3
0x14000397c  lea     r8, [rsp+28h+FileInformation]; lpFileInformation
0x140003981  mov     rbx, rcx
0x140003984  lea     edx, [r9+11h]; FileInformationClass
0x140003988  call    cs:__imp_SetFileInformationByHandle
0x14000398e  test    eax, eax
0x140003990  jnz     short loc_1400039D7
0x140003992  call    cs:__imp_GetLastError
0x140003998  mov     ecx, eax
0x14000399a  sub     ecx, 1
0x14000399d  jz      short loc_1400039AE
0x14000399f  sub     ecx, 4
0x1400039a2  jz      short loc_1400039D9
0x1400039a4  sub     ecx, 2Dh ; '-'
0x1400039a7  jz      short loc_1400039AE
0x1400039a9  cmp     ecx, 25h ; '%'
0x1400039ac  jnz     short loc_1400039D9
0x1400039ae  mov     r9d, 1; dwBufferSize
0x1400039b4  mov     [rsp+28h+arg_8], 1
0x1400039b9  lea     r8, [rsp+28h+arg_8]; lpFileInformation
0x1400039be  mov     rcx, rbx; hFile
0x1400039c1  lea     edx, [r9+3]; FileInformationClass
0x1400039c5  call    cs:__imp_SetFileInformationByHandle
0x1400039cb  test    eax, eax
0x1400039cd  jnz     short loc_1400039D7
0x1400039cf  call    cs:__imp_GetLastError
0x1400039d5  jmp     short loc_1400039D9
0x1400039d7  xor     eax, eax
0x1400039d9  add     rsp, 20h
0x1400039dd  pop     rbx
0x1400039de  retn
```
