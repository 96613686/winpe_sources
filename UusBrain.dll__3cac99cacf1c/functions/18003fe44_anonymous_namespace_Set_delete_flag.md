# _anonymous_namespace_::_Set_delete_flag

- ea: `0x18003fe44`
- end: `0x18003febb`
- name: `_anonymous_namespace_::_Set_delete_flag`
- size: `119`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180040158`

## callees

- `0x18003fe44`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fe6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003feab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fe6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003feab`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18003fe64`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18003fea1`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18003fe64`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x18003fea1`

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
0x18003fe44  push    rbx
0x18003fe46  sub     rsp, 20h
0x18003fe4a  mov     r9d, 4; dwBufferSize
0x18003fe50  mov     [rsp+28h+FileInformation], 3
0x18003fe58  lea     r8, [rsp+28h+FileInformation]; lpFileInformation
0x18003fe5d  mov     rbx, rcx
0x18003fe60  lea     edx, [r9+11h]; FileInformationClass
0x18003fe64  call    cs:__imp_SetFileInformationByHandle
0x18003fe6a  test    eax, eax
0x18003fe6c  jnz     short loc_18003FEB3
0x18003fe6e  call    cs:__imp_GetLastError
0x18003fe74  mov     ecx, eax
0x18003fe76  sub     ecx, 1
0x18003fe79  jz      short loc_18003FE8A
0x18003fe7b  sub     ecx, 4
0x18003fe7e  jz      short loc_18003FEB5
0x18003fe80  sub     ecx, 2Dh ; '-'
0x18003fe83  jz      short loc_18003FE8A
0x18003fe85  cmp     ecx, 25h ; '%'
0x18003fe88  jnz     short loc_18003FEB5
0x18003fe8a  mov     r9d, 1; dwBufferSize
0x18003fe90  mov     [rsp+28h+arg_8], 1
0x18003fe95  lea     r8, [rsp+28h+arg_8]; lpFileInformation
0x18003fe9a  mov     rcx, rbx; hFile
0x18003fe9d  lea     edx, [r9+3]; FileInformationClass
0x18003fea1  call    cs:__imp_SetFileInformationByHandle
0x18003fea7  test    eax, eax
0x18003fea9  jnz     short loc_18003FEB3
0x18003feab  call    cs:__imp_GetLastError
0x18003feb1  jmp     short loc_18003FEB5
0x18003feb3  xor     eax, eax
0x18003feb5  add     rsp, 20h
0x18003feb9  pop     rbx
0x18003feba  retn
```
