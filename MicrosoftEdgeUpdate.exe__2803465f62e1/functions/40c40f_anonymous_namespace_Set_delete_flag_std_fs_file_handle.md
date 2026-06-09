# `anonymous namespace'::_Set_delete_flag(__std_fs_file_handle)

- ea: `0x40c40f`
- end: `0x40c473`
- name: `?_Set_delete_flag@?A0xf5c61f79@@YG?AW4__std_win_error@@W4__std_fs_file_handle@@@Z`
- size: `100`
- prototype: `DWORD __stdcall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x40c9a0`

## callees

- `0x40c40f`

## import_xrefs

- `KERNEL32!GetLastError` at `0x40c430`
- `KERNEL32!GetLastError` at `0x40c465`
- `KERNEL32!GetLastError` at `0x40c430`
- `KERNEL32!GetLastError` at `0x40c465`
- `KERNEL32!SetFileInformationByHandle` at `0x40c426`
- `KERNEL32!SetFileInformationByHandle` at `0x40c45b`
- `KERNEL32!SetFileInformationByHandle` at `0x40c426`
- `KERNEL32!SetFileInformationByHandle` at `0x40c45b`

## pseudocode

```c
DWORD __stdcall `anonymous namespace'::_Set_delete_flag(HANDLE hFile)
{
  DWORD result; // eax
  int FileInformation; // [esp+0h] [ebp-8h] BYREF
  char v3; // [esp+7h] [ebp-1h] BYREF

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
0x40c40f  push    ebp
0x40c410  mov     ebp, esp
0x40c412  push    ecx
0x40c413  push    ecx
0x40c414  push    4; dwBufferSize
0x40c416  lea     eax, [ebp+FileInformation]
0x40c419  mov     [ebp+FileInformation], 3
0x40c420  push    eax; lpFileInformation
0x40c421  push    15h; FileInformationClass
0x40c423  push    [ebp+hFile]; hFile
0x40c426  call    ds:SetFileInformationByHandle
0x40c42c  test    eax, eax
0x40c42e  jnz     short loc_40C46D
0x40c430  call    ds:GetLastError
0x40c436  mov     ecx, eax
0x40c438  sub     ecx, 1
0x40c43b  jz      short loc_40C44C
0x40c43d  sub     ecx, 4
0x40c440  jz      short locret_40C46F
0x40c442  sub     ecx, 2Dh ; '-'
0x40c445  jz      short loc_40C44C
0x40c447  sub     ecx, 25h ; '%'
0x40c44a  jnz     short locret_40C46F
0x40c44c  push    1; dwBufferSize
0x40c44e  lea     eax, [ebp+var_1]
0x40c451  mov     [ebp+var_1], 1
0x40c455  push    eax; lpFileInformation
0x40c456  push    4; FileInformationClass
0x40c458  push    [ebp+hFile]; hFile
0x40c45b  call    ds:SetFileInformationByHandle
0x40c461  test    eax, eax
0x40c463  jnz     short loc_40C46D
0x40c465  call    ds:GetLastError
0x40c46b  jmp     short locret_40C46F
0x40c46d  xor     eax, eax
0x40c46f  leave
0x40c470  retn    4
```
