# LoadMUILibraryW

- ea: `0x1800c0e38`
- end: `0x1800c12ab`
- name: `LoadMUILibraryW`
- size: `1139`
- prototype: `HINSTANCE __stdcall(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x1801485ec`
- `0x18015a268`

## callees

- `0x1800c0e38`
- `0x1801244c0`
- `0x1801592a4`
- `0x180159324`
- `0x180159434`
- `0x18015955c`
- `0x1801595d0`
- `0x180159744`
- `0x180159870`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800c0e92`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800c126f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800c0e92`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800c126f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800c110a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800c1251`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800c1280`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800c110a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800c1251`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800c1280`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1800c0f1b`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1800c0f1b`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x1800c0ed5`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x1800c0ed5`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetSystemDefaultUILanguage` at `0x1800c0ff9`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetSystemDefaultUILanguage` at `0x1800c0ff9`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x1800c0f3b`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x1800c0f3b`

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
  dword_1802DC950 = GetOSType(pszFullModuleName, dwLangConvention, LangID);
  result = LoadLibraryExW(pszFullModuleName, 0, dword_1802DC950 & 0x20 | 2u);
  v5 = result;
  if ( !result )
    return 0;
  if ( (dword_1802DC950 & 0x20) != 0 )
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
    if ( (dword_1802DC950 & 4) != 0 )
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
    else if ( (dword_1802DC950 & 3) != 0 )
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
0x1800c0e38  push    rbp
0x1800c0e3a  push    rbx
0x1800c0e3b  push    rsi
0x1800c0e3c  push    rdi
0x1800c0e3d  push    r12
0x1800c0e3f  push    r13
0x1800c0e41  push    r14
0x1800c0e43  push    r15
0x1800c0e45  lea     rbp, [rsp-378h]
0x1800c0e4d  sub     rsp, 478h
0x1800c0e54  mov     rax, cs:__security_cookie
0x1800c0e5b  xor     rax, rsp
0x1800c0e5e  mov     [rbp+3B0h+var_50], rax
0x1800c0e65  xor     r13d, r13d
0x1800c0e68  mov     r12, rcx
0x1800c0e6b  mov     [rsp+4B0h+FilePart], r13
0x1800c0e70  test    rcx, rcx
0x1800c0e73  jz      loc_1800C1286
0x1800c0e79  call    GetOSType
0x1800c0e7e  mov     cs:dword_1802DC950, eax
0x1800c0e84  xor     edx, edx; hFile
0x1800c0e86  and     eax, 20h
0x1800c0e89  mov     rcx, r12; lpLibFileName
0x1800c0e8c  or      eax, 2
0x1800c0e8f  mov     r8d, eax; dwFlags
0x1800c0e92  call    cs:__imp_LoadLibraryExW
0x1800c0e98  mov     rdi, rax
0x1800c0e9b  test    rax, rax
0x1800c0e9e  jz      loc_1800C1286
0x1800c0ea4  test    byte ptr cs:dword_1802DC950, 20h
0x1800c0eab  jnz     loc_1800C1288
0x1800c0eb1  lea     rax, [rsp+4B0h+FilePart]
0x1800c0eb6  mov     r9d, 104h; nBufferLength
0x1800c0ebc  mov     [rsp+4B0h+lpFilePart], rax; lpFilePart
0x1800c0ec1  xor     r8d, r8d; lpExtension
0x1800c0ec4  lea     rax, [rbp+3B0h+Buffer]
0x1800c0ecb  mov     rdx, r12; lpFileName
0x1800c0ece  xor     ecx, ecx; lpPath
0x1800c0ed0  mov     [rsp+4B0h+lpBuffer], rax; lpBuffer
0x1800c0ed5  call    cs:__imp_SearchPathW
0x1800c0edb  test    eax, eax
0x1800c0edd  jz      loc_1800C127D
0x1800c0ee3  mov     rcx, [rsp+4B0h+FilePart]
0x1800c0ee8  test    rcx, rcx
0x1800c0eeb  jnz     short loc_1800C0EFE
0x1800c0eed  lea     rax, [rbp+3B0h+Buffer]
0x1800c0ef4  mov     esi, r13d
0x1800c0ef7  mov     [rsp+4B0h+FilePart], rax
0x1800c0efc  jmp     short loc_1800C0F0A
0x1800c0efe  lea     rsi, [rbp+3B0h+Buffer]
0x1800c0f05  mov     [rcx-2], r13w
0x1800c0f0a  xor     r9d, r9d; wLanguage
0x1800c0f0d  lea     rdx, Type; "MUI"
0x1800c0f14  mov     rcx, rdi; hModule
0x1800c0f17  lea     r8d, [r9+1]; lpName
0x1800c0f1b  call    cs:__imp_FindResourceExW
0x1800c0f21  test    rax, rax
0x1800c0f24  jz      loc_1800C10FD
0x1800c0f2a  mov     eax, cs:dword_1802DC950
0x1800c0f30  test    al, 4
0x1800c0f32  jz      loc_1800C115A
0x1800c0f38  mov     rbx, r13
0x1800c0f3b  call    cs:__imp_GetUserDefaultUILanguage
0x1800c0f41  mov     r15d, 404h
0x1800c0f47  movzx   r14d, ax
0x1800c0f4b  cmp     ax, r15w
0x1800c0f4f  jnz     short loc_1800C0F5A
0x1800c0f51  call    GetCHTLangauge
0x1800c0f56  movzx   r14d, ax
0x1800c0f5a  lea     r9, [rbp+3B0h+var_3C0]
0x1800c0f5e  movzx   ecx, r14w
0x1800c0f62  lea     r8, [rbp+3B0h+var_310]
0x1800c0f69  lea     rdx, [rsp+4B0h+var_470]
0x1800c0f6e  call    LookupLangID
0x1800c0f73  test    eax, eax
0x1800c0f75  jz      loc_1800C1245
0x1800c0f7b  mov     r9, [rsp+4B0h+FilePart]
0x1800c0f80  lea     r8, [rsp+4B0h+var_470]
0x1800c0f85  mov     rdx, rsi
0x1800c0f88  mov     rcx, rdi
0x1800c0f8b  call    LoadMUIFile
0x1800c0f90  mov     rbx, rax
0x1800c0f93  test    rax, rax
0x1800c0f96  jnz     loc_1800C124E
0x1800c0f9c  mov     r9, [rsp+4B0h+FilePart]
0x1800c0fa1  lea     r8, [rbp+3B0h+var_310]
0x1800c0fa8  mov     rdx, rsi
0x1800c0fab  mov     rcx, rdi
0x1800c0fae  call    LoadMUIFile
0x1800c0fb3  mov     rbx, rax
0x1800c0fb6  test    rax, rax
0x1800c0fb9  jnz     loc_1800C124E
0x1800c0fbf  cmp     [rbp+3B0h+var_3C0], r13w
0x1800c0fc4  jz      short loc_1800C0FE6
0x1800c0fc6  mov     r9, [rsp+4B0h+FilePart]
0x1800c0fcb  lea     r8, [rbp+3B0h+var_3C0]
0x1800c0fcf  mov     rdx, rsi
0x1800c0fd2  mov     rcx, rdi
0x1800c0fd5  call    LoadMUIFile
0x1800c0fda  mov     rbx, rax
0x1800c0fdd  test    rax, rax
0x1800c0fe0  jnz     loc_1800C124E
0x1800c0fe6  mov     eax, 0C04h
0x1800c0feb  cmp     r14w, ax
0x1800c0fef  jnz     short loc_1800C0FF9
0x1800c0ff1  mov     r14d, r15d
0x1800c0ff4  jmp     loc_1800C0F5A
0x1800c0ff9  call    cs:__imp_GetSystemDefaultUILanguage
0x1800c0fff  movzx   r15d, ax
0x1800c1003  cmp     ax, r14w
0x1800c1007  jz      loc_1800C1098
0x1800c100d  lea     r9, [rbp+3B0h+var_3C0]
0x1800c1011  movzx   ecx, ax
0x1800c1014  lea     r8, [rbp+3B0h+var_310]
0x1800c101b  lea     rdx, [rsp+4B0h+var_470]
0x1800c1020  call    LookupLangID
0x1800c1025  test    eax, eax
0x1800c1027  jz      loc_1800C10FD
0x1800c102d  mov     r9, [rsp+4B0h+FilePart]
0x1800c1032  lea     r8, [rsp+4B0h+var_470]
0x1800c1037  mov     rdx, rsi
0x1800c103a  mov     rcx, rdi
0x1800c103d  call    LoadMUIFile
0x1800c1042  mov     rbx, rax
0x1800c1045  test    rax, rax
0x1800c1048  jnz     loc_1800C124E
0x1800c104e  mov     r9, [rsp+4B0h+FilePart]
0x1800c1053  lea     r8, [rbp+3B0h+var_310]
0x1800c105a  mov     rdx, rsi
0x1800c105d  mov     rcx, rdi
0x1800c1060  call    LoadMUIFile
0x1800c1065  mov     rbx, rax
0x1800c1068  test    rax, rax
0x1800c106b  jnz     loc_1800C124E
0x1800c1071  cmp     [rbp+3B0h+var_3C0], r13w
0x1800c1076  jz      short loc_1800C1098
0x1800c1078  mov     r9, [rsp+4B0h+FilePart]
0x1800c107d  lea     r8, [rbp+3B0h+var_3C0]
0x1800c1081  mov     rdx, rsi
0x1800c1084  mov     rcx, rdi
0x1800c1087  call    LoadMUIFile
0x1800c108c  mov     rbx, rax
0x1800c108f  test    rax, rax
0x1800c1092  jnz     loc_1800C124E
0x1800c1098  mov     ecx, 409h
0x1800c109d  cmp     cx, r14w
0x1800c10a1  jz      short loc_1800C10DE
0x1800c10a3  cmp     cx, r15w
0x1800c10a7  jz      short loc_1800C10DE
0x1800c10a9  xor     r9d, r9d
0x1800c10ac  lea     r8, [rbp+3B0h+var_310]
0x1800c10b3  lea     rdx, [rsp+4B0h+var_470]
0x1800c10b8  call    LookupLangID
0x1800c10bd  mov     r9, [rsp+4B0h+FilePart]
0x1800c10c2  lea     r8, [rsp+4B0h+var_470]
0x1800c10c7  mov     rdx, rsi
0x1800c10ca  mov     rcx, rdi
0x1800c10cd  call    LoadMUIFile
0x1800c10d2  mov     rbx, rax
0x1800c10d5  test    rax, rax
0x1800c10d8  jnz     loc_1800C124E
0x1800c10de  mov     r9, [rsp+4B0h+FilePart]
0x1800c10e3  xor     r8d, r8d
0x1800c10e6  mov     rdx, rsi
0x1800c10e9  mov     rcx, rdi
0x1800c10ec  call    LoadMUIFile
0x1800c10f1  mov     rbx, rax
0x1800c10f4  test    rax, rax
0x1800c10f7  jnz     loc_1800C124E
0x1800c10fd  test    dil, 1
0x1800c1101  jz      loc_1800C1278
0x1800c1107  mov     rcx, rdi; hLibModule
0x1800c110a  call    cs:__imp_FreeLibrary
0x1800c1110  call    GetOSType
0x1800c1115  test    al, 38h
0x1800c1117  jz      loc_1800C125C
0x1800c111d  mov     rax, [rsp+4B0h+FilePart]
0x1800c1122  lea     r8, aSS_0; "%s\\%s"
0x1800c1129  mov     r9, rsi
0x1800c112c  mov     [rsp+4B0h+lpBuffer], rax
0x1800c1131  mov     edx, 104h; unsigned __int64
0x1800c1136  lea     rcx, [rbp+3B0h+Buffer]; unsigned __int16 *
0x1800c113d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800c1142  xor     r8d, r8d
0x1800c1145  lea     rcx, [rbp+3B0h+Buffer]
0x1800c114c  lea     edx, [r8+1]
0x1800c1150  call    MapMUIFile
0x1800c1155  jmp     loc_1800C1275
0x1800c115a  test    al, 3
0x1800c115c  jz      short loc_1800C10FD
0x1800c115e  call    GetInstallLanguage
0x1800c1163  lea     r9, [rbp+3B0h+var_3C0]
0x1800c1167  movzx   ecx, ax
0x1800c116a  lea     r8, [rbp+3B0h+var_310]
0x1800c1171  movzx   r14d, ax
0x1800c1175  lea     rdx, [rsp+4B0h+var_470]
0x1800c117a  call    LookupLangID
0x1800c117f  test    eax, eax
0x1800c1181  jz      loc_1800C10FD
0x1800c1187  mov     r9, [rsp+4B0h+FilePart]
0x1800c118c  lea     r8, [rsp+4B0h+var_470]
0x1800c1191  mov     rdx, rsi
0x1800c1194  mov     rcx, rdi
0x1800c1197  call    LoadMUIFile
0x1800c119c  mov     rbx, rax
0x1800c119f  test    rax, rax
0x1800c11a2  jnz     loc_1800C124E
0x1800c11a8  mov     r9, [rsp+4B0h+FilePart]
0x1800c11ad  lea     r8, [rbp+3B0h+var_310]
0x1800c11b4  mov     rdx, rsi
0x1800c11b7  mov     rcx, rdi
0x1800c11ba  call    LoadMUIFile
0x1800c11bf  mov     rbx, rax
0x1800c11c2  test    rax, rax
0x1800c11c5  jnz     loc_1800C124E
0x1800c11cb  cmp     [rbp+3B0h+var_3C0], r13w
0x1800c11d0  jz      short loc_1800C11EE
0x1800c11d2  mov     r9, [rsp+4B0h+FilePart]
0x1800c11d7  lea     r8, [rbp+3B0h+var_3C0]
0x1800c11db  mov     rdx, rsi
0x1800c11de  mov     rcx, rdi
0x1800c11e1  call    LoadMUIFile
0x1800c11e6  mov     rbx, rax
0x1800c11e9  test    rax, rax
0x1800c11ec  jnz     short loc_1800C124E
0x1800c11ee  mov     ecx, 409h
0x1800c11f3  cmp     cx, r14w
0x1800c11f7  jz      short loc_1800C122A
0x1800c11f9  xor     r9d, r9d
0x1800c11fc  lea     r8, [rbp+3B0h+var_310]
0x1800c1203  lea     rdx, [rsp+4B0h+var_470]
0x1800c1208  call    LookupLangID
0x1800c120d  mov     r9, [rsp+4B0h+FilePart]
0x1800c1212  lea     r8, [rsp+4B0h+var_470]
0x1800c1217  mov     rdx, rsi
0x1800c121a  mov     rcx, rdi
0x1800c121d  call    LoadMUIFile
0x1800c1222  mov     rbx, rax
0x1800c1225  test    rax, rax
0x1800c1228  jnz     short loc_1800C124E
0x1800c122a  mov     r9, [rsp+4B0h+FilePart]
0x1800c122f  xor     r8d, r8d
0x1800c1232  mov     rdx, rsi
0x1800c1235  mov     rcx, rdi
0x1800c1238  call    LoadMUIFile
0x1800c123d  mov     rbx, rax
0x1800c1240  test    rax, rax
0x1800c1243  jnz     short loc_1800C124E
0x1800c1245  test    rbx, rbx
0x1800c1248  jz      loc_1800C10FD
0x1800c124e  mov     rcx, rdi; hLibModule
0x1800c1251  call    cs:__imp_FreeLibrary
0x1800c1257  mov     rax, rbx
0x1800c125a  jmp     short loc_1800C1288
0x1800c125c  call    GetOSType
0x1800c1261  test    al, 26h
0x1800c1263  mov     r8d, r13d
0x1800c1266  mov     rcx, r12; lpLibFileName
0x1800c1269  setnz   r8b; dwFlags
0x1800c126d  xor     edx, edx; hFile
0x1800c126f  call    cs:__imp_LoadLibraryExW
0x1800c1275  mov     rdi, rax
0x1800c1278  mov     rax, rdi
0x1800c127b  jmp     short loc_1800C1288
0x1800c127d  mov     rcx, rdi; hLibModule
0x1800c1280  call    cs:__imp_FreeLibrary
0x1800c1286  xor     eax, eax
0x1800c1288  mov     rcx, [rbp+3B0h+var_50]
0x1800c128f  xor     rcx, rsp; StackCookie
0x1800c1292  call    __security_check_cookie
0x1800c1297  add     rsp, 478h
0x1800c129e  pop     r15
0x1800c12a0  pop     r14
0x1800c12a2  pop     r13
0x1800c12a4  pop     r12
0x1800c12a6  pop     rdi
0x1800c12a7  pop     rsi
0x1800c12a8  pop     rbx
0x1800c12a9  pop     rbp
0x1800c12aa  retn
```
