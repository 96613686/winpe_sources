# LoadMUILibraryW

- ea: `0x1802385e4`
- end: `0x1802387eb`
- name: `LoadMUILibraryW`
- size: `519`
- prototype: `HINSTANCE __stdcall(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180236e98`

## callees

- `0x18000c840`
- `0x18001a64c`
- `0x180238030`
- `0x180238164`
- `0x1802381d8`
- `0x180238360`
- `0x1802385e4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1802386cc`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1802386cc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180238640`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18023879e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180238640`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18023879e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180238723`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18023873f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1802387b5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180238723`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18023873f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1802387b5`
- `KERNEL32!SearchPathW` at `0x180238686`
- `KERNEL32!SearchPathW` at `0x180238686`

## pseudocode

```c
HINSTANCE __stdcall LoadMUILibraryW(PCWSTR pszFullModuleName, DWORD dwLangConvention, LANGID LangID)
{
  HINSTANCE result; // rax
  HMODULE v5; // rbx
  WCHAR *v6; // rsi
  HINSTANCE MUIFile; // r14
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  char OSType; // al
  LPWSTR FilePart; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v17[176]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Buffer[264]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v19[176]; // [rsp+300h] [rbp+200h] BYREF

  FilePart = 0;
  if ( !pszFullModuleName )
    return 0;
  dword_1803B07F0 = GetOSType(pszFullModuleName, dwLangConvention, LangID);
  result = LoadLibraryExW(pszFullModuleName, 0, dword_1803B07F0 & 0x20 | 2u);
  v5 = result;
  if ( !result )
    return 0;
  if ( (dword_1803B07F0 & 0x20) != 0 )
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
  if ( FindResourceExW(v5, L"MUI", (LPCWSTR)1, 0)
    && (dword_1803B07F0 & 7) != 0
    && (unsigned int)LookupLangID(1024, v17, v19, 0)
    && (MUIFile = (HINSTANCE)LoadMUIFile(v5, v6, v17, FilePart)) != 0 )
  {
    FreeLibrary(v5);
    return MUIFile;
  }
  else
  {
    if ( ((unsigned __int8)v5 & 1) != 0 )
    {
      FreeLibrary(v5);
      if ( (GetOSType(v9, v8, v10) & 0x38) != 0 )
      {
        StringCchPrintfW(Buffer, 0x104u, L"%s\\%s", v6, FilePart);
        return (HINSTANCE)MapMUIFile(Buffer, 1);
      }
      else
      {
        OSType = GetOSType(v12, v11, v13);
        return LoadLibraryExW(pszFullModuleName, 0, (OSType & 0x26) != 0);
      }
    }
    return v5;
  }
}

```

## disassembly

```asm
0x1802385e4  mov     [rsp-8+arg_8], rbx
0x1802385e9  mov     [rsp-8+arg_10], rsi
0x1802385ee  push    rbp
0x1802385ef  push    rdi
0x1802385f0  push    r14
0x1802385f2  lea     rbp, [rsp-2C0h]
0x1802385fa  sub     rsp, 3C0h
0x180238601  mov     rax, cs:__security_cookie
0x180238608  xor     rax, rsp
0x18023860b  mov     [rbp+2D0h+var_20], rax
0x180238612  mov     [rsp+3D0h+FilePart], 0
0x18023861b  mov     rdi, rcx
0x18023861e  test    rcx, rcx
0x180238621  jz      loc_1802387C1
0x180238627  call    GetOSType
0x18023862c  mov     cs:dword_1803B07F0, eax
0x180238632  xor     edx, edx; hFile
0x180238634  and     eax, 20h
0x180238637  mov     rcx, rdi; lpLibFileName
0x18023863a  or      eax, 2
0x18023863d  mov     r8d, eax; dwFlags
0x180238640  call    cs:__imp_LoadLibraryExW
0x180238647  nop     dword ptr [rax+rax+00h]
0x18023864c  mov     rbx, rax
0x18023864f  test    rax, rax
0x180238652  jz      loc_1802387C1
0x180238658  test    byte ptr cs:dword_1803B07F0, 20h
0x18023865f  jnz     loc_1802387C3
0x180238665  lea     rax, [rsp+3D0h+FilePart]
0x18023866a  mov     r9d, 104h; nBufferLength
0x180238670  mov     [rsp+3D0h+lpFilePart], rax; lpFilePart
0x180238675  xor     r8d, r8d; lpExtension
0x180238678  lea     rax, [rbp+2D0h+Buffer]
0x18023867c  mov     rdx, rdi; lpFileName
0x18023867f  xor     ecx, ecx; lpPath
0x180238681  mov     [rsp+3D0h+lpBuffer], rax; lpBuffer
0x180238686  call    cs:__imp_SearchPathW
0x18023868d  nop     dword ptr [rax+rax+00h]
0x180238692  test    eax, eax
0x180238694  jz      loc_1802387B2
0x18023869a  mov     rcx, [rsp+3D0h+FilePart]
0x18023869f  test    rcx, rcx
0x1802386a2  jnz     short loc_1802386B1
0x1802386a4  lea     rax, [rbp+2D0h+Buffer]
0x1802386a8  xor     esi, esi
0x1802386aa  mov     [rsp+3D0h+FilePart], rax
0x1802386af  jmp     short loc_1802386BB
0x1802386b1  xor     eax, eax
0x1802386b3  lea     rsi, [rbp+2D0h+Buffer]
0x1802386b7  mov     [rcx-2], ax
0x1802386bb  xor     r9d, r9d; wLanguage
0x1802386be  lea     rdx, Type; "MUI"
0x1802386c5  mov     rcx, rbx; hModule
0x1802386c8  lea     r8d, [r9+1]; lpName
0x1802386cc  call    cs:__imp_FindResourceExW
0x1802386d3  nop     dword ptr [rax+rax+00h]
0x1802386d8  test    rax, rax
0x1802386db  jz      short loc_180238737
0x1802386dd  test    byte ptr cs:dword_1803B07F0, 7
0x1802386e4  jz      short loc_180238737
0x1802386e6  mov     ecx, 400h
0x1802386eb  lea     r8, [rbp+2D0h+var_D0]
0x1802386f2  xor     r9d, r9d
0x1802386f5  lea     rdx, [rsp+3D0h+var_390]
0x1802386fa  call    LookupLangID
0x1802386ff  test    eax, eax
0x180238701  jz      short loc_180238737
0x180238703  mov     r9, [rsp+3D0h+FilePart]
0x180238708  lea     r8, [rsp+3D0h+var_390]
0x18023870d  mov     rdx, rsi
0x180238710  mov     rcx, rbx
0x180238713  call    LoadMUIFile
0x180238718  mov     r14, rax
0x18023871b  test    rax, rax
0x18023871e  jz      short loc_180238737
0x180238720  mov     rcx, rbx; hLibModule
0x180238723  call    cs:__imp_FreeLibrary
0x18023872a  nop     dword ptr [rax+rax+00h]
0x18023872f  mov     rax, r14
0x180238732  jmp     loc_1802387C3
0x180238737  test    bl, 1
0x18023873a  jz      short loc_1802387AD
0x18023873c  mov     rcx, rbx; hLibModule
0x18023873f  call    cs:__imp_FreeLibrary
0x180238746  nop     dword ptr [rax+rax+00h]
0x18023874b  call    GetOSType
0x180238750  test    al, 38h
0x180238752  jz      short loc_180238788
0x180238754  mov     rax, [rsp+3D0h+FilePart]
0x180238759  lea     r8, aSS; "%s\\%s"
0x180238760  mov     r9, rsi
0x180238763  mov     [rsp+3D0h+lpBuffer], rax
0x180238768  mov     edx, 104h; unsigned __int64
0x18023876d  lea     rcx, [rbp+2D0h+Buffer]; unsigned __int16 *
0x180238771  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180238776  xor     r8d, r8d
0x180238779  lea     rcx, [rbp+2D0h+Buffer]
0x18023877d  lea     edx, [r8+1]
0x180238781  call    MapMUIFile
0x180238786  jmp     short loc_1802387AA
0x180238788  call    GetOSType
0x18023878d  test    al, 26h
0x18023878f  mov     r8d, 0
0x180238795  mov     rcx, rdi; lpLibFileName
0x180238798  setnz   r8b; dwFlags
0x18023879c  xor     edx, edx; hFile
0x18023879e  call    cs:__imp_LoadLibraryExW
0x1802387a5  nop     dword ptr [rax+rax+00h]
0x1802387aa  mov     rbx, rax
0x1802387ad  mov     rax, rbx
0x1802387b0  jmp     short loc_1802387C3
0x1802387b2  mov     rcx, rbx; hLibModule
0x1802387b5  call    cs:__imp_FreeLibrary
0x1802387bc  nop     dword ptr [rax+rax+00h]
0x1802387c1  xor     eax, eax
0x1802387c3  mov     rcx, [rbp+2D0h+var_20]
0x1802387ca  xor     rcx, rsp; StackCookie
0x1802387cd  call    __security_check_cookie
0x1802387d2  lea     r11, [rsp+3D0h+var_10]
0x1802387da  mov     rbx, [r11+28h]
0x1802387de  mov     rsi, [r11+30h]
0x1802387e2  mov     rsp, r11
0x1802387e5  pop     r14
0x1802387e7  pop     rdi
0x1802387e8  pop     rbp
0x1802387e9  retn
```
