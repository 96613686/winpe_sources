# _anonymous_namespace_::_Set_delete_flag

- ea: `0x1800067d0`
- end: `0x180006847`
- name: `_anonymous_namespace_::_Set_delete_flag`
- size: `119`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180007670`

## callees

- `0x1800067d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800067fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006837`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800067fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006837`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800067f0`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18000682d`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800067f0`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18000682d`

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
0x1800067d0  push    rbx
0x1800067d2  sub     rsp, 20h
0x1800067d6  mov     r9d, 4; dwBufferSize
0x1800067dc  mov     [rsp+28h+FileInformation], 3
0x1800067e4  lea     r8, [rsp+28h+FileInformation]; lpFileInformation
0x1800067e9  mov     rbx, rcx
0x1800067ec  lea     edx, [r9+11h]; FileInformationClass
0x1800067f0  call    cs:__imp_SetFileInformationByHandle
0x1800067f6  test    eax, eax
0x1800067f8  jnz     short loc_18000683F
0x1800067fa  call    cs:__imp_GetLastError
0x180006800  mov     ecx, eax
0x180006802  sub     ecx, 1
0x180006805  jz      short loc_180006816
0x180006807  sub     ecx, 4
0x18000680a  jz      short loc_180006841
0x18000680c  sub     ecx, 2Dh ; '-'
0x18000680f  jz      short loc_180006816
0x180006811  cmp     ecx, 25h ; '%'
0x180006814  jnz     short loc_180006841
0x180006816  mov     r9d, 1; dwBufferSize
0x18000681c  mov     [rsp+28h+arg_8], 1
0x180006821  lea     r8, [rsp+28h+arg_8]; lpFileInformation
0x180006826  mov     rcx, rbx; hFile
0x180006829  lea     edx, [r9+3]; FileInformationClass
0x18000682d  call    cs:__imp_SetFileInformationByHandle
0x180006833  test    eax, eax
0x180006835  jnz     short loc_18000683F
0x180006837  call    cs:__imp_GetLastError
0x18000683d  jmp     short loc_180006841
0x18000683f  xor     eax, eax
0x180006841  add     rsp, 20h
0x180006845  pop     rbx
0x180006846  retn
```
