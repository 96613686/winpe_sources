# LoadMUILibraryW

- ea: `0x180054cc8`
- end: `0x18005514e`
- name: `LoadMUILibraryW`
- size: `1158`
- prototype: `HINSTANCE __stdcall(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x18004f970`

## callees

- `0x1800078b0`
- `0x18001be20`
- `0x1800545b8`
- `0x180054638`
- `0x180054740`
- `0x180054868`
- `0x1800548dc`
- `0x180054a50`
- `0x180054cc8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180054db2`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180054db2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180055058`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800550ed`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005511c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180055058`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800550ed`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005511c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180054d29`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005510b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180054d29`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005510b`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x180054d6c`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x180054d6c`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x180054e99`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x180054e99`
- `KERNEL32!GetUserDefaultUILanguage` at `0x180054ddb`
- `KERNEL32!GetUserDefaultUILanguage` at `0x180054ddb`

## pseudocode

```c
HINSTANCE __stdcall LoadMUILibraryW(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)
{
  HINSTANCE result; // rax
  HMODULE v6; // rdi
  WCHAR *v7; // rsi
  HINSTANCE MUIFile; // rbx
  LANGID UserDefaultUILanguage; // r14
  LANGID SystemDefaultUILanguage; // ax
  LANGID v11; // r15
  bool v12; // zf
  __int64 InstallLanguage; // r14
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rcx
  char OSType; // al
  LPWSTR FilePart; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v21[176]; // [rsp+40h] [rbp-C0h] BYREF
  _WORD v22[88]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v23[176]; // [rsp+1A0h] [rbp+A0h] BYREF
  WCHAR Buffer[264]; // [rsp+250h] [rbp+150h] BYREF

  FilePart = 0;
  if ( !pszFullModuleName )
    return 0;
  dword_1800A44F8 = GetOSType(pszFullModuleName, dwLangConvention);
  result = LoadLibraryExW(pszFullModuleName, 0, dword_1800A44F8 & 0x20 | 2u);
  v6 = result;
  if ( !result )
    return 0;
  if ( (dword_1800A44F8 & 0x20) != 0 )
    return result;
  if ( !SearchPathW(0, pszFullModuleName, 0, 0x104u, Buffer, &FilePart) )
  {
    FreeLibrary(v6);
    return 0;
  }
  if ( FilePart )
  {
    v7 = Buffer;
    *(FilePart - 1) = 0;
  }
  else
  {
    v7 = 0;
    FilePart = Buffer;
  }
  if ( FindResourceExW(v6, L"MUI", (LPCWSTR)1, 0) )
  {
    if ( !LangID )
    {
      if ( (dword_1800A44F8 & 4) == 0 )
      {
        if ( (dword_1800A44F8 & 3) != 0 )
        {
          InstallLanguage = (unsigned __int16)GetInstallLanguage();
          if ( (unsigned int)LookupLangID(InstallLanguage, v21, v23, v22) )
          {
            MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v21, FilePart);
            if ( MUIFile )
              goto LABEL_45;
            MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v23, FilePart);
            if ( MUIFile )
              goto LABEL_45;
            if ( v22[0] )
            {
              MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v22, FilePart);
              if ( MUIFile )
                goto LABEL_45;
            }
            v12 = (_WORD)InstallLanguage == 1033;
LABEL_35:
            if ( !v12 )
            {
              LookupLangID(1033, v21, v23, 0);
              MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v21, FilePart);
              if ( MUIFile )
                goto LABEL_45;
            }
LABEL_37:
            MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, 0, FilePart);
            if ( MUIFile )
            {
LABEL_45:
              FreeLibrary(v6);
              return MUIFile;
            }
          }
        }
        goto LABEL_38;
      }
      MUIFile = 0;
      UserDefaultUILanguage = GetUserDefaultUILanguage();
      if ( UserDefaultUILanguage == 1028 )
        UserDefaultUILanguage = GetCHTLangauge();
      while ( (unsigned int)LookupLangID(UserDefaultUILanguage, v21, v23, v22) )
      {
        MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v21, FilePart);
        if ( MUIFile )
          goto LABEL_45;
        MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v23, FilePart);
        if ( MUIFile )
          goto LABEL_45;
        if ( v22[0] )
        {
          MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v22, FilePart);
          if ( MUIFile )
            goto LABEL_45;
        }
        if ( UserDefaultUILanguage != 3076 )
        {
          SystemDefaultUILanguage = GetSystemDefaultUILanguage();
          v11 = SystemDefaultUILanguage;
          if ( SystemDefaultUILanguage != UserDefaultUILanguage )
          {
            if ( !(unsigned int)LookupLangID(SystemDefaultUILanguage, v21, v23, v22) )
              goto LABEL_38;
            MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v21, FilePart);
            if ( MUIFile )
              goto LABEL_45;
            MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v23, FilePart);
            if ( MUIFile )
              goto LABEL_45;
            if ( v22[0] )
            {
              MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v22, FilePart);
              if ( MUIFile )
                goto LABEL_45;
            }
          }
          if ( UserDefaultUILanguage == 1033 )
            goto LABEL_37;
          v12 = v11 == 1033;
          goto LABEL_35;
        }
        UserDefaultUILanguage = 1028;
      }
      goto LABEL_44;
    }
    if ( (dword_1800A44F8 & 7) != 0 && (unsigned int)LookupLangID(LangID, v21, v23, 0) )
    {
      MUIFile = (HINSTANCE)LoadMUIFile(v6, v7, v21, FilePart);
LABEL_44:
      if ( MUIFile )
        goto LABEL_45;
    }
  }
LABEL_38:
  if ( ((unsigned __int8)v6 & 1) != 0 )
  {
    FreeLibrary(v6);
    if ( (GetOSType(v15, v14) & 0x38) != 0 )
    {
      StringCchPrintfW(Buffer, 0x104u, L"%s\\%s", v7, FilePart);
      return (HINSTANCE)MapMUIFile(Buffer, 1);
    }
    else
    {
      OSType = GetOSType(v17, v16);
      return LoadLibraryExW(pszFullModuleName, 0, (OSType & 0x26) != 0);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180054cc8  mov     [rsp-8+arg_8], rbx
0x180054ccd  push    rbp
0x180054cce  push    rsi
0x180054ccf  push    rdi
0x180054cd0  push    r12
0x180054cd2  push    r13
0x180054cd4  push    r14
0x180054cd6  push    r15
0x180054cd8  lea     rbp, [rsp-370h]
0x180054ce0  sub     rsp, 470h
0x180054ce7  mov     rax, cs:__security_cookie
0x180054cee  xor     rax, rsp
0x180054cf1  mov     [rbp+3A0h+var_40], rax
0x180054cf8  xor     r13d, r13d
0x180054cfb  movzx   ebx, r8w
0x180054cff  mov     [rsp+4A0h+FilePart], r13
0x180054d04  mov     r12, rcx
0x180054d07  test    rcx, rcx
0x180054d0a  jz      loc_180055122
0x180054d10  call    GetOSType
0x180054d15  mov     cs:dword_1800A44F8, eax
0x180054d1b  xor     edx, edx; hFile
0x180054d1d  and     eax, 20h
0x180054d20  mov     rcx, r12; lpLibFileName
0x180054d23  or      eax, 2
0x180054d26  mov     r8d, eax; dwFlags
0x180054d29  call    cs:__imp_LoadLibraryExW
0x180054d2f  mov     rdi, rax
0x180054d32  test    rax, rax
0x180054d35  jz      loc_180055122
0x180054d3b  test    byte ptr cs:dword_1800A44F8, 20h
0x180054d42  jnz     loc_180055124
0x180054d48  lea     rax, [rsp+4A0h+FilePart]
0x180054d4d  mov     r9d, 104h; nBufferLength
0x180054d53  mov     [rsp+4A0h+lpFilePart], rax; lpFilePart
0x180054d58  xor     r8d, r8d; lpExtension
0x180054d5b  lea     rax, [rbp+3A0h+Buffer]
0x180054d62  mov     rdx, r12; lpFileName
0x180054d65  xor     ecx, ecx; lpPath
0x180054d67  mov     [rsp+4A0h+lpBuffer], rax; lpBuffer
0x180054d6c  call    cs:__imp_SearchPathW
0x180054d72  test    eax, eax
0x180054d74  jz      loc_180055119
0x180054d7a  mov     rcx, [rsp+4A0h+FilePart]
0x180054d7f  test    rcx, rcx
0x180054d82  jnz     short loc_180054D95
0x180054d84  lea     rax, [rbp+3A0h+Buffer]
0x180054d8b  mov     esi, r13d
0x180054d8e  mov     [rsp+4A0h+FilePart], rax
0x180054d93  jmp     short loc_180054DA1
0x180054d95  lea     rsi, [rbp+3A0h+Buffer]
0x180054d9c  mov     [rcx-2], r13w
0x180054da1  xor     r9d, r9d; wLanguage
0x180054da4  lea     rdx, Type; "MUI"
0x180054dab  mov     rcx, rdi; hModule
0x180054dae  lea     r8d, [r9+1]; lpName
0x180054db2  call    cs:__imp_FindResourceExW
0x180054db8  test    rax, rax
0x180054dbb  jz      loc_18005504B
0x180054dc1  test    bx, bx
0x180054dc4  jnz     loc_1800550A5
0x180054dca  mov     eax, cs:dword_1800A44F8
0x180054dd0  test    al, 4
0x180054dd2  jz      loc_180054F50
0x180054dd8  mov     rbx, r13
0x180054ddb  call    cs:__imp_GetUserDefaultUILanguage
0x180054de1  mov     r15d, 404h
0x180054de7  movzx   r14d, ax
0x180054deb  cmp     ax, r15w
0x180054def  jnz     short loc_180054DFA
0x180054df1  call    GetCHTLangauge
0x180054df6  movzx   r14d, ax
0x180054dfa  lea     r9, [rbp+3A0h+var_3B0]
0x180054dfe  movzx   ecx, r14w
0x180054e02  lea     r8, [rbp+3A0h+var_300]
0x180054e09  lea     rdx, [rsp+4A0h+var_460]
0x180054e0e  call    LookupLangID
0x180054e13  test    eax, eax
0x180054e15  jz      loc_1800550E1
0x180054e1b  mov     r9, [rsp+4A0h+FilePart]
0x180054e20  lea     r8, [rsp+4A0h+var_460]
0x180054e25  mov     rdx, rsi
0x180054e28  mov     rcx, rdi
0x180054e2b  call    LoadMUIFile
0x180054e30  mov     rbx, rax
0x180054e33  test    rax, rax
0x180054e36  jnz     loc_1800550EA
0x180054e3c  mov     r9, [rsp+4A0h+FilePart]
0x180054e41  lea     r8, [rbp+3A0h+var_300]
0x180054e48  mov     rdx, rsi
0x180054e4b  mov     rcx, rdi
0x180054e4e  call    LoadMUIFile
0x180054e53  mov     rbx, rax
0x180054e56  test    rax, rax
0x180054e59  jnz     loc_1800550EA
0x180054e5f  cmp     [rbp+3A0h+var_3B0], r13w
0x180054e64  jz      short loc_180054E86
0x180054e66  mov     r9, [rsp+4A0h+FilePart]
0x180054e6b  lea     r8, [rbp+3A0h+var_3B0]
0x180054e6f  mov     rdx, rsi
0x180054e72  mov     rcx, rdi
0x180054e75  call    LoadMUIFile
0x180054e7a  mov     rbx, rax
0x180054e7d  test    rax, rax
0x180054e80  jnz     loc_1800550EA
0x180054e86  mov     eax, 0C04h
0x180054e8b  cmp     r14w, ax
0x180054e8f  jnz     short loc_180054E99
0x180054e91  mov     r14d, r15d
0x180054e94  jmp     loc_180054DFA
0x180054e99  call    cs:__imp_GetSystemDefaultUILanguage
0x180054e9f  movzx   r15d, ax
0x180054ea3  cmp     ax, r14w
0x180054ea7  jz      loc_180054F38
0x180054ead  lea     r9, [rbp+3A0h+var_3B0]
0x180054eb1  movzx   ecx, ax
0x180054eb4  lea     r8, [rbp+3A0h+var_300]
0x180054ebb  lea     rdx, [rsp+4A0h+var_460]
0x180054ec0  call    LookupLangID
0x180054ec5  test    eax, eax
0x180054ec7  jz      loc_18005504B
0x180054ecd  mov     r9, [rsp+4A0h+FilePart]
0x180054ed2  lea     r8, [rsp+4A0h+var_460]
0x180054ed7  mov     rdx, rsi
0x180054eda  mov     rcx, rdi
0x180054edd  call    LoadMUIFile
0x180054ee2  mov     rbx, rax
0x180054ee5  test    rax, rax
0x180054ee8  jnz     loc_1800550EA
0x180054eee  mov     r9, [rsp+4A0h+FilePart]
0x180054ef3  lea     r8, [rbp+3A0h+var_300]
0x180054efa  mov     rdx, rsi
0x180054efd  mov     rcx, rdi
0x180054f00  call    LoadMUIFile
0x180054f05  mov     rbx, rax
0x180054f08  test    rax, rax
0x180054f0b  jnz     loc_1800550EA
0x180054f11  cmp     [rbp+3A0h+var_3B0], r13w
0x180054f16  jz      short loc_180054F38
0x180054f18  mov     r9, [rsp+4A0h+FilePart]
0x180054f1d  lea     r8, [rbp+3A0h+var_3B0]
0x180054f21  mov     rdx, rsi
0x180054f24  mov     rcx, rdi
0x180054f27  call    LoadMUIFile
0x180054f2c  mov     rbx, rax
0x180054f2f  test    rax, rax
0x180054f32  jnz     loc_1800550EA
0x180054f38  mov     ecx, 409h
0x180054f3d  cmp     cx, r14w
0x180054f41  jz      loc_18005502C
0x180054f47  cmp     cx, r15w
0x180054f4b  jmp     loc_180054FF5
0x180054f50  test    al, 3
0x180054f52  jz      loc_18005504B
0x180054f58  call    GetInstallLanguage
0x180054f5d  lea     r9, [rbp+3A0h+var_3B0]
0x180054f61  movzx   ecx, ax
0x180054f64  lea     r8, [rbp+3A0h+var_300]
0x180054f6b  movzx   r14d, ax
0x180054f6f  lea     rdx, [rsp+4A0h+var_460]
0x180054f74  call    LookupLangID
0x180054f79  test    eax, eax
0x180054f7b  jz      loc_18005504B
0x180054f81  mov     r9, [rsp+4A0h+FilePart]
0x180054f86  lea     r8, [rsp+4A0h+var_460]
0x180054f8b  mov     rdx, rsi
0x180054f8e  mov     rcx, rdi
0x180054f91  call    LoadMUIFile
0x180054f96  mov     rbx, rax
0x180054f99  test    rax, rax
0x180054f9c  jnz     loc_1800550EA
0x180054fa2  mov     r9, [rsp+4A0h+FilePart]
0x180054fa7  lea     r8, [rbp+3A0h+var_300]
0x180054fae  mov     rdx, rsi
0x180054fb1  mov     rcx, rdi
0x180054fb4  call    LoadMUIFile
0x180054fb9  mov     rbx, rax
0x180054fbc  test    rax, rax
0x180054fbf  jnz     loc_1800550EA
0x180054fc5  cmp     [rbp+3A0h+var_3B0], r13w
0x180054fca  jz      short loc_180054FEC
0x180054fcc  mov     r9, [rsp+4A0h+FilePart]
0x180054fd1  lea     r8, [rbp+3A0h+var_3B0]
0x180054fd5  mov     rdx, rsi
0x180054fd8  mov     rcx, rdi
0x180054fdb  call    LoadMUIFile
0x180054fe0  mov     rbx, rax
0x180054fe3  test    rax, rax
0x180054fe6  jnz     loc_1800550EA
0x180054fec  mov     ecx, 409h
0x180054ff1  cmp     cx, r14w
0x180054ff5  jz      short loc_18005502C
0x180054ff7  xor     r9d, r9d
0x180054ffa  lea     r8, [rbp+3A0h+var_300]
0x180055001  lea     rdx, [rsp+4A0h+var_460]
0x180055006  call    LookupLangID
0x18005500b  mov     r9, [rsp+4A0h+FilePart]
0x180055010  lea     r8, [rsp+4A0h+var_460]
0x180055015  mov     rdx, rsi
0x180055018  mov     rcx, rdi
0x18005501b  call    LoadMUIFile
0x180055020  mov     rbx, rax
0x180055023  test    rax, rax
0x180055026  jnz     loc_1800550EA
0x18005502c  mov     r9, [rsp+4A0h+FilePart]
0x180055031  xor     r8d, r8d
0x180055034  mov     rdx, rsi
0x180055037  mov     rcx, rdi
0x18005503a  call    LoadMUIFile
0x18005503f  mov     rbx, rax
0x180055042  test    rax, rax
0x180055045  jnz     loc_1800550EA
0x18005504b  test    dil, 1
0x18005504f  jz      loc_180055114
0x180055055  mov     rcx, rdi; hLibModule
0x180055058  call    cs:__imp_FreeLibrary
0x18005505e  call    GetOSType
0x180055063  test    al, 38h
0x180055065  jz      loc_1800550F8
0x18005506b  mov     rax, [rsp+4A0h+FilePart]
0x180055070  lea     r8, aSS; "%s\\%s"
0x180055077  mov     r9, rsi
0x18005507a  mov     [rsp+4A0h+lpBuffer], rax
0x18005507f  mov     edx, 104h; unsigned __int64
0x180055084  lea     rcx, [rbp+3A0h+Buffer]; unsigned __int16 *
0x18005508b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180055090  xor     r8d, r8d
0x180055093  lea     rcx, [rbp+3A0h+Buffer]
0x18005509a  lea     edx, [r8+1]
0x18005509e  call    MapMUIFile
0x1800550a3  jmp     short loc_180055111
0x1800550a5  test    byte ptr cs:dword_1800A44F8, 7
0x1800550ac  jz      short loc_18005504B
0x1800550ae  xor     r9d, r9d
0x1800550b1  lea     r8, [rbp+3A0h+var_300]
0x1800550b8  lea     rdx, [rsp+4A0h+var_460]
0x1800550bd  movzx   ecx, bx
0x1800550c0  call    LookupLangID
0x1800550c5  test    eax, eax
0x1800550c7  jz      short loc_18005504B
0x1800550c9  mov     r9, [rsp+4A0h+FilePart]
0x1800550ce  lea     r8, [rsp+4A0h+var_460]
0x1800550d3  mov     rdx, rsi
0x1800550d6  mov     rcx, rdi
0x1800550d9  call    LoadMUIFile
0x1800550de  mov     rbx, rax
0x1800550e1  test    rbx, rbx
0x1800550e4  jz      loc_18005504B
0x1800550ea  mov     rcx, rdi; hLibModule
0x1800550ed  call    cs:__imp_FreeLibrary
0x1800550f3  mov     rax, rbx
0x1800550f6  jmp     short loc_180055124
0x1800550f8  call    GetOSType
0x1800550fd  test    al, 26h
0x1800550ff  mov     r8d, r13d
0x180055102  mov     rcx, r12; lpLibFileName
0x180055105  setnz   r8b; dwFlags
0x180055109  xor     edx, edx; hFile
0x18005510b  call    cs:__imp_LoadLibraryExW
0x180055111  mov     rdi, rax
0x180055114  mov     rax, rdi
0x180055117  jmp     short loc_180055124
0x180055119  mov     rcx, rdi; hLibModule
0x18005511c  call    cs:__imp_FreeLibrary
0x180055122  xor     eax, eax
0x180055124  mov     rcx, [rbp+3A0h+var_40]
0x18005512b  xor     rcx, rsp; StackCookie
0x18005512e  call    __security_check_cookie
0x180055133  mov     rbx, [rsp+4A0h+arg_8]
0x18005513b  add     rsp, 470h
0x180055142  pop     r15
0x180055144  pop     r14
0x180055146  pop     r13
0x180055148  pop     r12
0x18005514a  pop     rdi
0x18005514b  pop     rsi
0x18005514c  pop     rbp
0x18005514d  retn
```
