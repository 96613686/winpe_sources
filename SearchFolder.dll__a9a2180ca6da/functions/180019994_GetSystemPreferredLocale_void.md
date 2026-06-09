# GetSystemPreferredLocale(void)

- ea: `0x180019994`
- end: `0x180019a3f`
- name: `?GetSystemPreferredLocale@@YAKXZ`
- size: `171`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800198c4`

## callees

- `0x180006900`
- `0x180019994`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x1800199d4`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x1800199d4`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x180019a21`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x180019a21`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x180019a09`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x180019a09`
- `api-ms-win-core-localization-l1-2-0!ResolveLocaleName` at `0x1800199f8`
- `api-ms-win-core-localization-l1-2-0!ResolveLocaleName` at `0x1800199f8`

## pseudocode

```c
unsigned int GetSystemPreferredLocale(void)
{
  unsigned int result; // eax
  ULONG pulNumLanguages; // [rsp+20h] [rbp-2D8h] BYREF
  ULONG pcchLanguagesBuffer[3]; // [rsp+24h] [rbp-2D4h] BYREF
  WCHAR LocaleName[88]; // [rsp+30h] [rbp-2C8h] BYREF
  WCHAR pwszLanguagesBuffer[256]; // [rsp+E0h] [rbp-218h] BYREF

  pulNumLanguages = 0;
  pcchLanguagesBuffer[0] = 256;
  if ( !GetSystemPreferredUILanguages(8u, &pulNumLanguages, pwszLanguagesBuffer, pcchLanguagesBuffer)
    || !pulNumLanguages
    || ResolveLocaleName(pwszLanguagesBuffer, LocaleName, 85) <= 0 )
  {
    return GetSystemDefaultLCID();
  }
  result = LocaleNameToLCID(LocaleName, 0);
  if ( result == 4096 )
    return 127;
  if ( !result )
    return GetSystemDefaultLCID();
  return result;
}

```

## disassembly

```asm
0x180019994  sub     rsp, 2F8h
0x18001999b  mov     rax, cs:__security_cookie
0x1800199a2  xor     rax, rsp
0x1800199a5  mov     [rsp+2F8h+var_18], rax
0x1800199ad  lea     r9, [rsp+2F8h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x1800199b2  mov     [rsp+2F8h+pulNumLanguages], 0
0x1800199ba  lea     r8, [rsp+2F8h+pwszLanguagesBuffer]; pwszLanguagesBuffer
0x1800199c2  mov     [rsp+2F8h+pcchLanguagesBuffer], 100h
0x1800199ca  lea     rdx, [rsp+2F8h+pulNumLanguages]; pulNumLanguages
0x1800199cf  mov     ecx, 8; dwFlags
0x1800199d4  call    cs:__imp_GetSystemPreferredUILanguages
0x1800199da  test    eax, eax
0x1800199dc  jz      short loc_180019A21
0x1800199de  cmp     [rsp+2F8h+pulNumLanguages], 0
0x1800199e3  jbe     short loc_180019A21
0x1800199e5  mov     r8d, 55h ; 'U'; cchLocaleName
0x1800199eb  lea     rdx, [rsp+2F8h+LocaleName]; lpLocaleName
0x1800199f0  lea     rcx, [rsp+2F8h+pwszLanguagesBuffer]; lpNameToResolve
0x1800199f8  call    cs:__imp_ResolveLocaleName
0x1800199fe  test    eax, eax
0x180019a00  jle     short loc_180019A21
0x180019a02  xor     edx, edx; dwFlags
0x180019a04  lea     rcx, [rsp+2F8h+LocaleName]; lpName
0x180019a09  call    cs:__imp_LocaleNameToLCID
0x180019a0f  cmp     eax, 1000h
0x180019a14  jnz     short loc_180019A1D
0x180019a16  mov     eax, 7Fh
0x180019a1b  jmp     short loc_180019A27
0x180019a1d  test    eax, eax
0x180019a1f  jnz     short loc_180019A27
0x180019a21  call    cs:__imp_GetSystemDefaultLCID
0x180019a27  mov     rcx, [rsp+2F8h+var_18]
0x180019a2f  xor     rcx, rsp; StackCookie
0x180019a32  call    __security_check_cookie
0x180019a37  add     rsp, 2F8h
0x180019a3e  retn
```
