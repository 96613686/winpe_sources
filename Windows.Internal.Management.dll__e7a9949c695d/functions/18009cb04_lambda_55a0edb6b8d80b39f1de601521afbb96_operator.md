# _lambda_55a0edb6b8d80b39f1de601521afbb96_::operator()

- ea: `0x18009cb04`
- end: `0x18009ccef`
- name: `_lambda_55a0edb6b8d80b39f1de601521afbb96_::operator()`
- size: `491`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18009c384`

## callees

- `0x180004d50`
- `0x18000a7c0`
- `0x18000a8a4`
- `0x180017204`
- `0x180019fb8`
- `0x18003ec00`
- `0x18009c684`
- `0x18009cb04`
- `0x18009ccf8`
- `0x18009d88c`
- `0x18009f474`
- `0x18009fff8`

## import_xrefs

- `msvcp_win!?swap@?$basic_istream@DU?$char_traits@D@std@@@std@@IEAAXAEAV12@@Z` at `0x18009cc37`
- `msvcp_win!?swap@?$basic_istream@DU?$char_traits@D@std@@@std@@IEAAXAEAV12@@Z` at `0x18009cc37`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18009cbc8`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18009cbfc`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18009cbc8`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18009cbfc`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall lambda_55a0edb6b8d80b39f1de601521afbb96_::operator()(__int64 a1)
{
  unsigned __int16 **v2; // r8
  int StoragePath; // eax
  int v4; // eax
  unsigned __int64 v5; // rdx
  int v6; // eax
  HRESULT v7; // eax
  HRESULT v8; // eax
  __int64 v9; // rdi
  __int64 v10; // rsi
  int v12; // [rsp+20h] [rbp-E0h]
  PWSTR ppszPathOut; // [rsp+30h] [rbp-D0h] BYREF
  PCWSTR pszPathIn; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR pszMore[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  pszPathIn = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pszPathIn,
    0);
  StoragePath = FirstSync::GetStoragePath(*(PCWSTR *)(a1 + 8), (PWSTR *)&pszPathIn, v2);
  if ( StoragePath < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xBF,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
      (const char *)(unsigned int)StoragePath,
      v12);
  ppszPathOut = 0;
  if ( *(_QWORD *)a1 )
  {
    v4 = StringCchCopyW(pszMore, 0x104u, *(const unsigned __int16 **)a1);
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC5,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
        (const char *)(unsigned int)v4,
        v12);
    v6 = StringCchCatW(pszMore, v5, *(const unsigned __int16 **)(a1 + 16));
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC6,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
        (const char *)(unsigned int)v6,
        v12);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &ppszPathOut,
      0);
    v7 = PathAllocCombine(pszPathIn, pszMore, 0, &ppszPathOut);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC7,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
        (const char *)(unsigned int)v7,
        v12);
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &ppszPathOut,
      0);
    v8 = PathAllocCombine(pszPathIn, *(PCWSTR *)(a1 + 16), 0, &ppszPathOut);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCB,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
        (const char *)(unsigned int)v8,
        v12);
  }
  v9 = std::ifstream::ifstream(pszMore, ppszPathOut);
  v10 = *(_QWORD *)(a1 + 24);
  if ( v10 != v9 )
  {
    std::filebuf::close(v10 + 16);
    std::istream::swap(v10, v9);
    std::filebuf::swap(v10 + 16, v9 + 16);
  }
  std::ifstream::`vbase destructor'(pszMore);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPathOut);
  return wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPathIn);
}

```

## disassembly

```asm
0x18009cb04  push    rbp
0x18009cb06  push    rbx
0x18009cb07  push    rsi
0x18009cb08  push    rdi
0x18009cb09  lea     rbp, [rsp-168h]
0x18009cb11  sub     rsp, 268h
0x18009cb18  mov     rax, cs:__security_cookie
0x18009cb1f  xor     rax, rsp
0x18009cb22  mov     [rbp+180h+var_30], rax
0x18009cb29  mov     rbx, rcx
0x18009cb2c  mov     [rsp+280h+pszPathIn], 0
0x18009cb35  xor     edx, edx
0x18009cb37  lea     rcx, [rsp+280h+pszPathIn]
0x18009cb3c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18009cb41  lea     rdx, [rsp+280h+pszPathIn]; ppszPathOut
0x18009cb46  mov     rcx, [rbx+8]; pszMore
0x18009cb4a  call    ?GetStoragePath@FirstSync@@YAJPEBGPEAPEAG@Z; FirstSync::GetStoragePath(ushort const *,ushort * *)
0x18009cb4f  mov     rcx, [rbp+188h]; this
0x18009cb56  test    eax, eax
0x18009cb58  js      loc_18009CCB0
0x18009cb5e  mov     [rsp+280h+ppszPathOut], 0
0x18009cb67  mov     r8, [rbx]; unsigned __int16 *
0x18009cb6a  test    r8, r8
0x18009cb6d  jz      short loc_18009CBDF
0x18009cb6f  mov     edx, 104h; unsigned __int64
0x18009cb74  lea     rcx, [rsp+280h+pszMore]; unsigned __int16 *
0x18009cb79  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18009cb7e  mov     rcx, [rbp+188h]; this
0x18009cb85  test    eax, eax
0x18009cb87  js      loc_18009CCC5
0x18009cb8d  mov     r8, [rbx+10h]; unsigned __int16 *
0x18009cb91  lea     rcx, [rsp+280h+pszMore]; unsigned __int16 *
0x18009cb96  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18009cb9b  mov     rcx, [rbp+188h]; this
0x18009cba2  test    eax, eax
0x18009cba4  js      loc_18009CCDA
0x18009cbaa  xor     edx, edx
0x18009cbac  lea     rcx, [rsp+280h+ppszPathOut]
0x18009cbb1  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18009cbb6  lea     r9, [rsp+280h+ppszPathOut]; ppszPathOut
0x18009cbbb  xor     r8d, r8d; dwFlags
0x18009cbbe  lea     rdx, [rsp+280h+pszMore]; pszMore
0x18009cbc3  mov     rcx, [rsp+280h+pszPathIn]; pszPathIn
0x18009cbc8  call    cs:__imp_PathAllocCombine
0x18009cbce  mov     rcx, [rbp+188h]; this
0x18009cbd5  test    eax, eax
0x18009cbd7  js      loc_18009CC9B
0x18009cbdd  jmp     short loc_18009CC0D
0x18009cbdf  xor     edx, edx
0x18009cbe1  lea     rcx, [rsp+280h+ppszPathOut]
0x18009cbe6  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18009cbeb  lea     r9, [rsp+280h+ppszPathOut]; ppszPathOut
0x18009cbf0  xor     r8d, r8d; dwFlags
0x18009cbf3  mov     rdx, [rbx+10h]; pszMore
0x18009cbf7  mov     rcx, [rsp+280h+pszPathIn]; pszPathIn
0x18009cbfc  call    cs:__imp_PathAllocCombine
0x18009cc02  mov     rcx, [rbp+188h]; this
0x18009cc09  test    eax, eax
0x18009cc0b  js      short loc_18009CC86
0x18009cc0d  mov     rdx, [rsp+280h+ppszPathOut]
0x18009cc12  lea     rcx, [rsp+280h+pszMore]
0x18009cc17  call    ??0?$basic_ifstream@DU?$char_traits@D@std@@@std@@QEAA@PEBGHH@Z; std::ifstream::ifstream(ushort const *,int,int)
0x18009cc1c  mov     rdi, rax
0x18009cc1f  mov     rsi, [rbx+18h]
0x18009cc23  cmp     rsi, rax
0x18009cc26  jz      short loc_18009CC4B
0x18009cc28  lea     rcx, [rsi+10h]
0x18009cc2c  call    ?close@?$basic_filebuf@DU?$char_traits@D@std@@@std@@QEAAPEAV12@XZ; std::filebuf::close(void)
0x18009cc31  mov     rdx, rdi
0x18009cc34  mov     rcx, rsi
0x18009cc37  call    cs:__imp_?swap@?$basic_istream@DU?$char_traits@D@std@@@std@@IEAAXAEAV12@@Z; std::istream::swap(std::istream &)
0x18009cc3d  lea     rdx, [rdi+10h]
0x18009cc41  lea     rcx, [rsi+10h]
0x18009cc45  call    ?swap@?$basic_filebuf@DU?$char_traits@D@std@@@std@@QEAAXAEAV12@@Z; std::filebuf::swap(std::filebuf &)
0x18009cc4a  nop
0x18009cc4b  lea     rcx, [rsp+280h+pszMore]
0x18009cc50  call    ??_D?$basic_ifstream@DU?$char_traits@D@std@@@std@@QEAAXXZ; std::ifstream::`vbase destructor'(void)
0x18009cc55  nop
0x18009cc56  lea     rcx, [rsp+280h+ppszPathOut]
0x18009cc5b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18009cc60  nop
0x18009cc61  lea     rcx, [rsp+280h+pszPathIn]
0x18009cc66  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18009cc6b  mov     rcx, [rbp+180h+var_30]
0x18009cc72  xor     rcx, rsp; StackCookie
0x18009cc75  call    __security_check_cookie
0x18009cc7a  add     rsp, 268h
0x18009cc81  pop     rdi
0x18009cc82  pop     rsi
0x18009cc83  pop     rbx
0x18009cc84  pop     rbp
0x18009cc85  retn
0x18009cc86  mov     r9d, eax; char *
0x18009cc89  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x18009cc90  mov     edx, 0CBh; void *
0x18009cc95  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009cc9b  mov     r9d, eax; char *
0x18009cc9e  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x18009cca5  mov     edx, 0C7h; void *
0x18009ccaa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009ccb0  mov     r9d, eax; char *
0x18009ccb3  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x18009ccba  mov     edx, 0BFh; void *
0x18009ccbf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009ccc5  mov     r9d, eax; char *
0x18009ccc8  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x18009cccf  mov     edx, 0C5h; void *
0x18009ccd4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009ccda  mov     r9d, eax; char *
0x18009ccdd  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x18009cce4  mov     edx, 0C6h; void *
0x18009cce9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
