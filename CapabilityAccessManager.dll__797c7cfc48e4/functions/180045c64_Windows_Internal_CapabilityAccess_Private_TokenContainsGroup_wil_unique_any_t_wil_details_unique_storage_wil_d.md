# Windows::Internal::CapabilityAccess::Private::TokenContainsGroup(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &,WELL_KNOWN_SID_TYPE)

- ea: `0x180045c64`
- end: `0x180045e3e`
- name: `?TokenContainsGroup@Private@CapabilityAccess@Internal@Windows@@YA_NAEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@W4WELL_KNOWN_SID_TYPE@@@Z`
- size: `474`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180044614`
- `0x18006ae88`
- `0x1800954a4`

## callees

- `0x18002392c`
- `0x18002f260`
- `0x180039e9c`
- `0x18003f274`
- `0x18003f43c`
- `0x18003f458`
- `0x180045c64`
- `0x18004624c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045cae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045cae`
- `ntdll!RtlEqualSid` at `0x180045d73`
- `ntdll!RtlEqualSid` at `0x180045d73`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180045d2c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180045d2c`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180045d52`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180045d52`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180045c9c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180045d07`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180045c9c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180045d07`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall Windows::Internal::CapabilityAccess::Private::TokenContainsGroup(HANDLE *a1)
{
  const char *v2; // r9
  PSID **v3; // rax
  PSID *v4; // rdi
  const char *v5; // r9
  const char *v6; // r9
  PSID *v7; // rsi
  HLOCAL v8; // rax
  const char *v9; // r9
  void *v10; // rbx
  const char *v11; // r9
  int v12; // r14d
  int ReturnLength; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  DWORD cbSid; // [rsp+60h] [rbp+30h] BYREF
  DWORD TokenInformationLength; // [rsp+68h] [rbp+38h] BYREF
  HLOCAL v18; // [rsp+70h] [rbp+40h] BYREF
  PSID *v19; // [rsp+78h] [rbp+48h] BYREF

  TokenInformationLength = 0;
  if ( GetTokenInformation(*a1, TokenGroups, 0, 0, &TokenInformationLength) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x965,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      (const char *)0x8000FFFFLL,
      ReturnLength);
  if ( GetLastError() != 122 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x966,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      v2);
  v3 = (PSID **)std::make_unique<unsigned char [0],0>(&cbSid, TokenInformationLength);
  v4 = *v3;
  *v3 = 0;
  v19 = v4;
  std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(&cbSid);
  if ( !v4 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x969,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      v5);
  if ( !GetTokenInformation(*a1, TokenGroups, v4, TokenInformationLength, &TokenInformationLength) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x96C,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      v6);
  if ( !*(_DWORD *)v4 )
    goto LABEL_15;
  v7 = v4 + 1;
  if ( v4 == (PSID *)-8LL )
    goto LABEL_15;
  cbSid = 68;
  v8 = LocalAlloc(0, 0x44u);
  v10 = v8;
  v18 = v8;
  if ( !v8 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x974,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      v9);
  if ( !CreateWellKnownSid(WinInteractiveSid, 0, v8, &cbSid) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x976,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      v11);
  v12 = 0;
  if ( !*(_DWORD *)v4 )
  {
LABEL_14:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v18);
LABEL_15:
    std::unique_ptr<_TOKEN_GROUPS>::~unique_ptr<_TOKEN_GROUPS>(&v19);
    return 0;
  }
  while ( !v7 )
  {
LABEL_13:
    if ( (unsigned int)++v12 >= *(_DWORD *)v4 )
      goto LABEL_14;
  }
  if ( !RtlEqualSid(*v7, v10) )
  {
    v7 += 2;
    goto LABEL_13;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v18);
  std::unique_ptr<_TOKEN_GROUPS>::~unique_ptr<_TOKEN_GROUPS>(&v19);
  return 1;
}

```

## disassembly

```asm
0x180045c64  mov     [rsp-28h+TokenInformationLength], edx
0x180045c68  push    rbp
0x180045c69  push    rbx
0x180045c6a  push    rsi
0x180045c6b  push    rdi
0x180045c6c  push    r14
0x180045c6e  mov     rbp, rsp
0x180045c71  sub     rsp, 30h
0x180045c75  mov     rsi, rcx
0x180045c78  mov     [rbp+TokenInformationLength], 0
0x180045c7f  mov     rbx, [rbp+28h]
0x180045c83  lea     rax, [rbp+TokenInformationLength]
0x180045c87  mov     qword ptr [rsp+30h+ReturnLength], rax; int
0x180045c8c  xor     r9d, r9d; TokenInformationLength
0x180045c8f  xor     r8d, r8d; TokenInformation
0x180045c92  lea     r14d, [r9+2]
0x180045c96  mov     edx, r14d; TokenInformationClass
0x180045c99  mov     rcx, [rcx]; TokenHandle
0x180045c9c  call    cs:__imp_GetTokenInformation
0x180045ca2  test    eax, eax
0x180045ca4  jnz     loc_180045DE4
0x180045caa  mov     rbx, [rbp+28h]
0x180045cae  call    cs:__imp_GetLastError
0x180045cb4  cmp     eax, 7Ah ; 'z'
0x180045cb7  jnz     loc_180045DFF
0x180045cbd  mov     edx, [rbp+TokenInformationLength]
0x180045cc0  lea     rcx, [rbp+cbSid]
0x180045cc4  call    ??$make_unique@$$BY0A@E$0A@@std@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@0@_K@Z; std::make_unique<uchar [0],0>(unsigned __int64)
0x180045cc9  mov     rdi, [rax]
0x180045ccc  mov     qword ptr [rax], 0
0x180045cd3  mov     [rbp+arg_18], rdi
0x180045cd7  lea     rcx, [rbp+cbSid]
0x180045cdb  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x180045ce0  mov     rcx, [rbp+28h]; this
0x180045ce4  test    rdi, rdi
0x180045ce7  jz      loc_180045DD2
0x180045ced  mov     rbx, [rbp+28h]
0x180045cf1  lea     rax, [rbp+TokenInformationLength]
0x180045cf5  mov     qword ptr [rsp+30h+ReturnLength], rax; ReturnLength
0x180045cfa  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180045cfe  mov     r8, rdi; TokenInformation
0x180045d01  mov     edx, r14d; TokenInformationClass
0x180045d04  mov     rcx, [rsi]; TokenHandle
0x180045d07  call    cs:__imp_GetTokenInformation
0x180045d0d  test    eax, eax
0x180045d0f  jz      loc_180045E14
0x180045d15  cmp     dword ptr [rdi], 0
0x180045d18  jbe     short loc_180045D93
0x180045d1a  lea     rsi, [rdi+8]
0x180045d1e  test    rsi, rsi
0x180045d21  jz      short loc_180045D93
0x180045d23  lea     edx, [r14+42h]; uBytes
0x180045d27  mov     [rbp+cbSid], edx
0x180045d2a  xor     ecx, ecx; uFlags
0x180045d2c  call    cs:__imp_LocalAlloc
0x180045d32  mov     rbx, rax
0x180045d35  mov     [rbp+arg_10], rax
0x180045d39  mov     rcx, [rbp+28h]; this
0x180045d3d  test    rax, rax
0x180045d40  jz      short loc_180045DC0
0x180045d42  mov     r14, [rbp+28h]
0x180045d46  lea     r9, [rbp+cbSid]; cbSid
0x180045d4a  mov     r8, rax; pSid
0x180045d4d  xor     edx, edx; DomainSid
0x180045d4f  lea     ecx, [rdx+0Bh]; WellKnownSidType
0x180045d52  call    cs:__imp_CreateWellKnownSid
0x180045d58  test    eax, eax
0x180045d5a  jz      loc_180045E29
0x180045d60  xor     r14d, r14d
0x180045d63  cmp     [rdi], r14d
0x180045d66  jbe     short loc_180045D89
0x180045d68  test    rsi, rsi
0x180045d6b  jz      short loc_180045D81
0x180045d6d  mov     rdx, rbx; Sid2
0x180045d70  mov     rcx, [rsi]; Sid1
0x180045d73  call    cs:__imp_RtlEqualSid
0x180045d79  test    al, al
0x180045d7b  jnz     short loc_180045DA9
0x180045d7d  add     rsi, 10h
0x180045d81  inc     r14d
0x180045d84  cmp     r14d, [rdi]
0x180045d87  jb      short loc_180045D68
0x180045d89  lea     rcx, [rbp+arg_10]
0x180045d8d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180045d92  nop
0x180045d93  lea     rcx, [rbp+arg_18]
0x180045d97  call    ??1?$unique_ptr@U_TOKEN_GROUPS@@U?$default_delete@U_TOKEN_GROUPS@@@std@@@std@@QEAA@XZ; std::unique_ptr<_TOKEN_GROUPS>::~unique_ptr<_TOKEN_GROUPS>(void)
0x180045d9c  xor     al, al
0x180045d9e  add     rsp, 30h
0x180045da2  pop     r14
0x180045da4  pop     rdi
0x180045da5  pop     rsi
0x180045da6  pop     rbx
0x180045da7  pop     rbp
0x180045da8  retn
0x180045da9  lea     rcx, [rbp+arg_10]
0x180045dad  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180045db2  nop
0x180045db3  lea     rcx, [rbp+arg_18]
0x180045db7  call    ??1?$unique_ptr@U_TOKEN_GROUPS@@U?$default_delete@U_TOKEN_GROUPS@@@std@@@std@@QEAA@XZ; std::unique_ptr<_TOKEN_GROUPS>::~unique_ptr<_TOKEN_GROUPS>(void)
0x180045dbc  mov     al, 1
0x180045dbe  jmp     short loc_180045D9E
0x180045dc0  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180045dc7  mov     edx, 974h; void *
0x180045dcc  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180045dd2  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180045dd9  mov     edx, 969h; void *
0x180045dde  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180045de4  mov     r9d, 8000FFFFh; char *
0x180045dea  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180045df1  mov     edx, 965h; void *
0x180045df6  mov     rcx, rbx; this
0x180045df9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180045dff  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180045e06  mov     edx, 966h; void *
0x180045e0b  mov     rcx, rbx; this
0x180045e0e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180045e14  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180045e1b  mov     edx, 96Ch; void *
0x180045e20  mov     rcx, rbx; this
0x180045e23  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180045e29  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180045e30  mov     edx, 976h; void *
0x180045e35  mov     rcx, r14; this
0x180045e38  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
