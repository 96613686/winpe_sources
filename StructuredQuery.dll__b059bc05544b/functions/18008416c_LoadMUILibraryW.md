# LoadMUILibraryW

- ea: `0x18008416c`
- end: `0x1800845df`
- name: `LoadMUILibraryW`
- size: `1139`
- prototype: `HINSTANCE __stdcall(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180051368`

## callees

- `0x18005daf0`
- `0x180083a24`
- `0x180083aa4`
- `0x180083bb4`
- `0x180083cdc`
- `0x180083d50`
- `0x180083ec4`
- `0x180083ff0`
- `0x18008416c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18008443e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180084585`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800845b4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18008443e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180084585`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800845b4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800841c6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800845a3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800841c6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800845a3`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18008424f`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18008424f`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x18008426f`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x18008426f`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetSystemDefaultUILanguage` at `0x18008432d`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetSystemDefaultUILanguage` at `0x18008432d`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x180084209`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x180084209`

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
  dword_1800B1508 = GetOSType(pszFullModuleName, dwLangConvention, LangID);
  result = LoadLibraryExW(pszFullModuleName, 0, dword_1800B1508 & 0x20 | 2u);
  v5 = result;
  if ( !result )
    return 0;
  if ( (dword_1800B1508 & 0x20) != 0 )
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
    if ( (dword_1800B1508 & 4) != 0 )
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
    else if ( (dword_1800B1508 & 3) != 0 )
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
      return MapMUIFile(Buffer, 1, 0);
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
0x18008416c  push    rbp
0x18008416e  push    rbx
0x18008416f  push    rsi
0x180084170  push    rdi
0x180084171  push    r12
0x180084173  push    r13
0x180084175  push    r14
0x180084177  push    r15
0x180084179  lea     rbp, [rsp-378h]
0x180084181  sub     rsp, 478h
0x180084188  mov     rax, cs:__security_cookie
0x18008418f  xor     rax, rsp
0x180084192  mov     [rbp+3B0h+var_50], rax
0x180084199  xor     r13d, r13d
0x18008419c  mov     r12, rcx
0x18008419f  mov     [rsp+4B0h+FilePart], r13
0x1800841a4  test    rcx, rcx
0x1800841a7  jz      loc_1800845BA
0x1800841ad  call    GetOSType
0x1800841b2  mov     cs:dword_1800B1508, eax
0x1800841b8  xor     edx, edx; hFile
0x1800841ba  and     eax, 20h
0x1800841bd  mov     rcx, r12; lpLibFileName
0x1800841c0  or      eax, 2
0x1800841c3  mov     r8d, eax; dwFlags
0x1800841c6  call    cs:__imp_LoadLibraryExW
0x1800841cc  mov     rdi, rax
0x1800841cf  test    rax, rax
0x1800841d2  jz      loc_1800845BA
0x1800841d8  test    byte ptr cs:dword_1800B1508, 20h
0x1800841df  jnz     loc_1800845BC
0x1800841e5  lea     rax, [rsp+4B0h+FilePart]
0x1800841ea  mov     r9d, 104h; nBufferLength
0x1800841f0  mov     [rsp+4B0h+lpFilePart], rax; lpFilePart
0x1800841f5  xor     r8d, r8d; lpExtension
0x1800841f8  lea     rax, [rbp+3B0h+Buffer]
0x1800841ff  mov     rdx, r12; lpFileName
0x180084202  xor     ecx, ecx; lpPath
0x180084204  mov     [rsp+4B0h+lpBuffer], rax; lpBuffer
0x180084209  call    cs:__imp_SearchPathW
0x18008420f  test    eax, eax
0x180084211  jz      loc_1800845B1
0x180084217  mov     rcx, [rsp+4B0h+FilePart]
0x18008421c  test    rcx, rcx
0x18008421f  jnz     short loc_180084232
0x180084221  lea     rax, [rbp+3B0h+Buffer]
0x180084228  mov     esi, r13d
0x18008422b  mov     [rsp+4B0h+FilePart], rax
0x180084230  jmp     short loc_18008423E
0x180084232  lea     rsi, [rbp+3B0h+Buffer]
0x180084239  mov     [rcx-2], r13w
0x18008423e  xor     r9d, r9d; wLanguage
0x180084241  lea     rdx, Type; "MUI"
0x180084248  mov     rcx, rdi; hModule
0x18008424b  lea     r8d, [r9+1]; lpName
0x18008424f  call    cs:__imp_FindResourceExW
0x180084255  test    rax, rax
0x180084258  jz      loc_180084431
0x18008425e  mov     eax, cs:dword_1800B1508
0x180084264  test    al, 4
0x180084266  jz      loc_18008448E
0x18008426c  mov     rbx, r13
0x18008426f  call    cs:__imp_GetUserDefaultUILanguage
0x180084275  mov     r15d, 404h
0x18008427b  movzx   r14d, ax
0x18008427f  cmp     ax, r15w
0x180084283  jnz     short loc_18008428E
0x180084285  call    GetCHTLangauge
0x18008428a  movzx   r14d, ax
0x18008428e  lea     r9, [rbp+3B0h+var_3C0]
0x180084292  movzx   ecx, r14w
0x180084296  lea     r8, [rbp+3B0h+var_310]
0x18008429d  lea     rdx, [rsp+4B0h+var_470]
0x1800842a2  call    LookupLangID
0x1800842a7  test    eax, eax
0x1800842a9  jz      loc_180084579
0x1800842af  mov     r9, [rsp+4B0h+FilePart]
0x1800842b4  lea     r8, [rsp+4B0h+var_470]
0x1800842b9  mov     rdx, rsi
0x1800842bc  mov     rcx, rdi
0x1800842bf  call    LoadMUIFile
0x1800842c4  mov     rbx, rax
0x1800842c7  test    rax, rax
0x1800842ca  jnz     loc_180084582
0x1800842d0  mov     r9, [rsp+4B0h+FilePart]
0x1800842d5  lea     r8, [rbp+3B0h+var_310]
0x1800842dc  mov     rdx, rsi
0x1800842df  mov     rcx, rdi
0x1800842e2  call    LoadMUIFile
0x1800842e7  mov     rbx, rax
0x1800842ea  test    rax, rax
0x1800842ed  jnz     loc_180084582
0x1800842f3  cmp     [rbp+3B0h+var_3C0], r13w
0x1800842f8  jz      short loc_18008431A
0x1800842fa  mov     r9, [rsp+4B0h+FilePart]
0x1800842ff  lea     r8, [rbp+3B0h+var_3C0]
0x180084303  mov     rdx, rsi
0x180084306  mov     rcx, rdi
0x180084309  call    LoadMUIFile
0x18008430e  mov     rbx, rax
0x180084311  test    rax, rax
0x180084314  jnz     loc_180084582
0x18008431a  mov     eax, 0C04h
0x18008431f  cmp     r14w, ax
0x180084323  jnz     short loc_18008432D
0x180084325  mov     r14d, r15d
0x180084328  jmp     loc_18008428E
0x18008432d  call    cs:__imp_GetSystemDefaultUILanguage
0x180084333  movzx   r15d, ax
0x180084337  cmp     ax, r14w
0x18008433b  jz      loc_1800843CC
0x180084341  lea     r9, [rbp+3B0h+var_3C0]
0x180084345  movzx   ecx, ax
0x180084348  lea     r8, [rbp+3B0h+var_310]
0x18008434f  lea     rdx, [rsp+4B0h+var_470]
0x180084354  call    LookupLangID
0x180084359  test    eax, eax
0x18008435b  jz      loc_180084431
0x180084361  mov     r9, [rsp+4B0h+FilePart]
0x180084366  lea     r8, [rsp+4B0h+var_470]
0x18008436b  mov     rdx, rsi
0x18008436e  mov     rcx, rdi
0x180084371  call    LoadMUIFile
0x180084376  mov     rbx, rax
0x180084379  test    rax, rax
0x18008437c  jnz     loc_180084582
0x180084382  mov     r9, [rsp+4B0h+FilePart]
0x180084387  lea     r8, [rbp+3B0h+var_310]
0x18008438e  mov     rdx, rsi
0x180084391  mov     rcx, rdi
0x180084394  call    LoadMUIFile
0x180084399  mov     rbx, rax
0x18008439c  test    rax, rax
0x18008439f  jnz     loc_180084582
0x1800843a5  cmp     [rbp+3B0h+var_3C0], r13w
0x1800843aa  jz      short loc_1800843CC
0x1800843ac  mov     r9, [rsp+4B0h+FilePart]
0x1800843b1  lea     r8, [rbp+3B0h+var_3C0]
0x1800843b5  mov     rdx, rsi
0x1800843b8  mov     rcx, rdi
0x1800843bb  call    LoadMUIFile
0x1800843c0  mov     rbx, rax
0x1800843c3  test    rax, rax
0x1800843c6  jnz     loc_180084582
0x1800843cc  mov     ecx, 409h
0x1800843d1  cmp     cx, r14w
0x1800843d5  jz      short loc_180084412
0x1800843d7  cmp     cx, r15w
0x1800843db  jz      short loc_180084412
0x1800843dd  xor     r9d, r9d
0x1800843e0  lea     r8, [rbp+3B0h+var_310]
0x1800843e7  lea     rdx, [rsp+4B0h+var_470]
0x1800843ec  call    LookupLangID
0x1800843f1  mov     r9, [rsp+4B0h+FilePart]
0x1800843f6  lea     r8, [rsp+4B0h+var_470]
0x1800843fb  mov     rdx, rsi
0x1800843fe  mov     rcx, rdi
0x180084401  call    LoadMUIFile
0x180084406  mov     rbx, rax
0x180084409  test    rax, rax
0x18008440c  jnz     loc_180084582
0x180084412  mov     r9, [rsp+4B0h+FilePart]
0x180084417  xor     r8d, r8d
0x18008441a  mov     rdx, rsi
0x18008441d  mov     rcx, rdi
0x180084420  call    LoadMUIFile
0x180084425  mov     rbx, rax
0x180084428  test    rax, rax
0x18008442b  jnz     loc_180084582
0x180084431  test    dil, 1
0x180084435  jz      loc_1800845AC
0x18008443b  mov     rcx, rdi; hLibModule
0x18008443e  call    cs:__imp_FreeLibrary
0x180084444  call    GetOSType
0x180084449  test    al, 38h
0x18008444b  jz      loc_180084590
0x180084451  mov     rax, [rsp+4B0h+FilePart]
0x180084456  lea     r8, aSS_0; "%s\\%s"
0x18008445d  mov     r9, rsi
0x180084460  mov     [rsp+4B0h+lpBuffer], rax
0x180084465  mov     edx, 104h; unsigned __int64
0x18008446a  lea     rcx, [rbp+3B0h+Buffer]; unsigned __int16 *
0x180084471  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180084476  xor     r8d, r8d
0x180084479  lea     rcx, [rbp+3B0h+Buffer]
0x180084480  lea     edx, [r8+1]
0x180084484  call    MapMUIFile
0x180084489  jmp     loc_1800845A9
0x18008448e  test    al, 3
0x180084490  jz      short loc_180084431
0x180084492  call    GetInstallLanguage
0x180084497  lea     r9, [rbp+3B0h+var_3C0]
0x18008449b  movzx   ecx, ax
0x18008449e  lea     r8, [rbp+3B0h+var_310]
0x1800844a5  movzx   r14d, ax
0x1800844a9  lea     rdx, [rsp+4B0h+var_470]
0x1800844ae  call    LookupLangID
0x1800844b3  test    eax, eax
0x1800844b5  jz      loc_180084431
0x1800844bb  mov     r9, [rsp+4B0h+FilePart]
0x1800844c0  lea     r8, [rsp+4B0h+var_470]
0x1800844c5  mov     rdx, rsi
0x1800844c8  mov     rcx, rdi
0x1800844cb  call    LoadMUIFile
0x1800844d0  mov     rbx, rax
0x1800844d3  test    rax, rax
0x1800844d6  jnz     loc_180084582
0x1800844dc  mov     r9, [rsp+4B0h+FilePart]
0x1800844e1  lea     r8, [rbp+3B0h+var_310]
0x1800844e8  mov     rdx, rsi
0x1800844eb  mov     rcx, rdi
0x1800844ee  call    LoadMUIFile
0x1800844f3  mov     rbx, rax
0x1800844f6  test    rax, rax
0x1800844f9  jnz     loc_180084582
0x1800844ff  cmp     [rbp+3B0h+var_3C0], r13w
0x180084504  jz      short loc_180084522
0x180084506  mov     r9, [rsp+4B0h+FilePart]
0x18008450b  lea     r8, [rbp+3B0h+var_3C0]
0x18008450f  mov     rdx, rsi
0x180084512  mov     rcx, rdi
0x180084515  call    LoadMUIFile
0x18008451a  mov     rbx, rax
0x18008451d  test    rax, rax
0x180084520  jnz     short loc_180084582
0x180084522  mov     ecx, 409h
0x180084527  cmp     cx, r14w
0x18008452b  jz      short loc_18008455E
0x18008452d  xor     r9d, r9d
0x180084530  lea     r8, [rbp+3B0h+var_310]
0x180084537  lea     rdx, [rsp+4B0h+var_470]
0x18008453c  call    LookupLangID
0x180084541  mov     r9, [rsp+4B0h+FilePart]
0x180084546  lea     r8, [rsp+4B0h+var_470]
0x18008454b  mov     rdx, rsi
0x18008454e  mov     rcx, rdi
0x180084551  call    LoadMUIFile
0x180084556  mov     rbx, rax
0x180084559  test    rax, rax
0x18008455c  jnz     short loc_180084582
0x18008455e  mov     r9, [rsp+4B0h+FilePart]
0x180084563  xor     r8d, r8d
0x180084566  mov     rdx, rsi
0x180084569  mov     rcx, rdi
0x18008456c  call    LoadMUIFile
0x180084571  mov     rbx, rax
0x180084574  test    rax, rax
0x180084577  jnz     short loc_180084582
0x180084579  test    rbx, rbx
0x18008457c  jz      loc_180084431
0x180084582  mov     rcx, rdi; hLibModule
0x180084585  call    cs:__imp_FreeLibrary
0x18008458b  mov     rax, rbx
0x18008458e  jmp     short loc_1800845BC
0x180084590  call    GetOSType
0x180084595  test    al, 26h
0x180084597  mov     r8d, r13d
0x18008459a  mov     rcx, r12; lpLibFileName
0x18008459d  setnz   r8b; dwFlags
0x1800845a1  xor     edx, edx; hFile
0x1800845a3  call    cs:__imp_LoadLibraryExW
0x1800845a9  mov     rdi, rax
0x1800845ac  mov     rax, rdi
0x1800845af  jmp     short loc_1800845BC
0x1800845b1  mov     rcx, rdi; hLibModule
0x1800845b4  call    cs:__imp_FreeLibrary
0x1800845ba  xor     eax, eax
0x1800845bc  mov     rcx, [rbp+3B0h+var_50]
0x1800845c3  xor     rcx, rsp; StackCookie
0x1800845c6  call    __security_check_cookie
0x1800845cb  add     rsp, 478h
0x1800845d2  pop     r15
0x1800845d4  pop     r14
0x1800845d6  pop     r13
0x1800845d8  pop     r12
0x1800845da  pop     rdi
0x1800845db  pop     rsi
0x1800845dc  pop     rbx
0x1800845dd  pop     rbp
0x1800845de  retn
```
