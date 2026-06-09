# LoadMUILibraryW

- ea: `0x1800c4230`
- end: `0x1800c46b9`
- name: `LoadMUILibraryW`
- size: `1161`
- prototype: `HINSTANCE __stdcall(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x1800c2d60`
- `0x1800c41c8`

## callees

- `0x180022120`
- `0x1800c4230`
- `0x180149084`
- `0x1802599ec`
- `0x180259a6c`
- `0x180259b80`
- `0x180259bf4`
- `0x180259d6c`
- `0x18025ab80`

## import_xrefs

- `KERNEL32!GetSystemDefaultUILanguage` at `0x1800c43ff`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x1800c43ff`
- `KERNEL32!GetUserDefaultUILanguage` at `0x1800c4341`
- `KERNEL32!GetUserDefaultUILanguage` at `0x1800c4341`
- `KERNEL32!LoadLibraryExW` at `0x1800c428b`
- `KERNEL32!LoadLibraryExW` at `0x1800c4675`
- `KERNEL32!LoadLibraryExW` at `0x1800c428b`
- `KERNEL32!LoadLibraryExW` at `0x1800c4675`
- `KERNEL32!FreeLibrary` at `0x1800c45be`
- `KERNEL32!FreeLibrary` at `0x1800c4653`
- `KERNEL32!FreeLibrary` at `0x1800c4686`
- `KERNEL32!FreeLibrary` at `0x1800c45be`
- `KERNEL32!FreeLibrary` at `0x1800c4653`
- `KERNEL32!FreeLibrary` at `0x1800c4686`
- `KERNEL32!FindResourceExW` at `0x1800c4318`
- `KERNEL32!FindResourceExW` at `0x1800c4318`
- `KERNEL32!SearchPathW` at `0x1800c42d2`
- `KERNEL32!SearchPathW` at `0x1800c42d2`

## string_xrefs

- `0x1800c4279`: `MsiMsg.dll`
- `0x1800c42ba`: `MsiMsg.dll`
- `0x1800c4665`: `MsiMsg.dll`

## pseudocode

```c
HINSTANCE __stdcall LoadMUILibraryW(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)
{
  HINSTANCE result; // rax
  HMODULE v5; // rdi
  WCHAR *v6; // rsi
  HINSTANCE MUIFile; // rbx
  LANGID UserDefaultUILanguage; // r14
  LANGID SystemDefaultUILanguage; // ax
  LANGID v10; // r15
  bool v11; // zf
  __int64 InstallLanguage; // r14
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  char OSType; // al
  LPWSTR FilePart; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v20[176]; // [rsp+40h] [rbp-C0h] BYREF
  _WORD v21[88]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v22[176]; // [rsp+1A0h] [rbp+A0h] BYREF
  WCHAR Buffer[264]; // [rsp+250h] [rbp+150h] BYREF

  FilePart = 0;
  dword_18030B3CC = GetOSType(pszFullModuleName, dwLangConvention);
  result = LoadLibraryExW(L"MsiMsg.dll", 0, dword_18030B3CC & 0x20 | 2u);
  v5 = result;
  if ( !result )
    return 0;
  if ( (dword_18030B3CC & 0x20) != 0 )
    return result;
  if ( !SearchPathW(0, L"MsiMsg.dll", 0, 0x104u, Buffer, &FilePart) )
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
    if ( !LangID )
    {
      if ( (dword_18030B3CC & 4) == 0 )
      {
        if ( (dword_18030B3CC & 3) != 0 )
        {
          InstallLanguage = (unsigned __int16)GetInstallLanguage();
          if ( (unsigned int)LookupLangID(InstallLanguage, v20, v22, v21) )
          {
            MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v20, FilePart);
            if ( MUIFile )
              goto LABEL_44;
            MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v22, FilePart);
            if ( MUIFile )
              goto LABEL_44;
            if ( v21[0] )
            {
              MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v21, FilePart);
              if ( MUIFile )
                goto LABEL_44;
            }
            v11 = (_WORD)InstallLanguage == 1033;
LABEL_34:
            if ( !v11 )
            {
              LookupLangID(1033, v20, v22, 0);
              MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v20, FilePart);
              if ( MUIFile )
                goto LABEL_44;
            }
LABEL_36:
            MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, 0, FilePart);
            if ( MUIFile )
            {
LABEL_44:
              FreeLibrary(v5);
              return MUIFile;
            }
          }
        }
        goto LABEL_37;
      }
      MUIFile = 0;
      UserDefaultUILanguage = GetUserDefaultUILanguage();
      if ( UserDefaultUILanguage == 1028 )
        UserDefaultUILanguage = GetCHTLangauge();
      while ( (unsigned int)LookupLangID(UserDefaultUILanguage, v20, v22, v21) )
      {
        MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v20, FilePart);
        if ( MUIFile )
          goto LABEL_44;
        MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v22, FilePart);
        if ( MUIFile )
          goto LABEL_44;
        if ( v21[0] )
        {
          MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v21, FilePart);
          if ( MUIFile )
            goto LABEL_44;
        }
        if ( UserDefaultUILanguage != 3076 )
        {
          SystemDefaultUILanguage = GetSystemDefaultUILanguage();
          v10 = SystemDefaultUILanguage;
          if ( SystemDefaultUILanguage != UserDefaultUILanguage )
          {
            if ( !(unsigned int)LookupLangID(SystemDefaultUILanguage, v20, v22, v21) )
              goto LABEL_37;
            MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v20, FilePart);
            if ( MUIFile )
              goto LABEL_44;
            MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v22, FilePart);
            if ( MUIFile )
              goto LABEL_44;
            if ( v21[0] )
            {
              MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v21, FilePart);
              if ( MUIFile )
                goto LABEL_44;
            }
          }
          if ( UserDefaultUILanguage == 1033 )
            goto LABEL_36;
          v11 = v10 == 1033;
          goto LABEL_34;
        }
        UserDefaultUILanguage = 1028;
      }
      goto LABEL_43;
    }
    if ( (dword_18030B3CC & 7) != 0 && (unsigned int)LookupLangID(LangID, v20, v22, 0) )
    {
      MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v20, FilePart);
LABEL_43:
      if ( MUIFile )
        goto LABEL_44;
    }
  }
LABEL_37:
  if ( ((unsigned __int8)v5 & 1) != 0 )
  {
    FreeLibrary(v5);
    if ( (GetOSType(v14, v13) & 0x38) != 0 )
    {
      StringCchPrintfW(Buffer, 0x104u, L"%s\\%s", v6, FilePart);
      return (HINSTANCE)MapMUIFile(Buffer, 1);
    }
    else
    {
      OSType = GetOSType(v16, v15);
      return LoadLibraryExW(L"MsiMsg.dll", 0, (OSType & 0x26) != 0);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1800c4230  mov     [rsp-8+arg_0], rbx
0x1800c4235  mov     [rsp-8+arg_8], rsi
0x1800c423a  push    rbp
0x1800c423b  push    rdi
0x1800c423c  push    r12
0x1800c423e  push    r14
0x1800c4240  push    r15
0x1800c4242  lea     rbp, [rsp-370h]
0x1800c424a  sub     rsp, 470h
0x1800c4251  mov     rax, cs:__security_cookie
0x1800c4258  xor     rax, rsp
0x1800c425b  mov     [rbp+390h+var_30], rax
0x1800c4262  xor     r12d, r12d
0x1800c4265  movzx   ebx, r8w
0x1800c4269  mov     [rsp+490h+FilePart], r12
0x1800c426e  call    GetOSType
0x1800c4273  mov     cs:dword_18030B3CC, eax
0x1800c4279  lea     rcx, FileName; "MsiMsg.dll"
0x1800c4280  and     eax, 20h
0x1800c4283  xor     edx, edx; hFile
0x1800c4285  or      eax, 2
0x1800c4288  mov     r8d, eax; dwFlags
0x1800c428b  call    cs:__imp_LoadLibraryExW
0x1800c4291  mov     rdi, rax
0x1800c4294  test    rax, rax
0x1800c4297  jz      loc_1800C468C
0x1800c429d  test    byte ptr cs:dword_18030B3CC, 20h
0x1800c42a4  jnz     loc_1800C468E
0x1800c42aa  lea     rax, [rsp+490h+FilePart]
0x1800c42af  mov     r9d, 104h; nBufferLength
0x1800c42b5  mov     [rsp+490h+lpFilePart], rax; lpFilePart
0x1800c42ba  lea     rdx, FileName; "MsiMsg.dll"
0x1800c42c1  lea     rax, [rbp+390h+Buffer]
0x1800c42c8  xor     r8d, r8d; lpExtension
0x1800c42cb  xor     ecx, ecx; lpPath
0x1800c42cd  mov     [rsp+490h+lpBuffer], rax; lpBuffer
0x1800c42d2  call    cs:__imp_SearchPathW
0x1800c42d8  test    eax, eax
0x1800c42da  jz      loc_1800C4683
0x1800c42e0  mov     rcx, [rsp+490h+FilePart]
0x1800c42e5  test    rcx, rcx
0x1800c42e8  jnz     short loc_1800C42FB
0x1800c42ea  lea     rax, [rbp+390h+Buffer]
0x1800c42f1  mov     esi, r12d
0x1800c42f4  mov     [rsp+490h+FilePart], rax
0x1800c42f9  jmp     short loc_1800C4307
0x1800c42fb  lea     rsi, [rbp+390h+Buffer]
0x1800c4302  mov     [rcx-2], r12w
0x1800c4307  xor     r9d, r9d; wLanguage
0x1800c430a  lea     rdx, Type; "MUI"
0x1800c4311  mov     rcx, rdi; hModule
0x1800c4314  lea     r8d, [r9+1]; lpName
0x1800c4318  call    cs:__imp_FindResourceExW
0x1800c431e  test    rax, rax
0x1800c4321  jz      loc_1800C45B1
0x1800c4327  test    bx, bx
0x1800c432a  jnz     loc_1800C460B
0x1800c4330  mov     eax, cs:dword_18030B3CC
0x1800c4336  test    al, 4
0x1800c4338  jz      loc_1800C44B6
0x1800c433e  mov     rbx, r12
0x1800c4341  call    cs:__imp_GetUserDefaultUILanguage
0x1800c4347  mov     r15d, 404h
0x1800c434d  movzx   r14d, ax
0x1800c4351  cmp     ax, r15w
0x1800c4355  jnz     short loc_1800C4360
0x1800c4357  call    GetCHTLangauge
0x1800c435c  movzx   r14d, ax
0x1800c4360  lea     r9, [rbp+390h+var_3A0]
0x1800c4364  movzx   ecx, r14w
0x1800c4368  lea     r8, [rbp+390h+var_2F0]
0x1800c436f  lea     rdx, [rsp+490h+var_450]
0x1800c4374  call    LookupLangID
0x1800c4379  test    eax, eax
0x1800c437b  jz      loc_1800C4647
0x1800c4381  mov     r9, [rsp+490h+FilePart]
0x1800c4386  lea     r8, [rsp+490h+var_450]
0x1800c438b  mov     rdx, rsi
0x1800c438e  mov     rcx, rdi
0x1800c4391  call    LoadMUIFile
0x1800c4396  mov     rbx, rax
0x1800c4399  test    rax, rax
0x1800c439c  jnz     loc_1800C4650
0x1800c43a2  mov     r9, [rsp+490h+FilePart]
0x1800c43a7  lea     r8, [rbp+390h+var_2F0]
0x1800c43ae  mov     rdx, rsi
0x1800c43b1  mov     rcx, rdi
0x1800c43b4  call    LoadMUIFile
0x1800c43b9  mov     rbx, rax
0x1800c43bc  test    rax, rax
0x1800c43bf  jnz     loc_1800C4650
0x1800c43c5  cmp     [rbp+390h+var_3A0], r12w
0x1800c43ca  jz      short loc_1800C43EC
0x1800c43cc  mov     r9, [rsp+490h+FilePart]
0x1800c43d1  lea     r8, [rbp+390h+var_3A0]
0x1800c43d5  mov     rdx, rsi
0x1800c43d8  mov     rcx, rdi
0x1800c43db  call    LoadMUIFile
0x1800c43e0  mov     rbx, rax
0x1800c43e3  test    rax, rax
0x1800c43e6  jnz     loc_1800C4650
0x1800c43ec  mov     eax, 0C04h
0x1800c43f1  cmp     r14w, ax
0x1800c43f5  jnz     short loc_1800C43FF
0x1800c43f7  mov     r14d, r15d
0x1800c43fa  jmp     loc_1800C4360
0x1800c43ff  call    cs:__imp_GetSystemDefaultUILanguage
0x1800c4405  movzx   r15d, ax
0x1800c4409  cmp     ax, r14w
0x1800c440d  jz      loc_1800C449E
0x1800c4413  lea     r9, [rbp+390h+var_3A0]
0x1800c4417  movzx   ecx, ax
0x1800c441a  lea     r8, [rbp+390h+var_2F0]
0x1800c4421  lea     rdx, [rsp+490h+var_450]
0x1800c4426  call    LookupLangID
0x1800c442b  test    eax, eax
0x1800c442d  jz      loc_1800C45B1
0x1800c4433  mov     r9, [rsp+490h+FilePart]
0x1800c4438  lea     r8, [rsp+490h+var_450]
0x1800c443d  mov     rdx, rsi
0x1800c4440  mov     rcx, rdi
0x1800c4443  call    LoadMUIFile
0x1800c4448  mov     rbx, rax
0x1800c444b  test    rax, rax
0x1800c444e  jnz     loc_1800C4650
0x1800c4454  mov     r9, [rsp+490h+FilePart]
0x1800c4459  lea     r8, [rbp+390h+var_2F0]
0x1800c4460  mov     rdx, rsi
0x1800c4463  mov     rcx, rdi
0x1800c4466  call    LoadMUIFile
0x1800c446b  mov     rbx, rax
0x1800c446e  test    rax, rax
0x1800c4471  jnz     loc_1800C4650
0x1800c4477  cmp     [rbp+390h+var_3A0], r12w
0x1800c447c  jz      short loc_1800C449E
0x1800c447e  mov     r9, [rsp+490h+FilePart]
0x1800c4483  lea     r8, [rbp+390h+var_3A0]
0x1800c4487  mov     rdx, rsi
0x1800c448a  mov     rcx, rdi
0x1800c448d  call    LoadMUIFile
0x1800c4492  mov     rbx, rax
0x1800c4495  test    rax, rax
0x1800c4498  jnz     loc_1800C4650
0x1800c449e  mov     ecx, 409h
0x1800c44a3  cmp     cx, r14w
0x1800c44a7  jz      loc_1800C4592
0x1800c44ad  cmp     cx, r15w
0x1800c44b1  jmp     loc_1800C455B
0x1800c44b6  test    al, 3
0x1800c44b8  jz      loc_1800C45B1
0x1800c44be  call    GetInstallLanguage
0x1800c44c3  lea     r9, [rbp+390h+var_3A0]
0x1800c44c7  movzx   ecx, ax
0x1800c44ca  lea     r8, [rbp+390h+var_2F0]
0x1800c44d1  movzx   r14d, ax
0x1800c44d5  lea     rdx, [rsp+490h+var_450]
0x1800c44da  call    LookupLangID
0x1800c44df  test    eax, eax
0x1800c44e1  jz      loc_1800C45B1
0x1800c44e7  mov     r9, [rsp+490h+FilePart]
0x1800c44ec  lea     r8, [rsp+490h+var_450]
0x1800c44f1  mov     rdx, rsi
0x1800c44f4  mov     rcx, rdi
0x1800c44f7  call    LoadMUIFile
0x1800c44fc  mov     rbx, rax
0x1800c44ff  test    rax, rax
0x1800c4502  jnz     loc_1800C4650
0x1800c4508  mov     r9, [rsp+490h+FilePart]
0x1800c450d  lea     r8, [rbp+390h+var_2F0]
0x1800c4514  mov     rdx, rsi
0x1800c4517  mov     rcx, rdi
0x1800c451a  call    LoadMUIFile
0x1800c451f  mov     rbx, rax
0x1800c4522  test    rax, rax
0x1800c4525  jnz     loc_1800C4650
0x1800c452b  cmp     [rbp+390h+var_3A0], r12w
0x1800c4530  jz      short loc_1800C4552
0x1800c4532  mov     r9, [rsp+490h+FilePart]
0x1800c4537  lea     r8, [rbp+390h+var_3A0]
0x1800c453b  mov     rdx, rsi
0x1800c453e  mov     rcx, rdi
0x1800c4541  call    LoadMUIFile
0x1800c4546  mov     rbx, rax
0x1800c4549  test    rax, rax
0x1800c454c  jnz     loc_1800C4650
0x1800c4552  mov     ecx, 409h
0x1800c4557  cmp     cx, r14w
0x1800c455b  jz      short loc_1800C4592
0x1800c455d  xor     r9d, r9d
0x1800c4560  lea     r8, [rbp+390h+var_2F0]
0x1800c4567  lea     rdx, [rsp+490h+var_450]
0x1800c456c  call    LookupLangID
0x1800c4571  mov     r9, [rsp+490h+FilePart]
0x1800c4576  lea     r8, [rsp+490h+var_450]
0x1800c457b  mov     rdx, rsi
0x1800c457e  mov     rcx, rdi
0x1800c4581  call    LoadMUIFile
0x1800c4586  mov     rbx, rax
0x1800c4589  test    rax, rax
0x1800c458c  jnz     loc_1800C4650
0x1800c4592  mov     r9, [rsp+490h+FilePart]
0x1800c4597  xor     r8d, r8d
0x1800c459a  mov     rdx, rsi
0x1800c459d  mov     rcx, rdi
0x1800c45a0  call    LoadMUIFile
0x1800c45a5  mov     rbx, rax
0x1800c45a8  test    rax, rax
0x1800c45ab  jnz     loc_1800C4650
0x1800c45b1  test    dil, 1
0x1800c45b5  jz      loc_1800C467E
0x1800c45bb  mov     rcx, rdi; hLibModule
0x1800c45be  call    cs:__imp_FreeLibrary
0x1800c45c4  call    GetOSType
0x1800c45c9  test    al, 38h
0x1800c45cb  jz      loc_1800C465E
0x1800c45d1  mov     rax, [rsp+490h+FilePart]
0x1800c45d6  lea     r8, aSS_0; "%s\\%s"
0x1800c45dd  mov     r9, rsi
0x1800c45e0  mov     [rsp+490h+lpBuffer], rax
0x1800c45e5  mov     edx, 104h; unsigned __int64
0x1800c45ea  lea     rcx, [rbp+390h+Buffer]; unsigned __int16 *
0x1800c45f1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800c45f6  xor     r8d, r8d
0x1800c45f9  lea     rcx, [rbp+390h+Buffer]
0x1800c4600  lea     edx, [r8+1]
0x1800c4604  call    MapMUIFile
0x1800c4609  jmp     short loc_1800C467B
0x1800c460b  test    byte ptr cs:dword_18030B3CC, 7
0x1800c4612  jz      short loc_1800C45B1
0x1800c4614  xor     r9d, r9d
0x1800c4617  lea     r8, [rbp+390h+var_2F0]
0x1800c461e  lea     rdx, [rsp+490h+var_450]
0x1800c4623  movzx   ecx, bx
0x1800c4626  call    LookupLangID
0x1800c462b  test    eax, eax
0x1800c462d  jz      short loc_1800C45B1
0x1800c462f  mov     r9, [rsp+490h+FilePart]
0x1800c4634  lea     r8, [rsp+490h+var_450]
0x1800c4639  mov     rdx, rsi
0x1800c463c  mov     rcx, rdi
0x1800c463f  call    LoadMUIFile
0x1800c4644  mov     rbx, rax
0x1800c4647  test    rbx, rbx
0x1800c464a  jz      loc_1800C45B1
0x1800c4650  mov     rcx, rdi; hLibModule
0x1800c4653  call    cs:__imp_FreeLibrary
0x1800c4659  mov     rax, rbx
0x1800c465c  jmp     short loc_1800C468E
0x1800c465e  call    GetOSType
0x1800c4663  test    al, 26h
0x1800c4665  lea     rcx, FileName; "MsiMsg.dll"
0x1800c466c  mov     r8d, r12d
0x1800c466f  setnz   r8b; dwFlags
0x1800c4673  xor     edx, edx; hFile
0x1800c4675  call    cs:__imp_LoadLibraryExW
0x1800c467b  mov     rdi, rax
0x1800c467e  mov     rax, rdi
0x1800c4681  jmp     short loc_1800C468E
0x1800c4683  mov     rcx, rdi; hLibModule
0x1800c4686  call    cs:__imp_FreeLibrary
0x1800c468c  xor     eax, eax
0x1800c468e  mov     rcx, [rbp+390h+var_30]
0x1800c4695  xor     rcx, rsp; StackCookie
0x1800c4698  call    __security_check_cookie
0x1800c469d  lea     r11, [rsp+490h+var_20]
0x1800c46a5  mov     rbx, [r11+30h]
0x1800c46a9  mov     rsi, [r11+38h]
0x1800c46ad  mov     rsp, r11
0x1800c46b0  pop     r15
0x1800c46b2  pop     r14
0x1800c46b4  pop     r12
0x1800c46b6  pop     rdi
0x1800c46b7  pop     rbp
0x1800c46b8  retn
```
