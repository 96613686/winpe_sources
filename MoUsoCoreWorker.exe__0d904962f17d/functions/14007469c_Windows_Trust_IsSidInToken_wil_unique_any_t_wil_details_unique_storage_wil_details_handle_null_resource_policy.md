# Windows::Trust::IsSidInToken(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> const &)

- ea: `0x14007469c`
- end: `0x140074823`
- name: `?IsSidInToken@Trust@Windows@@YA_NAEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@4@@Z`
- size: `391`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14007482c`
- `0x14023c518`

## callees

- `0x14003c578`
- `0x14007469c`
- `0x140379070`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140074786`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140074786`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x14007473f`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x14007473f`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x140074763`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1400747a1`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x140074763`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1400747a1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400746fe`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400746fe`

## string_xrefs

- `0x1400747d2`: `C:\__w\1\s\src\orchestrator\system\windows\common\Trust.cpp`
- `0x1400747e4`: `C:\__w\1\s\src\orchestrator\system\windows\common\Trust.cpp`
- `0x1400747f9`: `C:\__w\1\s\src\orchestrator\system\windows\common\Trust.cpp`
- `0x14007480e`: `C:\__w\1\s\src\orchestrator\system\windows\common\Trust.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall Windows::Trust::IsSidInToken(HANDLE *a1, PSID *a2)
{
  HANDLE v4; // rcx
  const char *v5; // r9
  const char *v6; // r9
  const char *v7; // r9
  bool v8; // bl
  const char *v10; // r9
  int TokenInformation; // [rsp+30h] [rbp-20h] BYREF
  WINBOOL IsMember; // [rsp+34h] [rbp-1Ch] BYREF
  WINBOOL v13; // [rsp+38h] [rbp-18h] BYREF
  DWORD ReturnLength; // [rsp+3Ch] [rbp-14h] BYREF
  HANDLE TokenHandle; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]

  v4 = *a1;
  if ( !v4 || v4 == (HANDLE)-1LL )
    goto LABEL_10;
  ReturnLength = 0;
  TokenInformation = 1;
  if ( !GetTokenInformation(v4, TokenType, &TokenInformation, 4u, &ReturnLength) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x107,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\Trust.cpp",
      v5);
  if ( TokenInformation == 2 )
  {
LABEL_10:
    v13 = 0;
    if ( !CheckTokenMembership(*a1, *a2, &v13) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x116,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\Trust.cpp",
        v10);
    return v13 != 0;
  }
  else
  {
    TokenHandle = 0;
    if ( !DuplicateTokenEx(*a1, 8u, 0, SecurityIdentification, TokenImpersonation, &TokenHandle) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x10C,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\Trust.cpp",
        v6);
    IsMember = 0;
    if ( !CheckTokenMembership(TokenHandle, *a2, &IsMember) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x10F,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\Trust.cpp",
        v7);
    v8 = IsMember != 0;
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    return v8;
  }
}

```

## disassembly

```asm
0x14007469c  mov     [rsp-18h+arg_10], rbx
0x1400746a1  push    rbp
0x1400746a2  push    rsi
0x1400746a3  push    rdi
0x1400746a4  mov     rbp, rsp
0x1400746a7  sub     rsp, 50h
0x1400746ab  mov     rax, cs:__security_cookie
0x1400746b2  xor     rax, rsp
0x1400746b5  mov     [rbp+var_8], rax
0x1400746b9  mov     rdi, rdx
0x1400746bc  mov     rbx, rcx
0x1400746bf  mov     rcx, [rcx]; TokenHandle
0x1400746c2  test    rcx, rcx
0x1400746c5  jz      loc_140074790
0x1400746cb  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400746cf  jz      loc_140074790
0x1400746d5  mov     [rbp+var_14], 0
0x1400746dc  mov     [rbp+TokenInformation], 1
0x1400746e3  mov     rsi, [rbp+18h]
0x1400746e7  lea     rax, [rbp+var_14]
0x1400746eb  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x1400746f0  mov     r9d, 4; TokenInformationLength
0x1400746f6  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1400746fa  lea     edx, [r9+4]; TokenInformationClass
0x1400746fe  call    cs:__imp_GetTokenInformation
0x140074704  test    eax, eax
0x140074706  jz      loc_1400747E4
0x14007470c  cmp     [rbp+TokenInformation], 2
0x140074710  jz      short loc_140074790
0x140074712  mov     [rbp+TokenHandle], 0
0x14007471a  mov     rsi, [rbp+18h]
0x14007471e  lea     rax, [rbp+TokenHandle]
0x140074722  mov     [rsp+50h+phNewToken], rax; phNewToken
0x140074727  mov     dword ptr [rsp+50h+ReturnLength], 2; TokenType
0x14007472f  mov     r9d, 1; ImpersonationLevel
0x140074735  xor     r8d, r8d; lpTokenAttributes
0x140074738  lea     edx, [r9+7]; dwDesiredAccess
0x14007473c  mov     rcx, [rbx]; hExistingToken
0x14007473f  call    cs:__imp_DuplicateTokenEx
0x140074745  test    eax, eax
0x140074747  jz      loc_1400747F9
0x14007474d  mov     [rbp+IsMember], 0
0x140074754  mov     rbx, [rbp+18h]
0x140074758  lea     r8, [rbp+IsMember]; IsMember
0x14007475c  mov     rdx, [rdi]; SidToCheck
0x14007475f  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x140074763  call    cs:__imp_CheckTokenMembership
0x140074769  test    eax, eax
0x14007476b  jz      loc_14007480E
0x140074771  cmp     [rbp+IsMember], 0
0x140074775  setnz   bl
0x140074778  mov     rcx, [rbp+TokenHandle]; hObject
0x14007477c  lea     rdx, [rcx-1]
0x140074780  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x140074784  ja      short loc_14007478C
0x140074786  call    cs:__imp_CloseHandle
0x14007478c  mov     al, bl
0x14007478e  jmp     short loc_1400747B2
0x140074790  mov     [rbp+var_18], 0
0x140074797  lea     r8, [rbp+var_18]; IsMember
0x14007479b  mov     rdx, [rdi]; SidToCheck
0x14007479e  mov     rcx, [rbx]; TokenHandle
0x1400747a1  call    cs:__imp_CheckTokenMembership
0x1400747a7  test    eax, eax
0x1400747a9  jz      short loc_1400747CE
0x1400747ab  cmp     [rbp+var_18], 0
0x1400747af  setnz   al
0x1400747b2  mov     rcx, [rbp+var_8]
0x1400747b6  xor     rcx, rsp; StackCookie
0x1400747b9  call    __security_check_cookie
0x1400747be  mov     rbx, [rsp+50h+arg_10]
0x1400747c6  add     rsp, 50h
0x1400747ca  pop     rdi
0x1400747cb  pop     rsi
0x1400747cc  pop     rbp
0x1400747cd  retn
0x1400747ce  mov     rcx, [rbp+18h]; this
0x1400747d2  lea     r8, aCW1SSrcOrchest_114; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1400747d9  mov     edx, 116h; void *
0x1400747de  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400747e4  lea     r8, aCW1SSrcOrchest_114; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1400747eb  mov     edx, 107h; void *
0x1400747f0  mov     rcx, rsi; this
0x1400747f3  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400747f9  lea     r8, aCW1SSrcOrchest_114; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140074800  mov     edx, 10Ch; void *
0x140074805  mov     rcx, rsi; this
0x140074808  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14007480e  lea     r8, aCW1SSrcOrchest_114; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140074815  mov     edx, 10Fh; void *
0x14007481a  mov     rcx, rbx; this
0x14007481d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
