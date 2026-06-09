# PiiSafeShellitemParsingNameHelpers::GetDriveTypeFromPath(ushort const *)

- ea: `0x180018428`
- end: `0x1800184e7`
- name: `?GetDriveTypeFromPath@PiiSafeShellitemParsingNameHelpers@@YAIPEBG@Z`
- size: `191`
- prototype: `unsigned int __fastcall(PiiSafeShellitemParsingNameHelpers *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path`

## callers

- `0x180018370`

## callees

- `0x180006900`
- `0x1800076dc`
- `0x18000ecc4`
- `0x180018428`
- `0x180021550`

## import_xrefs

- `SHLWAPI!PathStripToRootW` at `0x18001848c`
- `SHLWAPI!PathStripToRootW` at `0x18001848c`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800184b8`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800184b8`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x1800184ad`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x1800184ad`

## pseudocode

```c
__int64 __fastcall PiiSafeShellitemParsingNameHelpers::GetDriveTypeFromPath(
        PiiSafeShellitemParsingNameHelpers *this,
        const unsigned __int16 *a2)
{
  unsigned int v3; // edi
  WCHAR pszPath[264]; // [rsp+20h] [rbp-228h] BYREF

  v3 = 0;
  if ( this )
  {
    if ( *(_WORD *)this )
    {
      memset_0(pszPath, 0, 0x208u);
      if ( StringCchCopyW(pszPath, 0x104u, (const unsigned __int16 *)this) >= 0 )
      {
        if ( PathStripToRootW(pszPath) )
        {
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60851339>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60851339>::GetImpl'::`2'::impl) )
            PathCchAddBackslash(pszPath, 0x104u);
          return GetDriveTypeW(pszPath);
        }
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180018428  mov     [rsp+arg_8], rbx
0x18001842d  mov     [rsp+arg_10], rsi
0x180018432  push    rdi
0x180018433  sub     rsp, 240h
0x18001843a  mov     rax, cs:__security_cookie
0x180018441  xor     rax, rsp
0x180018444  mov     [rsp+248h+var_18], rax
0x18001844c  xor     esi, esi
0x18001844e  mov     rbx, rcx
0x180018451  mov     edi, esi
0x180018453  test    rcx, rcx
0x180018456  jz      short loc_1800184C0
0x180018458  cmp     [rcx], si
0x18001845b  jz      short loc_1800184C0
0x18001845d  xor     edx, edx; Val
0x18001845f  lea     rcx, [rsp+248h+pszPath]; void *
0x180018464  mov     r8d, 208h; Size
0x18001846a  call    memset_0
0x18001846f  mov     r8, rbx; unsigned __int16 *
0x180018472  lea     rcx, [rsp+248h+pszPath]; unsigned __int16 *
0x180018477  mov     ebx, 104h
0x18001847c  mov     edx, ebx; unsigned __int64
0x18001847e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180018483  test    eax, eax
0x180018485  js      short loc_1800184C0
0x180018487  lea     rcx, [rsp+248h+pszPath]; pszPath
0x18001848c  call    cs:__imp_PathStripToRootW
0x180018492  test    eax, eax
0x180018494  jz      short loc_1800184C0
0x180018496  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_60851339@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_60851339@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60851339> `wil::Feature<__WilFeatureTraits_Feature_60851339>::GetImpl(void)'::`2'::impl
0x18001849d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_60851339@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60851339>::__private_IsEnabled(void)
0x1800184a2  test    al, al
0x1800184a4  jz      short loc_1800184B3
0x1800184a6  mov     edx, ebx; cchPath
0x1800184a8  lea     rcx, [rsp+248h+pszPath]; pszPath
0x1800184ad  call    cs:__imp_PathCchAddBackslash
0x1800184b3  lea     rcx, [rsp+248h+pszPath]; lpRootPathName
0x1800184b8  call    cs:__imp_GetDriveTypeW
0x1800184be  mov     edi, eax
0x1800184c0  mov     eax, edi
0x1800184c2  mov     rcx, [rsp+248h+var_18]
0x1800184ca  xor     rcx, rsp; StackCookie
0x1800184cd  call    __security_check_cookie
0x1800184d2  lea     r11, [rsp+248h+var_8]
0x1800184da  mov     rbx, [r11+18h]
0x1800184de  mov     rsi, [r11+20h]
0x1800184e2  mov     rsp, r11
0x1800184e5  pop     rdi
0x1800184e6  retn
```
