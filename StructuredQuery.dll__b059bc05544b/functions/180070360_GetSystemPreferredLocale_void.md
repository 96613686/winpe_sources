# GetSystemPreferredLocale(void)

- ea: `0x180070360`
- end: `0x1800703fa`
- name: `?GetSystemPreferredLocale@@YAKXZ`
- size: `154`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180070290`

## callees

- `0x1800094d4`
- `0x18005daf0`
- `0x180070360`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x1800703dc`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x1800703dc`
- `api-ms-win-core-localization-l1-2-0!ResolveLocaleName` at `0x1800703c4`
- `api-ms-win-core-localization-l1-2-0!ResolveLocaleName` at `0x1800703c4`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x1800703a0`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x1800703a0`

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
0x180070360  sub     rsp, 2F8h
0x180070367  mov     rax, cs:__security_cookie
0x18007036e  xor     rax, rsp
0x180070371  mov     [rsp+2F8h+var_18], rax
0x180070379  lea     r9, [rsp+2F8h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x18007037e  mov     [rsp+2F8h+pulNumLanguages], 0
0x180070386  lea     r8, [rsp+2F8h+pwszLanguagesBuffer]; pwszLanguagesBuffer
0x18007038e  mov     [rsp+2F8h+pcchLanguagesBuffer], 100h
0x180070396  lea     rdx, [rsp+2F8h+pulNumLanguages]; pulNumLanguages
0x18007039b  mov     ecx, 8; dwFlags
0x1800703a0  call    cs:__imp_GetSystemPreferredUILanguages
0x1800703a6  test    eax, eax
0x1800703a8  jz      short loc_1800703DC
0x1800703aa  cmp     [rsp+2F8h+pulNumLanguages], 0
0x1800703af  jbe     short loc_1800703DC
0x1800703b1  mov     r8d, 55h ; 'U'; cchLocaleName
0x1800703b7  lea     rdx, [rsp+2F8h+LocaleName]; lpLocaleName
0x1800703bc  lea     rcx, [rsp+2F8h+pwszLanguagesBuffer]; lpNameToResolve
0x1800703c4  call    cs:__imp_ResolveLocaleName
0x1800703ca  test    eax, eax
0x1800703cc  jle     short loc_1800703DC
0x1800703ce  lea     rcx, [rsp+2F8h+LocaleName]; wchar_t *
0x1800703d3  call    ?_LocaleNameToLCIDNoCustomLocales@@YAKPEB_WK@Z; _LocaleNameToLCIDNoCustomLocales(wchar_t const *,ulong)
0x1800703d8  test    eax, eax
0x1800703da  jnz     short loc_1800703E2
0x1800703dc  call    cs:__imp_GetSystemDefaultLCID
0x1800703e2  mov     rcx, [rsp+2F8h+var_18]
0x1800703ea  xor     rcx, rsp; StackCookie
0x1800703ed  call    __security_check_cookie
0x1800703f2  add     rsp, 2F8h
0x1800703f9  retn
```
