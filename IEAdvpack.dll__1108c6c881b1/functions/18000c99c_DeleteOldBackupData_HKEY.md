# DeleteOldBackupData(HKEY__ *)

- ea: `0x18000c99c`
- end: `0x18000cc77`
- name: `?DeleteOldBackupData@@YAXPEAUHKEY__@@@Z`
- size: `731`
- prototype: `void __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callers

- `0x18000de30`

## callees

- `0x1800022bc`
- `0x18000c99c`
- `0x1800198d0`
- `0x18001a688`
- `0x18001b294`
- `0x18001b980`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x18000ca22`
- `KERNEL32!DeleteFileW` at `0x18000ca7e`
- `KERNEL32!DeleteFileW` at `0x18000cb99`
- `KERNEL32!DeleteFileW` at `0x18000cc4a`
- `KERNEL32!DeleteFileW` at `0x18000ca22`
- `KERNEL32!DeleteFileW` at `0x18000ca7e`
- `KERNEL32!DeleteFileW` at `0x18000cb99`
- `KERNEL32!DeleteFileW` at `0x18000cc4a`
- `KERNEL32!SetFileAttributesW` at `0x18000ca17`
- `KERNEL32!SetFileAttributesW` at `0x18000ca73`
- `KERNEL32!SetFileAttributesW` at `0x18000cb8c`
- `KERNEL32!SetFileAttributesW` at `0x18000cc3f`
- `KERNEL32!SetFileAttributesW` at `0x18000ca17`
- `KERNEL32!SetFileAttributesW` at `0x18000ca73`
- `KERNEL32!SetFileAttributesW` at `0x18000cb8c`
- `KERNEL32!SetFileAttributesW` at `0x18000cc3f`
- `ADVAPI32!RegQueryValueExW` at `0x18000c9ff`
- `ADVAPI32!RegQueryValueExW` at `0x18000cab0`
- `ADVAPI32!RegQueryValueExW` at `0x18000cc2b`
- `ADVAPI32!RegQueryValueExW` at `0x18000c9ff`
- `ADVAPI32!RegQueryValueExW` at `0x18000cab0`
- `ADVAPI32!RegQueryValueExW` at `0x18000cc2b`
- `ADVAPI32!RegCloseKey` at `0x18000cbf0`
- `ADVAPI32!RegCloseKey` at `0x18000cbf0`
- `ADVAPI32!RegOpenKeyExW` at `0x18000cae4`
- `ADVAPI32!RegOpenKeyExW` at `0x18000cae4`
- `ADVAPI32!RegEnumValueW` at `0x18000cbdd`
- `ADVAPI32!RegEnumValueW` at `0x18000cbdd`
- `SHLWAPI!StrRChrW` at `0x18000ca33`
- `SHLWAPI!StrRChrW` at `0x18000ca33`

## string_xrefs

- `0x18000ca96`: `BackupPath`
- `0x18000cc07`: `BackupRegPathName`

## pseudocode

```c
void __fastcall DeleteOldBackupData(HKEY hKey)
{
  unsigned __int16 *v2; // rax
  DWORD v3; // esi
  DWORD i; // edx
  WCHAR *v5; // rbx
  ULONG lpData; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Data[259]; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v10; // [rsp+256h] [rbp+156h]
  WCHAR pszMore[264]; // [rsp+260h] [rbp+160h] BYREF
  WCHAR pszPathOut[264]; // [rsp+470h] [rbp+370h] BYREF

  cbData = 518;
  v10 = 0;
  if ( !RegQueryValueExW(hKey, L"BackupFileName", 0, 0, (LPBYTE)Data, &cbData) )
  {
    SetFileAttributesW(Data, 0x80u);
    DeleteFileW(Data);
    v2 = StrRChrW(Data, 0, 0x2Eu);
    if ( v2 )
    {
      StringCchCopyW(v2, 260LL - (unsigned int)(v2 - Data), L".INI");
      SetFileAttributesW(Data, 0x80u);
      DeleteFileW(Data);
    }
    cbData = 520;
    if ( !RegQueryValueExW(hKey, L"BackupPath", 0, 0, (LPBYTE)Data, &cbData) )
    {
      phkResult = 0;
      if ( !RegOpenKeyExW(hKey, L"Catalogs", 0, 0x20019u, &phkResult) )
      {
        v3 = 0;
        for ( i = 0; ; i = v3 )
        {
          cbData = 260;
          if ( RegEnumValueW(phkResult, i, pszMore, &cbData, 0, 0, 0, 0) )
            break;
          StringCchCopyW(pszPathOut, 0x104u, Data);
          v5 = pszMore;
          if ( !(unsigned int)PathIsUnc2(pszMore) && !IsExtendedLengthDosDevicePath(pszMore) && pszMore[0] == 92 )
          {
            do
              ++v5;
            while ( *v5 == 92 );
          }
          PathCchCombineEx(pszPathOut, 0x104u, pszPathOut, v5, lpData);
          SetFileAttributesW(pszPathOut, 0x80u);
          DeleteFileW(pszPathOut);
          ++v3;
        }
        RegCloseKey(phkResult);
      }
    }
  }
  cbData = 518;
  v10 = 0;
  if ( !RegQueryValueExW(hKey, L"BackupRegPathName", 0, 0, (LPBYTE)Data, &cbData) )
  {
    SetFileAttributesW(Data, 0x80u);
    DeleteFileW(Data);
  }
}

```

## disassembly

```asm
0x18000c99c  mov     [rsp-8+arg_8], rbx
0x18000c9a1  mov     [rsp-8+arg_10], rsi
0x18000c9a6  push    rbp
0x18000c9a7  push    rdi
0x18000c9a8  push    r15
0x18000c9aa  lea     rbp, [rsp-590h]
0x18000c9b2  sub     rsp, 690h
0x18000c9b9  mov     rax, cs:__security_cookie
0x18000c9c0  xor     rax, rsp
0x18000c9c3  mov     [rbp+5A0h+var_20], rax
0x18000c9ca  xor     eax, eax
0x18000c9cc  mov     [rsp+6A0h+cbData], 206h
0x18000c9d4  mov     [rbp+5A0h+var_44A], ax
0x18000c9db  lea     rdx, aBackupfilename; "BackupFileName"
0x18000c9e2  lea     rax, [rsp+6A0h+cbData]
0x18000c9e7  xor     r9d, r9d; lpType
0x18000c9ea  mov     [rsp+6A0h+lpcbData], rax; lpcbData
0x18000c9ef  xor     r8d, r8d; lpReserved
0x18000c9f2  lea     rax, [rsp+6A0h+Data]
0x18000c9f7  mov     rdi, rcx
0x18000c9fa  mov     [rsp+6A0h+lpData], rax; lpData
0x18000c9ff  call    cs:__imp_RegQueryValueExW
0x18000ca05  test    eax, eax
0x18000ca07  jnz     loc_18000CBF6
0x18000ca0d  mov     edx, 80h; dwFileAttributes
0x18000ca12  lea     rcx, [rsp+6A0h+Data]; lpFileName
0x18000ca17  call    cs:__imp_SetFileAttributesW
0x18000ca1d  lea     rcx, [rsp+6A0h+Data]; lpFileName
0x18000ca22  call    cs:__imp_DeleteFileW
0x18000ca28  xor     edx, edx; pszEnd
0x18000ca2a  lea     rcx, [rsp+6A0h+Data]; pszStart
0x18000ca2f  lea     r8d, [rdx+2Eh]; wMatch
0x18000ca33  call    cs:__imp_StrRChrW
0x18000ca39  mov     r15d, 104h
0x18000ca3f  test    rax, rax
0x18000ca42  jz      short loc_18000CA84
0x18000ca44  lea     rdx, [rsp+6A0h+Data]
0x18000ca49  mov     rcx, rax
0x18000ca4c  sub     rcx, rdx
0x18000ca4f  lea     r8, aIni; ".INI"
0x18000ca56  sar     rcx, 1
0x18000ca59  mov     edx, r15d
0x18000ca5c  mov     ecx, ecx
0x18000ca5e  sub     rdx, rcx; unsigned __int64
0x18000ca61  mov     rcx, rax; unsigned __int16 *
0x18000ca64  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ca69  mov     edx, 80h; dwFileAttributes
0x18000ca6e  lea     rcx, [rsp+6A0h+Data]; lpFileName
0x18000ca73  call    cs:__imp_SetFileAttributesW
0x18000ca79  lea     rcx, [rsp+6A0h+Data]; lpFileName
0x18000ca7e  call    cs:__imp_DeleteFileW
0x18000ca84  lea     rax, [rsp+6A0h+cbData]
0x18000ca89  mov     [rsp+6A0h+cbData], 208h
0x18000ca91  mov     [rsp+6A0h+lpcbData], rax; lpcbData
0x18000ca96  lea     rdx, aBackuppath; "BackupPath"
0x18000ca9d  lea     rax, [rsp+6A0h+Data]
0x18000caa2  xor     r9d, r9d; lpType
0x18000caa5  xor     r8d, r8d; lpReserved
0x18000caa8  mov     [rsp+6A0h+lpData], rax; lpData
0x18000caad  mov     rcx, rdi; hKey
0x18000cab0  call    cs:__imp_RegQueryValueExW
0x18000cab6  test    eax, eax
0x18000cab8  jnz     loc_18000CBF6
0x18000cabe  lea     rax, [rsp+6A0h+phkResult]
0x18000cac3  mov     [rsp+6A0h+phkResult], 0
0x18000cacc  mov     r9d, 20019h; samDesired
0x18000cad2  mov     [rsp+6A0h+lpData], rax; phkResult
0x18000cad7  xor     r8d, r8d; ulOptions
0x18000cada  lea     rdx, aCatalogs; "Catalogs"
0x18000cae1  mov     rcx, rdi; hKey
0x18000cae4  call    cs:__imp_RegOpenKeyExW
0x18000caea  test    eax, eax
0x18000caec  jnz     loc_18000CBF6
0x18000caf2  xor     esi, esi
0x18000caf4  mov     [rsp+6A0h+var_668], rsi
0x18000caf9  xor     edx, edx
0x18000cafb  mov     [rsp+6A0h+var_670], rsi
0x18000cb00  mov     [rsp+6A0h+lpcbData], rsi
0x18000cb05  mov     [rsp+6A0h+lpData], rsi
0x18000cb0a  jmp     loc_18000CBC7
0x18000cb0f  lea     r8, [rsp+6A0h+Data]; unsigned __int16 *
0x18000cb14  mov     rdx, r15; unsigned __int64
0x18000cb17  lea     rcx, [rbp+5A0h+pszPathOut]; unsigned __int16 *
0x18000cb1e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000cb23  lea     r8, IsBackslash
0x18000cb2a  xor     edx, edx
0x18000cb2c  lea     rcx, [rbp+5A0h+pszMore]; unsigned __int16 *
0x18000cb33  lea     rbx, [rbp+5A0h+pszMore]
0x18000cb3a  call    PathIsUnc2
0x18000cb3f  test    eax, eax
0x18000cb41  jnz     short loc_18000CB67
0x18000cb43  lea     rcx, [rbp+5A0h+pszMore]; unsigned __int16 *
0x18000cb4a  call    ?IsExtendedLengthDosDevicePath@@YA_NPEBG@Z; IsExtendedLengthDosDevicePath(ushort const *)
0x18000cb4f  test    al, al
0x18000cb51  jnz     short loc_18000CB67
0x18000cb53  cmp     [rbp+5A0h+pszMore], 5Ch ; '\'
0x18000cb5b  jnz     short loc_18000CB67
0x18000cb5d  add     rbx, 2
0x18000cb61  cmp     word ptr [rbx], 5Ch ; '\'
0x18000cb65  jz      short loc_18000CB5D
0x18000cb67  mov     r9, rbx; pszMore
0x18000cb6a  lea     r8, [rbp+5A0h+pszPathOut]; pszPathIn
0x18000cb71  mov     rdx, r15; cchPathOut
0x18000cb74  lea     rcx, [rbp+5A0h+pszPathOut]; pszPathOut
0x18000cb7b  call    PathCchCombineEx
0x18000cb80  mov     edx, 80h; dwFileAttributes
0x18000cb85  lea     rcx, [rbp+5A0h+pszPathOut]; lpFileName
0x18000cb8c  call    cs:__imp_SetFileAttributesW
0x18000cb92  lea     rcx, [rbp+5A0h+pszPathOut]; lpFileName
0x18000cb99  call    cs:__imp_DeleteFileW
0x18000cb9f  mov     [rsp+6A0h+var_668], 0; lpcbData
0x18000cba8  inc     esi
0x18000cbaa  mov     [rsp+6A0h+var_670], 0; lpData
0x18000cbb3  mov     edx, esi; dwIndex
0x18000cbb5  mov     [rsp+6A0h+lpcbData], 0; lpType
0x18000cbbe  mov     [rsp+6A0h+lpData], 0; lpReserved
0x18000cbc7  mov     rcx, [rsp+6A0h+phkResult]; hKey
0x18000cbcc  lea     r9, [rsp+6A0h+cbData]; lpcchValueName
0x18000cbd1  lea     r8, [rbp+5A0h+pszMore]; lpValueName
0x18000cbd8  mov     [rsp+6A0h+cbData], r15d
0x18000cbdd  call    cs:__imp_RegEnumValueW
0x18000cbe3  test    eax, eax
0x18000cbe5  jz      loc_18000CB0F
0x18000cbeb  mov     rcx, [rsp+6A0h+phkResult]; hKey
0x18000cbf0  call    cs:__imp_RegCloseKey
0x18000cbf6  xor     eax, eax
0x18000cbf8  mov     [rsp+6A0h+cbData], 206h
0x18000cc00  mov     [rbp+5A0h+var_44A], ax
0x18000cc07  lea     rdx, aBackupregpathn; "BackupRegPathName"
0x18000cc0e  lea     rax, [rsp+6A0h+cbData]
0x18000cc13  xor     r9d, r9d; lpType
0x18000cc16  mov     [rsp+6A0h+lpcbData], rax; lpcbData
0x18000cc1b  xor     r8d, r8d; lpReserved
0x18000cc1e  lea     rax, [rsp+6A0h+Data]
0x18000cc23  mov     rcx, rdi; hKey
0x18000cc26  mov     [rsp+6A0h+lpData], rax; lpData
0x18000cc2b  call    cs:__imp_RegQueryValueExW
0x18000cc31  test    eax, eax
0x18000cc33  jnz     short loc_18000CC50
0x18000cc35  mov     edx, 80h; dwFileAttributes
0x18000cc3a  lea     rcx, [rsp+6A0h+Data]; lpFileName
0x18000cc3f  call    cs:__imp_SetFileAttributesW
0x18000cc45  lea     rcx, [rsp+6A0h+Data]; lpFileName
0x18000cc4a  call    cs:__imp_DeleteFileW
0x18000cc50  mov     rcx, [rbp+5A0h+var_20]
0x18000cc57  xor     rcx, rsp; StackCookie
0x18000cc5a  call    __security_check_cookie
0x18000cc5f  lea     r11, [rsp+6A0h+var_10]
0x18000cc67  mov     rbx, [r11+28h]
0x18000cc6b  mov     rsi, [r11+30h]
0x18000cc6f  mov     rsp, r11
0x18000cc72  pop     r15
0x18000cc74  pop     rdi
0x18000cc75  pop     rbp
0x18000cc76  retn
```
