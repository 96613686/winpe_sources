# CacheManager::LookupUrl(ushort const *,ulong,ushort const *,ushort * *,int *,ulong *,int *)

- ea: `0x180060c30`
- end: `0x180060e7b`
- name: `?LookupUrl@CacheManager@@UEAAJPEBGK0PEAPEAGPEAHPEAK2@Z`
- size: `587`
- prototype: `int(CacheManager *__hidden this, const unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned __int16 **, int *, unsigned int *, int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800117c0`
- `0x1800193e8`
- `0x18002ee38`
- `0x180060c30`
- `0x180060e84`
- `0x18006121c`
- `0x1800615b0`
- `0x1800a4270`
- `0x1800af0a4`
- `0x1800b99f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180060e2f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180060e2f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180060ca3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180060ca3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180060e0f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180060e0f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180060e1d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180060e1d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180060dd7`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180060dd7`
- `OLEAUT32!__imp_SysAllocString` at `0x180060d6a`
- `OLEAUT32!__imp_SysAllocString` at `0x180060d6a`

## string_xrefs

- `0x180060cda`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\cachemanager.cpp`
- `0x180060d84`: `onecoreuap\base\diagnosis\platform\notifications\platform\ui\cachemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CacheManager::LookupUrl(
        CacheManager *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        unsigned __int16 **a5,
        int *a6,
        unsigned int *a7,
        int *a8)
{
  RTL_SRWLOCK *v10; // r13
  CacheManager *v11; // rcx
  const unsigned __int16 *PrefixedUrl; // rax
  unsigned __int16 *v13; // rsi
  int UrlCacheEntryInfo; // ebx
  const OLECHAR *v15; // rcx
  unsigned __int16 *v16; // rdi
  const WCHAR *v17; // rcx
  BOOL v18; // eax
  HANDLE ProcessHeap; // rax
  _BYTE v23[32]; // [rsp+40h] [rbp-99h] BYREF
  OLECHAR *psz[3]; // [rsp+60h] [rbp-79h] BYREF
  unsigned __int64 v25; // [rsp+78h] [rbp-61h]
  _BYTE v26[32]; // [rsp+80h] [rbp-59h] BYREF
  struct _FILETIME v27; // [rsp+A0h] [rbp-39h] BYREF
  unsigned int v28; // [rsp+A8h] [rbp-31h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+3Fh]

  std::wstring::wstring(v23);
  std::wstring::wstring(psz);
  std::wstring::wstring(v26);
  v10 = (RTL_SRWLOCK *)((char *)this + 16);
  AcquireSRWLockShared((PSRWLOCK)this + 2);
  *a5 = 0;
  *a6 = 0;
  *a8 = 1;
  PrefixedUrl = CacheManager::GetPrefixedUrl(v11, a4, 0);
  v13 = (unsigned __int16 *)PrefixedUrl;
  if ( !PrefixedUrl )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1FD,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\cachemanager.cpp",
      (const char *)0x8007000ELL,
      a3);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_54d166b4b7773830bae608bc87214534_Traceguids, 2147942414LL);
LABEL_20:
    UrlCacheEntryInfo = 1;
    goto LABEL_21;
  }
  UrlCacheEntryInfo = CacheMetadataStorage::GetUrlCacheEntryInfo(
                        *((CacheMetadataStorage **)this + 11),
                        PrefixedUrl,
                        (struct CacheEntry *)v23);
  if ( UrlCacheEntryInfo >= 0 )
  {
    CacheManager::UpdateEntry(this, a2, a3, (struct CacheEntry *)v23);
    v15 = (const OLECHAR *)psz;
    if ( v25 > 7 )
      v15 = psz[0];
    v16 = SysAllocString(v15);
    if ( v16 )
    {
      v17 = (const WCHAR *)psz;
      if ( v25 > 7 )
        v17 = psz[0];
      v18 = PathFileExistsW(v17);
      *a8 = v18;
      if ( !v18 )
        UrlCacheEntryInfo = 1;
      if ( (unsigned int)CacheManager::IsCacheExpired((CacheManager *)a8, &v27) )
      {
        *a6 = 1;
        UrlCacheEntryInfo = 1;
      }
      *a5 = v16;
      *a7 = v28;
    }
    else
    {
      UrlCacheEntryInfo = -2147024882;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x207,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\cachemanager.cpp",
        (const char *)0x8007000ELL,
        a3);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_54d166b4b7773830bae608bc87214534_Traceguids, 2147942414LL);
    }
  }
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, v13);
  if ( UrlCacheEntryInfo < 0 )
    goto LABEL_20;
LABEL_21:
  ReleaseSRWLockShared(v10);
  std::pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>(v26);
  std::pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>(psz);
  std::pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>(v23);
  return (unsigned int)UrlCacheEntryInfo;
}

```

## disassembly

```asm
0x180060c30  mov     [rsp-8+arg_10], rbx
0x180060c35  push    rbp
0x180060c36  push    rsi
0x180060c37  push    rdi
0x180060c38  push    r12
0x180060c3a  push    r13
0x180060c3c  push    r14
0x180060c3e  push    r15
0x180060c40  lea     rbp, [rsp-7]
0x180060c45  sub     rsp, 0E0h
0x180060c4c  mov     rax, cs:__security_cookie
0x180060c53  xor     rax, rsp
0x180060c56  mov     [rbp+37h+var_40], rax
0x180060c5a  mov     rbx, r9
0x180060c5d  mov     [rsp+110h+var_F0], r8d; int
0x180060c62  mov     [rsp+110h+var_E8], rdx
0x180060c67  mov     rdi, rcx
0x180060c6a  mov     r15, [rbp+37h+arg_20]
0x180060c6e  mov     r14, [rbp+37h+arg_28]
0x180060c72  mov     r12, [rbp+37h+arg_30]
0x180060c76  mov     rsi, [rbp+37h+arg_38]
0x180060c7a  mov     [rsp+110h+var_E0], rsi
0x180060c7f  lea     rcx, [rsp+110h+var_D0]
0x180060c84  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180060c89  lea     rcx, [rbp+37h+psz]
0x180060c8d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180060c92  lea     rcx, [rbp+37h+var_90]
0x180060c96  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180060c9b  nop
0x180060c9c  lea     r13, [rdi+10h]
0x180060ca0  mov     rcx, r13; SRWLock
0x180060ca3  call    cs:__imp_AcquireSRWLockShared
0x180060ca9  mov     qword ptr [r15], 0
0x180060cb0  mov     dword ptr [r14], 0
0x180060cb7  mov     dword ptr [rsi], 1
0x180060cbd  xor     r8d, r8d; unsigned __int64 *
0x180060cc0  mov     rdx, rbx; unsigned __int16 *
0x180060cc3  call    ?GetPrefixedUrl@CacheManager@@AEAAPEAGPEBGPEA_K@Z; CacheManager::GetPrefixedUrl(ushort const *,unsigned __int64 *)
0x180060cc8  mov     rsi, rax
0x180060ccb  test    rax, rax
0x180060cce  jnz     short loc_180060D2A
0x180060cd0  mov     rcx, [rbp+3Fh]; this
0x180060cd4  mov     r9d, 8007000Eh; char *
0x180060cda  lea     r8, aOnecoreuapBase_64; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180060ce1  mov     edx, 1FDh; void *
0x180060ce6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180060ceb  lea     rax, WPP_GLOBAL_Control
0x180060cf2  mov     rcx, cs:WPP_GLOBAL_Control
0x180060cf9  cmp     rcx, rax
0x180060cfc  jz      loc_180060E27
0x180060d02  test    byte ptr [rcx+1Ch], 80h
0x180060d06  jz      loc_180060E27
0x180060d0c  lea     edx, [rsi+1Ah]
0x180060d0f  mov     r9d, 8007000Eh
0x180060d15  lea     r8, WPP_54d166b4b7773830bae608bc87214534_Traceguids
0x180060d1c  mov     rcx, [rcx+10h]
0x180060d20  call    WPP_SF_d
0x180060d25  jmp     loc_180060E27
0x180060d2a  lea     r8, [rsp+110h+var_D0]; struct CacheEntry *
0x180060d2f  mov     rdx, rsi; unsigned __int16 *
0x180060d32  mov     rcx, [rdi+58h]; this
0x180060d36  call    ?GetUrlCacheEntryInfo@CacheMetadataStorage@@QEAAJPEBGAEAVCacheEntry@@@Z; CacheMetadataStorage::GetUrlCacheEntryInfo(ushort const *,CacheEntry &)
0x180060d3b  mov     ebx, eax
0x180060d3d  test    eax, eax
0x180060d3f  js      loc_180060E0F
0x180060d45  lea     r9, [rsp+110h+var_D0]; struct CacheEntry *
0x180060d4a  mov     r8d, [rsp+110h+var_F0]; unsigned int
0x180060d4f  mov     rdx, [rsp+110h+var_E8]; unsigned __int16 *
0x180060d54  mov     rcx, rdi; this
0x180060d57  call    ?UpdateEntry@CacheManager@@AEAAXPEBGKPEAVCacheEntry@@@Z; CacheManager::UpdateEntry(ushort const *,ulong,CacheEntry *)
0x180060d5c  lea     rcx, [rbp+37h+psz]
0x180060d60  cmp     [rbp+37h+var_98], 7
0x180060d65  cmova   rcx, [rbp+37h+psz]; psz
0x180060d6a  call    cs:__imp_SysAllocString
0x180060d70  mov     rdi, rax
0x180060d73  test    rax, rax
0x180060d76  jnz     short loc_180060DC9
0x180060d78  mov     ebx, 8007000Eh
0x180060d7d  mov     rcx, [rbp+3Fh]; this
0x180060d81  mov     r9d, ebx; char *
0x180060d84  lea     r8, aOnecoreuapBase_64; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180060d8b  mov     edx, 207h; void *
0x180060d90  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180060d95  lea     rax, WPP_GLOBAL_Control
0x180060d9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180060da3  cmp     rcx, rax
0x180060da6  jz      short loc_180060E0F
0x180060da8  test    byte ptr [rcx+1Ch], 80h
0x180060dac  jz      short loc_180060E0F
0x180060dae  lea     edx, [rdi+1Bh]
0x180060db1  mov     r9d, 8007000Eh
0x180060db7  lea     r8, WPP_54d166b4b7773830bae608bc87214534_Traceguids
0x180060dbe  mov     rcx, [rcx+10h]
0x180060dc2  call    WPP_SF_d
0x180060dc7  jmp     short loc_180060E0F
0x180060dc9  lea     rcx, [rbp+37h+psz]
0x180060dcd  cmp     [rbp+37h+var_98], 7
0x180060dd2  cmova   rcx, [rbp+37h+psz]; pszPath
0x180060dd7  call    cs:__imp_PathFileExistsW
0x180060ddd  mov     rcx, [rsp+110h+var_E0]; this
0x180060de2  mov     [rcx], eax
0x180060de4  test    eax, eax
0x180060de6  mov     eax, 1
0x180060deb  cmovz   ebx, eax
0x180060dee  lea     rdx, [rbp+37h+var_70]; struct _FILETIME *
0x180060df2  call    ?IsCacheExpired@CacheManager@@AEAAHPEAU_FILETIME@@@Z; CacheManager::IsCacheExpired(_FILETIME *)
0x180060df7  test    eax, eax
0x180060df9  jz      short loc_180060E05
0x180060dfb  mov     eax, 1
0x180060e00  mov     [r14], eax
0x180060e03  mov     ebx, eax
0x180060e05  mov     [r15], rdi
0x180060e08  mov     eax, [rbp+37h+var_68]
0x180060e0b  mov     [r12], eax
0x180060e0f  call    cs:__imp_GetProcessHeap
0x180060e15  mov     rcx, rax; hHeap
0x180060e18  mov     r8, rsi; lpMem
0x180060e1b  xor     edx, edx; dwFlags
0x180060e1d  call    cs:__imp_HeapFree
0x180060e23  test    ebx, ebx
0x180060e25  jns     short loc_180060E2C
0x180060e27  mov     ebx, 1
0x180060e2c  mov     rcx, r13; SRWLock
0x180060e2f  call    cs:__imp_ReleaseSRWLockShared
0x180060e35  nop
0x180060e36  lea     rcx, [rbp+37h+var_90]; void *
0x180060e3a  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4__MIDL___MIDL_itf_wpntypes_0000_0000_0005@@@std@@QEAA@XZ; std::pair<std::wstring const,__MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,__MIDL___MIDL_itf_wpntypes_0000_0000_0005>(void)
0x180060e3f  lea     rcx, [rbp+37h+psz]; void *
0x180060e43  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4__MIDL___MIDL_itf_wpntypes_0000_0000_0005@@@std@@QEAA@XZ; std::pair<std::wstring const,__MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,__MIDL___MIDL_itf_wpntypes_0000_0000_0005>(void)
0x180060e48  lea     rcx, [rsp+110h+var_D0]; void *
0x180060e4d  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4__MIDL___MIDL_itf_wpntypes_0000_0000_0005@@@std@@QEAA@XZ; std::pair<std::wstring const,__MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,__MIDL___MIDL_itf_wpntypes_0000_0000_0005>(void)
0x180060e52  mov     eax, ebx
0x180060e54  mov     rcx, [rbp+37h+var_40]
0x180060e58  xor     rcx, rsp; StackCookie
0x180060e5b  call    __security_check_cookie
0x180060e60  mov     rbx, [rsp+110h+arg_10]
0x180060e68  add     rsp, 0E0h
0x180060e6f  pop     r15
0x180060e71  pop     r14
0x180060e73  pop     r13
0x180060e75  pop     r12
0x180060e77  pop     rdi
0x180060e78  pop     rsi
0x180060e79  pop     rbp
0x180060e7a  retn
```
