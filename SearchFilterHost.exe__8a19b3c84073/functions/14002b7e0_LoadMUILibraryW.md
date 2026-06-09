# LoadMUILibraryW

- ea: `0x14002b7e0`
- end: `0x14002bc53`
- name: `LoadMUILibraryW`
- size: `1139`
- prototype: `HINSTANCE __stdcall(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x14002849c`

## callees

- `0x1400030a0`
- `0x14000a684`
- `0x14002b0fc`
- `0x14002b17c`
- `0x14002b28c`
- `0x14002b3b4`
- `0x14002b428`
- `0x14002b59c`
- `0x14002b7e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14002bab2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14002bbf9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14002bc28`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14002bab2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14002bbf9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14002bc28`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x14002b8c3`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x14002b8c3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14002b83a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14002bc17`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14002b83a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14002bc17`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x14002b87d`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x14002b87d`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetSystemDefaultUILanguage` at `0x14002b9a1`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetSystemDefaultUILanguage` at `0x14002b9a1`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x14002b8e3`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x14002b8e3`

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
  dword_14006BE40 = GetOSType(pszFullModuleName, dwLangConvention, LangID);
  result = LoadLibraryExW(pszFullModuleName, 0, dword_14006BE40 & 0x20 | 2u);
  v5 = result;
  if ( !result )
    return 0;
  if ( (dword_14006BE40 & 0x20) != 0 )
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
    if ( (dword_14006BE40 & 4) != 0 )
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
    else if ( (dword_14006BE40 & 3) != 0 )
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
0x14002b7e0  push    rbp
0x14002b7e2  push    rbx
0x14002b7e3  push    rsi
0x14002b7e4  push    rdi
0x14002b7e5  push    r12
0x14002b7e7  push    r13
0x14002b7e9  push    r14
0x14002b7eb  push    r15
0x14002b7ed  lea     rbp, [rsp-378h]
0x14002b7f5  sub     rsp, 478h
0x14002b7fc  mov     rax, cs:__security_cookie
0x14002b803  xor     rax, rsp
0x14002b806  mov     [rbp+3B0h+var_50], rax
0x14002b80d  xor     r13d, r13d
0x14002b810  mov     r12, rcx
0x14002b813  mov     [rsp+4B0h+FilePart], r13
0x14002b818  test    rcx, rcx
0x14002b81b  jz      loc_14002BC2E
0x14002b821  call    GetOSType
0x14002b826  mov     cs:dword_14006BE40, eax
0x14002b82c  xor     edx, edx; hFile
0x14002b82e  and     eax, 20h
0x14002b831  mov     rcx, r12; lpLibFileName
0x14002b834  or      eax, 2
0x14002b837  mov     r8d, eax; dwFlags
0x14002b83a  call    cs:__imp_LoadLibraryExW
0x14002b840  mov     rdi, rax
0x14002b843  test    rax, rax
0x14002b846  jz      loc_14002BC2E
0x14002b84c  test    byte ptr cs:dword_14006BE40, 20h
0x14002b853  jnz     loc_14002BC30
0x14002b859  lea     rax, [rsp+4B0h+FilePart]
0x14002b85e  mov     r9d, 104h; nBufferLength
0x14002b864  mov     [rsp+4B0h+lpFilePart], rax; lpFilePart
0x14002b869  xor     r8d, r8d; lpExtension
0x14002b86c  lea     rax, [rbp+3B0h+Buffer]
0x14002b873  mov     rdx, r12; lpFileName
0x14002b876  xor     ecx, ecx; lpPath
0x14002b878  mov     [rsp+4B0h+lpBuffer], rax; lpBuffer
0x14002b87d  call    cs:__imp_SearchPathW
0x14002b883  test    eax, eax
0x14002b885  jz      loc_14002BC25
0x14002b88b  mov     rcx, [rsp+4B0h+FilePart]
0x14002b890  test    rcx, rcx
0x14002b893  jnz     short loc_14002B8A6
0x14002b895  lea     rax, [rbp+3B0h+Buffer]
0x14002b89c  mov     esi, r13d
0x14002b89f  mov     [rsp+4B0h+FilePart], rax
0x14002b8a4  jmp     short loc_14002B8B2
0x14002b8a6  lea     rsi, [rbp+3B0h+Buffer]
0x14002b8ad  mov     [rcx-2], r13w
0x14002b8b2  xor     r9d, r9d; wLanguage
0x14002b8b5  lea     rdx, Type; "MUI"
0x14002b8bc  mov     rcx, rdi; hModule
0x14002b8bf  lea     r8d, [r9+1]; lpName
0x14002b8c3  call    cs:__imp_FindResourceExW
0x14002b8c9  test    rax, rax
0x14002b8cc  jz      loc_14002BAA5
0x14002b8d2  mov     eax, cs:dword_14006BE40
0x14002b8d8  test    al, 4
0x14002b8da  jz      loc_14002BB02
0x14002b8e0  mov     rbx, r13
0x14002b8e3  call    cs:__imp_GetUserDefaultUILanguage
0x14002b8e9  mov     r15d, 404h
0x14002b8ef  movzx   r14d, ax
0x14002b8f3  cmp     ax, r15w
0x14002b8f7  jnz     short loc_14002B902
0x14002b8f9  call    GetCHTLangauge
0x14002b8fe  movzx   r14d, ax
0x14002b902  lea     r9, [rbp+3B0h+var_3C0]
0x14002b906  movzx   ecx, r14w
0x14002b90a  lea     r8, [rbp+3B0h+var_310]
0x14002b911  lea     rdx, [rsp+4B0h+var_470]
0x14002b916  call    LookupLangID
0x14002b91b  test    eax, eax
0x14002b91d  jz      loc_14002BBED
0x14002b923  mov     r9, [rsp+4B0h+FilePart]
0x14002b928  lea     r8, [rsp+4B0h+var_470]
0x14002b92d  mov     rdx, rsi
0x14002b930  mov     rcx, rdi
0x14002b933  call    LoadMUIFile
0x14002b938  mov     rbx, rax
0x14002b93b  test    rax, rax
0x14002b93e  jnz     loc_14002BBF6
0x14002b944  mov     r9, [rsp+4B0h+FilePart]
0x14002b949  lea     r8, [rbp+3B0h+var_310]
0x14002b950  mov     rdx, rsi
0x14002b953  mov     rcx, rdi
0x14002b956  call    LoadMUIFile
0x14002b95b  mov     rbx, rax
0x14002b95e  test    rax, rax
0x14002b961  jnz     loc_14002BBF6
0x14002b967  cmp     [rbp+3B0h+var_3C0], r13w
0x14002b96c  jz      short loc_14002B98E
0x14002b96e  mov     r9, [rsp+4B0h+FilePart]
0x14002b973  lea     r8, [rbp+3B0h+var_3C0]
0x14002b977  mov     rdx, rsi
0x14002b97a  mov     rcx, rdi
0x14002b97d  call    LoadMUIFile
0x14002b982  mov     rbx, rax
0x14002b985  test    rax, rax
0x14002b988  jnz     loc_14002BBF6
0x14002b98e  mov     eax, 0C04h
0x14002b993  cmp     r14w, ax
0x14002b997  jnz     short loc_14002B9A1
0x14002b999  mov     r14d, r15d
0x14002b99c  jmp     loc_14002B902
0x14002b9a1  call    cs:__imp_GetSystemDefaultUILanguage
0x14002b9a7  movzx   r15d, ax
0x14002b9ab  cmp     ax, r14w
0x14002b9af  jz      loc_14002BA40
0x14002b9b5  lea     r9, [rbp+3B0h+var_3C0]
0x14002b9b9  movzx   ecx, ax
0x14002b9bc  lea     r8, [rbp+3B0h+var_310]
0x14002b9c3  lea     rdx, [rsp+4B0h+var_470]
0x14002b9c8  call    LookupLangID
0x14002b9cd  test    eax, eax
0x14002b9cf  jz      loc_14002BAA5
0x14002b9d5  mov     r9, [rsp+4B0h+FilePart]
0x14002b9da  lea     r8, [rsp+4B0h+var_470]
0x14002b9df  mov     rdx, rsi
0x14002b9e2  mov     rcx, rdi
0x14002b9e5  call    LoadMUIFile
0x14002b9ea  mov     rbx, rax
0x14002b9ed  test    rax, rax
0x14002b9f0  jnz     loc_14002BBF6
0x14002b9f6  mov     r9, [rsp+4B0h+FilePart]
0x14002b9fb  lea     r8, [rbp+3B0h+var_310]
0x14002ba02  mov     rdx, rsi
0x14002ba05  mov     rcx, rdi
0x14002ba08  call    LoadMUIFile
0x14002ba0d  mov     rbx, rax
0x14002ba10  test    rax, rax
0x14002ba13  jnz     loc_14002BBF6
0x14002ba19  cmp     [rbp+3B0h+var_3C0], r13w
0x14002ba1e  jz      short loc_14002BA40
0x14002ba20  mov     r9, [rsp+4B0h+FilePart]
0x14002ba25  lea     r8, [rbp+3B0h+var_3C0]
0x14002ba29  mov     rdx, rsi
0x14002ba2c  mov     rcx, rdi
0x14002ba2f  call    LoadMUIFile
0x14002ba34  mov     rbx, rax
0x14002ba37  test    rax, rax
0x14002ba3a  jnz     loc_14002BBF6
0x14002ba40  mov     ecx, 409h
0x14002ba45  cmp     cx, r14w
0x14002ba49  jz      short loc_14002BA86
0x14002ba4b  cmp     cx, r15w
0x14002ba4f  jz      short loc_14002BA86
0x14002ba51  xor     r9d, r9d
0x14002ba54  lea     r8, [rbp+3B0h+var_310]
0x14002ba5b  lea     rdx, [rsp+4B0h+var_470]
0x14002ba60  call    LookupLangID
0x14002ba65  mov     r9, [rsp+4B0h+FilePart]
0x14002ba6a  lea     r8, [rsp+4B0h+var_470]
0x14002ba6f  mov     rdx, rsi
0x14002ba72  mov     rcx, rdi
0x14002ba75  call    LoadMUIFile
0x14002ba7a  mov     rbx, rax
0x14002ba7d  test    rax, rax
0x14002ba80  jnz     loc_14002BBF6
0x14002ba86  mov     r9, [rsp+4B0h+FilePart]
0x14002ba8b  xor     r8d, r8d
0x14002ba8e  mov     rdx, rsi
0x14002ba91  mov     rcx, rdi
0x14002ba94  call    LoadMUIFile
0x14002ba99  mov     rbx, rax
0x14002ba9c  test    rax, rax
0x14002ba9f  jnz     loc_14002BBF6
0x14002baa5  test    dil, 1
0x14002baa9  jz      loc_14002BC20
0x14002baaf  mov     rcx, rdi; hLibModule
0x14002bab2  call    cs:__imp_FreeLibrary
0x14002bab8  call    GetOSType
0x14002babd  test    al, 38h
0x14002babf  jz      loc_14002BC04
0x14002bac5  mov     rax, [rsp+4B0h+FilePart]
0x14002baca  lea     r8, aSS; "%s\\%s"
0x14002bad1  mov     r9, rsi
0x14002bad4  mov     [rsp+4B0h+lpBuffer], rax
0x14002bad9  mov     edx, 104h; unsigned __int64
0x14002bade  lea     rcx, [rbp+3B0h+Buffer]; unsigned __int16 *
0x14002bae5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002baea  xor     r8d, r8d
0x14002baed  lea     rcx, [rbp+3B0h+Buffer]
0x14002baf4  lea     edx, [r8+1]
0x14002baf8  call    MapMUIFile
0x14002bafd  jmp     loc_14002BC1D
0x14002bb02  test    al, 3
0x14002bb04  jz      short loc_14002BAA5
0x14002bb06  call    GetInstallLanguage
0x14002bb0b  lea     r9, [rbp+3B0h+var_3C0]
0x14002bb0f  movzx   ecx, ax
0x14002bb12  lea     r8, [rbp+3B0h+var_310]
0x14002bb19  movzx   r14d, ax
0x14002bb1d  lea     rdx, [rsp+4B0h+var_470]
0x14002bb22  call    LookupLangID
0x14002bb27  test    eax, eax
0x14002bb29  jz      loc_14002BAA5
0x14002bb2f  mov     r9, [rsp+4B0h+FilePart]
0x14002bb34  lea     r8, [rsp+4B0h+var_470]
0x14002bb39  mov     rdx, rsi
0x14002bb3c  mov     rcx, rdi
0x14002bb3f  call    LoadMUIFile
0x14002bb44  mov     rbx, rax
0x14002bb47  test    rax, rax
0x14002bb4a  jnz     loc_14002BBF6
0x14002bb50  mov     r9, [rsp+4B0h+FilePart]
0x14002bb55  lea     r8, [rbp+3B0h+var_310]
0x14002bb5c  mov     rdx, rsi
0x14002bb5f  mov     rcx, rdi
0x14002bb62  call    LoadMUIFile
0x14002bb67  mov     rbx, rax
0x14002bb6a  test    rax, rax
0x14002bb6d  jnz     loc_14002BBF6
0x14002bb73  cmp     [rbp+3B0h+var_3C0], r13w
0x14002bb78  jz      short loc_14002BB96
0x14002bb7a  mov     r9, [rsp+4B0h+FilePart]
0x14002bb7f  lea     r8, [rbp+3B0h+var_3C0]
0x14002bb83  mov     rdx, rsi
0x14002bb86  mov     rcx, rdi
0x14002bb89  call    LoadMUIFile
0x14002bb8e  mov     rbx, rax
0x14002bb91  test    rax, rax
0x14002bb94  jnz     short loc_14002BBF6
0x14002bb96  mov     ecx, 409h
0x14002bb9b  cmp     cx, r14w
0x14002bb9f  jz      short loc_14002BBD2
0x14002bba1  xor     r9d, r9d
0x14002bba4  lea     r8, [rbp+3B0h+var_310]
0x14002bbab  lea     rdx, [rsp+4B0h+var_470]
0x14002bbb0  call    LookupLangID
0x14002bbb5  mov     r9, [rsp+4B0h+FilePart]
0x14002bbba  lea     r8, [rsp+4B0h+var_470]
0x14002bbbf  mov     rdx, rsi
0x14002bbc2  mov     rcx, rdi
0x14002bbc5  call    LoadMUIFile
0x14002bbca  mov     rbx, rax
0x14002bbcd  test    rax, rax
0x14002bbd0  jnz     short loc_14002BBF6
0x14002bbd2  mov     r9, [rsp+4B0h+FilePart]
0x14002bbd7  xor     r8d, r8d
0x14002bbda  mov     rdx, rsi
0x14002bbdd  mov     rcx, rdi
0x14002bbe0  call    LoadMUIFile
0x14002bbe5  mov     rbx, rax
0x14002bbe8  test    rax, rax
0x14002bbeb  jnz     short loc_14002BBF6
0x14002bbed  test    rbx, rbx
0x14002bbf0  jz      loc_14002BAA5
0x14002bbf6  mov     rcx, rdi; hLibModule
0x14002bbf9  call    cs:__imp_FreeLibrary
0x14002bbff  mov     rax, rbx
0x14002bc02  jmp     short loc_14002BC30
0x14002bc04  call    GetOSType
0x14002bc09  test    al, 26h
0x14002bc0b  mov     r8d, r13d
0x14002bc0e  mov     rcx, r12; lpLibFileName
0x14002bc11  setnz   r8b; dwFlags
0x14002bc15  xor     edx, edx; hFile
0x14002bc17  call    cs:__imp_LoadLibraryExW
0x14002bc1d  mov     rdi, rax
0x14002bc20  mov     rax, rdi
0x14002bc23  jmp     short loc_14002BC30
0x14002bc25  mov     rcx, rdi; hLibModule
0x14002bc28  call    cs:__imp_FreeLibrary
0x14002bc2e  xor     eax, eax
0x14002bc30  mov     rcx, [rbp+3B0h+var_50]
0x14002bc37  xor     rcx, rsp; StackCookie
0x14002bc3a  call    __security_check_cookie
0x14002bc3f  add     rsp, 478h
0x14002bc46  pop     r15
0x14002bc48  pop     r14
0x14002bc4a  pop     r13
0x14002bc4c  pop     r12
0x14002bc4e  pop     rdi
0x14002bc4f  pop     rsi
0x14002bc50  pop     rbx
0x14002bc51  pop     rbp
0x14002bc52  retn
```
