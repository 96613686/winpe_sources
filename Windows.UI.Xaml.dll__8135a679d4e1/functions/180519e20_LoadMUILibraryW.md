# LoadMUILibraryW

- ea: `0x180519e20`
- end: `0x18051a28f`
- name: `LoadMUILibraryW`
- size: `1135`
- prototype: `HINSTANCE__ *__fastcall(const wchar_t *pwszModuleName, unsigned int dwLangConvention, unsigned __int16 wLangID)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180519a8c`

## callees

- `0x180511238`
- `0x180519e20`
- `0x18051a38c`
- `0x18076e110`
- `0x180bf18b4`
- `0x180bf1934`
- `0x180bf1a44`
- `0x180bf1ab8`
- `0x180bf1c2c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180519e70`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18051a255`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180519e70`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18051a255`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18051a0ec`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18051a233`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18051a266`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18051a0ec`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18051a233`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18051a266`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180519efd`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180519efd`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x180519eb7`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x180519eb7`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetSystemDefaultUILanguage` at `0x180519fdb`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetSystemDefaultUILanguage` at `0x180519fdb`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x180519f1d`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x180519f1d`

## string_xrefs

- `0x180519e5e`: `windows.ui.xaml.dll`
- `0x180519e9f`: `windows.ui.xaml.dll`
- `0x18051a245`: `windows.ui.xaml.dll`

## pseudocode

```c
HINSTANCE__ *__fastcall LoadMUILibraryW(
        const wchar_t *pwszModuleName,
        unsigned int dwLangConvention,
        unsigned __int16 wLangID)
{
  HINSTANCE__ *result; // rax
  HMODULE v4; // rdi
  wchar_t *v5; // rsi
  LANGID UserDefaultUILanguage; // r14
  HINSTANCE__ *MUIFile; // rbx
  LANGID SystemDefaultUILanguage; // ax
  LANGID v9; // r15
  unsigned __int16 InstallLanguage; // r14
  char OSType; // al
  wchar_t *pwszFileName; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t wszLangSubdir[88]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t wszLangPreVistaSubdir[88]; // [rsp+F0h] [rbp-10h] BYREF
  wchar_t wszLangParentSubdir[88]; // [rsp+1A0h] [rbp+A0h] BYREF
  wchar_t wszFullFilePath[264]; // [rsp+250h] [rbp+150h] BYREF

  pwszFileName = 0;
  uOSType = GetOSType();
  result = LoadLibraryExW(L"windows.ui.xaml.dll", 0, uOSType & 0x20 | 2);
  v4 = result;
  if ( !result )
    return 0;
  if ( (uOSType & 0x20) != 0 )
    return result;
  if ( !SearchPathW(0, L"windows.ui.xaml.dll", 0, 0x104u, wszFullFilePath, &pwszFileName) )
  {
    FreeLibrary(v4);
    return 0;
  }
  if ( pwszFileName )
  {
    v5 = wszFullFilePath;
    *(pwszFileName - 1) = 0;
  }
  else
  {
    v5 = 0;
    pwszFileName = wszFullFilePath;
  }
  if ( FindResourceExW(v4, L"MUI", (LPCWSTR)1, 0) )
  {
    if ( (uOSType & 4) != 0 )
    {
      UserDefaultUILanguage = GetUserDefaultUILanguage();
      if ( UserDefaultUILanguage == 1028 )
        UserDefaultUILanguage = GetCHTLangauge();
      while ( LookupLangID(UserDefaultUILanguage, wszLangSubdir, wszLangParentSubdir, wszLangPreVistaSubdir) )
      {
        MUIFile = LoadMUIFile(v4, v5, wszLangSubdir, pwszFileName);
        if ( MUIFile )
          goto LABEL_41;
        MUIFile = LoadMUIFile(v4, v5, wszLangParentSubdir, pwszFileName);
        if ( MUIFile )
          goto LABEL_41;
        if ( wszLangPreVistaSubdir[0] )
        {
          MUIFile = LoadMUIFile(v4, v5, wszLangPreVistaSubdir, pwszFileName);
          if ( MUIFile )
            goto LABEL_41;
        }
        if ( UserDefaultUILanguage != 3076 )
        {
          SystemDefaultUILanguage = GetSystemDefaultUILanguage();
          v9 = SystemDefaultUILanguage;
          if ( SystemDefaultUILanguage != UserDefaultUILanguage )
          {
            if ( !LookupLangID(SystemDefaultUILanguage, wszLangSubdir, wszLangParentSubdir, wszLangPreVistaSubdir) )
              break;
            MUIFile = LoadMUIFile(v4, v5, wszLangSubdir, pwszFileName);
            if ( MUIFile )
              goto LABEL_41;
            MUIFile = LoadMUIFile(v4, v5, wszLangParentSubdir, pwszFileName);
            if ( MUIFile )
              goto LABEL_41;
            if ( wszLangPreVistaSubdir[0] )
            {
              MUIFile = LoadMUIFile(v4, v5, wszLangPreVistaSubdir, pwszFileName);
              if ( MUIFile )
                goto LABEL_41;
            }
          }
          if ( UserDefaultUILanguage != 1033 && v9 != 1033 )
          {
            LookupLangID(0x409u, wszLangSubdir, wszLangParentSubdir, 0);
            MUIFile = LoadMUIFile(v4, v5, wszLangSubdir, pwszFileName);
            if ( MUIFile )
              goto LABEL_41;
          }
          MUIFile = LoadMUIFile(v4, v5, 0, pwszFileName);
          if ( MUIFile )
            goto LABEL_41;
          break;
        }
        UserDefaultUILanguage = 1028;
      }
    }
    else if ( (uOSType & 3) != 0 )
    {
      InstallLanguage = GetInstallLanguage();
      if ( LookupLangID(InstallLanguage, wszLangSubdir, wszLangParentSubdir, wszLangPreVistaSubdir) )
      {
        if ( (MUIFile = LoadMUIFile(v4, v5, wszLangSubdir, pwszFileName)) != 0
          || (MUIFile = LoadMUIFile(v4, v5, wszLangParentSubdir, pwszFileName)) != 0
          || wszLangPreVistaSubdir[0] && (MUIFile = LoadMUIFile(v4, v5, wszLangPreVistaSubdir, pwszFileName)) != 0
          || InstallLanguage != 1033
          && (LookupLangID(0x409u, wszLangSubdir, wszLangParentSubdir, 0),
              (MUIFile = LoadMUIFile(v4, v5, wszLangSubdir, pwszFileName)) != 0)
          || (MUIFile = LoadMUIFile(v4, v5, 0, pwszFileName)) != 0 )
        {
LABEL_41:
          FreeLibrary(v4);
          return MUIFile;
        }
      }
    }
  }
  if ( ((unsigned __int8)v4 & 1) != 0 )
  {
    FreeLibrary(v4);
    if ( (GetOSType() & 0x38) != 0 )
    {
      StringCchPrintfW(wszFullFilePath, 0x104u, L"%s\\%s", v5, pwszFileName);
      return MapMUIFile(wszFullFilePath, 1, 0);
    }
    else
    {
      OSType = GetOSType();
      return LoadLibraryExW(L"windows.ui.xaml.dll", 0, (OSType & 0x26) != 0);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180519e20  push    rbp
0x180519e22  push    rbx
0x180519e23  push    rsi
0x180519e24  push    rdi
0x180519e25  push    r12
0x180519e27  push    r14
0x180519e29  push    r15
0x180519e2b  lea     rbp, [rsp-370h]
0x180519e33  sub     rsp, 470h
0x180519e3a  mov     rax, cs:__security_cookie
0x180519e41  xor     rax, rsp
0x180519e44  mov     [rbp+3A0h+var_40], rax
0x180519e4b  xor     r12d, r12d
0x180519e4e  mov     [rsp+4A0h+pwszFileName], r12
0x180519e53  call    GetOSType
0x180519e58  mov     cs:uOSType, eax
0x180519e5e  lea     rcx, FileName; "windows.ui.xaml.dll"
0x180519e65  and     eax, 20h
0x180519e68  xor     edx, edx; hFile
0x180519e6a  or      eax, 2
0x180519e6d  mov     r8d, eax; dwFlags
0x180519e70  call    cs:__imp_LoadLibraryExW
0x180519e76  mov     rdi, rax
0x180519e79  test    rax, rax
0x180519e7c  jz      loc_18051A26C
0x180519e82  test    byte ptr cs:uOSType, 20h
0x180519e89  jnz     loc_18051A26E
0x180519e8f  lea     rax, [rsp+4A0h+pwszFileName]
0x180519e94  mov     r9d, 104h; nBufferLength
0x180519e9a  mov     [rsp+4A0h+lpFilePart], rax; lpFilePart
0x180519e9f  lea     rdx, FileName; "windows.ui.xaml.dll"
0x180519ea6  lea     rax, [rbp+3A0h+wszFullFilePath]
0x180519ead  xor     r8d, r8d; lpExtension
0x180519eb0  xor     ecx, ecx; lpPath
0x180519eb2  mov     [rsp+4A0h+lpBuffer], rax; lpBuffer
0x180519eb7  call    cs:__imp_SearchPathW
0x180519ebd  test    eax, eax
0x180519ebf  jz      $Fail
0x180519ec5  mov     rcx, [rsp+4A0h+pwszFileName]
0x180519eca  test    rcx, rcx
0x180519ecd  jnz     short loc_180519EE0
0x180519ecf  lea     rax, [rbp+3A0h+wszFullFilePath]
0x180519ed6  mov     esi, r12d
0x180519ed9  mov     [rsp+4A0h+pwszFileName], rax
0x180519ede  jmp     short loc_180519EEC
0x180519ee0  lea     rsi, [rbp+3A0h+wszFullFilePath]
0x180519ee7  mov     [rcx-2], r12w
0x180519eec  xor     r9d, r9d; wLanguage
0x180519eef  lea     rdx, Type; "MUI"
0x180519ef6  mov     rcx, rdi; hModule
0x180519ef9  lea     r8d, [r9+1]; lpName
0x180519efd  call    cs:__imp_FindResourceExW
0x180519f03  test    rax, rax
0x180519f06  jz      loc_18051A0DF
0x180519f0c  mov     eax, cs:uOSType
0x180519f12  test    al, 4
0x180519f14  jz      loc_18051A13C
0x180519f1a  mov     rbx, r12
0x180519f1d  call    cs:__imp_GetUserDefaultUILanguage
0x180519f23  mov     r15d, 404h
0x180519f29  movzx   r14d, ax
0x180519f2d  cmp     ax, r15w
0x180519f31  jnz     short $ChtUserLang
0x180519f33  call    GetCHTLangauge
0x180519f38  movzx   r14d, ax
0x180519f3c  lea     r9, [rbp+3A0h+wszLangPreVistaSubdir]; pwszLangPreVistaSubDirBuffer
0x180519f40  movzx   ecx, r14w; lang_match
0x180519f44  lea     r8, [rbp+3A0h+wszLangParentSubdir]; pwszLangParentSubdirBuffer
0x180519f4b  lea     rdx, [rsp+4A0h+wszLangSubdir]; pwszLangSubdirBuffer
0x180519f50  call    LookupLangID
0x180519f55  test    eax, eax
0x180519f57  jz      $Exit
0x180519f5d  mov     r9, [rsp+4A0h+pwszFileName]; pwszFileName
0x180519f62  lea     r8, [rsp+4A0h+wszLangSubdir]; pwszMUIAndLanguage
0x180519f67  mov     rdx, rsi; pwszFilePath
0x180519f6a  mov     rcx, rdi; hModule
0x180519f6d  call    LoadMUIFile
0x180519f72  mov     rbx, rax
0x180519f75  test    rax, rax
0x180519f78  jnz     loc_18051A230
0x180519f7e  mov     r9, [rsp+4A0h+pwszFileName]; pwszFileName
0x180519f83  lea     r8, [rbp+3A0h+wszLangParentSubdir]; pwszMUIAndLanguage
0x180519f8a  mov     rdx, rsi; pwszFilePath
0x180519f8d  mov     rcx, rdi; hModule
0x180519f90  call    LoadMUIFile
0x180519f95  mov     rbx, rax
0x180519f98  test    rax, rax
0x180519f9b  jnz     loc_18051A230
0x180519fa1  cmp     [rbp+3A0h+wszLangPreVistaSubdir], r12w
0x180519fa6  jz      short loc_180519FC8
0x180519fa8  mov     r9, [rsp+4A0h+pwszFileName]; pwszFileName
0x180519fad  lea     r8, [rbp+3A0h+wszLangPreVistaSubdir]; pwszMUIAndLanguage
0x180519fb1  mov     rdx, rsi; pwszFilePath
0x180519fb4  mov     rcx, rdi; hModule
0x180519fb7  call    LoadMUIFile
0x180519fbc  mov     rbx, rax
0x180519fbf  test    rax, rax
0x180519fc2  jnz     loc_18051A230
0x180519fc8  mov     eax, 0C04h
0x180519fcd  cmp     r14w, ax
0x180519fd1  jnz     short loc_180519FDB
0x180519fd3  mov     r14d, r15d
0x180519fd6  jmp     $ChtUserLang
0x180519fdb  call    cs:__imp_GetSystemDefaultUILanguage
0x180519fe1  movzx   r15d, ax
0x180519fe5  cmp     ax, r14w
0x180519fe9  jz      loc_18051A07A
0x180519fef  lea     r9, [rbp+3A0h+wszLangPreVistaSubdir]; pwszLangPreVistaSubDirBuffer
0x180519ff3  movzx   ecx, ax; lang_match
0x180519ff6  lea     r8, [rbp+3A0h+wszLangParentSubdir]; pwszLangParentSubdirBuffer
0x180519ffd  lea     rdx, [rsp+4A0h+wszLangSubdir]; pwszLangSubdirBuffer
0x18051a002  call    LookupLangID
0x18051a007  test    eax, eax
0x18051a009  jz      loc_18051A0DF
0x18051a00f  mov     r9, [rsp+4A0h+pwszFileName]; pwszFileName
0x18051a014  lea     r8, [rsp+4A0h+wszLangSubdir]; pwszMUIAndLanguage
0x18051a019  mov     rdx, rsi; pwszFilePath
0x18051a01c  mov     rcx, rdi; hModule
0x18051a01f  call    LoadMUIFile
0x18051a024  mov     rbx, rax
0x18051a027  test    rax, rax
0x18051a02a  jnz     loc_18051A230
0x18051a030  mov     r9, [rsp+4A0h+pwszFileName]; pwszFileName
0x18051a035  lea     r8, [rbp+3A0h+wszLangParentSubdir]; pwszMUIAndLanguage
0x18051a03c  mov     rdx, rsi; pwszFilePath
0x18051a03f  mov     rcx, rdi; hModule
0x18051a042  call    LoadMUIFile
0x18051a047  mov     rbx, rax
0x18051a04a  test    rax, rax
0x18051a04d  jnz     loc_18051A230
0x18051a053  cmp     [rbp+3A0h+wszLangPreVistaSubdir], r12w
0x18051a058  jz      short loc_18051A07A
0x18051a05a  mov     r9, [rsp+4A0h+pwszFileName]; pwszFileName
0x18051a05f  lea     r8, [rbp+3A0h+wszLangPreVistaSubdir]; pwszMUIAndLanguage
0x18051a063  mov     rdx, rsi; pwszFilePath
0x18051a066  mov     rcx, rdi; hModule
0x18051a069  call    LoadMUIFile
0x18051a06e  mov     rbx, rax
0x18051a071  test    rax, rax
0x18051a074  jnz     loc_18051A230
0x18051a07a  mov     ecx, 409h; lang_match
0x18051a07f  cmp     cx, r14w
0x18051a083  jz      short loc_18051A0C0
0x18051a085  cmp     cx, r15w
0x18051a089  jz      short loc_18051A0C0
0x18051a08b  xor     r9d, r9d; pwszLangPreVistaSubDirBuffer
0x18051a08e  lea     r8, [rbp+3A0h+wszLangParentSubdir]; pwszLangParentSubdirBuffer
0x18051a095  lea     rdx, [rsp+4A0h+wszLangSubdir]; pwszLangSubdirBuffer
0x18051a09a  call    LookupLangID
0x18051a09f  mov     r9, [rsp+4A0h+pwszFileName]; pwszFileName
0x18051a0a4  lea     r8, [rsp+4A0h+wszLangSubdir]; pwszMUIAndLanguage
0x18051a0a9  mov     rdx, rsi; pwszFilePath
0x18051a0ac  mov     rcx, rdi; hModule
0x18051a0af  call    LoadMUIFile
0x18051a0b4  mov     rbx, rax
0x18051a0b7  test    rax, rax
0x18051a0ba  jnz     loc_18051A230
0x18051a0c0  mov     r9, [rsp+4A0h+pwszFileName]; pwszFileName
0x18051a0c5  xor     r8d, r8d; pwszMUIAndLanguage
0x18051a0c8  mov     rdx, rsi; pwszFilePath
0x18051a0cb  mov     rcx, rdi; hModule
0x18051a0ce  call    LoadMUIFile
0x18051a0d3  mov     rbx, rax
0x18051a0d6  test    rax, rax
0x18051a0d9  jnz     loc_18051A230
0x18051a0df  test    dil, 1
0x18051a0e3  jz      loc_18051A25E
0x18051a0e9  mov     rcx, rdi; hLibModule
0x18051a0ec  call    cs:__imp_FreeLibrary
0x18051a0f2  call    GetOSType
0x18051a0f7  test    al, 38h
0x18051a0f9  jz      loc_18051A23E
0x18051a0ff  mov     rax, [rsp+4A0h+pwszFileName]
0x18051a104  lea     r8, aSS; "%s\\%s"
0x18051a10b  mov     r9, rsi
0x18051a10e  mov     [rsp+4A0h+lpBuffer], rax
0x18051a113  mov     edx, 104h; cchDest
0x18051a118  lea     rcx, [rbp+3A0h+wszFullFilePath]; pszDest
0x18051a11f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18051a124  xor     r8d, r8d; fIsDontResolveDll
0x18051a127  lea     rcx, [rbp+3A0h+wszFullFilePath]; FullFilePath
0x18051a12e  lea     edx, [r8+1]; fIsData
0x18051a132  call    MapMUIFile
0x18051a137  jmp     loc_18051A25B
0x18051a13c  test    al, 3
0x18051a13e  jz      short loc_18051A0DF
0x18051a140  call    GetInstallLanguage
0x18051a145  lea     r9, [rbp+3A0h+wszLangPreVistaSubdir]; pwszLangPreVistaSubDirBuffer
0x18051a149  movzx   ecx, ax; lang_match
0x18051a14c  lea     r8, [rbp+3A0h+wszLangParentSubdir]; pwszLangParentSubdirBuffer
0x18051a153  movzx   r14d, ax
0x18051a157  lea     rdx, [rsp+4A0h+wszLangSubdir]; pwszLangSubdirBuffer
0x18051a15c  call    LookupLangID
0x18051a161  test    eax, eax
0x18051a163  jz      loc_18051A0DF
0x18051a169  mov     r9, [rsp+4A0h+pwszFileName]; pwszFileName
0x18051a16e  lea     r8, [rsp+4A0h+wszLangSubdir]; pwszMUIAndLanguage
0x18051a173  mov     rdx, rsi; pwszFilePath
0x18051a176  mov     rcx, rdi; hModule
0x18051a179  call    LoadMUIFile
0x18051a17e  mov     rbx, rax
0x18051a181  test    rax, rax
0x18051a184  jnz     loc_18051A230
0x18051a18a  mov     r9, [rsp+4A0h+pwszFileName]; pwszFileName
0x18051a18f  lea     r8, [rbp+3A0h+wszLangParentSubdir]; pwszMUIAndLanguage
0x18051a196  mov     rdx, rsi; pwszFilePath
0x18051a199  mov     rcx, rdi; hModule
0x18051a19c  call    LoadMUIFile
0x18051a1a1  mov     rbx, rax
0x18051a1a4  test    rax, rax
0x18051a1a7  jnz     loc_18051A230
0x18051a1ad  cmp     [rbp+3A0h+wszLangPreVistaSubdir], r12w
0x18051a1b2  jz      short loc_18051A1D0
0x18051a1b4  mov     r9, [rsp+4A0h+pwszFileName]; pwszFileName
0x18051a1b9  lea     r8, [rbp+3A0h+wszLangPreVistaSubdir]; pwszMUIAndLanguage
0x18051a1bd  mov     rdx, rsi; pwszFilePath
0x18051a1c0  mov     rcx, rdi; hModule
0x18051a1c3  call    LoadMUIFile
0x18051a1c8  mov     rbx, rax
0x18051a1cb  test    rax, rax
0x18051a1ce  jnz     short loc_18051A230
0x18051a1d0  mov     ecx, 409h; lang_match
0x18051a1d5  cmp     cx, r14w
0x18051a1d9  jz      short loc_18051A20C
0x18051a1db  xor     r9d, r9d; pwszLangPreVistaSubDirBuffer
0x18051a1de  lea     r8, [rbp+3A0h+wszLangParentSubdir]; pwszLangParentSubdirBuffer
0x18051a1e5  lea     rdx, [rsp+4A0h+wszLangSubdir]; pwszLangSubdirBuffer
0x18051a1ea  call    LookupLangID
0x18051a1ef  mov     r9, [rsp+4A0h+pwszFileName]; pwszFileName
0x18051a1f4  lea     r8, [rsp+4A0h+wszLangSubdir]; pwszMUIAndLanguage
0x18051a1f9  mov     rdx, rsi; pwszFilePath
0x18051a1fc  mov     rcx, rdi; hModule
0x18051a1ff  call    LoadMUIFile
0x18051a204  mov     rbx, rax
0x18051a207  test    rax, rax
0x18051a20a  jnz     short loc_18051A230
0x18051a20c  mov     r9, [rsp+4A0h+pwszFileName]; pwszFileName
0x18051a211  xor     r8d, r8d; pwszMUIAndLanguage
0x18051a214  mov     rdx, rsi; pwszFilePath
0x18051a217  mov     rcx, rdi; hModule
0x18051a21a  call    LoadMUIFile
0x18051a21f  mov     rbx, rax
0x18051a222  test    rax, rax
0x18051a225  jnz     short loc_18051A230
0x18051a227  test    rbx, rbx
0x18051a22a  jz      loc_18051A0DF
0x18051a230  mov     rcx, rdi; hLibModule
0x18051a233  call    cs:__imp_FreeLibrary
0x18051a239  mov     rax, rbx
0x18051a23c  jmp     short loc_18051A26E
0x18051a23e  call    GetOSType
0x18051a243  test    al, 26h
0x18051a245  lea     rcx, FileName; "windows.ui.xaml.dll"
0x18051a24c  mov     r8d, r12d
0x18051a24f  setnz   r8b; dwFlags
0x18051a253  xor     edx, edx; hFile
0x18051a255  call    cs:__imp_LoadLibraryExW
0x18051a25b  mov     rdi, rax
0x18051a25e  mov     rax, rdi
0x18051a261  jmp     short loc_18051A26E
0x18051a263  mov     rcx, rdi; hLibModule
0x18051a266  call    cs:__imp_FreeLibrary
0x18051a26c  xor     eax, eax
0x18051a26e  mov     rcx, [rbp+3A0h+var_40]
0x18051a275  xor     rcx, rsp; StackCookie
0x18051a278  call    __security_check_cookie
0x18051a27d  add     rsp, 470h
0x18051a284  pop     r15
0x18051a286  pop     r14
0x18051a288  pop     r12
0x18051a28a  pop     rdi
0x18051a28b  pop     rsi
0x18051a28c  pop     rbx
0x18051a28d  pop     rbp
0x18051a28e  retn
```
