# Windows::Globalization::Spelling::UserDictionaries::EnsureDefaultUserDictionaryIsUtf16(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18004b100`
- end: `0x18004b2d5`
- name: `?EnsureDefaultUserDictionaryIsUtf16@UserDictionaries@Spelling@Globalization@Windows@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV56@0@Z`
- size: `469`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, PCWSTR pszDir)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18001ee7c`
- `0x1800202e4`
- `0x180021410`
- `0x1800479dc`
- `0x18004b100`
- `0x18004b404`
- `0x18004b470`
- `0x18004b598`
- `0x18004b6d4`
- `0x18004b75c`
- `0x180061320`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x18004b203`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x18004b203`
- `ext-ms-win-shell32-shellfolders-l1-1-1!PathMakeUniqueName` at `0x18004b1e6`
- `ext-ms-win-shell32-shellfolders-l1-1-1!PathMakeUniqueName` at `0x18004b1e6`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall Windows::Globalization::Spelling::UserDictionaries::EnsureDefaultUserDictionaryIsUtf16(
        _QWORD *lpFileName,
        const WCHAR *pszDir)
{
  __int64 v4; // rax
  __int64 v5; // rdx
  const WCHAR *v6; // r9
  const WCHAR *v7; // r8
  __int64 v8; // rcx
  const WCHAR *v9; // rcx
  __int64 v10; // rdx
  _QWORD *v11; // r8
  _QWORD *v12; // r8
  _WORD *v13; // rcx
  PCWSTR pszLongPlate[4]; // [rsp+40h] [rbp-C0h] BYREF
  PCWSTR pszTemplate[4]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR pszUniqueName[264]; // [rsp+80h] [rbp-80h] BYREF

  std::operator+<unsigned short>(pszTemplate, L"default");
  v4 = std::operator+<unsigned short>(pszLongPlate, pszDir, 92);
  std::operator+<unsigned short>(lpFileName, v4, pszTemplate);
  std::wstring::_Tidy_deallocate(pszLongPlate);
  LOBYTE(v5) = 1;
  if ( !(unsigned __int8)Windows::Globalization::Spelling::UserDictionaries::IsUtf16File(lpFileName, v5) )
  {
    std::operator+<unsigned short>(pszLongPlate, L"default NotUtf16");
    if ( *((_QWORD *)pszDir + 3) > 7u )
      pszDir = *(const WCHAR **)pszDir;
    v6 = (const WCHAR *)pszLongPlate;
    if ( pszLongPlate[3] > (PCWSTR)7 )
      v6 = pszLongPlate[0];
    v7 = (const WCHAR *)pszTemplate;
    if ( pszTemplate[3] > (PCWSTR)7 )
      v7 = pszTemplate[0];
    if ( PathMakeUniqueName(pszUniqueName, 0x104u, v7, v6, pszDir)
      && (lpFileName[3] <= 7u ? (v9 = (const WCHAR *)lpFileName) : (v9 = (const WCHAR *)*lpFileName),
          MoveFileW(v9, pszUniqueName)) )
    {
      if ( (Microsoft_Windows_Spell_CheckingEnableBits & 2) != 0 )
      {
        if ( lpFileName[3] <= 7u )
          v11 = lpFileName;
        else
          v11 = (_QWORD *)*lpFileName;
        McTemplateU0zz_EventWriteTransfer(v8, v10, v11, pszUniqueName);
      }
    }
    else
    {
      if ( (Microsoft_Windows_Spell_CheckingEnableBits & 4) != 0 )
      {
        if ( lpFileName[3] <= 7u )
          v12 = lpFileName;
        else
          v12 = (_QWORD *)*lpFileName;
        McTemplateU0z_EventWriteTransfer(v8, DefaultFileNotUnicodeFailedMove, v12);
      }
      lpFileName[2] = 0;
      if ( lpFileName[3] <= 7u )
        v13 = lpFileName;
      else
        v13 = (_WORD *)*lpFileName;
      *v13 = 0;
    }
    std::wstring::_Tidy_deallocate(pszLongPlate);
  }
  std::wstring::wstring((char **)pszLongPlate, &dword_1800D3F14);
  Windows::Globalization::Spelling::UserDictionaries::AddWordToFile((const WCHAR *)lpFileName, (__int64)pszLongPlate);
  std::wstring::_Tidy_deallocate(pszLongPlate);
  std::wstring::_Tidy_deallocate(pszTemplate);
  return lpFileName;
}

```

## disassembly

```asm
0x18004b100  mov     [rsp-8+arg_18], rbx
0x18004b105  push    rbp
0x18004b106  push    rsi
0x18004b107  push    rdi
0x18004b108  lea     rbp, [rsp-1A0h]
0x18004b110  sub     rsp, 2A0h
0x18004b117  mov     rax, cs:__security_cookie
0x18004b11e  xor     rax, rsp
0x18004b121  mov     [rbp+1B0h+var_20], rax
0x18004b128  mov     rsi, r8
0x18004b12b  mov     rdi, rdx
0x18004b12e  mov     rbx, rcx
0x18004b131  mov     [rsp+2B0h+var_278], rcx
0x18004b136  mov     [rsp+2B0h+var_280], 0
0x18004b13e  lea     rdx, aDefault; "default"
0x18004b145  lea     rcx, [rsp+2B0h+pszTemplate]
0x18004b14a  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x18004b14f  nop
0x18004b150  mov     r8d, 5Ch ; '\'
0x18004b156  mov     rdx, rdi
0x18004b159  lea     rcx, [rsp+2B0h+pszLongPlate]
0x18004b15e  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@G@Z; std::operator+<ushort>(std::wstring const &,ushort)
0x18004b163  nop
0x18004b164  lea     r8, [rsp+2B0h+pszTemplate]
0x18004b169  mov     rdx, rax
0x18004b16c  mov     rcx, rbx
0x18004b16f  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x18004b174  mov     [rsp+2B0h+var_280], 1
0x18004b17c  lea     rcx, [rsp+2B0h+pszLongPlate]
0x18004b181  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004b186  mov     dl, 1
0x18004b188  mov     rcx, rbx
0x18004b18b  call    ?IsUtf16File@UserDictionaries@Spelling@Globalization@Windows@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; Windows::Globalization::Spelling::UserDictionaries::IsUtf16File(std::wstring const &,bool)
0x18004b190  test    al, al
0x18004b192  jnz     loc_18004B27A
0x18004b198  mov     r8, rsi
0x18004b19b  lea     rdx, aDefaultNotutf1; "default NotUtf16"
0x18004b1a2  lea     rcx, [rsp+2B0h+pszLongPlate]
0x18004b1a7  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x18004b1ac  cmp     qword ptr [rdi+18h], 7
0x18004b1b1  jbe     short loc_18004B1B6
0x18004b1b3  mov     rdi, [rdi]
0x18004b1b6  lea     r9, [rsp+2B0h+pszLongPlate]
0x18004b1bb  cmp     [rsp+2B0h+var_258], 7
0x18004b1c1  cmova   r9, [rsp+2B0h+pszLongPlate]; pszLongPlate
0x18004b1c7  lea     r8, [rsp+2B0h+pszTemplate]
0x18004b1cc  cmp     [rsp+2B0h+var_238], 7
0x18004b1d2  cmova   r8, [rsp+2B0h+pszTemplate]; pszTemplate
0x18004b1d8  mov     [rsp+2B0h+pszDir], rdi; pszDir
0x18004b1dd  mov     edx, 104h; cchMax
0x18004b1e2  lea     rcx, [rbp+1B0h+pszUniqueName]; pszUniqueName
0x18004b1e6  call    cs:__imp_PathMakeUniqueName
0x18004b1ec  test    eax, eax
0x18004b1ee  jz      short loc_18004B230
0x18004b1f0  cmp     qword ptr [rbx+18h], 7
0x18004b1f5  jbe     short loc_18004B1FC
0x18004b1f7  mov     rcx, [rbx]
0x18004b1fa  jmp     short loc_18004B1FF
0x18004b1fc  mov     rcx, rbx; lpExistingFileName
0x18004b1ff  lea     rdx, [rbp+1B0h+pszUniqueName]; lpNewFileName
0x18004b203  call    cs:__imp_MoveFileW
0x18004b209  test    eax, eax
0x18004b20b  jz      short loc_18004B230
0x18004b20d  test    cs:Microsoft_Windows_Spell_CheckingEnableBits, 2
0x18004b214  jz      short loc_18004B270
0x18004b216  cmp     qword ptr [rbx+18h], 7
0x18004b21b  jbe     short loc_18004B222
0x18004b21d  mov     r8, [rbx]
0x18004b220  jmp     short loc_18004B225
0x18004b222  mov     r8, rbx
0x18004b225  lea     r9, [rbp+1B0h+pszUniqueName]
0x18004b229  call    McTemplateU0zz_EventWriteTransfer
0x18004b22e  jmp     short loc_18004B270
0x18004b230  test    cs:Microsoft_Windows_Spell_CheckingEnableBits, 4
0x18004b237  jz      short loc_18004B254
0x18004b239  cmp     qword ptr [rbx+18h], 7
0x18004b23e  jbe     short loc_18004B245
0x18004b240  mov     r8, [rbx]
0x18004b243  jmp     short loc_18004B248
0x18004b245  mov     r8, rbx
0x18004b248  lea     rdx, DefaultFileNotUnicodeFailedMove
0x18004b24f  call    McTemplateU0z_EventWriteTransfer
0x18004b254  mov     qword ptr [rbx+10h], 0
0x18004b25c  cmp     qword ptr [rbx+18h], 7
0x18004b261  jbe     short loc_18004B268
0x18004b263  mov     rcx, [rbx]
0x18004b266  jmp     short loc_18004B26B
0x18004b268  mov     rcx, rbx
0x18004b26b  xor     eax, eax
0x18004b26d  mov     [rcx], ax
0x18004b270  lea     rcx, [rsp+2B0h+pszLongPlate]
0x18004b275  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004b27a  lea     rdx, dword_1800D3F14
0x18004b281  lea     rcx, [rsp+2B0h+pszLongPlate]
0x18004b286  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004b28b  nop
0x18004b28c  lea     rdx, [rsp+2B0h+pszLongPlate]
0x18004b291  mov     rcx, rbx; lpFileName
0x18004b294  call    ?AddWordToFile@UserDictionaries@Spelling@Globalization@Windows@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Windows::Globalization::Spelling::UserDictionaries::AddWordToFile(std::wstring const &,std::wstring const &)
0x18004b299  nop
0x18004b29a  lea     rcx, [rsp+2B0h+pszLongPlate]
0x18004b29f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004b2a4  nop
0x18004b2a5  lea     rcx, [rsp+2B0h+pszTemplate]
0x18004b2aa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004b2af  mov     rax, rbx
0x18004b2b2  mov     rcx, [rbp+1B0h+var_20]
0x18004b2b9  xor     rcx, rsp; StackCookie
0x18004b2bc  call    __security_check_cookie
0x18004b2c1  mov     rbx, [rsp+2B0h+arg_18]
0x18004b2c9  add     rsp, 2A0h
0x18004b2d0  pop     rdi
0x18004b2d1  pop     rsi
0x18004b2d2  pop     rbp
0x18004b2d3  retn
```
