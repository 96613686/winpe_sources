# LoadMUILibraryW

- ea: `0x180010ac8`
- end: `0x180010f82`
- name: `LoadMUILibraryW`
- size: `1210`
- prototype: `HINSTANCE __stdcall(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x18000cc10`

## callees

- `0x180010690`
- `0x180010ac8`
- `0x180010f88`
- `0x18002f42c`
- `0x18002f4bc`
- `0x18002f600`
- `0x18002f674`
- `0x18002f824`
- `0x18002fb50`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180010b25`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180010f2c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180010b25`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180010f2c`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180010bbd`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180010bbd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180010db9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180010f05`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180010f43`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180010db9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180010f05`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180010f43`
- `KERNEL32!GetUserDefaultUILanguage` at `0x180010be0`
- `KERNEL32!GetUserDefaultUILanguage` at `0x180010be0`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x180010ca3`
- `KERNEL32!GetSystemDefaultUILanguage` at `0x180010ca3`
- `KERNEL32!SearchPathW` at `0x180010b72`
- `KERNEL32!SearchPathW` at `0x180010b72`

## pseudocode

```c
HINSTANCE __stdcall LoadMUILibraryW(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)
{
  DWORD v3; // ebx
  HINSTANCE result; // rax
  HMODULE v5; // rsi
  WCHAR *v6; // r14
  LANGID UserDefaultUILanguage; // r15
  HINSTANCE MUIFile; // rdi
  LANGID SystemDefaultUILanguage; // ax
  LANGID v10; // r12
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 InstallLanguage; // r15
  LPWSTR FilePart; // [rsp+38h] [rbp-D0h] BYREF
  _BYTE v20[176]; // [rsp+48h] [rbp-C0h] BYREF
  _WORD v21[88]; // [rsp+F8h] [rbp-10h] BYREF
  _BYTE v22[176]; // [rsp+1A8h] [rbp+A0h] BYREF
  WCHAR Buffer[264]; // [rsp+258h] [rbp+150h] BYREF

  v3 = 0;
  FilePart = 0;
  dword_1800506A8 = GetOSType(pszFullModuleName, dwLangConvention, LangID);
  result = LoadLibraryExW(&FileName, 0, dword_1800506A8 & 0x20 | 2u);
  v5 = result;
  if ( !result )
    return 0;
  if ( (dword_1800506A8 & 0x20) != 0 )
    return result;
  if ( !SearchPathW(0, &FileName, 0, 0x104u, Buffer, &FilePart) )
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
    if ( (dword_1800506A8 & 4) != 0 )
    {
      UserDefaultUILanguage = GetUserDefaultUILanguage();
      if ( UserDefaultUILanguage == 1028 )
        UserDefaultUILanguage = GetCHTLangauge();
      while ( (unsigned int)LookupLangID(UserDefaultUILanguage, v20, v22, v21) )
      {
        MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v20, FilePart);
        if ( MUIFile )
          goto LABEL_41;
        MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v22, FilePart);
        if ( MUIFile )
          goto LABEL_41;
        if ( v21[0] )
        {
          MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v21, FilePart);
          if ( MUIFile )
            goto LABEL_41;
        }
        if ( UserDefaultUILanguage != 3076 )
        {
          SystemDefaultUILanguage = GetSystemDefaultUILanguage();
          v10 = SystemDefaultUILanguage;
          if ( SystemDefaultUILanguage != UserDefaultUILanguage )
          {
            if ( !(unsigned int)LookupLangID(SystemDefaultUILanguage, v20, v22, v21) )
              break;
            MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v20, FilePart);
            if ( MUIFile )
              goto LABEL_41;
            MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v22, FilePart);
            if ( MUIFile )
              goto LABEL_41;
            if ( v21[0] )
            {
              MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v21, FilePart);
              if ( MUIFile )
                goto LABEL_41;
            }
          }
          if ( UserDefaultUILanguage != 1033 && v10 != 1033 )
          {
            LookupLangID(1033, v20, v22, 0);
            MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v20, FilePart);
            if ( MUIFile )
              goto LABEL_41;
          }
          MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, 0, FilePart);
          if ( MUIFile )
            goto LABEL_41;
          break;
        }
        UserDefaultUILanguage = 1028;
      }
    }
    else if ( (dword_1800506A8 & 3) != 0 )
    {
      InstallLanguage = (unsigned __int16)GetInstallLanguage();
      if ( (unsigned int)LookupLangID(InstallLanguage, v20, v22, v21) )
      {
        if ( (MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v20, FilePart)) != 0
          || (MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v22, FilePart)) != 0
          || v21[0] && (MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v21, FilePart)) != 0
          || (_WORD)InstallLanguage != 1033
          && (LookupLangID(1033, v20, v22, 0), (MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v20, FilePart)) != 0)
          || (MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, 0, FilePart)) != 0 )
        {
LABEL_41:
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
      LOBYTE(v3) = (GetOSType(v15, v14, v16) & 0x26) != 0;
      return LoadLibraryExW(&FileName, 0, v3);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180010ac8  mov     rax, rsp
0x180010acb  mov     [rax+8], rbx
0x180010acf  mov     [rax+10h], rsi
0x180010ad3  mov     [rax+18h], rdi
0x180010ad7  mov     [rax+20h], r12
0x180010adb  push    rbp
0x180010adc  push    r14
0x180010ade  push    r15
0x180010ae0  lea     rbp, [rax-388h]
0x180010ae7  sub     rsp, 470h
0x180010aee  mov     rax, cs:__security_cookie
0x180010af5  xor     rax, rsp
0x180010af8  mov     [rbp+380h+var_20], rax
0x180010aff  xor     ebx, ebx
0x180010b01  mov     [rsp+480h+FilePart], rbx
0x180010b06  call    GetOSType
0x180010b0b  mov     cs:dword_1800506A8, eax
0x180010b11  lea     rcx, FileName; lpLibFileName
0x180010b18  and     eax, 20h
0x180010b1b  xor     edx, edx; hFile
0x180010b1d  or      eax, 2
0x180010b20  mov     edi, ebx
0x180010b22  mov     r8d, eax; dwFlags
0x180010b25  call    cs:__imp_LoadLibraryExW
0x180010b2c  nop     dword ptr [rax+rax+00h]
0x180010b31  mov     rsi, rax
0x180010b34  test    rax, rax
0x180010b37  jz      loc_180010F4F
0x180010b3d  test    byte ptr cs:dword_1800506A8, 20h
0x180010b44  jnz     loc_180010F51
0x180010b4a  lea     rax, [rsp+480h+FilePart]
0x180010b4f  mov     r9d, 104h; nBufferLength
0x180010b55  mov     [rsp+480h+lpFilePart], rax; lpFilePart
0x180010b5a  lea     rdx, FileName; lpFileName
0x180010b61  lea     rax, [rbp+380h+Buffer]
0x180010b68  xor     r8d, r8d; lpExtension
0x180010b6b  xor     ecx, ecx; lpPath
0x180010b6d  mov     [rsp+480h+lpBuffer], rax; lpBuffer
0x180010b72  call    cs:__imp_SearchPathW
0x180010b79  nop     dword ptr [rax+rax+00h]
0x180010b7e  test    eax, eax
0x180010b80  jz      loc_180010F40
0x180010b86  mov     rax, [rsp+480h+FilePart]
0x180010b8b  test    rax, rax
0x180010b8e  jnz     short loc_180010BA1
0x180010b90  lea     rax, [rbp+380h+Buffer]
0x180010b97  mov     r14d, ebx
0x180010b9a  mov     [rsp+480h+FilePart], rax
0x180010b9f  jmp     short loc_180010BAC
0x180010ba1  lea     r14, [rbp+380h+Buffer]
0x180010ba8  mov     [rax-2], bx
0x180010bac  xor     r9d, r9d; wLanguage
0x180010baf  lea     rdx, Type; "MUI"
0x180010bb6  mov     rcx, rsi; hModule
0x180010bb9  lea     r8d, [r9+1]; lpName
0x180010bbd  call    cs:__imp_FindResourceExW
0x180010bc4  nop     dword ptr [rax+rax+00h]
0x180010bc9  test    rax, rax
0x180010bcc  jz      loc_180010DAC
0x180010bd2  mov     eax, cs:dword_1800506A8
0x180010bd8  test    al, 4
0x180010bda  jz      loc_180010E0F
0x180010be0  call    cs:__imp_GetUserDefaultUILanguage
0x180010be7  nop     dword ptr [rax+rax+00h]
0x180010bec  mov     r12d, 404h
0x180010bf2  movzx   r15d, ax
0x180010bf6  cmp     ax, r12w
0x180010bfa  jnz     short loc_180010C05
0x180010bfc  call    GetCHTLangauge
0x180010c01  movzx   r15d, ax
0x180010c05  lea     r9, [rbp+380h+var_390]
0x180010c09  movzx   ecx, r15w
0x180010c0d  lea     r8, [rbp+380h+var_2E0]
0x180010c14  lea     rdx, [rsp+480h+var_440]
0x180010c19  call    LookupLangID
0x180010c1e  test    eax, eax
0x180010c20  jz      loc_180010EF9
0x180010c26  mov     r9, [rsp+480h+FilePart]
0x180010c2b  lea     r8, [rsp+480h+var_440]
0x180010c30  mov     rdx, r14
0x180010c33  mov     rcx, rsi
0x180010c36  call    LoadMUIFile
0x180010c3b  mov     rdi, rax
0x180010c3e  test    rax, rax
0x180010c41  jnz     loc_180010F02
0x180010c47  mov     r9, [rsp+480h+FilePart]
0x180010c4c  lea     r8, [rbp+380h+var_2E0]
0x180010c53  mov     rdx, r14
0x180010c56  mov     rcx, rsi
0x180010c59  call    LoadMUIFile
0x180010c5e  mov     rdi, rax
0x180010c61  test    rax, rax
0x180010c64  jnz     loc_180010F02
0x180010c6a  cmp     [rbp+380h+var_390], bx
0x180010c6e  jz      short loc_180010C90
0x180010c70  mov     r9, [rsp+480h+FilePart]
0x180010c75  lea     r8, [rbp+380h+var_390]
0x180010c79  mov     rdx, r14
0x180010c7c  mov     rcx, rsi
0x180010c7f  call    LoadMUIFile
0x180010c84  mov     rdi, rax
0x180010c87  test    rax, rax
0x180010c8a  jnz     loc_180010F02
0x180010c90  mov     eax, 0C04h
0x180010c95  cmp     r15w, ax
0x180010c99  jnz     short loc_180010CA3
0x180010c9b  mov     r15d, r12d
0x180010c9e  jmp     loc_180010C05
0x180010ca3  call    cs:__imp_GetSystemDefaultUILanguage
0x180010caa  nop     dword ptr [rax+rax+00h]
0x180010caf  movzx   r12d, ax
0x180010cb3  cmp     ax, r15w
0x180010cb7  jz      loc_180010D47
0x180010cbd  lea     r9, [rbp+380h+var_390]
0x180010cc1  movzx   ecx, ax
0x180010cc4  lea     r8, [rbp+380h+var_2E0]
0x180010ccb  lea     rdx, [rsp+480h+var_440]
0x180010cd0  call    LookupLangID
0x180010cd5  test    eax, eax
0x180010cd7  jz      loc_180010DAC
0x180010cdd  mov     r9, [rsp+480h+FilePart]
0x180010ce2  lea     r8, [rsp+480h+var_440]
0x180010ce7  mov     rdx, r14
0x180010cea  mov     rcx, rsi
0x180010ced  call    LoadMUIFile
0x180010cf2  mov     rdi, rax
0x180010cf5  test    rax, rax
0x180010cf8  jnz     loc_180010F02
0x180010cfe  mov     r9, [rsp+480h+FilePart]
0x180010d03  lea     r8, [rbp+380h+var_2E0]
0x180010d0a  mov     rdx, r14
0x180010d0d  mov     rcx, rsi
0x180010d10  call    LoadMUIFile
0x180010d15  mov     rdi, rax
0x180010d18  test    rax, rax
0x180010d1b  jnz     loc_180010F02
0x180010d21  cmp     [rbp+380h+var_390], bx
0x180010d25  jz      short loc_180010D47
0x180010d27  mov     r9, [rsp+480h+FilePart]
0x180010d2c  lea     r8, [rbp+380h+var_390]
0x180010d30  mov     rdx, r14
0x180010d33  mov     rcx, rsi
0x180010d36  call    LoadMUIFile
0x180010d3b  mov     rdi, rax
0x180010d3e  test    rax, rax
0x180010d41  jnz     loc_180010F02
0x180010d47  mov     ecx, 409h
0x180010d4c  cmp     cx, r15w
0x180010d50  jz      short loc_180010D8D
0x180010d52  cmp     cx, r12w
0x180010d56  jz      short loc_180010D8D
0x180010d58  xor     r9d, r9d
0x180010d5b  lea     r8, [rbp+380h+var_2E0]
0x180010d62  lea     rdx, [rsp+480h+var_440]
0x180010d67  call    LookupLangID
0x180010d6c  mov     r9, [rsp+480h+FilePart]
0x180010d71  lea     r8, [rsp+480h+var_440]
0x180010d76  mov     rdx, r14
0x180010d79  mov     rcx, rsi
0x180010d7c  call    LoadMUIFile
0x180010d81  mov     rdi, rax
0x180010d84  test    rax, rax
0x180010d87  jnz     loc_180010F02
0x180010d8d  mov     r9, [rsp+480h+FilePart]
0x180010d92  xor     r8d, r8d
0x180010d95  mov     rdx, r14
0x180010d98  mov     rcx, rsi
0x180010d9b  call    LoadMUIFile
0x180010da0  mov     rdi, rax
0x180010da3  test    rax, rax
0x180010da6  jnz     loc_180010F02
0x180010dac  test    sil, 1
0x180010db0  jz      loc_180010F3B
0x180010db6  mov     rcx, rsi; hLibModule
0x180010db9  call    cs:__imp_FreeLibrary
0x180010dc0  nop     dword ptr [rax+rax+00h]
0x180010dc5  call    GetOSType
0x180010dca  test    al, 38h
0x180010dcc  jz      loc_180010F16
0x180010dd2  mov     rax, [rsp+480h+FilePart]
0x180010dd7  lea     r8, aSS; "%s\\%s"
0x180010dde  mov     r9, r14
0x180010de1  mov     [rsp+480h+lpBuffer], rax
0x180010de6  mov     edx, 104h; unsigned __int64
0x180010deb  lea     rcx, [rbp+380h+Buffer]; unsigned __int16 *
0x180010df2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010df7  xor     r8d, r8d
0x180010dfa  lea     rcx, [rbp+380h+Buffer]
0x180010e01  lea     edx, [r8+1]
0x180010e05  call    MapMUIFile
0x180010e0a  jmp     loc_180010F38
0x180010e0f  test    al, 3
0x180010e11  jz      short loc_180010DAC
0x180010e13  call    GetInstallLanguage
0x180010e18  lea     r9, [rbp+380h+var_390]
0x180010e1c  movzx   ecx, ax
0x180010e1f  lea     r8, [rbp+380h+var_2E0]
0x180010e26  movzx   r15d, ax
0x180010e2a  lea     rdx, [rsp+480h+var_440]
0x180010e2f  call    LookupLangID
0x180010e34  test    eax, eax
0x180010e36  jz      loc_180010DAC
0x180010e3c  mov     r9, [rsp+480h+FilePart]
0x180010e41  lea     r8, [rsp+480h+var_440]
0x180010e46  mov     rdx, r14
0x180010e49  mov     rcx, rsi
0x180010e4c  call    LoadMUIFile
0x180010e51  mov     rdi, rax
0x180010e54  test    rax, rax
0x180010e57  jnz     loc_180010F02
0x180010e5d  mov     r9, [rsp+480h+FilePart]
0x180010e62  lea     r8, [rbp+380h+var_2E0]
0x180010e69  mov     rdx, r14
0x180010e6c  mov     rcx, rsi
0x180010e6f  call    LoadMUIFile
0x180010e74  mov     rdi, rax
0x180010e77  test    rax, rax
0x180010e7a  jnz     loc_180010F02
0x180010e80  cmp     [rbp+380h+var_390], bx
0x180010e84  jz      short loc_180010EA2
0x180010e86  mov     r9, [rsp+480h+FilePart]
0x180010e8b  lea     r8, [rbp+380h+var_390]
0x180010e8f  mov     rdx, r14
0x180010e92  mov     rcx, rsi
0x180010e95  call    LoadMUIFile
0x180010e9a  mov     rdi, rax
0x180010e9d  test    rax, rax
0x180010ea0  jnz     short loc_180010F02
0x180010ea2  mov     ecx, 409h
0x180010ea7  cmp     cx, r15w
0x180010eab  jz      short loc_180010EDE
0x180010ead  xor     r9d, r9d
0x180010eb0  lea     r8, [rbp+380h+var_2E0]
0x180010eb7  lea     rdx, [rsp+480h+var_440]
0x180010ebc  call    LookupLangID
0x180010ec1  mov     r9, [rsp+480h+FilePart]
0x180010ec6  lea     r8, [rsp+480h+var_440]
0x180010ecb  mov     rdx, r14
0x180010ece  mov     rcx, rsi
0x180010ed1  call    LoadMUIFile
0x180010ed6  mov     rdi, rax
0x180010ed9  test    rax, rax
0x180010edc  jnz     short loc_180010F02
0x180010ede  mov     r9, [rsp+480h+FilePart]
0x180010ee3  xor     r8d, r8d
0x180010ee6  mov     rdx, r14
0x180010ee9  mov     rcx, rsi
0x180010eec  call    LoadMUIFile
0x180010ef1  mov     rdi, rax
0x180010ef4  test    rax, rax
0x180010ef7  jnz     short loc_180010F02
0x180010ef9  test    rdi, rdi
0x180010efc  jz      loc_180010DAC
0x180010f02  mov     rcx, rsi; hLibModule
0x180010f05  call    cs:__imp_FreeLibrary
0x180010f0c  nop     dword ptr [rax+rax+00h]
0x180010f11  mov     rax, rdi
0x180010f14  jmp     short loc_180010F51
0x180010f16  call    GetOSType
0x180010f1b  test    al, 26h
0x180010f1d  lea     rcx, FileName; lpLibFileName
0x180010f24  setnz   bl
0x180010f27  xor     edx, edx; hFile
0x180010f29  mov     r8d, ebx; dwFlags
0x180010f2c  call    cs:__imp_LoadLibraryExW
0x180010f33  nop     dword ptr [rax+rax+00h]
0x180010f38  mov     rsi, rax
0x180010f3b  mov     rax, rsi
0x180010f3e  jmp     short loc_180010F51
0x180010f40  mov     rcx, rsi; hLibModule
0x180010f43  call    cs:__imp_FreeLibrary
0x180010f4a  nop     dword ptr [rax+rax+00h]
0x180010f4f  xor     eax, eax
0x180010f51  mov     rcx, [rbp+380h+var_20]
0x180010f58  xor     rcx, rsp; StackCookie
0x180010f5b  call    __security_check_cookie
0x180010f60  lea     r11, [rsp+480h+var_10]
0x180010f68  mov     rbx, [r11+20h]
0x180010f6c  mov     rsi, [r11+28h]
0x180010f70  mov     rdi, [r11+30h]
0x180010f74  mov     r12, [r11+38h]
0x180010f78  mov     rsp, r11
0x180010f7b  pop     r15
0x180010f7d  pop     r14
0x180010f7f  pop     rbp
0x180010f80  retn
```
