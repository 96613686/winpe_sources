# StartLogging(ushort const *)

- ea: `0x180013c98`
- end: `0x180013e57`
- name: `?StartLogging@@YAXPEBG@Z`
- size: `447`
- prototype: `void __fastcall(LPCWSTR lpValueName)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x180014440`

## callees

- `0x1800022bc`
- `0x180013c98`
- `0x1800198d0`
- `0x18001a688`
- `0x18001b294`
- `0x18001b980`

## import_xrefs

- `KERNEL32!GetWindowsDirectoryW` at `0x180013d83`
- `KERNEL32!GetWindowsDirectoryW` at `0x180013d83`
- `KERNEL32!CreateFileW` at `0x180013e15`
- `KERNEL32!CreateFileW` at `0x180013e15`
- `KERNEL32!SetFilePointer` at `0x180013e36`
- `KERNEL32!SetFilePointer` at `0x180013e36`
- `KERNEL32!GetProfileStringW` at `0x180013ceb`
- `KERNEL32!GetProfileStringW` at `0x180013ceb`
- `ADVAPI32!RegQueryValueExW` at `0x180013d4d`
- `ADVAPI32!RegQueryValueExW` at `0x180013d4d`
- `ADVAPI32!RegCloseKey` at `0x180013d61`
- `ADVAPI32!RegCloseKey` at `0x180013d61`
- `ADVAPI32!RegOpenKeyExW` at `0x180013d19`
- `ADVAPI32!RegOpenKeyExW` at `0x180013d19`

## pseudocode

```c
void __fastcall StartLogging(LPCWSTR lpValueName)
{
  WCHAR *v2; // rbx
  HANDLE FileW; // rax
  ULONG nSize; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR ReturnedString[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[264]; // [rsp+260h] [rbp+160h] BYREF

  phkResult = 0;
  ReturnedString[0] = 0;
  GetProfileStringW(L"RegBackup", lpValueName, &word_18001DE6C, ReturnedString, 0x104u);
  if ( ReturnedString[0] )
    goto LABEL_7;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Advanced INF Setup", 0, 0x20019u, &phkResult) )
  {
    cbData = 520;
    if ( RegQueryValueExW(phkResult, lpValueName, 0, 0, (LPBYTE)ReturnedString, &cbData) )
      ReturnedString[0] = 0;
    RegCloseKey(phkResult);
  }
  if ( ReturnedString[0] )
  {
LABEL_7:
    if ( ReturnedString[1] == 58 )
    {
      StringCchCopyW(Buffer, 0x104u, ReturnedString);
    }
    else
    {
      GetWindowsDirectoryW(Buffer, 0x104u);
      v2 = ReturnedString;
      if ( !(unsigned int)PathIsUnc2(ReturnedString)
        && !IsExtendedLengthDosDevicePath(ReturnedString)
        && ReturnedString[0] == 92 )
      {
        do
          ++v2;
        while ( *v2 == 92 );
      }
      PathCchCombineEx(Buffer, 0x104u, Buffer, v2, nSize);
    }
    FileW = CreateFileW(Buffer, 0x40000000u, 1u, 0, 4u, 0x80u, 0);
    g_hLogFile = FileW;
    if ( FileW != (HANDLE)-1LL )
      SetFilePointer(FileW, 0, 0, 2u);
  }
}

```

## disassembly

```asm
0x180013c98  push    rbp
0x180013c9a  push    rbx
0x180013c9b  push    rsi
0x180013c9c  push    rdi
0x180013c9d  lea     rbp, [rsp-388h]
0x180013ca5  sub     rsp, 488h
0x180013cac  mov     rax, cs:__security_cookie
0x180013cb3  xor     rax, rsp
0x180013cb6  mov     [rbp+3A0h+var_30], rax
0x180013cbd  mov     rbx, rcx
0x180013cc0  lea     r9, [rsp+4A0h+ReturnedString]; lpReturnedString
0x180013cc5  xor     edi, edi
0x180013cc7  lea     r8, word_18001DE6C; lpDefault
0x180013cce  mov     rdx, rcx; lpKeyName
0x180013cd1  mov     [rsp+4A0h+phkResult], rdi
0x180013cd6  mov     esi, 104h
0x180013cdb  mov     [rsp+4A0h+ReturnedString], di
0x180013ce0  lea     rcx, aRegbackup; "RegBackup"
0x180013ce7  mov     [rsp+4A0h+nSize], esi; nSize
0x180013ceb  call    cs:__imp_GetProfileStringW
0x180013cf1  cmp     [rsp+4A0h+ReturnedString], di
0x180013cf6  jnz     short loc_180013D72
0x180013cf8  lea     rax, [rsp+4A0h+phkResult]
0x180013cfd  mov     r9d, 20019h; samDesired
0x180013d03  xor     r8d, r8d; ulOptions
0x180013d06  mov     qword ptr [rsp+4A0h+nSize], rax; phkResult
0x180013d0b  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Advanced INF Setup"
0x180013d12  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180013d19  call    cs:__imp_RegOpenKeyExW
0x180013d1f  test    eax, eax
0x180013d21  jnz     short loc_180013D67
0x180013d23  mov     rcx, [rsp+4A0h+phkResult]; hKey
0x180013d28  lea     rax, [rsp+4A0h+cbData]
0x180013d2d  mov     [rsp+4A0h+lpcbData], rax; lpcbData
0x180013d32  xor     r9d, r9d; lpType
0x180013d35  lea     rax, [rsp+4A0h+ReturnedString]
0x180013d3a  mov     [rsp+4A0h+cbData], 208h
0x180013d42  xor     r8d, r8d; lpReserved
0x180013d45  mov     qword ptr [rsp+4A0h+nSize], rax; dwFlags
0x180013d4a  mov     rdx, rbx; lpValueName
0x180013d4d  call    cs:__imp_RegQueryValueExW
0x180013d53  test    eax, eax
0x180013d55  jz      short loc_180013D5C
0x180013d57  mov     [rsp+4A0h+ReturnedString], di
0x180013d5c  mov     rcx, [rsp+4A0h+phkResult]; hKey
0x180013d61  call    cs:__imp_RegCloseKey
0x180013d67  cmp     [rsp+4A0h+ReturnedString], di
0x180013d6c  jz      loc_180013E3C
0x180013d72  cmp     [rsp+4A0h+var_44E], 3Ah ; ':'
0x180013d78  lea     rcx, [rbp+3A0h+Buffer]; unsigned __int16 *
0x180013d7f  jz      short loc_180013DE0
0x180013d81  mov     edx, esi; uSize
0x180013d83  call    cs:__imp_GetWindowsDirectoryW
0x180013d89  lea     r8, IsBackslash
0x180013d90  xor     edx, edx
0x180013d92  lea     rcx, [rsp+4A0h+ReturnedString]; unsigned __int16 *
0x180013d97  lea     rbx, [rsp+4A0h+ReturnedString]
0x180013d9c  call    PathIsUnc2
0x180013da1  test    eax, eax
0x180013da3  jnz     short loc_180013DC5
0x180013da5  lea     rcx, [rsp+4A0h+ReturnedString]; unsigned __int16 *
0x180013daa  call    ?IsExtendedLengthDosDevicePath@@YA_NPEBG@Z; IsExtendedLengthDosDevicePath(ushort const *)
0x180013daf  test    al, al
0x180013db1  jnz     short loc_180013DC5
0x180013db3  cmp     [rsp+4A0h+ReturnedString], 5Ch ; '\'
0x180013db9  jnz     short loc_180013DC5
0x180013dbb  add     rbx, 2
0x180013dbf  cmp     word ptr [rbx], 5Ch ; '\'
0x180013dc3  jz      short loc_180013DBB
0x180013dc5  mov     r9, rbx; pszMore
0x180013dc8  lea     r8, [rbp+3A0h+Buffer]; pszPathIn
0x180013dcf  mov     rdx, rsi; cchPathOut
0x180013dd2  lea     rcx, [rbp+3A0h+Buffer]; pszPathOut
0x180013dd9  call    PathCchCombineEx
0x180013dde  jmp     short loc_180013DED
0x180013de0  lea     r8, [rsp+4A0h+ReturnedString]; unsigned __int16 *
0x180013de5  mov     rdx, rsi; unsigned __int64
0x180013de8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180013ded  xor     r9d, r9d; lpSecurityAttributes
0x180013df0  mov     [rsp+4A0h+hTemplateFile], rdi; hTemplateFile
0x180013df5  mov     dword ptr [rsp+4A0h+lpcbData], 80h; dwFlagsAndAttributes
0x180013dfd  lea     rcx, [rbp+3A0h+Buffer]; lpFileName
0x180013e04  mov     edx, 40000000h; dwDesiredAccess
0x180013e09  mov     [rsp+4A0h+nSize], 4; dwCreationDisposition
0x180013e11  lea     r8d, [r9+1]; dwShareMode
0x180013e15  call    cs:__imp_CreateFileW
0x180013e1b  mov     cs:?g_hLogFile@@3PEAXEA, rax; void * g_hLogFile
0x180013e22  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180013e26  jz      short loc_180013E3C
0x180013e28  mov     r9d, 2; dwMoveMethod
0x180013e2e  xor     r8d, r8d; lpDistanceToMoveHigh
0x180013e31  xor     edx, edx; lDistanceToMove
0x180013e33  mov     rcx, rax; hFile
0x180013e36  call    cs:__imp_SetFilePointer
0x180013e3c  mov     rcx, [rbp+3A0h+var_30]
0x180013e43  xor     rcx, rsp; StackCookie
0x180013e46  call    __security_check_cookie
0x180013e4b  add     rsp, 488h
0x180013e52  pop     rdi
0x180013e53  pop     rsi
0x180013e54  pop     rbx
0x180013e55  pop     rbp
0x180013e56  retn
```
