# Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::GetSymbolCachePath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x18003bef8`
- end: `0x18003c075`
- name: `?GetSymbolCachePath@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@QEAAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `381`
- prototype: `__int64 __fastcall(Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180038a24`

## callees

- `0x1800020bc`
- `0x18000a17c`
- `0x18002f17c`
- `0x18003bef8`
- `0x18003c73c`
- `0x18003d864`

## import_xrefs

- `KERNEL32!GetEnvironmentVariableW` at `0x18003bfae`
- `KERNEL32!GetEnvironmentVariableW` at `0x18003bfe7`
- `KERNEL32!GetEnvironmentVariableW` at `0x18003bfae`
- `KERNEL32!GetEnvironmentVariableW` at `0x18003bfe7`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18003bf17`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18003c015`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18003c03f`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18003bf17`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18003c015`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18003c03f`

## string_xrefs

- `0x18003bf67`: `Provided symbol cache path %s is invalid, defaulting to environment variable option _NT_SYMCACHE_PATH`
- `0x18003bf7c`: `No valid symbol cache path provided by SetSymbolCachePath, attempting to set symbol cache path via env var _NT_SYMCACHE_PATH`
- `0x18003bfa7`: `_NT_SYMCACHE_PATH`
- `0x18003bfe0`: `_NT_SYMCACHE_PATH`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::GetSymbolCachePath(
        Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper *this,
        __int64 *a2)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  __int64 result; // rax
  DWORD EnvironmentVariableW; // eax
  DWORD v8; // eax
  LPWSTR v9; // rsi
  unsigned int v10; // eax
  LPWSTR lpBuffer[2]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v12; // [rsp+30h] [rbp-28h]

  v4 = wcslen(&word_180055D48);
  ATL::CSimpleStringT<unsigned short,0>::SetString(a2, &word_180055D48, v4);
  v5 = 0;
  if ( *(_DWORD *)(*((_QWORD *)this + 12) - 16LL) )
  {
    Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::GetLongSymbolCachePath(
      (LPCWSTR *)this,
      (LPCWSTR *)a2);
    if ( !*(_DWORD *)(*a2 - 16) && *((_QWORD *)_logger + 14) != *((_QWORD *)_logger + 15) )
      DiagHubCommon::LogStream::Write(
        (DiagHubCommon::LogStream *)((char *)_logger + 112),
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\NgenSymbolHelper.cpp",
        L"Provided symbol cache path %s is invalid, defaulting to environment variable option _NT_SYMCACHE_PATH",
        *((_QWORD *)this + 12));
  }
  else
  {
    DiagHubCommon::LogStream::Write(
      _logger,
      L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\NgenSymbolHelper.cpp",
      L"No valid symbol cache path provided by SetSymbolCachePath, attempting to set symbol cache path via env var _NT_SYMCACHE_PATH");
  }
  result = *a2;
  if ( !*(_DWORD *)(*a2 - 16) )
  {
    EnvironmentVariableW = GetEnvironmentVariableW(L"_NT_SYMCACHE_PATH", 0, 0);
    *(_OWORD *)lpBuffer = 0;
    v12 = 0;
    std::vector<unsigned short>::vector<unsigned short>(lpBuffer, EnvironmentVariableW);
    v8 = GetEnvironmentVariableW(L"_NT_SYMCACHE_PATH", lpBuffer[0], lpBuffer[1] - lpBuffer[0]);
    if ( v8 && (v9 = lpBuffer[0], v8 < (unsigned __int64)(lpBuffer[1] - lpBuffer[0])) )
    {
      _mm_lfence();
      if ( lpBuffer[0] )
        v5 = wcslen(lpBuffer[0]);
      ATL::CSimpleStringT<unsigned short,0>::SetString((__int64 *)this + 12, v9, v5);
      Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::GetLongSymbolCachePath(
        (LPCWSTR *)this,
        (LPCWSTR *)a2);
    }
    else
    {
      v10 = wcslen(&word_180055D48);
      ATL::CSimpleStringT<unsigned short,0>::SetString(a2, &word_180055D48, v10);
    }
    return std::vector<unsigned short>::~vector<unsigned short>(lpBuffer);
  }
  return result;
}

```

## disassembly

```asm
0x18003bef8  mov     [rsp+arg_10], rbx
0x18003befd  mov     [rsp+arg_18], rbp
0x18003bf02  push    rsi
0x18003bf03  push    rdi
0x18003bf04  push    r14
0x18003bf06  sub     rsp, 40h
0x18003bf0a  mov     rdi, rdx
0x18003bf0d  mov     rbp, rcx
0x18003bf10  lea     rcx, word_180055D48; String
0x18003bf17  call    cs:__imp_wcslen
0x18003bf1d  mov     r8d, eax
0x18003bf20  lea     rdx, word_180055D48
0x18003bf27  mov     rcx, rdi
0x18003bf2a  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18003bf2f  lea     r14, [rbp+60h]
0x18003bf33  mov     rax, [r14]
0x18003bf36  xor     ebx, ebx
0x18003bf38  cmp     [rax-10h], ebx
0x18003bf3b  jz      short loc_18003BF7C
0x18003bf3d  mov     rdx, rdi
0x18003bf40  mov     rcx, rbp; this
0x18003bf43  call    ?GetLongSymbolCachePath@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@AEAAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::GetLongSymbolCachePath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18003bf48  mov     rax, [rdi]
0x18003bf4b  cmp     [rax-10h], ebx
0x18003bf4e  jnz     short loc_18003BF96
0x18003bf50  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18003bf57  add     rcx, 70h ; 'p'; this
0x18003bf5b  mov     rax, [rcx+8]
0x18003bf5f  cmp     [rcx], rax
0x18003bf62  jz      short loc_18003BF96
0x18003bf64  mov     r9, [r14]
0x18003bf67  lea     r8, aProvidedSymbol; "Provided symbol cache path %s is invali"...
0x18003bf6e  lea     rdx, aDAWork1SSource_10; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18003bf75  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18003bf7a  jmp     short loc_18003BF96
0x18003bf7c  lea     r8, aNoValidSymbolC; "No valid symbol cache path provided by "...
0x18003bf83  lea     rdx, aDAWork1SSource_10; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18003bf8a  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; this
0x18003bf91  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18003bf96  mov     rax, [rdi]
0x18003bf99  cmp     [rax-10h], ebx
0x18003bf9c  jnz     loc_18003C062
0x18003bfa2  xor     r8d, r8d; nSize
0x18003bfa5  xor     edx, edx; lpBuffer
0x18003bfa7  lea     rcx, Name; "_NT_SYMCACHE_PATH"
0x18003bfae  call    cs:__imp_GetEnvironmentVariableW
0x18003bfb4  xorps   xmm0, xmm0
0x18003bfb7  xor     edx, edx
0x18003bfb9  movups  xmmword ptr [rsp+58h+lpBuffer], xmm0
0x18003bfbe  mov     [rsp+58h+var_28], rdx
0x18003bfc3  mov     edx, eax
0x18003bfc5  lea     rcx, [rsp+58h+lpBuffer]
0x18003bfca  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x18003bfcf  nop
0x18003bfd0  mov     rdx, [rsp+58h+lpBuffer]; lpBuffer
0x18003bfd5  mov     r8, [rsp+58h+lpBuffer+8]
0x18003bfda  sub     r8, rdx
0x18003bfdd  sar     r8, 1; nSize
0x18003bfe0  lea     rcx, Name; "_NT_SYMCACHE_PATH"
0x18003bfe7  call    cs:__imp_GetEnvironmentVariableW
0x18003bfed  test    eax, eax
0x18003bfef  jz      short loc_18003C038
0x18003bff1  mov     rsi, [rsp+58h+lpBuffer]
0x18003bff6  mov     rcx, [rsp+58h+lpBuffer+8]
0x18003bffb  sub     rcx, rsi
0x18003bffe  sar     rcx, 1
0x18003c001  mov     eax, eax
0x18003c003  cmp     rax, rcx
0x18003c006  jnb     short loc_18003C038
0x18003c008  lfence
0x18003c00b  cmp     [rsp+58h+lpBuffer], rbx
0x18003c010  jz      short loc_18003C01D
0x18003c012  mov     rcx, rsi; String
0x18003c015  call    cs:__imp_wcslen
0x18003c01b  mov     ebx, eax
0x18003c01d  mov     r8d, ebx
0x18003c020  mov     rdx, rsi
0x18003c023  mov     rcx, r14
0x18003c026  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18003c02b  mov     rdx, rdi
0x18003c02e  mov     rcx, rbp; this
0x18003c031  call    ?GetLongSymbolCachePath@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@AEAAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::GetLongSymbolCachePath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18003c036  jmp     short loc_18003C058
0x18003c038  lea     rcx, word_180055D48; String
0x18003c03f  call    cs:__imp_wcslen
0x18003c045  mov     r8d, eax
0x18003c048  lea     rdx, word_180055D48
0x18003c04f  mov     rcx, rdi
0x18003c052  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18003c057  nop
0x18003c058  lea     rcx, [rsp+58h+lpBuffer]
0x18003c05d  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003c062  mov     rbx, [rsp+58h+arg_10]
0x18003c067  mov     rbp, [rsp+58h+arg_18]
0x18003c06c  add     rsp, 40h
0x18003c070  pop     r14
0x18003c072  pop     rdi
0x18003c073  pop     rsi
0x18003c074  retn
```
