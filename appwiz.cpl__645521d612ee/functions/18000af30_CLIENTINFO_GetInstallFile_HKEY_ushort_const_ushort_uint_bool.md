# CLIENTINFO::GetInstallFile(HKEY__ *,ushort const *,ushort *,uint,bool)

- ea: `0x18000af30`
- end: `0x18000b135`
- name: `?GetInstallFile@CLIENTINFO@@QEAA_NPEAUHKEY__@@PEBGPEAGI_N@Z`
- size: `517`
- prototype: `bool(CLIENTINFO *__hidden this, HKEY, const unsigned __int16 *, unsigned __int16 *, unsigned int, bool)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x180009550`
- `0x18000b65c`

## callees

- `0x18000791c`
- `0x180007960`
- `0x18000af30`
- `0x1800582e0`

## import_xrefs

- `SHCORE!SHQueryValueExW` at `0x18000af98`
- `SHCORE!SHQueryValueExW` at `0x18000af98`
- `SHCORE!__imp_PathIsNetworkPathW` at `0x18000b0e8`
- `SHCORE!__imp_PathIsNetworkPathW` at `0x18000b0e8`
- `SHELL32!SHGetFolderPathW` at `0x18000b022`
- `SHELL32!SHGetFolderPathW` at `0x18000b075`
- `SHELL32!SHGetFolderPathW` at `0x18000b022`
- `SHELL32!SHGetFolderPathW` at `0x18000b075`
- `SHLWAPI!PathRemoveArgsW` at `0x18000afdd`
- `SHLWAPI!PathRemoveArgsW` at `0x18000afdd`
- `SHLWAPI!PathUnquoteSpacesW` at `0x18000afe8`
- `SHLWAPI!PathUnquoteSpacesW` at `0x18000afe8`
- `SHLWAPI!PathIsRelativeW` at `0x18000aff3`
- `SHLWAPI!PathIsRelativeW` at `0x18000aff3`
- `SHLWAPI!PathCommonPrefixW` at `0x18000b03f`
- `SHLWAPI!PathCommonPrefixW` at `0x18000b03f`
- `SHLWAPI!PathCombineW` at `0x18000b094`
- `SHLWAPI!PathCombineW` at `0x18000b094`
- `SHLWAPI!PathQuoteSpacesW` at `0x18000b09f`
- `SHLWAPI!PathQuoteSpacesW` at `0x18000b09f`
- `SHLWAPI!PathFileExistsW` at `0x18000b0f7`
- `SHLWAPI!PathFileExistsW` at `0x18000b0f7`
- `SHLWAPI!PathGetArgsW` at `0x18000b0a8`
- `SHLWAPI!PathGetArgsW` at `0x18000b0a8`
- `KERNEL32!lstrlenW` at `0x18000b04f`
- `KERNEL32!lstrlenW` at `0x18000b04f`

## pseudocode

```c
bool __fastcall CLIENTINFO::GetInstallFile(
        CLIENTINFO *this,
        HKEY a2,
        const unsigned __int16 *a3,
        unsigned __int16 *pvData,
        unsigned int a5,
        bool a6)
{
  __int64 v8; // rdi
  const unsigned __int16 *ArgsW; // rax
  DWORD pdwType; // [rsp+30h] [rbp-D0h] BYREF
  DWORD pcbData[3]; // [rsp+34h] [rbp-CCh] BYREF
  WCHAR pszPath[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pszFile1[264]; // [rsp+250h] [rbp+150h] BYREF

  pdwType = 0;
  *pvData = 0;
  pcbData[0] = 520;
  if ( SHQueryValueExW(a2, a3, 0, &pdwType, pvData, pcbData) || pdwType != 1 )
    return a6;
  if ( StringCchCopyW(pszPath, 0x104u, pvData) >= 0 )
  {
    if ( !a6 )
    {
      PathRemoveArgsW(pszPath);
      PathUnquoteSpacesW(pszPath);
    }
    if ( PathIsRelativeW(pszPath) )
      return 0;
    if ( *((_BYTE *)this + 40) )
    {
      if ( !SHGetFolderPathW(0, 37, 0, 0, pszFile1) )
      {
        v8 = PathCommonPrefixW(pszFile1, pszPath, 0);
        if ( (_DWORD)v8 == lstrlenW(pszFile1) && !SHGetFolderPathW(0, 41, 0, 0, pszFile1) )
        {
          PathCombineW(pszPath, pszFile1, &pszPath[v8 + 1]);
          PathQuoteSpacesW(pszPath);
          ArgsW = PathGetArgsW(pvData);
          StringCchCopyW(pszFile1, 0x104u, ArgsW);
          StringCchPrintfW(pvData, 0x104u, L"%s %s", pszPath, pszFile1);
        }
      }
    }
    if ( !PathIsNetworkPathW(pszPath) )
      return PathFileExistsW(pszPath);
  }
  return 1;
}

```

## disassembly

```asm
0x18000af30  mov     [rsp-8+arg_0], rbx
0x18000af35  push    rbp
0x18000af36  push    rdi
0x18000af37  push    r14
0x18000af39  lea     rbp, [rsp-370h]
0x18000af41  sub     rsp, 470h
0x18000af48  mov     rax, cs:__security_cookie
0x18000af4f  xor     rax, rsp
0x18000af52  mov     [rbp+380h+var_20], rax
0x18000af59  xor     eax, eax
0x18000af5b  mov     [rsp+480h+pdwType], 0
0x18000af63  mov     [r9], ax
0x18000af67  mov     r11, r8
0x18000af6a  mov     r10, rdx
0x18000af6d  mov     [rsp+480h+var_44C], 208h
0x18000af75  mov     rbx, r9
0x18000af78  lea     rax, [rsp+480h+var_44C]
0x18000af7d  mov     rdi, rcx
0x18000af80  mov     [rsp+480h+pcbData], rax; pcbData
0x18000af85  lea     r9, [rsp+480h+pdwType]; pdwType
0x18000af8a  mov     [rsp+480h+pvData], rbx; pvData
0x18000af8f  xor     r8d, r8d; pdwReserved
0x18000af92  mov     rdx, r11; pszValue
0x18000af95  mov     rcx, r10; hkey
0x18000af98  call    cs:__imp_SHQueryValueExW
0x18000af9e  test    eax, eax
0x18000afa0  jnz     loc_18000B10C
0x18000afa6  cmp     [rsp+480h+pdwType], 1
0x18000afab  jnz     loc_18000B10C
0x18000afb1  mov     r14d, 104h
0x18000afb7  lea     rcx, [rsp+480h+pszPath]; unsigned __int16 *
0x18000afbc  mov     edx, r14d; unsigned __int64
0x18000afbf  mov     r8, rbx; unsigned __int16 *
0x18000afc2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000afc7  test    eax, eax
0x18000afc9  js      loc_18000B108
0x18000afcf  cmp     [rbp+380h+arg_28], 0
0x18000afd6  jnz     short loc_18000AFEE
0x18000afd8  lea     rcx, [rsp+480h+pszPath]; pszPath
0x18000afdd  call    cs:__imp_PathRemoveArgsW
0x18000afe3  lea     rcx, [rsp+480h+pszPath]; lpsz
0x18000afe8  call    cs:__imp_PathUnquoteSpacesW
0x18000afee  lea     rcx, [rsp+480h+pszPath]; pszPath
0x18000aff3  call    cs:__imp_PathIsRelativeW
0x18000aff9  test    eax, eax
0x18000affb  jnz     loc_18000B104
0x18000b001  cmp     [rdi+28h], al
0x18000b004  jz      loc_18000B0E3
0x18000b00a  xor     r9d, r9d; dwFlags
0x18000b00d  lea     rax, [rbp+380h+pszFile1]
0x18000b014  xor     r8d, r8d; hToken
0x18000b017  mov     [rsp+480h+pvData], rax; pszPath
0x18000b01c  xor     ecx, ecx; hwnd
0x18000b01e  lea     edx, [r9+25h]; csidl
0x18000b022  call    cs:__imp_SHGetFolderPathW
0x18000b028  test    eax, eax
0x18000b02a  jnz     loc_18000B0E3
0x18000b030  xor     r8d, r8d; achPath
0x18000b033  lea     rdx, [rsp+480h+pszPath]; pszFile2
0x18000b038  lea     rcx, [rbp+380h+pszFile1]; pszFile1
0x18000b03f  call    cs:__imp_PathCommonPrefixW
0x18000b045  lea     rcx, [rbp+380h+pszFile1]; lpString
0x18000b04c  movsxd  rdi, eax
0x18000b04f  call    cs:__imp_lstrlenW
0x18000b055  cmp     edi, eax
0x18000b057  jnz     loc_18000B0E3
0x18000b05d  xor     r9d, r9d; dwFlags
0x18000b060  lea     rax, [rbp+380h+pszFile1]
0x18000b067  xor     r8d, r8d; hToken
0x18000b06a  mov     [rsp+480h+pvData], rax; pszPath
0x18000b06f  xor     ecx, ecx; hwnd
0x18000b071  lea     edx, [r9+29h]; csidl
0x18000b075  call    cs:__imp_SHGetFolderPathW
0x18000b07b  test    eax, eax
0x18000b07d  jnz     short loc_18000B0E3
0x18000b07f  lea     r8, [rsp+480h+var_43E]
0x18000b084  lea     r8, [r8+rdi*2]; pszFile
0x18000b088  lea     rdx, [rbp+380h+pszFile1]; pszDir
0x18000b08f  lea     rcx, [rsp+480h+pszPath]; pszDest
0x18000b094  call    cs:__imp_PathCombineW
0x18000b09a  lea     rcx, [rsp+480h+pszPath]; lpsz
0x18000b09f  call    cs:__imp_PathQuoteSpacesW
0x18000b0a5  mov     rcx, rbx; pszPath
0x18000b0a8  call    cs:__imp_PathGetArgsW
0x18000b0ae  mov     rdx, r14; unsigned __int64
0x18000b0b1  lea     rcx, [rbp+380h+pszFile1]; unsigned __int16 *
0x18000b0b8  mov     r8, rax; unsigned __int16 *
0x18000b0bb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b0c0  lea     r11, [rbp+380h+pszFile1]
0x18000b0c7  mov     rdx, r14; unsigned __int64
0x18000b0ca  lea     r9, [rsp+480h+pszPath]
0x18000b0cf  mov     [rsp+480h+pvData], r11
0x18000b0d4  lea     r8, aSS_0; "%s %s"
0x18000b0db  mov     rcx, rbx; unsigned __int16 *
0x18000b0de  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000b0e3  lea     rcx, [rsp+480h+pszPath]; pszPath
0x18000b0e8  call    cs:__imp_PathIsNetworkPathW
0x18000b0ee  test    eax, eax
0x18000b0f0  jnz     short loc_18000B108
0x18000b0f2  lea     rcx, [rsp+480h+pszPath]; pszPath
0x18000b0f7  call    cs:__imp_PathFileExistsW
0x18000b0fd  test    eax, eax
0x18000b0ff  setnz   al
0x18000b102  jmp     short loc_18000B112
0x18000b104  xor     al, al
0x18000b106  jmp     short loc_18000B112
0x18000b108  mov     al, 1
0x18000b10a  jmp     short loc_18000B112
0x18000b10c  mov     al, [rbp+380h+arg_28]
0x18000b112  mov     rcx, [rbp+380h+var_20]
0x18000b119  xor     rcx, rsp; StackCookie
0x18000b11c  call    __security_check_cookie
0x18000b121  mov     rbx, [rsp+480h+arg_0]
0x18000b129  add     rsp, 470h
0x18000b130  pop     r14
0x18000b132  pop     rdi
0x18000b133  pop     rbp
0x18000b134  retn
```
