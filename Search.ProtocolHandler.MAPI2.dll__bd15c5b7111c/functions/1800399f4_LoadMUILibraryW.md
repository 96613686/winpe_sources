# LoadMUILibraryW

- ea: `0x1800399f4`
- end: `0x180039e67`
- name: `LoadMUILibraryW`
- size: `1139`
- prototype: `HINSTANCE __stdcall(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x18001f41c`

## callees

- `0x180002300`
- `0x180008ae0`
- `0x180039310`
- `0x180039390`
- `0x1800394a0`
- `0x1800395c8`
- `0x18003963c`
- `0x1800397b0`
- `0x1800399f4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180039cc6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180039e0d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180039e3c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180039cc6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180039e0d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180039e3c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180039a4e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180039e2b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180039a4e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180039e2b`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180039ad7`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180039ad7`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x180039a91`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x180039a91`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x180039af7`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x180039af7`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetSystemDefaultUILanguage` at `0x180039bb5`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetSystemDefaultUILanguage` at `0x180039bb5`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
HINSTANCE __stdcall LoadMUILibraryW(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)
{
  HINSTANCE result; // rax
  HMODULE v5; // rdi
  WCHAR *v6; // rsi
  LANGID UserDefaultUILanguage; // r14
  HINSTANCE MUIFile; // rbx
  LANGID SystemDefaultUILanguage; // ax
  LANGID v10; // r15
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 InstallLanguage; // r14
  char OSType; // al
  LPWSTR FilePart; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v21[176]; // [rsp+40h] [rbp-C0h] BYREF
  _WORD v22[88]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v23[176]; // [rsp+1A0h] [rbp+A0h] BYREF
  WCHAR Buffer[264]; // [rsp+250h] [rbp+150h] BYREF

  FilePart = 0;
  if ( !pszFullModuleName )
    return 0;
  dword_18005A460 = GetOSType(pszFullModuleName, dwLangConvention, LangID);
  result = LoadLibraryExW(pszFullModuleName, 0, dword_18005A460 & 0x20 | 2u);
  v5 = result;
  if ( !result )
    return 0;
  if ( (dword_18005A460 & 0x20) != 0 )
    return result;
  if ( !SearchPathW(0, pszFullModuleName, 0, 0x104u, Buffer, &FilePart) )
  {
    FreeLibrary(v5);
    return 0;
  }
  if ( FilePart )
  {
    v6 = Buffer;
    *(FilePart - 1) = 0;
  }
  else
  {
    v6 = 0;
    FilePart = Buffer;
  }
  if ( FindResourceExW(v5, L"MUI", (LPCWSTR)1, 0) )
  {
    if ( (dword_18005A460 & 4) != 0 )
    {
      UserDefaultUILanguage = GetUserDefaultUILanguage();
      if ( UserDefaultUILanguage == 1028 )
        UserDefaultUILanguage = GetCHTLangauge();
      while ( (unsigned int)LookupLangID(UserDefaultUILanguage, v21, v23, v22) )
      {
        MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v21, FilePart);
        if ( MUIFile )
          goto LABEL_42;
        MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v23, FilePart);
        if ( MUIFile )
          goto LABEL_42;
        if ( v22[0] )
        {
          MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v22, FilePart);
          if ( MUIFile )
            goto LABEL_42;
        }
        if ( UserDefaultUILanguage != 3076 )
        {
          SystemDefaultUILanguage = GetSystemDefaultUILanguage();
          v10 = SystemDefaultUILanguage;
          if ( SystemDefaultUILanguage != UserDefaultUILanguage )
          {
            if ( !(unsigned int)LookupLangID(SystemDefaultUILanguage, v21, v23, v22) )
              break;
            MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v21, FilePart);
            if ( MUIFile )
              goto LABEL_42;
            MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v23, FilePart);
            if ( MUIFile )
              goto LABEL_42;
            if ( v22[0] )
            {
              MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v22, FilePart);
              if ( MUIFile )
                goto LABEL_42;
            }
          }
          if ( UserDefaultUILanguage != 1033 && v10 != 1033 )
          {
            LookupLangID(1033, v21, v23, 0);
            MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v21, FilePart);
            if ( MUIFile )
              goto LABEL_42;
          }
          MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, 0, FilePart);
          if ( MUIFile )
            goto LABEL_42;
          break;
        }
        UserDefaultUILanguage = 1028;
      }
    }
    else if ( (dword_18005A460 & 3) != 0 )
    {
      InstallLanguage = (unsigned __int16)GetInstallLanguage();
      if ( (unsigned int)LookupLangID(InstallLanguage, v21, v23, v22) )
      {
        if ( (MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v21, FilePart)) != 0
          || (MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v23, FilePart)) != 0
          || v22[0] && (MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v22, FilePart)) != 0
          || (_WORD)InstallLanguage != 1033
          && (LookupLangID(1033, v21, v23, 0), (MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v21, FilePart)) != 0)
          || (MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, 0, FilePart)) != 0 )
        {
LABEL_42:
          FreeLibrary(v5);
          return MUIFile;
        }
      }
    }
  }
  if ( ((unsigned __int8)v5 & 1) != 0 )
  {
    FreeLibrary(v5);
    if ( (GetOSType(v12, v11, v13) & 0x38) != 0 )
    {
      StringCchPrintfW(Buffer, 0x104u, L"%s\\%s", v6, FilePart);
      return (HINSTANCE)MapMUIFile(Buffer, 1);
    }
    else
    {
      OSType = GetOSType(v15, v14, v16);
      return LoadLibraryExW(pszFullModuleName, 0, (OSType & 0x26) != 0);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1800399f4  push    rbp
0x1800399f6  push    rbx
0x1800399f7  push    rsi
0x1800399f8  push    rdi
0x1800399f9  push    r12
0x1800399fb  push    r13
0x1800399fd  push    r14
0x1800399ff  push    r15
0x180039a01  lea     rbp, [rsp-378h]
0x180039a09  sub     rsp, 478h
0x180039a10  mov     rax, cs:__security_cookie
0x180039a17  xor     rax, rsp
0x180039a1a  mov     [rbp+3B0h+var_50], rax
0x180039a21  xor     r13d, r13d
0x180039a24  mov     r12, rcx
0x180039a27  mov     [rsp+4B0h+FilePart], r13
0x180039a2c  test    rcx, rcx
0x180039a2f  jz      loc_180039E42
0x180039a35  call    GetOSType
0x180039a3a  mov     cs:dword_18005A460, eax
0x180039a40  xor     edx, edx; hFile
0x180039a42  and     eax, 20h
0x180039a45  mov     rcx, r12; lpLibFileName
0x180039a48  or      eax, 2
0x180039a4b  mov     r8d, eax; dwFlags
0x180039a4e  call    cs:__imp_LoadLibraryExW
0x180039a54  mov     rdi, rax
0x180039a57  test    rax, rax
0x180039a5a  jz      loc_180039E42
0x180039a60  test    byte ptr cs:dword_18005A460, 20h
0x180039a67  jnz     loc_180039E44
0x180039a6d  lea     rax, [rsp+4B0h+FilePart]
0x180039a72  mov     r9d, 104h; nBufferLength
0x180039a78  mov     [rsp+4B0h+lpFilePart], rax; lpFilePart
0x180039a7d  xor     r8d, r8d; lpExtension
0x180039a80  lea     rax, [rbp+3B0h+Buffer]
0x180039a87  mov     rdx, r12; lpFileName
0x180039a8a  xor     ecx, ecx; lpPath
0x180039a8c  mov     [rsp+4B0h+lpBuffer], rax; lpBuffer
0x180039a91  call    cs:__imp_SearchPathW
0x180039a97  test    eax, eax
0x180039a99  jz      loc_180039E39
0x180039a9f  mov     rcx, [rsp+4B0h+FilePart]
0x180039aa4  test    rcx, rcx
0x180039aa7  jnz     short loc_180039ABA
0x180039aa9  lea     rax, [rbp+3B0h+Buffer]
0x180039ab0  mov     esi, r13d
0x180039ab3  mov     [rsp+4B0h+FilePart], rax
0x180039ab8  jmp     short loc_180039AC6
0x180039aba  lea     rsi, [rbp+3B0h+Buffer]
0x180039ac1  mov     [rcx-2], r13w
0x180039ac6  xor     r9d, r9d; wLanguage
0x180039ac9  lea     rdx, Type; "MUI"
0x180039ad0  mov     rcx, rdi; hModule
0x180039ad3  lea     r8d, [r9+1]; lpName
0x180039ad7  call    cs:__imp_FindResourceExW
0x180039add  test    rax, rax
0x180039ae0  jz      loc_180039CB9
0x180039ae6  mov     eax, cs:dword_18005A460
0x180039aec  test    al, 4
0x180039aee  jz      loc_180039D16
0x180039af4  mov     rbx, r13
0x180039af7  call    cs:__imp_GetUserDefaultUILanguage
0x180039afd  mov     r15d, 404h
0x180039b03  movzx   r14d, ax
0x180039b07  cmp     ax, r15w
0x180039b0b  jnz     short loc_180039B16
0x180039b0d  call    GetCHTLangauge
0x180039b12  movzx   r14d, ax
0x180039b16  lea     r9, [rbp+3B0h+var_3C0]
0x180039b1a  movzx   ecx, r14w
0x180039b1e  lea     r8, [rbp+3B0h+var_310]
0x180039b25  lea     rdx, [rsp+4B0h+var_470]
0x180039b2a  call    LookupLangID
0x180039b2f  test    eax, eax
0x180039b31  jz      loc_180039E01
0x180039b37  mov     r9, [rsp+4B0h+FilePart]
0x180039b3c  lea     r8, [rsp+4B0h+var_470]
0x180039b41  mov     rdx, rsi
0x180039b44  mov     rcx, rdi
0x180039b47  call    LoadMUIFile
0x180039b4c  mov     rbx, rax
0x180039b4f  test    rax, rax
0x180039b52  jnz     loc_180039E0A
0x180039b58  mov     r9, [rsp+4B0h+FilePart]
0x180039b5d  lea     r8, [rbp+3B0h+var_310]
0x180039b64  mov     rdx, rsi
0x180039b67  mov     rcx, rdi
0x180039b6a  call    LoadMUIFile
0x180039b6f  mov     rbx, rax
0x180039b72  test    rax, rax
0x180039b75  jnz     loc_180039E0A
0x180039b7b  cmp     [rbp+3B0h+var_3C0], r13w
0x180039b80  jz      short loc_180039BA2
0x180039b82  mov     r9, [rsp+4B0h+FilePart]
0x180039b87  lea     r8, [rbp+3B0h+var_3C0]
0x180039b8b  mov     rdx, rsi
0x180039b8e  mov     rcx, rdi
0x180039b91  call    LoadMUIFile
0x180039b96  mov     rbx, rax
0x180039b99  test    rax, rax
0x180039b9c  jnz     loc_180039E0A
0x180039ba2  mov     eax, 0C04h
0x180039ba7  cmp     r14w, ax
0x180039bab  jnz     short loc_180039BB5
0x180039bad  mov     r14d, r15d
0x180039bb0  jmp     loc_180039B16
0x180039bb5  call    cs:__imp_GetSystemDefaultUILanguage
0x180039bbb  movzx   r15d, ax
0x180039bbf  cmp     ax, r14w
0x180039bc3  jz      loc_180039C54
0x180039bc9  lea     r9, [rbp+3B0h+var_3C0]
0x180039bcd  movzx   ecx, ax
0x180039bd0  lea     r8, [rbp+3B0h+var_310]
0x180039bd7  lea     rdx, [rsp+4B0h+var_470]
0x180039bdc  call    LookupLangID
0x180039be1  test    eax, eax
0x180039be3  jz      loc_180039CB9
0x180039be9  mov     r9, [rsp+4B0h+FilePart]
0x180039bee  lea     r8, [rsp+4B0h+var_470]
0x180039bf3  mov     rdx, rsi
0x180039bf6  mov     rcx, rdi
0x180039bf9  call    LoadMUIFile
0x180039bfe  mov     rbx, rax
0x180039c01  test    rax, rax
0x180039c04  jnz     loc_180039E0A
0x180039c0a  mov     r9, [rsp+4B0h+FilePart]
0x180039c0f  lea     r8, [rbp+3B0h+var_310]
0x180039c16  mov     rdx, rsi
0x180039c19  mov     rcx, rdi
0x180039c1c  call    LoadMUIFile
0x180039c21  mov     rbx, rax
0x180039c24  test    rax, rax
0x180039c27  jnz     loc_180039E0A
0x180039c2d  cmp     [rbp+3B0h+var_3C0], r13w
0x180039c32  jz      short loc_180039C54
0x180039c34  mov     r9, [rsp+4B0h+FilePart]
0x180039c39  lea     r8, [rbp+3B0h+var_3C0]
0x180039c3d  mov     rdx, rsi
0x180039c40  mov     rcx, rdi
0x180039c43  call    LoadMUIFile
0x180039c48  mov     rbx, rax
0x180039c4b  test    rax, rax
0x180039c4e  jnz     loc_180039E0A
0x180039c54  mov     ecx, 409h
0x180039c59  cmp     cx, r14w
0x180039c5d  jz      short loc_180039C9A
0x180039c5f  cmp     cx, r15w
0x180039c63  jz      short loc_180039C9A
0x180039c65  xor     r9d, r9d
0x180039c68  lea     r8, [rbp+3B0h+var_310]
0x180039c6f  lea     rdx, [rsp+4B0h+var_470]
0x180039c74  call    LookupLangID
0x180039c79  mov     r9, [rsp+4B0h+FilePart]
0x180039c7e  lea     r8, [rsp+4B0h+var_470]
0x180039c83  mov     rdx, rsi
0x180039c86  mov     rcx, rdi
0x180039c89  call    LoadMUIFile
0x180039c8e  mov     rbx, rax
0x180039c91  test    rax, rax
0x180039c94  jnz     loc_180039E0A
0x180039c9a  mov     r9, [rsp+4B0h+FilePart]
0x180039c9f  xor     r8d, r8d
0x180039ca2  mov     rdx, rsi
0x180039ca5  mov     rcx, rdi
0x180039ca8  call    LoadMUIFile
0x180039cad  mov     rbx, rax
0x180039cb0  test    rax, rax
0x180039cb3  jnz     loc_180039E0A
0x180039cb9  test    dil, 1
0x180039cbd  jz      loc_180039E34
0x180039cc3  mov     rcx, rdi; hLibModule
0x180039cc6  call    cs:__imp_FreeLibrary
0x180039ccc  call    GetOSType
0x180039cd1  test    al, 38h
0x180039cd3  jz      loc_180039E18
0x180039cd9  mov     rax, [rsp+4B0h+FilePart]
0x180039cde  lea     r8, aSS_0; "%s\\%s"
0x180039ce5  mov     r9, rsi
0x180039ce8  mov     [rsp+4B0h+lpBuffer], rax
0x180039ced  mov     edx, 104h; unsigned __int64
0x180039cf2  lea     rcx, [rbp+3B0h+Buffer]; unsigned __int16 *
0x180039cf9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180039cfe  xor     r8d, r8d
0x180039d01  lea     rcx, [rbp+3B0h+Buffer]
0x180039d08  lea     edx, [r8+1]
0x180039d0c  call    MapMUIFile
0x180039d11  jmp     loc_180039E31
0x180039d16  test    al, 3
0x180039d18  jz      short loc_180039CB9
0x180039d1a  call    GetInstallLanguage
0x180039d1f  lea     r9, [rbp+3B0h+var_3C0]
0x180039d23  movzx   ecx, ax
0x180039d26  lea     r8, [rbp+3B0h+var_310]
0x180039d2d  movzx   r14d, ax
0x180039d31  lea     rdx, [rsp+4B0h+var_470]
0x180039d36  call    LookupLangID
0x180039d3b  test    eax, eax
0x180039d3d  jz      loc_180039CB9
0x180039d43  mov     r9, [rsp+4B0h+FilePart]
0x180039d48  lea     r8, [rsp+4B0h+var_470]
0x180039d4d  mov     rdx, rsi
0x180039d50  mov     rcx, rdi
0x180039d53  call    LoadMUIFile
0x180039d58  mov     rbx, rax
0x180039d5b  test    rax, rax
0x180039d5e  jnz     loc_180039E0A
0x180039d64  mov     r9, [rsp+4B0h+FilePart]
0x180039d69  lea     r8, [rbp+3B0h+var_310]
0x180039d70  mov     rdx, rsi
0x180039d73  mov     rcx, rdi
0x180039d76  call    LoadMUIFile
0x180039d7b  mov     rbx, rax
0x180039d7e  test    rax, rax
0x180039d81  jnz     loc_180039E0A
0x180039d87  cmp     [rbp+3B0h+var_3C0], r13w
0x180039d8c  jz      short loc_180039DAA
0x180039d8e  mov     r9, [rsp+4B0h+FilePart]
0x180039d93  lea     r8, [rbp+3B0h+var_3C0]
0x180039d97  mov     rdx, rsi
0x180039d9a  mov     rcx, rdi
0x180039d9d  call    LoadMUIFile
0x180039da2  mov     rbx, rax
0x180039da5  test    rax, rax
0x180039da8  jnz     short loc_180039E0A
0x180039daa  mov     ecx, 409h
0x180039daf  cmp     cx, r14w
0x180039db3  jz      short loc_180039DE6
0x180039db5  xor     r9d, r9d
0x180039db8  lea     r8, [rbp+3B0h+var_310]
0x180039dbf  lea     rdx, [rsp+4B0h+var_470]
0x180039dc4  call    LookupLangID
0x180039dc9  mov     r9, [rsp+4B0h+FilePart]
0x180039dce  lea     r8, [rsp+4B0h+var_470]
0x180039dd3  mov     rdx, rsi
0x180039dd6  mov     rcx, rdi
0x180039dd9  call    LoadMUIFile
0x180039dde  mov     rbx, rax
0x180039de1  test    rax, rax
0x180039de4  jnz     short loc_180039E0A
0x180039de6  mov     r9, [rsp+4B0h+FilePart]
0x180039deb  xor     r8d, r8d
0x180039dee  mov     rdx, rsi
0x180039df1  mov     rcx, rdi
0x180039df4  call    LoadMUIFile
0x180039df9  mov     rbx, rax
0x180039dfc  test    rax, rax
0x180039dff  jnz     short loc_180039E0A
0x180039e01  test    rbx, rbx
0x180039e04  jz      loc_180039CB9
0x180039e0a  mov     rcx, rdi; hLibModule
0x180039e0d  call    cs:__imp_FreeLibrary
0x180039e13  mov     rax, rbx
0x180039e16  jmp     short loc_180039E44
0x180039e18  call    GetOSType
0x180039e1d  test    al, 26h
0x180039e1f  mov     r8d, r13d
0x180039e22  mov     rcx, r12; lpLibFileName
0x180039e25  setnz   r8b; dwFlags
0x180039e29  xor     edx, edx; hFile
0x180039e2b  call    cs:__imp_LoadLibraryExW
0x180039e31  mov     rdi, rax
0x180039e34  mov     rax, rdi
0x180039e37  jmp     short loc_180039E44
0x180039e39  mov     rcx, rdi; hLibModule
0x180039e3c  call    cs:__imp_FreeLibrary
0x180039e42  xor     eax, eax
0x180039e44  mov     rcx, [rbp+3B0h+var_50]
0x180039e4b  xor     rcx, rsp; StackCookie
0x180039e4e  call    __security_check_cookie
0x180039e53  add     rsp, 478h
0x180039e5a  pop     r15
0x180039e5c  pop     r14
0x180039e5e  pop     r13
0x180039e60  pop     r12
0x180039e62  pop     rdi
0x180039e63  pop     rsi
0x180039e64  pop     rbx
0x180039e65  pop     rbp
0x180039e66  retn
```
