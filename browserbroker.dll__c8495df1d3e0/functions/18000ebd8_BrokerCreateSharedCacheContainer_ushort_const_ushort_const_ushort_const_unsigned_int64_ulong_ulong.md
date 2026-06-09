# BrokerCreateSharedCacheContainer(ushort const *,ushort const *,ushort const *,unsigned __int64,ulong,ulong)

- ea: `0x18000ebd8`
- end: `0x18000ed57`
- name: `?BrokerCreateSharedCacheContainer@@YAJPEBG00_KKK@Z`
- size: `383`
- prototype: `signed int __fastcall(PCWSTR pszPathIn, PCWSTR, const unsigned __int16 *, ULONGLONG, DWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800082e0`

## callees

- `0x180002ce0`
- `0x18000ebd8`
- `0x18000ed60`
- `0x18000ee44`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18000ec0f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18000ec23`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18000ec37`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18000ec4b`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18000ec0f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18000ec23`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18000ec37`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18000ec4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ed0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ed0b`
- `urlmon!__imp_GetIEBrowserModeFilterSpartanMediumILPath` at `0x18000ec94`
- `urlmon!__imp_GetIEBrowserModeFilterSpartanMediumILPath` at `0x18000ec94`
- `WININET!UrlCacheCreateContainer` at `0x18000ecdf`
- `WININET!UrlCacheCreateContainer` at `0x18000ed2b`
- `WININET!UrlCacheCreateContainer` at `0x18000ecdf`
- `WININET!UrlCacheCreateContainer` at `0x18000ed2b`
- `WININET!DeleteUrlCacheContainerW` at `0x18000ed01`
- `WININET!DeleteUrlCacheContainerW` at `0x18000ed01`

## string_xrefs

- `0x18000ec05`: `iecompat`
- `0x18000ec19`: `iecompatua`

## pseudocode

```c
signed int __fastcall BrokerCreateSharedCacheContainer(
        PCWSTR pszPathIn,
        PCWSTR a2,
        const unsigned __int16 *a3,
        ULONGLONG a4,
        DWORD a5)
{
  unsigned __int64 v8; // rdx
  DWORD dwOptions; // ebx
  signed int result; // eax
  unsigned __int64 v11; // rdx
  bool v12; // zf
  WCHAR pwszName[264]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR pwszDirectory[264]; // [rsp+240h] [rbp+140h] BYREF
  WCHAR pwszPrefix[264]; // [rsp+450h] [rbp+350h] BYREF

  if ( StrCmpICW(pszPathIn, L"iecompat")
    && StrCmpICW(pszPathIn, L"iecompatua")
    && StrCmpICW(pszPathIn, L"EmieSiteList")
    && StrCmpICW(pszPathIn, L"EmieUserList") )
  {
    dwOptions = a5;
  }
  else
  {
    dwOptions = a5 & 0xFFFFFCFF | 0x100;
  }
  result = CanonicalizeString(pszPathIn, v8, pwszName);
  if ( !result )
  {
    result = GetIEBrowserModeFilterSpartanMediumILPath(0, pwszName, pwszDirectory, 260);
    v12 = result == 0;
    if ( result >= 0 )
    {
      result = BrokerEnsureFileOrFolderExists(pwszDirectory, v11);
      v12 = result == 0;
    }
    if ( v12 )
    {
      result = CanonicalizeString(a2, v11, pwszPrefix);
      if ( !result )
      {
        result = UrlCacheCreateContainer(pwszName, pwszPrefix, pwszDirectory, a4, dwOptions);
        if ( result > 0 )
          result = (unsigned __int16)result | 0x80070000;
        if ( result == -2147024713 )
        {
          if ( !DeleteUrlCacheContainerW(pwszName, 0) )
            GetLastError();
          result = UrlCacheCreateContainer(pwszName, pwszPrefix, pwszDirectory, a4, dwOptions);
          if ( result > 0 )
            return (unsigned __int16)result | 0x80070000;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000ebd8  push    rbp
0x18000ebda  push    rbx
0x18000ebdb  push    rsi
0x18000ebdc  push    rdi
0x18000ebdd  push    r14
0x18000ebdf  lea     rbp, [rsp-570h]
0x18000ebe7  sub     rsp, 670h
0x18000ebee  mov     rax, cs:__security_cookie
0x18000ebf5  xor     rax, rsp
0x18000ebf8  mov     [rbp+590h+var_30], rax
0x18000ebff  mov     r14, rdx
0x18000ec02  mov     rsi, r9
0x18000ec05  lea     rdx, pszStr2; "iecompat"
0x18000ec0c  mov     rdi, rcx
0x18000ec0f  call    cs:__imp_StrCmpICW
0x18000ec15  test    eax, eax
0x18000ec17  jz      short loc_18000EC5D
0x18000ec19  lea     rdx, aIecompatua; "iecompatua"
0x18000ec20  mov     rcx, rdi; pszStr1
0x18000ec23  call    cs:__imp_StrCmpICW
0x18000ec29  test    eax, eax
0x18000ec2b  jz      short loc_18000EC5D
0x18000ec2d  lea     rdx, aEmiesitelist; "EmieSiteList"
0x18000ec34  mov     rcx, rdi; pszStr1
0x18000ec37  call    cs:__imp_StrCmpICW
0x18000ec3d  test    eax, eax
0x18000ec3f  jz      short loc_18000EC5D
0x18000ec41  lea     rdx, aEmieuserlist; "EmieUserList"
0x18000ec48  mov     rcx, rdi; pszStr1
0x18000ec4b  call    cs:__imp_StrCmpICW
0x18000ec51  test    eax, eax
0x18000ec53  jz      short loc_18000EC5D
0x18000ec55  mov     ebx, [rbp+590h+arg_20]
0x18000ec5b  jmp     short loc_18000EC6B
0x18000ec5d  mov     ebx, [rbp+590h+arg_20]
0x18000ec63  btr     ebx, 9
0x18000ec67  bts     ebx, 8
0x18000ec6b  lea     r8, [rsp+690h+pwszName]; unsigned __int16 *
0x18000ec70  mov     rcx, rdi; pszPathIn
0x18000ec73  call    ?CanonicalizeString@@YAJPEBG_KPEAG@Z; CanonicalizeString(ushort const *,unsigned __int64,ushort *)
0x18000ec78  test    eax, eax
0x18000ec7a  jnz     loc_18000ED3A
0x18000ec80  mov     r9d, 104h
0x18000ec86  lea     r8, [rbp+590h+pwszDirectory]
0x18000ec8d  lea     rdx, [rsp+690h+pwszName]
0x18000ec92  xor     ecx, ecx
0x18000ec94  call    cs:__imp_GetIEBrowserModeFilterSpartanMediumILPath
0x18000ec9a  test    eax, eax
0x18000ec9c  js      short loc_18000ECAC
0x18000ec9e  lea     rcx, [rbp+590h+pwszDirectory]; lpFileName
0x18000eca5  call    ?BrokerEnsureFileOrFolderExists@@YAJPEBG_N@Z; BrokerEnsureFileOrFolderExists(ushort const *,bool)
0x18000ecaa  test    eax, eax
0x18000ecac  jnz     loc_18000ED3A
0x18000ecb2  lea     r8, [rbp+590h+pwszPrefix]; unsigned __int16 *
0x18000ecb9  mov     rcx, r14; pszPathIn
0x18000ecbc  call    ?CanonicalizeString@@YAJPEBG_KPEAG@Z; CanonicalizeString(ushort const *,unsigned __int64,ushort *)
0x18000ecc1  test    eax, eax
0x18000ecc3  jnz     short loc_18000ED3A
0x18000ecc5  mov     r9, rsi; ullLimit
0x18000ecc8  mov     [rsp+690h+dwOptions], ebx; dwOptions
0x18000eccc  lea     r8, [rbp+590h+pwszDirectory]; pwszDirectory
0x18000ecd3  lea     rdx, [rbp+590h+pwszPrefix]; pwszPrefix
0x18000ecda  lea     rcx, [rsp+690h+pwszName]; pwszName
0x18000ecdf  call    cs:__imp_UrlCacheCreateContainer
0x18000ece5  mov     edi, 80070000h
0x18000ecea  test    eax, eax
0x18000ecec  jle     short loc_18000ECF3
0x18000ecee  movzx   eax, ax
0x18000ecf1  or      eax, edi
0x18000ecf3  cmp     eax, 800700B7h
0x18000ecf8  jnz     short loc_18000ED3A
0x18000ecfa  xor     edx, edx; dwOptions
0x18000ecfc  lea     rcx, [rsp+690h+pwszName]; Name
0x18000ed01  call    cs:__imp_DeleteUrlCacheContainerW
0x18000ed07  test    eax, eax
0x18000ed09  jnz     short loc_18000ED11
0x18000ed0b  call    cs:__imp_GetLastError
0x18000ed11  mov     r9, rsi; ullLimit
0x18000ed14  mov     [rsp+690h+dwOptions], ebx; dwOptions
0x18000ed18  lea     r8, [rbp+590h+pwszDirectory]; pwszDirectory
0x18000ed1f  lea     rdx, [rbp+590h+pwszPrefix]; pwszPrefix
0x18000ed26  lea     rcx, [rsp+690h+pwszName]; pwszName
0x18000ed2b  call    cs:__imp_UrlCacheCreateContainer
0x18000ed31  test    eax, eax
0x18000ed33  jle     short loc_18000ED3A
0x18000ed35  movzx   eax, ax
0x18000ed38  or      eax, edi
0x18000ed3a  mov     rcx, [rbp+590h+var_30]
0x18000ed41  xor     rcx, rsp; StackCookie
0x18000ed44  call    __security_check_cookie
0x18000ed49  add     rsp, 670h
0x18000ed50  pop     r14
0x18000ed52  pop     rdi
0x18000ed53  pop     rsi
0x18000ed54  pop     rbx
0x18000ed55  pop     rbp
0x18000ed56  retn
```
