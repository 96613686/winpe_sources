# NeedToRunGrpconv

- ea: `0x180017728`
- end: `0x180017838`
- name: `NeedToRunGrpconv`
- size: `272`
- prototype: `_BOOL8()`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callers

- `0x180004880`

## callees

- `0x180017434`
- `0x180017728`
- `0x18001a688`
- `0x18001b294`
- `0x18001b980`

## import_xrefs

- `KERNEL32!GetWindowsDirectoryW` at `0x18001774f`
- `KERNEL32!GetWindowsDirectoryW` at `0x18001774f`
- `KERNEL32!GetFileAttributesW` at `0x180017787`
- `KERNEL32!GetFileAttributesW` at `0x1800177e8`
- `KERNEL32!GetFileAttributesW` at `0x180017787`
- `KERNEL32!GetFileAttributesW` at `0x1800177e8`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800177ab`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800177ab`

## string_xrefs

- `0x1800177f3`: `RenameFiles`
- `0x180017803`: `DeleteFiles`
- `0x180017813`: `PreConvRenameFiles`

## pseudocode

```c
_BOOL8 NeedToRunGrpconv()
{
  _BOOL8 result; // rax
  ULONG v1; // [rsp+20h] [rbp-238h]
  ULONG v2; // [rsp+20h] [rbp-238h]
  WCHAR Buffer[264]; // [rsp+30h] [rbp-228h] BYREF

  GetWindowsDirectoryW(Buffer, 0x104u);
  PathIsUnc2(L"setup.ini");
  PathCchCombineEx(Buffer, 0x104u, Buffer, L"setup.ini", v1);
  if ( GetFileAttributesW(Buffer) != -1 )
    return 1;
  if ( ExpandEnvironmentStringsW(L"%USERPROFILE%", Buffer, 0x104u) )
  {
    PathIsUnc2(L"setup.ini");
    PathCchCombineEx(Buffer, 0x104u, Buffer, L"setup.ini", v2);
    if ( GetFileAttributesW(Buffer) != -1 )
      return 1;
  }
  result = CheckGrpconvRegkey(L"RenameFiles");
  if ( !result )
  {
    result = CheckGrpconvRegkey(L"DeleteFiles");
    if ( !result )
      return CheckGrpconvRegkey(L"PreConvRenameFiles");
  }
  return result;
}

```

## disassembly

```asm
0x180017728  push    rbx
0x18001772a  sub     rsp, 250h
0x180017731  mov     rax, cs:__security_cookie
0x180017738  xor     rax, rsp
0x18001773b  mov     [rsp+258h+var_18], rax
0x180017743  mov     ebx, 104h
0x180017748  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x18001774d  mov     edx, ebx; uSize
0x18001774f  call    cs:__imp_GetWindowsDirectoryW
0x180017755  lea     r8, IsBackslash
0x18001775c  xor     edx, edx
0x18001775e  lea     rcx, aSetupIni; "setup.ini"
0x180017765  call    PathIsUnc2
0x18001776a  lea     r9, aSetupIni; "setup.ini"
0x180017771  mov     edx, ebx; cchPathOut
0x180017773  lea     r8, [rsp+258h+Buffer]; pszPathIn
0x180017778  lea     rcx, [rsp+258h+Buffer]; pszPathOut
0x18001777d  call    PathCchCombineEx
0x180017782  lea     rcx, [rsp+258h+Buffer]; lpFileName
0x180017787  call    cs:__imp_GetFileAttributesW
0x18001778d  cmp     eax, 0FFFFFFFFh
0x180017790  jz      short loc_18001779C
0x180017792  mov     eax, 1
0x180017797  jmp     loc_18001781F
0x18001779c  mov     r8d, ebx; nSize
0x18001779f  lea     rdx, [rsp+258h+Buffer]; lpDst
0x1800177a4  lea     rcx, Src; "%USERPROFILE%"
0x1800177ab  call    cs:__imp_ExpandEnvironmentStringsW
0x1800177b1  test    eax, eax
0x1800177b3  jz      short loc_1800177F3
0x1800177b5  lea     r8, IsBackslash
0x1800177bc  xor     edx, edx
0x1800177be  lea     rcx, aSetupIni; "setup.ini"
0x1800177c5  call    PathIsUnc2
0x1800177ca  lea     r9, aSetupIni; "setup.ini"
0x1800177d1  mov     rdx, rbx; cchPathOut
0x1800177d4  lea     r8, [rsp+258h+Buffer]; pszPathIn
0x1800177d9  lea     rcx, [rsp+258h+Buffer]; pszPathOut
0x1800177de  call    PathCchCombineEx
0x1800177e3  lea     rcx, [rsp+258h+Buffer]; lpFileName
0x1800177e8  call    cs:__imp_GetFileAttributesW
0x1800177ee  cmp     eax, 0FFFFFFFFh
0x1800177f1  jnz     short loc_180017792
0x1800177f3  lea     rcx, aRenamefiles; "RenameFiles"
0x1800177fa  call    CheckGrpconvRegkey
0x1800177ff  test    eax, eax
0x180017801  jnz     short loc_18001781F
0x180017803  lea     rcx, aDeletefiles; "DeleteFiles"
0x18001780a  call    CheckGrpconvRegkey
0x18001780f  test    eax, eax
0x180017811  jnz     short loc_18001781F
0x180017813  lea     rcx, aPreconvrenamef; "PreConvRenameFiles"
0x18001781a  call    CheckGrpconvRegkey
0x18001781f  mov     rcx, [rsp+258h+var_18]
0x180017827  xor     rcx, rsp; StackCookie
0x18001782a  call    __security_check_cookie
0x18001782f  add     rsp, 250h
0x180017836  pop     rbx
0x180017837  retn
```
