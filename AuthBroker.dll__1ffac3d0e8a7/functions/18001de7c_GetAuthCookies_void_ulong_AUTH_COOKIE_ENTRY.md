# GetAuthCookies(void *,ulong *,_AUTH_COOKIE_ENTRY * *)

- ea: `0x18001de7c`
- end: `0x18001e05b`
- name: `?GetAuthCookies@@YAJPEAXPEAKPEAPEAU_AUTH_COOKIE_ENTRY@@@Z`
- size: `479`
- prototype: `__int64 __fastcall(void *clientTokenHandle, unsigned int *cookieCount, _AUTH_COOKIE_ENTRY **cookieEntry)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001449c`

## callees

- `0x18001de7c`
- `0x18001e210`
- `0x18001e54c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001df97`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001df97`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001dffa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e03b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001dffa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e03b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ded6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001dfc6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ded6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001dfc6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001df3b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001df3b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e02c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e02c`

## pseudocode

```c
__int64 __fastcall GetAuthCookies(void *clientTokenHandle, unsigned int *cookieCount, _AUTH_COOKIE_ENTRY **cookieEntry)
{
  wchar_t *v6; // rsi
  LSTATUS v7; // eax
  signed int SubKeyInfo; // ebx
  DWORD i; // r14d
  LSTATUS v10; // eax
  LSTATUS v11; // eax
  int ProviderCookies; // eax
  unsigned int entryCount; // [rsp+40h] [rbp-20h] BYREF
  HKEY__ *rootKey; // [rsp+48h] [rbp-18h] BYREF
  HKEY__ *providerKey; // [rsp+50h] [rbp-10h] BYREF
  _AUTH_COOKIE_ENTRY *entry; // [rsp+58h] [rbp-8h] BYREF
  unsigned int providerCount; // [rsp+A8h] [rbp+48h] BYREF
  unsigned int maxProviderSubKeyNameLength; // [rsp+B0h] [rbp+50h] BYREF
  unsigned int providerSubKeyNameLength; // [rsp+B8h] [rbp+58h] BYREF

  *cookieCount = 0;
  *cookieEntry = 0;
  rootKey = 0;
  providerCount = 0;
  maxProviderSubKeyNameLength = 0;
  entryCount = 0;
  entry = 0;
  v6 = 0;
  v7 = RegOpenKeyExW(HKEY_CURRENT_USER, L"SOFTWARE\\Microsoft\\AuthCookies", 0, 0x20019u, &rootKey);
  SubKeyInfo = v7;
  if ( v7 )
  {
    if ( v7 != 2 )
    {
      if ( v7 > 0 )
        SubKeyInfo = (unsigned __int16)v7 | 0x80070000;
      goto $Exit_20;
    }
LABEL_28:
    SubKeyInfo = 0;
    goto $Exit_20;
  }
  SubKeyInfo = GetSubKeyInfo(rootKey, &providerCount, &maxProviderSubKeyNameLength);
  if ( SubKeyInfo >= 0 && providerCount && maxProviderSubKeyNameLength )
  {
    v6 = (wchar_t *)LocalAlloc(0x40u, 2LL * (maxProviderSubKeyNameLength + 1));
    if ( !v6 )
    {
      SubKeyInfo = -2147024882;
      goto $Exit_20;
    }
    SubKeyInfo = 0;
    for ( i = 0; i < providerCount; ++i )
    {
      providerSubKeyNameLength = maxProviderSubKeyNameLength + 1;
      providerKey = 0;
      v10 = RegEnumKeyExW(rootKey, i, v6, &providerSubKeyNameLength, 0, 0, 0, 0);
      if ( v10 )
      {
        if ( v10 > 0 )
          SubKeyInfo = (unsigned __int16)v10 | 0x80070000;
        else
          SubKeyInfo = v10;
        break;
      }
      if ( providerSubKeyNameLength && *v6 )
      {
        v11 = RegOpenKeyExW(rootKey, v6, 0, 0x20019u, &providerKey);
        if ( v11 )
        {
          if ( v11 > 0 )
            SubKeyInfo = (unsigned __int16)v11 | 0x80070000;
          else
            SubKeyInfo = v11;
        }
        else
        {
          ProviderCookies = GetProviderCookies(clientTokenHandle, providerKey, &entryCount, &entry);
          if ( ProviderCookies < 0 )
            SubKeyInfo = ProviderCookies;
          RegCloseKey(providerKey);
        }
      }
    }
    if ( entryCount )
    {
      *cookieCount = entryCount;
      *cookieEntry = entry;
      goto LABEL_28;
    }
  }
$Exit_20:
  LocalFree(v6);
  if ( rootKey )
    RegCloseKey(rootKey);
  return (unsigned int)SubKeyInfo;
}

```

## disassembly

```asm
0x18001de7c  mov     [rsp-38h+arg_0], rbx
0x18001de81  push    rbp
0x18001de82  push    rsi
0x18001de83  push    rdi
0x18001de84  push    r12
0x18001de86  push    r13
0x18001de88  push    r14
0x18001de8a  push    r15
0x18001de8c  mov     rbp, rsp
0x18001de8f  sub     rsp, 60h
0x18001de93  xor     edi, edi
0x18001de95  lea     rax, [rbp+rootKey]
0x18001de99  mov     [cookieCount], edi
0x18001de9b  mov     r15, cookieEntry
0x18001de9e  mov     [cookieEntry], rdi
0x18001dea1  mov     r12, cookieCount
0x18001dea4  mov     r13, clientTokenHandle
0x18001dea7  mov     [rbp+rootKey], rdi
0x18001deab  xor     r8d, r8d; ulOptions
0x18001deae  mov     [rbp+providerCount], edi
0x18001deb1  lea     cookieCount, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\AuthCookies"
0x18001deb8  mov     [rbp+maxProviderSubKeyNameLength], edi
0x18001debb  mov     r9d, 20019h; samDesired
0x18001dec1  mov     [rbp+entryCount], edi
0x18001dec4  mov     clientTokenHandle, 0FFFFFFFF80000001h; hKey
0x18001decb  mov     [rbp+entry], rdi
0x18001decf  mov     esi, edi
0x18001ded1  mov     [rsp+60h+phkResult], rax; phkResult
0x18001ded6  call    cs:__imp_RegOpenKeyExW
0x18001dedc  mov     ebx, eax
0x18001dede  test    eax, eax
0x18001dee0  jz      short loc_18001DF01
0x18001dee2  cmp     eax, 2
0x18001dee5  jz      loc_18001E027
0x18001deeb  test    eax, eax
0x18001deed  jle     $Exit_20
0x18001def3  movzx   ebx, ax
0x18001def6  or      ebx, 80070000h
0x18001defc  jmp     $Exit_20
0x18001df01  mov     clientTokenHandle, [rbp+rootKey]; key
0x18001df05  lea     cookieEntry, [rbp+maxProviderSubKeyNameLength]; maxSubKeyNameLength
0x18001df09  lea     cookieCount, [rbp+providerCount]; subKeyCount
0x18001df0d  call    _GetSubKeyInfo
0x18001df12  mov     ebx, eax
0x18001df14  test    eax, eax
0x18001df16  js      $Exit_20
0x18001df1c  cmp     [rbp+providerCount], edi
0x18001df1f  jz      $Exit_20
0x18001df25  mov     eax, [rbp+maxProviderSubKeyNameLength]
0x18001df28  test    eax, eax
0x18001df2a  jz      $Exit_20
0x18001df30  lea     edx, [rax+1]
0x18001df33  mov     ecx, 40h ; '@'; uFlags
0x18001df38  add     cookieCount, cookieCount; uBytes
0x18001df3b  call    cs:__imp_LocalAlloc
0x18001df41  mov     rsi, rax
0x18001df44  test    rax, rax
0x18001df47  jnz     short loc_18001DF53
0x18001df49  mov     ebx, 8007000Eh
0x18001df4e  jmp     $Exit_20
0x18001df53  mov     ebx, edi
0x18001df55  mov     r14d, edi
0x18001df58  mov     edi, 80070000h
0x18001df5d  cmp     r14d, [rbp+providerCount]
0x18001df61  jnb     loc_18001E013
0x18001df67  mov     eax, [rbp+maxProviderSubKeyNameLength]
0x18001df6a  lea     r9, [rbp+providerSubKeyNameLength]; lpcchName
0x18001df6e  mov     clientTokenHandle, [rbp+rootKey]; hKey
0x18001df72  inc     eax
0x18001df74  mov     [rbp+providerSubKeyNameLength], eax
0x18001df77  mov     cookieEntry, rsi; lpName
0x18001df7a  xor     eax, eax
0x18001df7c  mov     edx, r14d; dwIndex
0x18001df7f  mov     [rsp+60h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18001df84  mov     [rsp+60h+lpcchClass], rax; lpcchClass
0x18001df89  mov     [rsp+60h+lpClass], rax; lpClass
0x18001df8e  mov     [rsp+60h+phkResult], rax; lpReserved
0x18001df93  mov     [rbp+providerKey], rax
0x18001df97  call    cs:__imp_RegEnumKeyExW
0x18001df9d  xor     ecx, ecx
0x18001df9f  test    eax, eax
0x18001dfa1  jnz     short loc_18001E008
0x18001dfa3  cmp     [rbp+providerSubKeyNameLength], ecx
0x18001dfa6  jz      short loc_18001E000
0x18001dfa8  cmp     [rsi], cx
0x18001dfab  jz      short loc_18001E000
0x18001dfad  mov     clientTokenHandle, [rbp+rootKey]; hKey
0x18001dfb1  lea     rax, [rbp+providerKey]
0x18001dfb5  mov     r9d, 20019h; samDesired
0x18001dfbb  mov     [rsp+60h+phkResult], rax; phkResult
0x18001dfc0  xor     r8d, r8d; ulOptions
0x18001dfc3  mov     cookieCount, rsi; lpSubKey
0x18001dfc6  call    cs:__imp_RegOpenKeyExW
0x18001dfcc  test    eax, eax
0x18001dfce  jz      short loc_18001DFDD
0x18001dfd0  jg      short loc_18001DFD6
0x18001dfd2  mov     ebx, eax
0x18001dfd4  jmp     short loc_18001E000
0x18001dfd6  movzx   ebx, ax
0x18001dfd9  or      ebx, edi
0x18001dfdb  jmp     short loc_18001E000
0x18001dfdd  mov     cookieCount, [rbp+providerKey]; providerKey
0x18001dfe1  lea     r9, [rbp+entry]; cookieEntry
0x18001dfe5  lea     cookieEntry, [rbp+entryCount]; cookieCount
0x18001dfe9  mov     clientTokenHandle, r13; clientTokenHandle
0x18001dfec  call    _GetProviderCookies
0x18001dff1  mov     clientTokenHandle, [rbp+providerKey]; hKey
0x18001dff5  test    eax, eax
0x18001dff7  cmovs   ebx, eax
0x18001dffa  call    cs:__imp_RegCloseKey
0x18001e000  inc     r14d
0x18001e003  jmp     loc_18001DF5D
0x18001e008  jg      short loc_18001E00E
0x18001e00a  mov     ebx, eax
0x18001e00c  jmp     short loc_18001E013
0x18001e00e  movzx   ebx, ax
0x18001e011  or      ebx, edi
0x18001e013  mov     eax, [rbp+entryCount]
0x18001e016  xor     edi, edi
0x18001e018  test    eax, eax
0x18001e01a  jz      short $Exit_20
0x18001e01c  mov     [r12], eax
0x18001e020  mov     rax, [rbp+entry]
0x18001e024  mov     [r15], rax
0x18001e027  mov     ebx, edi
0x18001e029  mov     clientTokenHandle, rsi; hMem
0x18001e02c  call    cs:__imp_LocalFree
0x18001e032  mov     clientTokenHandle, [rbp+rootKey]; hKey
0x18001e036  test    clientTokenHandle, clientTokenHandle
0x18001e039  jz      short loc_18001E041
0x18001e03b  call    cs:__imp_RegCloseKey
0x18001e041  mov     eax, ebx
0x18001e043  mov     rbx, [rsp+60h+arg_0]
0x18001e04b  add     rsp, 60h
0x18001e04f  pop     r15
0x18001e051  pop     r14
0x18001e053  pop     r13
0x18001e055  pop     r12
0x18001e057  pop     rdi
0x18001e058  pop     rsi
0x18001e059  pop     rbp
0x18001e05a  retn
```
