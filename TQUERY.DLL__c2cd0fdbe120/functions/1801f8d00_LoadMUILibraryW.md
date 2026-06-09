# LoadMUILibraryW

- ea: `0x1801f8d00`
- end: `0x1801f9173`
- name: `LoadMUILibraryW`
- size: `1139`
- prototype: `HINSTANCE __stdcall(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180197b4c`

## callees

- `0x1800e4128`
- `0x180188d90`
- `0x1801f8604`
- `0x1801f8684`
- `0x1801f8794`
- `0x1801f88bc`
- `0x1801f8930`
- `0x1801f8aa4`
- `0x1801f8d00`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801f8d5a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801f9137`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801f8d5a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801f9137`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1801f8de3`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1801f8de3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801f8fd2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801f9119`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801f9148`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801f8fd2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801f9119`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801f9148`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x1801f8d9d`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x1801f8d9d`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x1801f8e03`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x1801f8e03`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetSystemDefaultUILanguage` at `0x1801f8ec1`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetSystemDefaultUILanguage` at `0x1801f8ec1`

## pseudocode

```c
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
  dword_1803693E8 = GetOSType(pszFullModuleName, dwLangConvention, LangID);
  result = LoadLibraryExW(pszFullModuleName, 0, dword_1803693E8 & 0x20 | 2u);
  v5 = result;
  if ( !result )
    return 0;
  if ( (dword_1803693E8 & 0x20) != 0 )
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
    if ( (dword_1803693E8 & 4) != 0 )
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
    else if ( (dword_1803693E8 & 3) != 0 )
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
0x1801f8d00  push    rbp
0x1801f8d02  push    rbx
0x1801f8d03  push    rsi
0x1801f8d04  push    rdi
0x1801f8d05  push    r12
0x1801f8d07  push    r13
0x1801f8d09  push    r14
0x1801f8d0b  push    r15
0x1801f8d0d  lea     rbp, [rsp-378h]
0x1801f8d15  sub     rsp, 478h
0x1801f8d1c  mov     rax, cs:__security_cookie
0x1801f8d23  xor     rax, rsp
0x1801f8d26  mov     [rbp+3B0h+var_50], rax
0x1801f8d2d  xor     r13d, r13d
0x1801f8d30  mov     r12, rcx
0x1801f8d33  mov     [rsp+4B0h+FilePart], r13
0x1801f8d38  test    rcx, rcx
0x1801f8d3b  jz      loc_1801F914E
0x1801f8d41  call    GetOSType
0x1801f8d46  mov     cs:dword_1803693E8, eax
0x1801f8d4c  xor     edx, edx; hFile
0x1801f8d4e  and     eax, 20h
0x1801f8d51  mov     rcx, r12; lpLibFileName
0x1801f8d54  or      eax, 2
0x1801f8d57  mov     r8d, eax; dwFlags
0x1801f8d5a  call    cs:__imp_LoadLibraryExW
0x1801f8d60  mov     rdi, rax
0x1801f8d63  test    rax, rax
0x1801f8d66  jz      loc_1801F914E
0x1801f8d6c  test    byte ptr cs:dword_1803693E8, 20h
0x1801f8d73  jnz     loc_1801F9150
0x1801f8d79  lea     rax, [rsp+4B0h+FilePart]
0x1801f8d7e  mov     r9d, 104h; nBufferLength
0x1801f8d84  mov     [rsp+4B0h+lpFilePart], rax; lpFilePart
0x1801f8d89  xor     r8d, r8d; lpExtension
0x1801f8d8c  lea     rax, [rbp+3B0h+Buffer]
0x1801f8d93  mov     rdx, r12; lpFileName
0x1801f8d96  xor     ecx, ecx; lpPath
0x1801f8d98  mov     [rsp+4B0h+lpBuffer], rax; lpBuffer
0x1801f8d9d  call    cs:__imp_SearchPathW
0x1801f8da3  test    eax, eax
0x1801f8da5  jz      loc_1801F9145
0x1801f8dab  mov     rcx, [rsp+4B0h+FilePart]
0x1801f8db0  test    rcx, rcx
0x1801f8db3  jnz     short loc_1801F8DC6
0x1801f8db5  lea     rax, [rbp+3B0h+Buffer]
0x1801f8dbc  mov     esi, r13d
0x1801f8dbf  mov     [rsp+4B0h+FilePart], rax
0x1801f8dc4  jmp     short loc_1801F8DD2
0x1801f8dc6  lea     rsi, [rbp+3B0h+Buffer]
0x1801f8dcd  mov     [rcx-2], r13w
0x1801f8dd2  xor     r9d, r9d; wLanguage
0x1801f8dd5  lea     rdx, Type; "MUI"
0x1801f8ddc  mov     rcx, rdi; hModule
0x1801f8ddf  lea     r8d, [r9+1]; lpName
0x1801f8de3  call    cs:__imp_FindResourceExW
0x1801f8de9  test    rax, rax
0x1801f8dec  jz      loc_1801F8FC5
0x1801f8df2  mov     eax, cs:dword_1803693E8
0x1801f8df8  test    al, 4
0x1801f8dfa  jz      loc_1801F9022
0x1801f8e00  mov     rbx, r13
0x1801f8e03  call    cs:__imp_GetUserDefaultUILanguage
0x1801f8e09  mov     r15d, 404h
0x1801f8e0f  movzx   r14d, ax
0x1801f8e13  cmp     ax, r15w
0x1801f8e17  jnz     short loc_1801F8E22
0x1801f8e19  call    GetCHTLangauge
0x1801f8e1e  movzx   r14d, ax
0x1801f8e22  lea     r9, [rbp+3B0h+var_3C0]
0x1801f8e26  movzx   ecx, r14w
0x1801f8e2a  lea     r8, [rbp+3B0h+var_310]
0x1801f8e31  lea     rdx, [rsp+4B0h+var_470]
0x1801f8e36  call    LookupLangID
0x1801f8e3b  test    eax, eax
0x1801f8e3d  jz      loc_1801F910D
0x1801f8e43  mov     r9, [rsp+4B0h+FilePart]
0x1801f8e48  lea     r8, [rsp+4B0h+var_470]
0x1801f8e4d  mov     rdx, rsi
0x1801f8e50  mov     rcx, rdi
0x1801f8e53  call    LoadMUIFile
0x1801f8e58  mov     rbx, rax
0x1801f8e5b  test    rax, rax
0x1801f8e5e  jnz     loc_1801F9116
0x1801f8e64  mov     r9, [rsp+4B0h+FilePart]
0x1801f8e69  lea     r8, [rbp+3B0h+var_310]
0x1801f8e70  mov     rdx, rsi
0x1801f8e73  mov     rcx, rdi
0x1801f8e76  call    LoadMUIFile
0x1801f8e7b  mov     rbx, rax
0x1801f8e7e  test    rax, rax
0x1801f8e81  jnz     loc_1801F9116
0x1801f8e87  cmp     [rbp+3B0h+var_3C0], r13w
0x1801f8e8c  jz      short loc_1801F8EAE
0x1801f8e8e  mov     r9, [rsp+4B0h+FilePart]
0x1801f8e93  lea     r8, [rbp+3B0h+var_3C0]
0x1801f8e97  mov     rdx, rsi
0x1801f8e9a  mov     rcx, rdi
0x1801f8e9d  call    LoadMUIFile
0x1801f8ea2  mov     rbx, rax
0x1801f8ea5  test    rax, rax
0x1801f8ea8  jnz     loc_1801F9116
0x1801f8eae  mov     eax, 0C04h
0x1801f8eb3  cmp     r14w, ax
0x1801f8eb7  jnz     short loc_1801F8EC1
0x1801f8eb9  mov     r14d, r15d
0x1801f8ebc  jmp     loc_1801F8E22
0x1801f8ec1  call    cs:__imp_GetSystemDefaultUILanguage
0x1801f8ec7  movzx   r15d, ax
0x1801f8ecb  cmp     ax, r14w
0x1801f8ecf  jz      loc_1801F8F60
0x1801f8ed5  lea     r9, [rbp+3B0h+var_3C0]
0x1801f8ed9  movzx   ecx, ax
0x1801f8edc  lea     r8, [rbp+3B0h+var_310]
0x1801f8ee3  lea     rdx, [rsp+4B0h+var_470]
0x1801f8ee8  call    LookupLangID
0x1801f8eed  test    eax, eax
0x1801f8eef  jz      loc_1801F8FC5
0x1801f8ef5  mov     r9, [rsp+4B0h+FilePart]
0x1801f8efa  lea     r8, [rsp+4B0h+var_470]
0x1801f8eff  mov     rdx, rsi
0x1801f8f02  mov     rcx, rdi
0x1801f8f05  call    LoadMUIFile
0x1801f8f0a  mov     rbx, rax
0x1801f8f0d  test    rax, rax
0x1801f8f10  jnz     loc_1801F9116
0x1801f8f16  mov     r9, [rsp+4B0h+FilePart]
0x1801f8f1b  lea     r8, [rbp+3B0h+var_310]
0x1801f8f22  mov     rdx, rsi
0x1801f8f25  mov     rcx, rdi
0x1801f8f28  call    LoadMUIFile
0x1801f8f2d  mov     rbx, rax
0x1801f8f30  test    rax, rax
0x1801f8f33  jnz     loc_1801F9116
0x1801f8f39  cmp     [rbp+3B0h+var_3C0], r13w
0x1801f8f3e  jz      short loc_1801F8F60
0x1801f8f40  mov     r9, [rsp+4B0h+FilePart]
0x1801f8f45  lea     r8, [rbp+3B0h+var_3C0]
0x1801f8f49  mov     rdx, rsi
0x1801f8f4c  mov     rcx, rdi
0x1801f8f4f  call    LoadMUIFile
0x1801f8f54  mov     rbx, rax
0x1801f8f57  test    rax, rax
0x1801f8f5a  jnz     loc_1801F9116
0x1801f8f60  mov     ecx, 409h
0x1801f8f65  cmp     cx, r14w
0x1801f8f69  jz      short loc_1801F8FA6
0x1801f8f6b  cmp     cx, r15w
0x1801f8f6f  jz      short loc_1801F8FA6
0x1801f8f71  xor     r9d, r9d
0x1801f8f74  lea     r8, [rbp+3B0h+var_310]
0x1801f8f7b  lea     rdx, [rsp+4B0h+var_470]
0x1801f8f80  call    LookupLangID
0x1801f8f85  mov     r9, [rsp+4B0h+FilePart]
0x1801f8f8a  lea     r8, [rsp+4B0h+var_470]
0x1801f8f8f  mov     rdx, rsi
0x1801f8f92  mov     rcx, rdi
0x1801f8f95  call    LoadMUIFile
0x1801f8f9a  mov     rbx, rax
0x1801f8f9d  test    rax, rax
0x1801f8fa0  jnz     loc_1801F9116
0x1801f8fa6  mov     r9, [rsp+4B0h+FilePart]
0x1801f8fab  xor     r8d, r8d
0x1801f8fae  mov     rdx, rsi
0x1801f8fb1  mov     rcx, rdi
0x1801f8fb4  call    LoadMUIFile
0x1801f8fb9  mov     rbx, rax
0x1801f8fbc  test    rax, rax
0x1801f8fbf  jnz     loc_1801F9116
0x1801f8fc5  test    dil, 1
0x1801f8fc9  jz      loc_1801F9140
0x1801f8fcf  mov     rcx, rdi; hLibModule
0x1801f8fd2  call    cs:__imp_FreeLibrary
0x1801f8fd8  call    GetOSType
0x1801f8fdd  test    al, 38h
0x1801f8fdf  jz      loc_1801F9124
0x1801f8fe5  mov     rax, [rsp+4B0h+FilePart]
0x1801f8fea  lea     r8, aSS_0; "%s\\%s"
0x1801f8ff1  mov     r9, rsi
0x1801f8ff4  mov     [rsp+4B0h+lpBuffer], rax
0x1801f8ff9  mov     edx, 104h; unsigned __int64
0x1801f8ffe  lea     rcx, [rbp+3B0h+Buffer]; unsigned __int16 *
0x1801f9005  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801f900a  xor     r8d, r8d
0x1801f900d  lea     rcx, [rbp+3B0h+Buffer]
0x1801f9014  lea     edx, [r8+1]
0x1801f9018  call    MapMUIFile
0x1801f901d  jmp     loc_1801F913D
0x1801f9022  test    al, 3
0x1801f9024  jz      short loc_1801F8FC5
0x1801f9026  call    GetInstallLanguage
0x1801f902b  lea     r9, [rbp+3B0h+var_3C0]
0x1801f902f  movzx   ecx, ax
0x1801f9032  lea     r8, [rbp+3B0h+var_310]
0x1801f9039  movzx   r14d, ax
0x1801f903d  lea     rdx, [rsp+4B0h+var_470]
0x1801f9042  call    LookupLangID
0x1801f9047  test    eax, eax
0x1801f9049  jz      loc_1801F8FC5
0x1801f904f  mov     r9, [rsp+4B0h+FilePart]
0x1801f9054  lea     r8, [rsp+4B0h+var_470]
0x1801f9059  mov     rdx, rsi
0x1801f905c  mov     rcx, rdi
0x1801f905f  call    LoadMUIFile
0x1801f9064  mov     rbx, rax
0x1801f9067  test    rax, rax
0x1801f906a  jnz     loc_1801F9116
0x1801f9070  mov     r9, [rsp+4B0h+FilePart]
0x1801f9075  lea     r8, [rbp+3B0h+var_310]
0x1801f907c  mov     rdx, rsi
0x1801f907f  mov     rcx, rdi
0x1801f9082  call    LoadMUIFile
0x1801f9087  mov     rbx, rax
0x1801f908a  test    rax, rax
0x1801f908d  jnz     loc_1801F9116
0x1801f9093  cmp     [rbp+3B0h+var_3C0], r13w
0x1801f9098  jz      short loc_1801F90B6
0x1801f909a  mov     r9, [rsp+4B0h+FilePart]
0x1801f909f  lea     r8, [rbp+3B0h+var_3C0]
0x1801f90a3  mov     rdx, rsi
0x1801f90a6  mov     rcx, rdi
0x1801f90a9  call    LoadMUIFile
0x1801f90ae  mov     rbx, rax
0x1801f90b1  test    rax, rax
0x1801f90b4  jnz     short loc_1801F9116
0x1801f90b6  mov     ecx, 409h
0x1801f90bb  cmp     cx, r14w
0x1801f90bf  jz      short loc_1801F90F2
0x1801f90c1  xor     r9d, r9d
0x1801f90c4  lea     r8, [rbp+3B0h+var_310]
0x1801f90cb  lea     rdx, [rsp+4B0h+var_470]
0x1801f90d0  call    LookupLangID
0x1801f90d5  mov     r9, [rsp+4B0h+FilePart]
0x1801f90da  lea     r8, [rsp+4B0h+var_470]
0x1801f90df  mov     rdx, rsi
0x1801f90e2  mov     rcx, rdi
0x1801f90e5  call    LoadMUIFile
0x1801f90ea  mov     rbx, rax
0x1801f90ed  test    rax, rax
0x1801f90f0  jnz     short loc_1801F9116
0x1801f90f2  mov     r9, [rsp+4B0h+FilePart]
0x1801f90f7  xor     r8d, r8d
0x1801f90fa  mov     rdx, rsi
0x1801f90fd  mov     rcx, rdi
0x1801f9100  call    LoadMUIFile
0x1801f9105  mov     rbx, rax
0x1801f9108  test    rax, rax
0x1801f910b  jnz     short loc_1801F9116
0x1801f910d  test    rbx, rbx
0x1801f9110  jz      loc_1801F8FC5
0x1801f9116  mov     rcx, rdi; hLibModule
0x1801f9119  call    cs:__imp_FreeLibrary
0x1801f911f  mov     rax, rbx
0x1801f9122  jmp     short loc_1801F9150
0x1801f9124  call    GetOSType
0x1801f9129  test    al, 26h
0x1801f912b  mov     r8d, r13d
0x1801f912e  mov     rcx, r12; lpLibFileName
0x1801f9131  setnz   r8b; dwFlags
0x1801f9135  xor     edx, edx; hFile
0x1801f9137  call    cs:__imp_LoadLibraryExW
0x1801f913d  mov     rdi, rax
0x1801f9140  mov     rax, rdi
0x1801f9143  jmp     short loc_1801F9150
0x1801f9145  mov     rcx, rdi; hLibModule
0x1801f9148  call    cs:__imp_FreeLibrary
0x1801f914e  xor     eax, eax
0x1801f9150  mov     rcx, [rbp+3B0h+var_50]
0x1801f9157  xor     rcx, rsp; StackCookie
0x1801f915a  call    __security_check_cookie
0x1801f915f  add     rsp, 478h
0x1801f9166  pop     r15
0x1801f9168  pop     r14
0x1801f916a  pop     r13
0x1801f916c  pop     r12
0x1801f916e  pop     rdi
0x1801f916f  pop     rsi
0x1801f9170  pop     rbx
0x1801f9171  pop     rbp
0x1801f9172  retn
```
