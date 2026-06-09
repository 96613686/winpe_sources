# _lambda_55a0edb6b8d80b39f1de601521afbb96_::operator()

- ea: `0x18009f9f4`
- end: `0x18009fbf6`
- name: `_lambda_55a0edb6b8d80b39f1de601521afbb96_::operator()`
- size: `514`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18009f1fc`

## callees

- `0x180004eb0`
- `0x18000ab00`
- `0x18000abec`
- `0x1800179f8`
- `0x1800187d4`
- `0x18003e5d4`
- `0x18009f528`
- `0x18009f9f4`
- `0x18009fbfc`
- `0x1800a0804`
- `0x1800a2508`
- `0x1800a30e0`

## import_xrefs

- `msvcp_win!?swap@?$basic_istream@DU?$char_traits@D@std@@@std@@IEAAXAEAV12@@Z` at `0x18009fb37`
- `msvcp_win!?swap@?$basic_istream@DU?$char_traits@D@std@@@std@@IEAAXAEAV12@@Z` at `0x18009fb37`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18009fab8`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18009faf2`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18009fab8`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18009faf2`

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
0x18009f9f4  push    rbp
0x18009f9f6  push    rbx
0x18009f9f7  push    rsi
0x18009f9f8  push    rdi
0x18009f9f9  lea     rbp, [rsp-168h]
0x18009fa01  sub     rsp, 268h
0x18009fa08  mov     rax, cs:__security_cookie
0x18009fa0f  xor     rax, rsp
0x18009fa12  mov     [rbp+180h+var_30], rax
0x18009fa19  mov     rbx, rcx
0x18009fa1c  mov     [rsp+280h+pszPathIn], 0
0x18009fa25  xor     edx, edx
0x18009fa27  lea     rcx, [rsp+280h+pszPathIn]
0x18009fa2c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18009fa31  lea     rdx, [rsp+280h+pszPathIn]; ppszPathOut
0x18009fa36  mov     rcx, [rbx+8]; pszMore
0x18009fa3a  call    ?GetStoragePath@FirstSync@@YAJPEBGPEAPEAG@Z; FirstSync::GetStoragePath(ushort const *,ushort * *)
0x18009fa3f  mov     rcx, [rbp+188h]; this
0x18009fa46  test    eax, eax
0x18009fa48  js      loc_18009FBB7
0x18009fa4e  mov     [rsp+280h+ppszPathOut], 0
0x18009fa57  mov     r8, [rbx]; unsigned __int16 *
0x18009fa5a  test    r8, r8
0x18009fa5d  jz      short loc_18009FAD5
0x18009fa5f  mov     edx, 104h; unsigned __int64
0x18009fa64  lea     rcx, [rsp+280h+pszMore]; unsigned __int16 *
0x18009fa69  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18009fa6e  mov     rcx, [rbp+188h]; this
0x18009fa75  test    eax, eax
0x18009fa77  js      loc_18009FBCC
0x18009fa7d  mov     r8, [rbx+10h]; unsigned __int16 *
0x18009fa81  lea     rcx, [rsp+280h+pszMore]; unsigned __int16 *
0x18009fa86  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18009fa8b  mov     rcx, [rbp+188h]; this
0x18009fa92  test    eax, eax
0x18009fa94  js      loc_18009FBE1
0x18009fa9a  xor     edx, edx
0x18009fa9c  lea     rcx, [rsp+280h+ppszPathOut]
0x18009faa1  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18009faa6  lea     r9, [rsp+280h+ppszPathOut]; ppszPathOut
0x18009faab  xor     r8d, r8d; dwFlags
0x18009faae  lea     rdx, [rsp+280h+pszMore]; pszMore
0x18009fab3  mov     rcx, [rsp+280h+pszPathIn]; pszPathIn
0x18009fab8  call    cs:__imp_PathAllocCombine
0x18009fabf  nop     dword ptr [rax+rax+00h]
0x18009fac4  mov     rcx, [rbp+188h]; this
0x18009facb  test    eax, eax
0x18009facd  js      loc_18009FBA2
0x18009fad3  jmp     short loc_18009FB0D
0x18009fad5  xor     edx, edx
0x18009fad7  lea     rcx, [rsp+280h+ppszPathOut]
0x18009fadc  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18009fae1  lea     r9, [rsp+280h+ppszPathOut]; ppszPathOut
0x18009fae6  xor     r8d, r8d; dwFlags
0x18009fae9  mov     rdx, [rbx+10h]; pszMore
0x18009faed  mov     rcx, [rsp+280h+pszPathIn]; pszPathIn
0x18009faf2  call    cs:__imp_PathAllocCombine
0x18009faf9  nop     dword ptr [rax+rax+00h]
0x18009fafe  mov     rcx, [rbp+188h]; this
0x18009fb05  test    eax, eax
0x18009fb07  js      loc_18009FB8D
0x18009fb0d  mov     rdx, [rsp+280h+ppszPathOut]
0x18009fb12  lea     rcx, [rsp+280h+pszMore]
0x18009fb17  call    ??0?$basic_ifstream@DU?$char_traits@D@std@@@std@@QEAA@PEBGHH@Z; std::ifstream::ifstream(ushort const *,int,int)
0x18009fb1c  mov     rdi, rax
0x18009fb1f  mov     rsi, [rbx+18h]
0x18009fb23  cmp     rsi, rax
0x18009fb26  jz      short loc_18009FB51
0x18009fb28  lea     rcx, [rsi+10h]
0x18009fb2c  call    ?close@?$basic_filebuf@DU?$char_traits@D@std@@@std@@QEAAPEAV12@XZ; std::filebuf::close(void)
0x18009fb31  mov     rdx, rdi
0x18009fb34  mov     rcx, rsi
0x18009fb37  call    cs:__imp_?swap@?$basic_istream@DU?$char_traits@D@std@@@std@@IEAAXAEAV12@@Z; std::istream::swap(std::istream &)
0x18009fb3e  nop     dword ptr [rax+rax+00h]
0x18009fb43  lea     rdx, [rdi+10h]
0x18009fb47  lea     rcx, [rsi+10h]
0x18009fb4b  call    ?swap@?$basic_filebuf@DU?$char_traits@D@std@@@std@@QEAAXAEAV12@@Z; std::filebuf::swap(std::filebuf &)
0x18009fb50  nop
0x18009fb51  lea     rcx, [rsp+280h+pszMore]
0x18009fb56  call    ??_D?$basic_ifstream@DU?$char_traits@D@std@@@std@@QEAAXXZ; std::ifstream::`vbase destructor'(void)
0x18009fb5b  nop
0x18009fb5c  lea     rcx, [rsp+280h+ppszPathOut]
0x18009fb61  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18009fb66  nop
0x18009fb67  lea     rcx, [rsp+280h+pszPathIn]
0x18009fb6c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18009fb71  mov     rcx, [rbp+180h+var_30]
0x18009fb78  xor     rcx, rsp; StackCookie
0x18009fb7b  call    __security_check_cookie
0x18009fb80  add     rsp, 268h
0x18009fb87  pop     rdi
0x18009fb88  pop     rsi
0x18009fb89  pop     rbx
0x18009fb8a  pop     rbp
0x18009fb8b  retn
0x18009fb8d  mov     r9d, eax; char *
0x18009fb90  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x18009fb97  mov     edx, 0CBh; void *
0x18009fb9c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009fba2  mov     r9d, eax; char *
0x18009fba5  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x18009fbac  mov     edx, 0C7h; void *
0x18009fbb1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009fbb7  mov     r9d, eax; char *
0x18009fbba  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x18009fbc1  mov     edx, 0BFh; void *
0x18009fbc6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009fbcc  mov     r9d, eax; char *
0x18009fbcf  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x18009fbd6  mov     edx, 0C5h; void *
0x18009fbdb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009fbe1  mov     r9d, eax; char *
0x18009fbe4  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x18009fbeb  mov     edx, 0C6h; void *
0x18009fbf0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
