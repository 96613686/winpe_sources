# Windows::Globalization::Spelling::UserDictionaries::IsNonAppDataNetworkPath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ushort const *)

- ea: `0x18001ec68`
- end: `0x18001ed94`
- name: `?IsNonAppDataNetworkPath@UserDictionaries@Spelling@Globalization@Windows@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z`
- size: `300`
- prototype: `__int64 __fastcall(LPCWSTR pszPath)`
- caller_count: `2`
- callee_count: `8`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x18001eb7c`
- `0x18005d6f4`

## callees

- `0x18001ec68`
- `0x18001ee7c`
- `0x1800202e4`
- `0x1800206ec`
- `0x180061320`
- `0x18006a0e4`
- `0x180075078`
- `0x18007f12c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ed00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ed00`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsPrefixW` at `0x18001ed22`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsPrefixW` at `0x18001ed22`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathCombineW` at `0x18001ecd9`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathCombineW` at `0x18001ecd9`

## pseudocode

```c
char __fastcall Windows::Globalization::Spelling::UserDictionaries::IsNonAppDataNetworkPath(
        WCHAR *pszPath,
        const unsigned __int16 *a2)
{
  char v2; // si
  int RoamingAppDataPath; // eax
  int v5; // edi
  unsigned int v6; // r8d
  const char *v7; // r9
  const WCHAR *v9; // rdx
  char v10; // bl
  LPCWSTR pszDir; // [rsp+20h] [rbp-258h] BYREF
  WCHAR pszPatha[20]; // [rsp+28h] [rbp-250h] BYREF
  WCHAR pszDest[264]; // [rsp+50h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  v2 = 0;
  pszDir = 0;
  RoamingAppDataPath = Windows::Globalization::Spelling::SpellerUDFiles::GetRoamingAppDataPath(
                         (unsigned __int16 **)&pszDir,
                         a2);
  v5 = RoamingAppDataPath;
  if ( RoamingAppDataPath < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2FF,
      (unsigned int)"OnecoreUAP\\private\\Base\\inc\\SpellerUserDictionaries.h",
      (const char *)(unsigned int)RoamingAppDataPath,
      (int)pszDir);
    return 1;
  }
  if ( !PathCombineW(pszDest, pszDir, L"Microsoft\\Spelling") )
  {
    wil::details::in1diag3::Log_GetLastError(retaddr, (void *)0x307, v6, v7);
    v5 = -2147467259;
  }
  CoTaskMemFree((LPVOID)pszDir);
  if ( v5 < 0 )
    return 1;
  if ( *((_QWORD *)pszPath + 3) <= 7u )
    v9 = pszPath;
  else
    v9 = *(const WCHAR **)pszPath;
  if ( PathIsPrefixW(pszDest, v9) )
    goto LABEL_15;
  if ( *((_QWORD *)pszPath + 3) > 7u )
    pszPath = *(WCHAR **)pszPath;
  std::wstring::wstring((char **)pszPatha, pszPath);
  v2 = 1;
  if ( !(unsigned __int8)Windows::Globalization::Spelling::UserDictionaries::IsNetworkPath(pszPatha) )
LABEL_15:
    v10 = 0;
  else
    v10 = 1;
  if ( (v2 & 1) != 0 )
    std::wstring::_Tidy_deallocate(pszPatha);
  return v10;
}

```

## disassembly

```asm
0x18001ec68  mov     [rsp+arg_10], rbx
0x18001ec6d  mov     [rsp+arg_18], rsi
0x18001ec72  push    rdi
0x18001ec73  sub     rsp, 270h
0x18001ec7a  mov     rax, cs:__security_cookie
0x18001ec81  xor     rax, rsp
0x18001ec84  mov     [rsp+278h+var_18], rax
0x18001ec8c  xor     esi, esi
0x18001ec8e  mov     rbx, rcx
0x18001ec91  mov     dword ptr [rsp+278h+pszDir], esi
0x18001ec95  lea     rcx, [rsp+278h+pszDir]; unsigned __int16 **
0x18001ec9a  mov     [rsp+278h+pszDir], rsi; int
0x18001ec9f  call    ?GetRoamingAppDataPath@SpellerUDFiles@Spelling@Globalization@Windows@@SAJPEAPEAGPEBG@Z; Windows::Globalization::Spelling::SpellerUDFiles::GetRoamingAppDataPath(ushort * *,ushort const *)
0x18001eca4  mov     edi, eax
0x18001eca6  test    eax, eax
0x18001eca8  jns     short loc_18001ECC8
0x18001ecaa  mov     rcx, [rsp+278h]; this
0x18001ecb2  lea     r8, aOnecoreuapPriv; "OnecoreUAP\\private\\Base\\inc\\Speller"...
0x18001ecb9  mov     r9d, eax; char *
0x18001ecbc  mov     edx, 2FFh; void *
0x18001ecc1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001ecc6  jmp     short loc_18001ED0A
0x18001ecc8  mov     rdx, [rsp+278h+pszDir]; pszDir
0x18001eccd  lea     r8, pszFile; "Microsoft\\Spelling"
0x18001ecd4  lea     rcx, [rsp+278h+pszDest]; pszDest
0x18001ecd9  call    cs:__imp_PathCombineW
0x18001ecdf  test    rax, rax
0x18001ece2  jnz     short loc_18001ECFB
0x18001ece4  mov     rcx, [rsp+278h]; this
0x18001ecec  mov     edx, 307h; void *
0x18001ecf1  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x18001ecf6  mov     edi, 80004005h
0x18001ecfb  mov     rcx, [rsp+278h+pszDir]; pv
0x18001ed00  call    cs:__imp_CoTaskMemFree
0x18001ed06  test    edi, edi
0x18001ed08  jns     short loc_18001ED0E
0x18001ed0a  mov     al, 1
0x18001ed0c  jmp     short loc_18001ED6F
0x18001ed0e  cmp     qword ptr [rbx+18h], 7
0x18001ed13  jbe     short loc_18001ED1A
0x18001ed15  mov     rdx, [rbx]
0x18001ed18  jmp     short loc_18001ED1D
0x18001ed1a  mov     rdx, rbx; pszPath
0x18001ed1d  lea     rcx, [rsp+278h+pszDest]; pszPrefix
0x18001ed22  call    cs:__imp_PathIsPrefixW
0x18001ed28  test    eax, eax
0x18001ed2a  jnz     short loc_18001ED5B
0x18001ed2c  cmp     qword ptr [rbx+18h], 7
0x18001ed31  jbe     short loc_18001ED36
0x18001ed33  mov     rbx, [rbx]
0x18001ed36  mov     rdx, rbx
0x18001ed39  lea     rcx, [rsp+278h+pszPath]
0x18001ed3e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001ed43  lea     rcx, [rsp+278h+pszPath]; pszPath
0x18001ed48  mov     esi, 1
0x18001ed4d  call    ?IsNetworkPath@UserDictionaries@Spelling@Globalization@Windows@@CA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Globalization::Spelling::UserDictionaries::IsNetworkPath(std::wstring const &)
0x18001ed52  test    al, al
0x18001ed54  jz      short loc_18001ED5B
0x18001ed56  mov     bl, sil
0x18001ed59  jmp     short loc_18001ED5D
0x18001ed5b  xor     bl, bl
0x18001ed5d  test    sil, 1
0x18001ed61  jz      short loc_18001ED6D
0x18001ed63  lea     rcx, [rsp+278h+pszPath]
0x18001ed68  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ed6d  mov     al, bl
0x18001ed6f  mov     rcx, [rsp+278h+var_18]
0x18001ed77  xor     rcx, rsp; StackCookie
0x18001ed7a  call    __security_check_cookie
0x18001ed7f  lea     r11, [rsp+278h+var_8]
0x18001ed87  mov     rbx, [r11+20h]
0x18001ed8b  mov     rsi, [r11+28h]
0x18001ed8f  mov     rsp, r11
0x18001ed92  pop     rdi
0x18001ed93  retn
```
