# _anonymous_namespace_::_Set_delete_flag

- ea: `0x1801d219c`
- end: `0x1801d2213`
- name: `_anonymous_namespace_::_Set_delete_flag`
- size: `119`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1801d2824`

## callees

- `0x1801d219c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1801d21c6`
- `KERNEL32!GetLastError` at `0x1801d2203`
- `KERNEL32!GetLastError` at `0x1801d21c6`
- `KERNEL32!GetLastError` at `0x1801d2203`
- `KERNEL32!SetFileInformationByHandle` at `0x1801d21bc`
- `KERNEL32!SetFileInformationByHandle` at `0x1801d21f9`
- `KERNEL32!SetFileInformationByHandle` at `0x1801d21bc`
- `KERNEL32!SetFileInformationByHandle` at `0x1801d21f9`

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
0x1801d219c  push    rbx
0x1801d219e  sub     rsp, 20h
0x1801d21a2  mov     r9d, 4; dwBufferSize
0x1801d21a8  mov     [rsp+28h+FileInformation], 3
0x1801d21b0  lea     r8, [rsp+28h+FileInformation]; lpFileInformation
0x1801d21b5  mov     rbx, rcx
0x1801d21b8  lea     edx, [r9+11h]; FileInformationClass
0x1801d21bc  call    cs:__imp_SetFileInformationByHandle
0x1801d21c2  test    eax, eax
0x1801d21c4  jnz     short loc_1801D220B
0x1801d21c6  call    cs:__imp_GetLastError
0x1801d21cc  mov     ecx, eax
0x1801d21ce  sub     ecx, 1
0x1801d21d1  jz      short loc_1801D21E2
0x1801d21d3  sub     ecx, 4
0x1801d21d6  jz      short loc_1801D220D
0x1801d21d8  sub     ecx, 2Dh ; '-'
0x1801d21db  jz      short loc_1801D21E2
0x1801d21dd  cmp     ecx, 25h ; '%'
0x1801d21e0  jnz     short loc_1801D220D
0x1801d21e2  mov     r9d, 1; dwBufferSize
0x1801d21e8  mov     [rsp+28h+arg_8], 1
0x1801d21ed  lea     r8, [rsp+28h+arg_8]; lpFileInformation
0x1801d21f2  mov     rcx, rbx; hFile
0x1801d21f5  lea     edx, [r9+3]; FileInformationClass
0x1801d21f9  call    cs:__imp_SetFileInformationByHandle
0x1801d21ff  test    eax, eax
0x1801d2201  jnz     short loc_1801D220B
0x1801d2203  call    cs:__imp_GetLastError
0x1801d2209  jmp     short loc_1801D220D
0x1801d220b  xor     eax, eax
0x1801d220d  add     rsp, 20h
0x1801d2211  pop     rbx
0x1801d2212  retn
```
