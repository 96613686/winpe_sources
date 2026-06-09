# LoadMUILibraryW

- ea: `0x1400693d0`
- end: `0x140069843`
- name: `LoadMUILibraryW`
- size: `1139`
- prototype: `HINSTANCE __stdcall(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x14004d35c`

## callees

- `0x140005240`
- `0x140029a8c`
- `0x140068cec`
- `0x140068d6c`
- `0x140068e7c`
- `0x140068fa4`
- `0x140069018`
- `0x14006918c`
- `0x1400693d0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400696a2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400697e9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140069818`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400696a2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400697e9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140069818`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14006942a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140069807`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14006942a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140069807`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1400694b3`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1400694b3`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x14006946d`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x14006946d`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x1400694d3`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x1400694d3`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetSystemDefaultUILanguage` at `0x140069591`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetSystemDefaultUILanguage` at `0x140069591`

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
  dword_1400989A8 = GetOSType(pszFullModuleName, dwLangConvention, LangID);
  result = LoadLibraryExW(pszFullModuleName, 0, dword_1400989A8 & 0x20 | 2u);
  v5 = result;
  if ( !result )
    return 0;
  if ( (dword_1400989A8 & 0x20) != 0 )
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
    if ( (dword_1400989A8 & 4) != 0 )
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
    else if ( (dword_1400989A8 & 3) != 0 )
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
0x1400693d0  push    rbp
0x1400693d2  push    rbx
0x1400693d3  push    rsi
0x1400693d4  push    rdi
0x1400693d5  push    r12
0x1400693d7  push    r13
0x1400693d9  push    r14
0x1400693db  push    r15
0x1400693dd  lea     rbp, [rsp-378h]
0x1400693e5  sub     rsp, 478h
0x1400693ec  mov     rax, cs:__security_cookie
0x1400693f3  xor     rax, rsp
0x1400693f6  mov     [rbp+3B0h+var_50], rax
0x1400693fd  xor     r13d, r13d
0x140069400  mov     r12, rcx
0x140069403  mov     [rsp+4B0h+FilePart], r13
0x140069408  test    rcx, rcx
0x14006940b  jz      loc_14006981E
0x140069411  call    GetOSType
0x140069416  mov     cs:dword_1400989A8, eax
0x14006941c  xor     edx, edx; hFile
0x14006941e  and     eax, 20h
0x140069421  mov     rcx, r12; lpLibFileName
0x140069424  or      eax, 2
0x140069427  mov     r8d, eax; dwFlags
0x14006942a  call    cs:__imp_LoadLibraryExW
0x140069430  mov     rdi, rax
0x140069433  test    rax, rax
0x140069436  jz      loc_14006981E
0x14006943c  test    byte ptr cs:dword_1400989A8, 20h
0x140069443  jnz     loc_140069820
0x140069449  lea     rax, [rsp+4B0h+FilePart]
0x14006944e  mov     r9d, 104h; nBufferLength
0x140069454  mov     [rsp+4B0h+lpFilePart], rax; lpFilePart
0x140069459  xor     r8d, r8d; lpExtension
0x14006945c  lea     rax, [rbp+3B0h+Buffer]
0x140069463  mov     rdx, r12; lpFileName
0x140069466  xor     ecx, ecx; lpPath
0x140069468  mov     [rsp+4B0h+lpBuffer], rax; lpBuffer
0x14006946d  call    cs:__imp_SearchPathW
0x140069473  test    eax, eax
0x140069475  jz      loc_140069815
0x14006947b  mov     rcx, [rsp+4B0h+FilePart]
0x140069480  test    rcx, rcx
0x140069483  jnz     short loc_140069496
0x140069485  lea     rax, [rbp+3B0h+Buffer]
0x14006948c  mov     esi, r13d
0x14006948f  mov     [rsp+4B0h+FilePart], rax
0x140069494  jmp     short loc_1400694A2
0x140069496  lea     rsi, [rbp+3B0h+Buffer]
0x14006949d  mov     [rcx-2], r13w
0x1400694a2  xor     r9d, r9d; wLanguage
0x1400694a5  lea     rdx, Type; "MUI"
0x1400694ac  mov     rcx, rdi; hModule
0x1400694af  lea     r8d, [r9+1]; lpName
0x1400694b3  call    cs:__imp_FindResourceExW
0x1400694b9  test    rax, rax
0x1400694bc  jz      loc_140069695
0x1400694c2  mov     eax, cs:dword_1400989A8
0x1400694c8  test    al, 4
0x1400694ca  jz      loc_1400696F2
0x1400694d0  mov     rbx, r13
0x1400694d3  call    cs:__imp_GetUserDefaultUILanguage
0x1400694d9  mov     r15d, 404h
0x1400694df  movzx   r14d, ax
0x1400694e3  cmp     ax, r15w
0x1400694e7  jnz     short loc_1400694F2
0x1400694e9  call    GetCHTLangauge
0x1400694ee  movzx   r14d, ax
0x1400694f2  lea     r9, [rbp+3B0h+var_3C0]
0x1400694f6  movzx   ecx, r14w
0x1400694fa  lea     r8, [rbp+3B0h+var_310]
0x140069501  lea     rdx, [rsp+4B0h+var_470]
0x140069506  call    LookupLangID
0x14006950b  test    eax, eax
0x14006950d  jz      loc_1400697DD
0x140069513  mov     r9, [rsp+4B0h+FilePart]
0x140069518  lea     r8, [rsp+4B0h+var_470]
0x14006951d  mov     rdx, rsi
0x140069520  mov     rcx, rdi
0x140069523  call    LoadMUIFile
0x140069528  mov     rbx, rax
0x14006952b  test    rax, rax
0x14006952e  jnz     loc_1400697E6
0x140069534  mov     r9, [rsp+4B0h+FilePart]
0x140069539  lea     r8, [rbp+3B0h+var_310]
0x140069540  mov     rdx, rsi
0x140069543  mov     rcx, rdi
0x140069546  call    LoadMUIFile
0x14006954b  mov     rbx, rax
0x14006954e  test    rax, rax
0x140069551  jnz     loc_1400697E6
0x140069557  cmp     [rbp+3B0h+var_3C0], r13w
0x14006955c  jz      short loc_14006957E
0x14006955e  mov     r9, [rsp+4B0h+FilePart]
0x140069563  lea     r8, [rbp+3B0h+var_3C0]
0x140069567  mov     rdx, rsi
0x14006956a  mov     rcx, rdi
0x14006956d  call    LoadMUIFile
0x140069572  mov     rbx, rax
0x140069575  test    rax, rax
0x140069578  jnz     loc_1400697E6
0x14006957e  mov     eax, 0C04h
0x140069583  cmp     r14w, ax
0x140069587  jnz     short loc_140069591
0x140069589  mov     r14d, r15d
0x14006958c  jmp     loc_1400694F2
0x140069591  call    cs:__imp_GetSystemDefaultUILanguage
0x140069597  movzx   r15d, ax
0x14006959b  cmp     ax, r14w
0x14006959f  jz      loc_140069630
0x1400695a5  lea     r9, [rbp+3B0h+var_3C0]
0x1400695a9  movzx   ecx, ax
0x1400695ac  lea     r8, [rbp+3B0h+var_310]
0x1400695b3  lea     rdx, [rsp+4B0h+var_470]
0x1400695b8  call    LookupLangID
0x1400695bd  test    eax, eax
0x1400695bf  jz      loc_140069695
0x1400695c5  mov     r9, [rsp+4B0h+FilePart]
0x1400695ca  lea     r8, [rsp+4B0h+var_470]
0x1400695cf  mov     rdx, rsi
0x1400695d2  mov     rcx, rdi
0x1400695d5  call    LoadMUIFile
0x1400695da  mov     rbx, rax
0x1400695dd  test    rax, rax
0x1400695e0  jnz     loc_1400697E6
0x1400695e6  mov     r9, [rsp+4B0h+FilePart]
0x1400695eb  lea     r8, [rbp+3B0h+var_310]
0x1400695f2  mov     rdx, rsi
0x1400695f5  mov     rcx, rdi
0x1400695f8  call    LoadMUIFile
0x1400695fd  mov     rbx, rax
0x140069600  test    rax, rax
0x140069603  jnz     loc_1400697E6
0x140069609  cmp     [rbp+3B0h+var_3C0], r13w
0x14006960e  jz      short loc_140069630
0x140069610  mov     r9, [rsp+4B0h+FilePart]
0x140069615  lea     r8, [rbp+3B0h+var_3C0]
0x140069619  mov     rdx, rsi
0x14006961c  mov     rcx, rdi
0x14006961f  call    LoadMUIFile
0x140069624  mov     rbx, rax
0x140069627  test    rax, rax
0x14006962a  jnz     loc_1400697E6
0x140069630  mov     ecx, 409h
0x140069635  cmp     cx, r14w
0x140069639  jz      short loc_140069676
0x14006963b  cmp     cx, r15w
0x14006963f  jz      short loc_140069676
0x140069641  xor     r9d, r9d
0x140069644  lea     r8, [rbp+3B0h+var_310]
0x14006964b  lea     rdx, [rsp+4B0h+var_470]
0x140069650  call    LookupLangID
0x140069655  mov     r9, [rsp+4B0h+FilePart]
0x14006965a  lea     r8, [rsp+4B0h+var_470]
0x14006965f  mov     rdx, rsi
0x140069662  mov     rcx, rdi
0x140069665  call    LoadMUIFile
0x14006966a  mov     rbx, rax
0x14006966d  test    rax, rax
0x140069670  jnz     loc_1400697E6
0x140069676  mov     r9, [rsp+4B0h+FilePart]
0x14006967b  xor     r8d, r8d
0x14006967e  mov     rdx, rsi
0x140069681  mov     rcx, rdi
0x140069684  call    LoadMUIFile
0x140069689  mov     rbx, rax
0x14006968c  test    rax, rax
0x14006968f  jnz     loc_1400697E6
0x140069695  test    dil, 1
0x140069699  jz      loc_140069810
0x14006969f  mov     rcx, rdi; hLibModule
0x1400696a2  call    cs:__imp_FreeLibrary
0x1400696a8  call    GetOSType
0x1400696ad  test    al, 38h
0x1400696af  jz      loc_1400697F4
0x1400696b5  mov     rax, [rsp+4B0h+FilePart]
0x1400696ba  lea     r8, aSS; "%s\\%s"
0x1400696c1  mov     r9, rsi
0x1400696c4  mov     [rsp+4B0h+lpBuffer], rax
0x1400696c9  mov     edx, 104h; unsigned __int64
0x1400696ce  lea     rcx, [rbp+3B0h+Buffer]; unsigned __int16 *
0x1400696d5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400696da  xor     r8d, r8d
0x1400696dd  lea     rcx, [rbp+3B0h+Buffer]
0x1400696e4  lea     edx, [r8+1]
0x1400696e8  call    MapMUIFile
0x1400696ed  jmp     loc_14006980D
0x1400696f2  test    al, 3
0x1400696f4  jz      short loc_140069695
0x1400696f6  call    GetInstallLanguage
0x1400696fb  lea     r9, [rbp+3B0h+var_3C0]
0x1400696ff  movzx   ecx, ax
0x140069702  lea     r8, [rbp+3B0h+var_310]
0x140069709  movzx   r14d, ax
0x14006970d  lea     rdx, [rsp+4B0h+var_470]
0x140069712  call    LookupLangID
0x140069717  test    eax, eax
0x140069719  jz      loc_140069695
0x14006971f  mov     r9, [rsp+4B0h+FilePart]
0x140069724  lea     r8, [rsp+4B0h+var_470]
0x140069729  mov     rdx, rsi
0x14006972c  mov     rcx, rdi
0x14006972f  call    LoadMUIFile
0x140069734  mov     rbx, rax
0x140069737  test    rax, rax
0x14006973a  jnz     loc_1400697E6
0x140069740  mov     r9, [rsp+4B0h+FilePart]
0x140069745  lea     r8, [rbp+3B0h+var_310]
0x14006974c  mov     rdx, rsi
0x14006974f  mov     rcx, rdi
0x140069752  call    LoadMUIFile
0x140069757  mov     rbx, rax
0x14006975a  test    rax, rax
0x14006975d  jnz     loc_1400697E6
0x140069763  cmp     [rbp+3B0h+var_3C0], r13w
0x140069768  jz      short loc_140069786
0x14006976a  mov     r9, [rsp+4B0h+FilePart]
0x14006976f  lea     r8, [rbp+3B0h+var_3C0]
0x140069773  mov     rdx, rsi
0x140069776  mov     rcx, rdi
0x140069779  call    LoadMUIFile
0x14006977e  mov     rbx, rax
0x140069781  test    rax, rax
0x140069784  jnz     short loc_1400697E6
0x140069786  mov     ecx, 409h
0x14006978b  cmp     cx, r14w
0x14006978f  jz      short loc_1400697C2
0x140069791  xor     r9d, r9d
0x140069794  lea     r8, [rbp+3B0h+var_310]
0x14006979b  lea     rdx, [rsp+4B0h+var_470]
0x1400697a0  call    LookupLangID
0x1400697a5  mov     r9, [rsp+4B0h+FilePart]
0x1400697aa  lea     r8, [rsp+4B0h+var_470]
0x1400697af  mov     rdx, rsi
0x1400697b2  mov     rcx, rdi
0x1400697b5  call    LoadMUIFile
0x1400697ba  mov     rbx, rax
0x1400697bd  test    rax, rax
0x1400697c0  jnz     short loc_1400697E6
0x1400697c2  mov     r9, [rsp+4B0h+FilePart]
0x1400697c7  xor     r8d, r8d
0x1400697ca  mov     rdx, rsi
0x1400697cd  mov     rcx, rdi
0x1400697d0  call    LoadMUIFile
0x1400697d5  mov     rbx, rax
0x1400697d8  test    rax, rax
0x1400697db  jnz     short loc_1400697E6
0x1400697dd  test    rbx, rbx
0x1400697e0  jz      loc_140069695
0x1400697e6  mov     rcx, rdi; hLibModule
0x1400697e9  call    cs:__imp_FreeLibrary
0x1400697ef  mov     rax, rbx
0x1400697f2  jmp     short loc_140069820
0x1400697f4  call    GetOSType
0x1400697f9  test    al, 26h
0x1400697fb  mov     r8d, r13d
0x1400697fe  mov     rcx, r12; lpLibFileName
0x140069801  setnz   r8b; dwFlags
0x140069805  xor     edx, edx; hFile
0x140069807  call    cs:__imp_LoadLibraryExW
0x14006980d  mov     rdi, rax
0x140069810  mov     rax, rdi
0x140069813  jmp     short loc_140069820
0x140069815  mov     rcx, rdi; hLibModule
0x140069818  call    cs:__imp_FreeLibrary
0x14006981e  xor     eax, eax
0x140069820  mov     rcx, [rbp+3B0h+var_50]
0x140069827  xor     rcx, rsp; StackCookie
0x14006982a  call    __security_check_cookie
0x14006982f  add     rsp, 478h
0x140069836  pop     r15
0x140069838  pop     r14
0x14006983a  pop     r13
0x14006983c  pop     r12
0x14006983e  pop     rdi
0x14006983f  pop     rsi
0x140069840  pop     rbx
0x140069841  pop     rbp
0x140069842  retn
```
