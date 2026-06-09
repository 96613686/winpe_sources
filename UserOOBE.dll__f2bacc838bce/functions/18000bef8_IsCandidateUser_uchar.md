# IsCandidateUser(uchar *)

- ea: `0x18000bef8`
- end: `0x18000c05a`
- name: `?IsCandidateUser@@YAJPEAE@Z`
- size: `354`
- prototype: `__int64 __fastcall(unsigned __int8 *)`
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000ac54`
- `0x18000b6c0`
- `0x18002bce0`

## callees

- `0x1800046c4`
- `0x1800054ac`
- `0x180005768`
- `0x180007114`
- `0x180007134`
- `0x18000a5e8`
- `0x18000bc50`
- `0x18000bef8`
- `0x18000e270`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bf71`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bf71`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000bf90`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000bf90`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamIsEphemeralCandidateUser` at `0x18000c01a`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamIsEphemeralCandidateUser` at `0x18000c01a`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamIsCandidateUser` at `0x18000bfe8`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamIsCandidateUser` at `0x18000bfe8`

## pseudocode

```c
__int64 __fastcall IsCandidateUser(unsigned __int8 *a1)
{
  void *v2; // rcx
  int UserSidFromToken; // eax
  unsigned int LastError; // ebx
  HLOCAL v5; // rbx
  const char *v6; // r9
  int v8; // eax
  int IsEphemeralCandidateUser; // eax
  int v10[4]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  int v12; // [rsp+50h] [rbp+20h] BYREF
  int v13; // [rsp+58h] [rbp+28h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp+30h] BYREF
  LPCWSTR StringSid; // [rsp+68h] [rbp+38h] BYREF

  *a1 = 0;
  if ( !(unsigned __int8)IsCamIsEphemeralCandidateUserPresent()
    || !(unsigned __int8)IsCamIsEphemeralCandidateUserPresent() )
  {
    return 0;
  }
  hMem = 0;
  StringSid = 0;
  UserSidFromToken = GetUserSidFromToken(v2, (unsigned __int16 **)&StringSid);
  LastError = UserSidFromToken;
  if ( UserSidFromToken < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E,
      (unsigned int)"onecore\\internal\\shell\\inc\\private\\candidateuserhelpers.h",
      (const char *)(unsigned int)UserSidFromToken,
      v10[0]);
LABEL_9:
    wil::details::unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>(&StringSid);
    wil::details::unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>(&hMem);
    return LastError;
  }
  v5 = hMem;
  if ( hMem )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v10);
    LocalFree(v5);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v10);
  }
  hMem = 0;
  if ( !ConvertStringSidToSidW(StringSid, &hMem) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x2F,
                  (unsigned int)"onecore\\internal\\shell\\inc\\private\\candidateuserhelpers.h",
                  v6);
    goto LABEL_9;
  }
  wil::details::unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>(&StringSid);
  v12 = 0;
  v13 = 0;
  v8 = CamIsCandidateUser(hMem, &v12);
  if ( v8 >= 0 )
  {
    if ( v12 )
      goto LABEL_16;
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x34,
      (unsigned int)"onecore\\internal\\shell\\inc\\private\\candidateuserhelpers.h",
      (const char *)(unsigned int)v8,
      v10[0]);
  }
  IsEphemeralCandidateUser = CamIsEphemeralCandidateUser(hMem, &v13);
  if ( IsEphemeralCandidateUser >= 0 )
  {
    if ( !v13 )
      goto LABEL_17;
LABEL_16:
    *a1 = 1;
    goto LABEL_17;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x35,
    (unsigned int)"onecore\\internal\\shell\\inc\\private\\candidateuserhelpers.h",
    (const char *)(unsigned int)IsEphemeralCandidateUser,
    v10[0]);
LABEL_17:
  wil::details::unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>(&hMem);
  return 0;
}

```

## disassembly

```asm
0x18000bef8  push    rbp
0x18000befa  push    rbx
0x18000befb  push    rdi
0x18000befc  mov     rbp, rsp
0x18000beff  sub     rsp, 30h
0x18000bf03  mov     rdi, rcx
0x18000bf06  mov     byte ptr [rcx], 0
0x18000bf09  call    IsCamIsEphemeralCandidateUserPresent
0x18000bf0e  test    al, al
0x18000bf10  jz      loc_18000C050
0x18000bf16  call    IsCamIsEphemeralCandidateUserPresent
0x18000bf1b  test    al, al
0x18000bf1d  jz      loc_18000C050
0x18000bf23  mov     [rbp+hMem], 0
0x18000bf2b  mov     [rbp+StringSid], 0
0x18000bf33  lea     rdx, [rbp+StringSid]; unsigned __int16 **
0x18000bf37  call    ?GetUserSidFromToken@@YAJQEAXPEAPEAG@Z; GetUserSidFromToken(void * const,ushort * *)
0x18000bf3c  mov     ebx, eax
0x18000bf3e  test    eax, eax
0x18000bf40  jns     short loc_18000BF5C
0x18000bf42  mov     rcx, [rbp+18h]; this
0x18000bf46  mov     r9d, eax; char *
0x18000bf49  lea     r8, aOnecoreInterna_7; "onecore\\internal\\shell\\inc\\private"...
0x18000bf50  mov     edx, 2Eh ; '.'; void *
0x18000bf55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bf5a  jmp     short loc_18000BFAF
0x18000bf5c  mov     rbx, [rbp+hMem]
0x18000bf60  test    rbx, rbx
0x18000bf63  jz      short loc_18000BF80
0x18000bf65  lea     rcx, [rbp+var_10]; this
0x18000bf69  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000bf6e  mov     rcx, rbx; hMem
0x18000bf71  call    cs:__imp_LocalFree
0x18000bf77  lea     rcx, [rbp+var_10]; this
0x18000bf7b  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000bf80  mov     [rbp+hMem], 0
0x18000bf88  lea     rdx, [rbp+hMem]; Sid
0x18000bf8c  mov     rcx, [rbp+StringSid]; StringSid
0x18000bf90  call    cs:__imp_ConvertStringSidToSidW
0x18000bf96  test    eax, eax
0x18000bf98  jnz     short loc_18000BFC9
0x18000bf9a  mov     rcx, [rbp+18h]; this
0x18000bf9e  lea     r8, aOnecoreInterna_7; "onecore\\internal\\shell\\inc\\private"...
0x18000bfa5  lea     edx, [rax+2Fh]; void *
0x18000bfa8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000bfad  mov     ebx, eax
0x18000bfaf  lea     rcx, [rbp+StringSid]
0x18000bfb3  call    ??1?$unique_storage@U?$resource_policy@PEAU_TOKEN_GROUPS@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>(void)
0x18000bfb8  nop
0x18000bfb9  lea     rcx, [rbp+hMem]
0x18000bfbd  call    ??1?$unique_storage@U?$resource_policy@PEAU_TOKEN_GROUPS@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>(void)
0x18000bfc2  mov     eax, ebx
0x18000bfc4  jmp     loc_18000C052
0x18000bfc9  lea     rcx, [rbp+StringSid]
0x18000bfcd  call    ??1?$unique_storage@U?$resource_policy@PEAU_TOKEN_GROUPS@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>(void)
0x18000bfd2  mov     [rbp+arg_0], 0
0x18000bfd9  mov     [rbp+arg_8], 0
0x18000bfe0  lea     rdx, [rbp+arg_0]
0x18000bfe4  mov     rcx, [rbp+hMem]
0x18000bfe8  call    cs:__imp_CamIsCandidateUser
0x18000bfee  mov     rcx, [rbp+18h]; this
0x18000bff2  test    eax, eax
0x18000bff4  jns     short loc_18000C00C
0x18000bff6  mov     r9d, eax; char *
0x18000bff9  lea     r8, aOnecoreInterna_7; "onecore\\internal\\shell\\inc\\private"...
0x18000c000  mov     edx, 34h ; '4'; void *
0x18000c005  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000c00a  jmp     short loc_18000C012
0x18000c00c  cmp     [rbp+arg_0], 0
0x18000c010  jnz     short loc_18000C044
0x18000c012  lea     rdx, [rbp+arg_8]
0x18000c016  mov     rcx, [rbp+hMem]
0x18000c01a  call    cs:__imp_CamIsEphemeralCandidateUser
0x18000c020  mov     rcx, [rbp+18h]; this
0x18000c024  test    eax, eax
0x18000c026  jns     short loc_18000C03E
0x18000c028  mov     r9d, eax; char *
0x18000c02b  lea     r8, aOnecoreInterna_7; "onecore\\internal\\shell\\inc\\private"...
0x18000c032  mov     edx, 35h ; '5'; void *
0x18000c037  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000c03c  jmp     short loc_18000C047
0x18000c03e  cmp     [rbp+arg_8], 0
0x18000c042  jz      short loc_18000C047
0x18000c044  mov     byte ptr [rdi], 1
0x18000c047  lea     rcx, [rbp+hMem]
0x18000c04b  call    ??1?$unique_storage@U?$resource_policy@PEAU_TOKEN_GROUPS@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>(void)
0x18000c050  xor     eax, eax
0x18000c052  add     rsp, 30h
0x18000c056  pop     rdi
0x18000c057  pop     rbx
0x18000c058  pop     rbp
0x18000c059  retn
```
