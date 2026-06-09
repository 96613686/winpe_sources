# PiiSafeShellitemParsingNameHelpers::GetDriveTypeFromPath(ushort const *)

- ea: `0x180073c4c`
- end: `0x180073d0b`
- name: `?GetDriveTypeFromPath@PiiSafeShellitemParsingNameHelpers@@YAIPEBG@Z`
- size: `191`
- prototype: `unsigned int __fastcall(PiiSafeShellitemParsingNameHelpers *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path`

## callers

- `0x180073b94`

## callees

- `0x18001bf68`
- `0x180037780`
- `0x180038708`
- `0x180073c4c`
- `0x180077f60`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180073cdc`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180073cdc`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x180073cd1`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x180073cd1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripToRootW` at `0x180073cb0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripToRootW` at `0x180073cb0`

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
      if ( (int)StringCchCopyW(pszPath, 0x104u, (const unsigned __int16 *)this) >= 0 )
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
0x180073c4c  mov     [rsp+arg_8], rbx
0x180073c51  mov     [rsp+arg_10], rsi
0x180073c56  push    rdi
0x180073c57  sub     rsp, 240h
0x180073c5e  mov     rax, cs:__security_cookie
0x180073c65  xor     rax, rsp
0x180073c68  mov     [rsp+248h+var_18], rax
0x180073c70  xor     esi, esi
0x180073c72  mov     rbx, rcx
0x180073c75  mov     edi, esi
0x180073c77  test    rcx, rcx
0x180073c7a  jz      short loc_180073CE4
0x180073c7c  cmp     [rcx], si
0x180073c7f  jz      short loc_180073CE4
0x180073c81  xor     edx, edx; Val
0x180073c83  lea     rcx, [rsp+248h+pszPath]; void *
0x180073c88  mov     r8d, 208h; Size
0x180073c8e  call    memset_0
0x180073c93  mov     r8, rbx; unsigned __int16 *
0x180073c96  lea     rcx, [rsp+248h+pszPath]; unsigned __int16 *
0x180073c9b  mov     ebx, 104h
0x180073ca0  mov     edx, ebx; unsigned __int64
0x180073ca2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180073ca7  test    eax, eax
0x180073ca9  js      short loc_180073CE4
0x180073cab  lea     rcx, [rsp+248h+pszPath]; pszPath
0x180073cb0  call    cs:__imp_PathStripToRootW
0x180073cb6  test    eax, eax
0x180073cb8  jz      short loc_180073CE4
0x180073cba  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_60851339@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_60851339@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60851339> `wil::Feature<__WilFeatureTraits_Feature_60851339>::GetImpl(void)'::`2'::impl
0x180073cc1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_60851339@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60851339>::__private_IsEnabled(void)
0x180073cc6  test    al, al
0x180073cc8  jz      short loc_180073CD7
0x180073cca  mov     edx, ebx; cchPath
0x180073ccc  lea     rcx, [rsp+248h+pszPath]; pszPath
0x180073cd1  call    cs:__imp_PathCchAddBackslash
0x180073cd7  lea     rcx, [rsp+248h+pszPath]; lpRootPathName
0x180073cdc  call    cs:__imp_GetDriveTypeW
0x180073ce2  mov     edi, eax
0x180073ce4  mov     eax, edi
0x180073ce6  mov     rcx, [rsp+248h+var_18]
0x180073cee  xor     rcx, rsp; StackCookie
0x180073cf1  call    __security_check_cookie
0x180073cf6  lea     r11, [rsp+248h+var_8]
0x180073cfe  mov     rbx, [r11+18h]
0x180073d02  mov     rsi, [r11+20h]
0x180073d06  mov     rsp, r11
0x180073d09  pop     rdi
0x180073d0a  retn
```
