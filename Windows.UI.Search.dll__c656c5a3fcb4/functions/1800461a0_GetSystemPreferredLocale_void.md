# GetSystemPreferredLocale(void)

- ea: `0x1800461a0`
- end: `0x18004623a`
- name: `?GetSystemPreferredLocale@@YAKXZ`
- size: `154`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800460d0`

## callees

- `0x1800461a0`
- `0x18004af5c`
- `0x180076c50`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x18004621c`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x18004621c`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x1800461e0`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x1800461e0`
- `api-ms-win-core-localization-l1-2-0!ResolveLocaleName` at `0x180046204`
- `api-ms-win-core-localization-l1-2-0!ResolveLocaleName` at `0x180046204`

## pseudocode

```c
unsigned int GetSystemPreferredLocale(void)
{
  unsigned int v0; // edx
  unsigned int result; // eax
  ULONG pulNumLanguages; // [rsp+20h] [rbp-2D8h] BYREF
  ULONG pcchLanguagesBuffer[3]; // [rsp+24h] [rbp-2D4h] BYREF
  WCHAR LocaleName[88]; // [rsp+30h] [rbp-2C8h] BYREF
  WCHAR pwszLanguagesBuffer[256]; // [rsp+E0h] [rbp-218h] BYREF

  pulNumLanguages = 0;
  pcchLanguagesBuffer[0] = 256;
  if ( !GetSystemPreferredUILanguages(8u, &pulNumLanguages, pwszLanguagesBuffer, pcchLanguagesBuffer) )
    return GetSystemDefaultLCID();
  if ( !pulNumLanguages )
    return GetSystemDefaultLCID();
  if ( ResolveLocaleName(pwszLanguagesBuffer, LocaleName, 85) <= 0 )
    return GetSystemDefaultLCID();
  result = _LocaleNameToLCIDNoCustomLocales(LocaleName, v0);
  if ( !result )
    return GetSystemDefaultLCID();
  return result;
}

```

## disassembly

```asm
0x1800461a0  sub     rsp, 2F8h
0x1800461a7  mov     rax, cs:__security_cookie
0x1800461ae  xor     rax, rsp
0x1800461b1  mov     [rsp+2F8h+var_18], rax
0x1800461b9  lea     r9, [rsp+2F8h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x1800461be  mov     [rsp+2F8h+pulNumLanguages], 0
0x1800461c6  lea     r8, [rsp+2F8h+pwszLanguagesBuffer]; pwszLanguagesBuffer
0x1800461ce  mov     [rsp+2F8h+pcchLanguagesBuffer], 100h
0x1800461d6  lea     rdx, [rsp+2F8h+pulNumLanguages]; pulNumLanguages
0x1800461db  mov     ecx, 8; dwFlags
0x1800461e0  call    cs:__imp_GetSystemPreferredUILanguages
0x1800461e6  test    eax, eax
0x1800461e8  jz      short loc_18004621C
0x1800461ea  cmp     [rsp+2F8h+pulNumLanguages], 0
0x1800461ef  jbe     short loc_18004621C
0x1800461f1  mov     r8d, 55h ; 'U'; cchLocaleName
0x1800461f7  lea     rdx, [rsp+2F8h+LocaleName]; lpLocaleName
0x1800461fc  lea     rcx, [rsp+2F8h+pwszLanguagesBuffer]; lpNameToResolve
0x180046204  call    cs:__imp_ResolveLocaleName
0x18004620a  test    eax, eax
0x18004620c  jle     short loc_18004621C
0x18004620e  lea     rcx, [rsp+2F8h+LocaleName]; unsigned __int16 *
0x180046213  call    ?_LocaleNameToLCIDNoCustomLocales@@YAKPEBGK@Z; _LocaleNameToLCIDNoCustomLocales(ushort const *,ulong)
0x180046218  test    eax, eax
0x18004621a  jnz     short loc_180046222
0x18004621c  call    cs:__imp_GetSystemDefaultLCID
0x180046222  mov     rcx, [rsp+2F8h+var_18]
0x18004622a  xor     rcx, rsp; StackCookie
0x18004622d  call    __security_check_cookie
0x180046232  add     rsp, 2F8h
0x180046239  retn
```
