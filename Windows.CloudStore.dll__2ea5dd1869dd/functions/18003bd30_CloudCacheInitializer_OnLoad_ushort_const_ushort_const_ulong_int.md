# CloudCacheInitializer::OnLoad(ushort const *,ushort const *,ulong,int)

- ea: `0x18003bd30`
- end: `0x18003be42`
- name: `?OnLoad@CloudCacheInitializer@@UEAAJPEBG0KH@Z`
- size: `274`
- prototype: `int(CloudCacheInitializer *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18003bb7c`
- `0x18003bd30`
- `0x18003be48`
- `0x18003c340`
- `0x1800c8458`
- `0x1800e93e0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003bda9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003bde9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003be16`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003bda9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003bde9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003be16`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003bd68`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003bd68`

## string_xrefs

- `0x18003bdce`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`
- `0x18003bdfb`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`
- `0x18003be23`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`

## pseudocode

```c
__int64 __fastcall CloudCacheInitializer::OnLoad(
        CloudCacheInitializer *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4)
{
  int v7; // eax
  int v8; // eax
  const char *v9; // r9
  unsigned int v10; // ebx
  __int64 result; // rax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-28h]
  WCHAR *lpString1; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  try
  {
    CloudCacheInitializer::GetCurrentThreadUserStringSid();
    if ( CompareStringOrdinal(lpString1, -1, a2, -1, 1) == 2 )
    {
      v7 = CloudCacheInitializer::EnsureSysprepDataCleaned();
      if ( v7 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xD2,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
          (const char *)(unsigned int)v7,
          bIgnoreCase);
      v8 = CloudCacheInitializer::EnsureCacheInitialized(this, a2, a4, 3);
      v10 = v8;
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD3,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
          (const char *)(unsigned int)v8,
          bIgnoreCase);
        if ( lpString1 )
          LocalFree(lpString1);
        result = v10;
      }
      else
      {
        if ( lpString1 )
          LocalFree(lpString1);
        result = 0;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD0,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
        (const char *)0x8007051DLL,
        bIgnoreCase);
      if ( lpString1 )
        LocalFree(lpString1);
      result = 2147943709LL;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xDC,
                           (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
                           v9);
  }
  return result;
}

```

## disassembly

```asm
0x18003bd30  mov     [rsp+arg_0], rbx
0x18003bd35  mov     [rsp+arg_8], rsi
0x18003bd3a  push    rdi
0x18003bd3b  sub     rsp, 40h
0x18003bd3f  mov     edi, r9d
0x18003bd42  mov     rbx, rdx
0x18003bd45  mov     rsi, rcx
0x18003bd48  lea     rcx, [rsp+48h+lpString1]
0x18003bd4d  call    ?GetCurrentThreadUserStringSid@CloudCacheInitializer@@CA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; CloudCacheInitializer::GetCurrentThreadUserStringSid(void)
0x18003bd52  mov     [rsp+48h+bIgnoreCase], 1; int
0x18003bd5a  or      edx, 0FFFFFFFFh; cchCount1
0x18003bd5d  mov     r9d, edx; cchCount2
0x18003bd60  mov     r8, rbx; lpString2
0x18003bd63  mov     rcx, [rsp+48h+lpString1]; lpString1
0x18003bd68  call    cs:__imp_CompareStringOrdinal
0x18003bd6e  cmp     eax, 2
0x18003bd71  jnz     short loc_18003BDC1
0x18003bd73  call    ?EnsureSysprepDataCleaned@CloudCacheInitializer@@CAJXZ; CloudCacheInitializer::EnsureSysprepDataCleaned(void)
0x18003bd78  mov     rcx, [rsp+48h]; this
0x18003bd7d  test    eax, eax
0x18003bd7f  js      loc_18003BE20
0x18003bd85  mov     r9d, 3
0x18003bd8b  mov     r8d, edi
0x18003bd8e  mov     rdx, rbx
0x18003bd91  mov     rcx, rsi
0x18003bd94  call    ?EnsureCacheInitialized@CloudCacheInitializer@@AEAAJPEBGKW4CacheVersion@@@Z; CloudCacheInitializer::EnsureCacheInitialized(ushort const *,ulong,CacheVersion)
0x18003bd99  mov     ebx, eax
0x18003bd9b  test    eax, eax
0x18003bd9d  js      short loc_18003BDF3
0x18003bd9f  mov     rcx, [rsp+48h+lpString1]; hMem
0x18003bda4  test    rcx, rcx
0x18003bda7  jz      short loc_18003BDAF
0x18003bda9  call    cs:__imp_LocalFree
0x18003bdaf  xor     eax, eax
0x18003bdb1  mov     rbx, [rsp+48h+arg_0]
0x18003bdb6  mov     rsi, [rsp+48h+arg_8]
0x18003bdbb  add     rsp, 40h
0x18003bdbf  pop     rdi
0x18003bdc0  retn
0x18003bdc1  mov     rcx, [rsp+48h]; this
0x18003bdc6  mov     ebx, 8007051Dh
0x18003bdcb  mov     r9d, ebx; char *
0x18003bdce  lea     r8, aOnecoreuapShel_17; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x18003bdd5  mov     edx, 0D0h; void *
0x18003bdda  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bddf  mov     rcx, [rsp+48h+lpString1]; hMem
0x18003bde4  test    rcx, rcx
0x18003bde7  jz      short loc_18003BDEF
0x18003bde9  call    cs:__imp_LocalFree
0x18003bdef  mov     eax, ebx
0x18003bdf1  jmp     short loc_18003BDB1
0x18003bdf3  mov     rcx, [rsp+48h]; this
0x18003bdf8  mov     r9d, ebx; char *
0x18003bdfb  lea     r8, aOnecoreuapShel_17; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x18003be02  mov     edx, 0D3h; void *
0x18003be07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003be0c  mov     rcx, [rsp+48h+lpString1]; hMem
0x18003be11  test    rcx, rcx
0x18003be14  jz      short loc_18003BE1C
0x18003be16  call    cs:__imp_LocalFree
0x18003be1c  mov     eax, ebx
0x18003be1e  jmp     short loc_18003BDB1
0x18003be20  mov     r9d, eax; char *
0x18003be23  lea     r8, aOnecoreuapShel_17; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x18003be2a  mov     edx, 0D2h; void *
0x18003be2f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003be34  jmp     loc_18003BD85
0x18003be39  mov     eax, dword ptr [rsp+48h+lpString1]
0x18003be3d  jmp     loc_18003BDB1
```
