# Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::GetLongSymbolCachePath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x18003c73c`
- end: `0x18003c9c2`
- name: `?GetLongSymbolCachePath@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@AEAAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `646`
- prototype: `__int64 __fastcall(Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper *this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18003bef8`

## callees

- `0x1800020bc`
- `0x18000a17c`
- `0x18002f17c`
- `0x18003c078`
- `0x18003c13c`
- `0x18003c73c`
- `0x18003d864`

## import_xrefs

- `KERNEL32!GetFinalPathNameByHandleW` at `0x18003c7e8`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x18003c828`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x18003c7e8`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x18003c828`
- `KERNEL32!GetFileAttributesW` at `0x18003c929`
- `KERNEL32!GetFileAttributesW` at `0x18003c929`
- `KERNEL32!CreateFileW` at `0x18003c77b`
- `KERNEL32!CreateFileW` at `0x18003c77b`
- `KERNEL32!CloseHandle` at `0x18003c9a7`
- `KERNEL32!CloseHandle` at `0x18003c9a7`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18003c7bf`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18003c867`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18003c883`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18003c8d9`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18003c982`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18003c7bf`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18003c867`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18003c883`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18003c8d9`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18003c982`

## string_xrefs

- `0x18003c7a2`: `Unable to get handle for directory path %s, unable to set symbol cache path`
- `0x18003c851`: `Unable to get long path name for path %s, unable to set symbol cache path`
- `0x18003c8bc`: `Unable to get long path size for path %s, unable to set symbol cache path`
- `0x18003c911`: `Unable to impersonate user, unable to verify the user can write to symbol cache path`
- `0x18003c948`: `Unable to verify that %s is a valid directory, unable to set symbol cache path`
- `0x18003c969`: `The provided symbol cache path %s is not a directory, unable to set symbol cache path`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::GetLongSymbolCachePath(
        LPCWSTR *this,
        LPCWSTR *a2)
{
  HANDLE FileW; // rax
  void *v5; // rbp
  unsigned int v6; // eax
  LPCWSTR v7; // rax
  DWORD FinalPathNameByHandleW; // eax
  unsigned int v9; // eax
  const OLECHAR *v10; // rdx
  LPWSTR v11; // r14
  unsigned int v12; // eax
  DWORD FileAttributesW; // eax
  unsigned int v14; // eax
  LPWSTR lpszFilePath[2]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v17; // [rsp+50h] [rbp-28h]
  HANDLE v18; // [rsp+58h] [rbp-20h]

  FileW = CreateFileW(this[12], 0x80000000, 1u, 0, 3u, 0x2000000u, 0);
  v5 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    if ( *((_QWORD *)_logger + 14) != *((_QWORD *)_logger + 15) )
      DiagHubCommon::LogStream::Write(
        (DiagHubCommon::LogStream *)((char *)_logger + 112),
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\NgenSymbolHelper.cpp",
        L"Unable to get handle for directory path %s, unable to set symbol cache path",
        this[12]);
    v6 = wcslen(&word_180055D48);
    LOBYTE(v7) = ATL::CSimpleStringT<unsigned short,0>::SetString(a2, &word_180055D48, v6);
    return (char)v7;
  }
  v18 = FileW;
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(FileW, 0, 0, 0);
  if ( FinalPathNameByHandleW )
  {
    *(_OWORD *)lpszFilePath = 0;
    v17 = 0;
    std::vector<unsigned short>::vector<unsigned short>(lpszFilePath, FinalPathNameByHandleW);
    if ( GetFinalPathNameByHandleW(v5, lpszFilePath[0], lpszFilePath[1] - lpszFilePath[0], 0) )
    {
      v11 = lpszFilePath[0];
      if ( lpszFilePath[0] )
        v9 = wcslen(lpszFilePath[0]);
      else
        v9 = 0;
      v10 = v11;
    }
    else
    {
      if ( *((_QWORD *)_logger + 14) != *((_QWORD *)_logger + 15) )
        DiagHubCommon::LogStream::Write(
          (DiagHubCommon::LogStream *)((char *)_logger + 112),
          L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\NgenSymbolHelper.cpp",
          L"Unable to get long path name for path %s, unable to set symbol cache path",
          this[12]);
      v9 = wcslen(&word_180055D48);
      v10 = &word_180055D48;
    }
    ATL::CSimpleStringT<unsigned short,0>::SetString(a2, v10, v9);
    std::vector<unsigned short>::~vector<unsigned short>(lpszFilePath);
  }
  else
  {
    if ( *((_QWORD *)_logger + 14) != *((_QWORD *)_logger + 15) )
      DiagHubCommon::LogStream::Write(
        (DiagHubCommon::LogStream *)((char *)_logger + 112),
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\NgenSymbolHelper.cpp",
        L"Unable to get long path size for path %s, unable to set symbol cache path",
        this[12]);
    v12 = wcslen(&word_180055D48);
    ATL::CSimpleStringT<unsigned short,0>::SetString(a2, &word_180055D48, v12);
  }
  v7 = *a2;
  if ( *((_DWORD *)*a2 - 4) )
  {
    if ( Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ImpersonateUser((_Mtx_t)this) )
    {
      FileAttributesW = GetFileAttributesW(*a2);
      if ( FileAttributesW == -1 )
      {
        if ( *((_QWORD *)_logger + 14) != *((_QWORD *)_logger + 15) )
          DiagHubCommon::LogStream::Write(
            (DiagHubCommon::LogStream *)((char *)_logger + 112),
            L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\NgenSymbolHelper.cpp",
            L"Unable to verify that %s is a valid directory, unable to set symbol cache path",
            *a2);
      }
      else
      {
        if ( (FileAttributesW & 0x10) != 0 )
        {
LABEL_28:
          LOBYTE(v7) = Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::RevertImpersonation((Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper *)this);
          goto LABEL_29;
        }
        if ( *((_QWORD *)_logger + 14) != *((_QWORD *)_logger + 15) )
          DiagHubCommon::LogStream::Write(
            (DiagHubCommon::LogStream *)((char *)_logger + 112),
            L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\NgenSymbolHelper.cpp",
            L"The provided symbol cache path %s is not a directory, unable to set symbol cache path",
            *a2);
      }
    }
    else
    {
      DiagHubCommon::LogStream::Write(
        (DiagHubCommon::LogStream *)((char *)_logger + 112),
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\NgenSymbolHelper.cpp",
        L"Unable to impersonate user, unable to verify the user can write to symbol cache path");
    }
    v14 = wcslen(&word_180055D48);
    ATL::CSimpleStringT<unsigned short,0>::SetString(a2, &word_180055D48, v14);
    goto LABEL_28;
  }
LABEL_29:
  if ( v5 )
    LOBYTE(v7) = CloseHandle(v5);
  return (char)v7;
}

```

## disassembly

```asm
0x18003c73c  mov     rax, rsp
0x18003c73f  mov     [rax+18h], rbx
0x18003c743  mov     [rax+20h], rbp
0x18003c747  push    rsi
0x18003c748  push    rdi
0x18003c749  push    r14
0x18003c74b  sub     rsp, 60h
0x18003c74f  mov     rdi, rdx
0x18003c752  mov     rsi, rcx
0x18003c755  mov     qword ptr [rax-48h], 0
0x18003c75d  mov     dword ptr [rax-50h], 2000000h
0x18003c764  mov     dword ptr [rax-58h], 3
0x18003c76b  xor     r9d, r9d; lpSecurityAttributes
0x18003c76e  mov     edx, 80000000h; dwDesiredAccess
0x18003c773  lea     r8d, [r9+1]; dwShareMode
0x18003c777  mov     rcx, [rcx+60h]; lpFileName
0x18003c77b  call    cs:__imp_CreateFileW
0x18003c781  mov     rbp, rax
0x18003c784  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003c788  jnz     short loc_18003C7D8
0x18003c78a  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18003c791  add     rcx, 70h ; 'p'; this
0x18003c795  mov     rax, [rcx+8]
0x18003c799  cmp     [rcx], rax
0x18003c79c  jz      short loc_18003C7B5
0x18003c79e  mov     r9, [rsi+60h]
0x18003c7a2  lea     r8, aUnableToGetHan; "Unable to get handle for directory path"...
0x18003c7a9  lea     rdx, aDAWork1SSource_10; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18003c7b0  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18003c7b5  lea     rbx, word_180055D48
0x18003c7bc  mov     rcx, rbx; String
0x18003c7bf  call    cs:__imp_wcslen
0x18003c7c5  mov     r8d, eax
0x18003c7c8  mov     rdx, rbx
0x18003c7cb  mov     rcx, rdi
0x18003c7ce  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18003c7d3  jmp     loc_18003C9AD
0x18003c7d8  mov     [rsp+78h+var_20], rbp
0x18003c7dd  xor     r9d, r9d; dwFlags
0x18003c7e0  xor     r8d, r8d; cchFilePath
0x18003c7e3  xor     edx, edx; lpszFilePath
0x18003c7e5  mov     rcx, rbp; hFile
0x18003c7e8  call    cs:__imp_GetFinalPathNameByHandleW
0x18003c7ee  test    eax, eax
0x18003c7f0  jz      loc_18003C8A4
0x18003c7f6  xorps   xmm0, xmm0
0x18003c7f9  xor     ecx, ecx
0x18003c7fb  movups  xmmword ptr [rsp+78h+lpszFilePath], xmm0
0x18003c800  mov     [rsp+78h+var_28], rcx
0x18003c805  mov     edx, eax
0x18003c807  lea     rcx, [rsp+78h+lpszFilePath]
0x18003c80c  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x18003c811  nop
0x18003c812  mov     rdx, [rsp+78h+lpszFilePath]; lpszFilePath
0x18003c817  mov     r8, [rsp+78h+lpszFilePath+8]
0x18003c81c  sub     r8, rdx
0x18003c81f  sar     r8, 1; cchFilePath
0x18003c822  xor     r9d, r9d; dwFlags
0x18003c825  mov     rcx, rbp; hFile
0x18003c828  call    cs:__imp_GetFinalPathNameByHandleW
0x18003c82e  lea     rbx, word_180055D48
0x18003c835  test    eax, eax
0x18003c837  jnz     short loc_18003C872
0x18003c839  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18003c840  add     rcx, 70h ; 'p'; this
0x18003c844  mov     rax, [rcx+8]
0x18003c848  cmp     [rcx], rax
0x18003c84b  jz      short loc_18003C864
0x18003c84d  mov     r9, [rsi+60h]
0x18003c851  lea     r8, aUnableToGetLon; "Unable to get long path name for path %"...
0x18003c858  lea     rdx, aDAWork1SSource_10; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18003c85f  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18003c864  mov     rcx, rbx; String
0x18003c867  call    cs:__imp_wcslen
0x18003c86d  mov     rdx, rbx
0x18003c870  jmp     short loc_18003C88C
0x18003c872  mov     r14, [rsp+78h+lpszFilePath]
0x18003c877  test    r14, r14
0x18003c87a  jnz     short loc_18003C880
0x18003c87c  xor     eax, eax
0x18003c87e  jmp     short loc_18003C889
0x18003c880  mov     rcx, r14; String
0x18003c883  call    cs:__imp_wcslen
0x18003c889  mov     rdx, r14
0x18003c88c  mov     r8d, eax
0x18003c88f  mov     rcx, rdi
0x18003c892  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18003c897  nop
0x18003c898  lea     rcx, [rsp+78h+lpszFilePath]
0x18003c89d  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003c8a2  jmp     short loc_18003C8ED
0x18003c8a4  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18003c8ab  add     rcx, 70h ; 'p'; this
0x18003c8af  mov     rax, [rcx+8]
0x18003c8b3  cmp     [rcx], rax
0x18003c8b6  jz      short loc_18003C8CF
0x18003c8b8  mov     r9, [rsi+60h]
0x18003c8bc  lea     r8, aUnableToGetLon_0; "Unable to get long path size for path %"...
0x18003c8c3  lea     rdx, aDAWork1SSource_10; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18003c8ca  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18003c8cf  lea     rbx, word_180055D48
0x18003c8d6  mov     rcx, rbx; String
0x18003c8d9  call    cs:__imp_wcslen
0x18003c8df  mov     r8d, eax
0x18003c8e2  mov     rdx, rbx
0x18003c8e5  mov     rcx, rdi
0x18003c8e8  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18003c8ed  mov     rax, [rdi]
0x18003c8f0  cmp     dword ptr [rax-10h], 0
0x18003c8f4  jz      loc_18003C99F
0x18003c8fa  mov     rcx, rsi; this
0x18003c8fd  call    ?ImpersonateUser@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@AEAA_NXZ; Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ImpersonateUser(void)
0x18003c902  test    al, al
0x18003c904  jnz     short loc_18003C926
0x18003c906  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18003c90d  add     rcx, 70h ; 'p'; this
0x18003c911  lea     r8, aUnableToImpers_0; "Unable to impersonate user, unable to v"...
0x18003c918  lea     rdx, aDAWork1SSource_10; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18003c91f  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18003c924  jmp     short loc_18003C97F
0x18003c926  mov     rcx, [rdi]; lpFileName
0x18003c929  call    cs:__imp_GetFileAttributesW
0x18003c92f  cmp     eax, 0FFFFFFFFh
0x18003c932  jnz     short loc_18003C951
0x18003c934  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18003c93b  add     rcx, 70h ; 'p'
0x18003c93f  mov     rax, [rcx+8]
0x18003c943  cmp     [rcx], rax
0x18003c946  jz      short loc_18003C97F
0x18003c948  lea     r8, aUnableToVerify_0; "Unable to verify that %s is a valid dir"...
0x18003c94f  jmp     short loc_18003C970
0x18003c951  test    al, 10h
0x18003c953  jnz     short loc_18003C996
0x18003c955  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18003c95c  add     rcx, 70h ; 'p'; this
0x18003c960  mov     rax, [rcx+8]
0x18003c964  cmp     [rcx], rax
0x18003c967  jz      short loc_18003C97F
0x18003c969  lea     r8, aTheProvidedSym; "The provided symbol cache path %s is no"...
0x18003c970  mov     r9, [rdi]
0x18003c973  lea     rdx, aDAWork1SSource_10; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18003c97a  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18003c97f  mov     rcx, rbx; String
0x18003c982  call    cs:__imp_wcslen
0x18003c988  mov     r8d, eax
0x18003c98b  mov     rdx, rbx
0x18003c98e  mov     rcx, rdi
0x18003c991  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18003c996  mov     rcx, rsi; this
0x18003c999  call    ?RevertImpersonation@NgenSymbolHelper@StandardCollector@DiagnosticsHub@Microsoft@@AEAA_NXZ; Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::RevertImpersonation(void)
0x18003c99e  nop
0x18003c99f  test    rbp, rbp
0x18003c9a2  jz      short loc_18003C9AD
0x18003c9a4  mov     rcx, rbp; hObject
0x18003c9a7  call    cs:__imp_CloseHandle
0x18003c9ad  lea     r11, [rsp+78h+var_18]
0x18003c9b2  mov     rbx, [r11+30h]
0x18003c9b6  mov     rbp, [r11+38h]
0x18003c9ba  mov     rsp, r11
0x18003c9bd  pop     r14
0x18003c9bf  pop     rdi
0x18003c9c0  pop     rsi
0x18003c9c1  retn
```
