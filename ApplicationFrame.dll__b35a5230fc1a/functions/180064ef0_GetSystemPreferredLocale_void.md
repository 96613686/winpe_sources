# GetSystemPreferredLocale(void)

- ea: `0x180064ef0`
- end: `0x180064f9b`
- name: `?GetSystemPreferredLocale@@YAKXZ`
- size: `171`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180064e20`

## callees

- `0x180043c30`
- `0x180064ef0`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x180064f65`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x180064f65`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x180064f30`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x180064f30`
- `api-ms-win-core-localization-l1-2-0!ResolveLocaleName` at `0x180064f54`
- `api-ms-win-core-localization-l1-2-0!ResolveLocaleName` at `0x180064f54`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x180064f7d`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x180064f7d`

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
0x180064ef0  sub     rsp, 2F8h
0x180064ef7  mov     rax, cs:__security_cookie
0x180064efe  xor     rax, rsp
0x180064f01  mov     [rsp+2F8h+var_18], rax
0x180064f09  lea     r9, [rsp+2F8h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x180064f0e  mov     [rsp+2F8h+pulNumLanguages], 0
0x180064f16  lea     r8, [rsp+2F8h+pwszLanguagesBuffer]; pwszLanguagesBuffer
0x180064f1e  mov     [rsp+2F8h+pcchLanguagesBuffer], 100h
0x180064f26  lea     rdx, [rsp+2F8h+pulNumLanguages]; pulNumLanguages
0x180064f2b  mov     ecx, 8; dwFlags
0x180064f30  call    cs:__imp_GetSystemPreferredUILanguages
0x180064f36  test    eax, eax
0x180064f38  jz      short loc_180064F7D
0x180064f3a  cmp     [rsp+2F8h+pulNumLanguages], 0
0x180064f3f  jbe     short loc_180064F7D
0x180064f41  mov     r8d, 55h ; 'U'; cchLocaleName
0x180064f47  lea     rdx, [rsp+2F8h+LocaleName]; lpLocaleName
0x180064f4c  lea     rcx, [rsp+2F8h+pwszLanguagesBuffer]; lpNameToResolve
0x180064f54  call    cs:__imp_ResolveLocaleName
0x180064f5a  test    eax, eax
0x180064f5c  jle     short loc_180064F7D
0x180064f5e  xor     edx, edx; dwFlags
0x180064f60  lea     rcx, [rsp+2F8h+LocaleName]; lpName
0x180064f65  call    cs:__imp_LocaleNameToLCID
0x180064f6b  cmp     eax, 1000h
0x180064f70  jnz     short loc_180064F79
0x180064f72  mov     eax, 7Fh
0x180064f77  jmp     short loc_180064F83
0x180064f79  test    eax, eax
0x180064f7b  jnz     short loc_180064F83
0x180064f7d  call    cs:__imp_GetSystemDefaultLCID
0x180064f83  mov     rcx, [rsp+2F8h+var_18]
0x180064f8b  xor     rcx, rsp; StackCookie
0x180064f8e  call    __security_check_cookie
0x180064f93  add     rsp, 2F8h
0x180064f9a  retn
```
