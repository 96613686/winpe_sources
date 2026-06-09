# GetCallerTokenHandleForImpersonation(void)

- ea: `0x180036318`
- end: `0x18003646d`
- name: `?GetCallerTokenHandleForImpersonation@@YA?AV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@XZ`
- size: `341`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800179d8`
- `0x1800180d8`
- `0x18002b9f0`
- `0x18002ce04`

## callees

- `0x180003a00`
- `0x180004b24`
- `0x180004c3c`
- `0x180011318`
- `0x180011334`
- `0x180034f80`
- `0x1800362a0`
- `0x180036318`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036393`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036393`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180036373`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180036373`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x1800363cc`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x1800363cc`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x1800363ef`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x1800363ef`

## string_xrefs

- `0x180036417`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageproviderutils.cpp`
- `0x18003642d`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageproviderutils.cpp`
- `0x180036449`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageproviderutils.cpp`
- `0x18003645b`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageproviderutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall GetCallerTokenHandleForImpersonation(_QWORD *a1)
{
  HANDLE *CallerTokenHandleForIdentification; // rax
  const char *v3; // r9
  void **v4; // rax
  const char *v5; // r9
  __int64 v6; // rax
  const char *v7; // r9
  unsigned int ReturnLength; // [rsp+20h] [rbp-40h]
  HANDLE hObject[2]; // [rsp+38h] [rbp-28h] BYREF
  ULONG TokenInformation; // [rsp+48h] [rbp-18h] BYREF
  DWORD v12; // [rsp+4Ch] [rbp-14h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  hObject[1] = a1;
  TokenInformation = 0;
  v12 = 0;
  CallerTokenHandleForIdentification = (HANDLE *)GetCallerTokenHandleForIdentification(hObject);
  if ( !GetTokenInformation(*CallerTokenHandleForIdentification, TokenSessionId, &TokenInformation, 4u, &v12) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x171,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageproviderutils.cpp",
      v3);
  if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(hObject[0]);
  *(_OWORD *)a1 = 0;
  *a1 = 0;
  a1[1] = 0;
  if ( (unsigned __int8)IsWTSEnumerateSessionsWPresent() )
  {
    v4 = (void **)wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::addressof<wistd::integral_constant<unsigned __int64,0>,0>(a1);
    if ( !WTSQueryUserToken(TokenInformation, v4) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x176,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageproviderutils.cpp",
        v5);
  }
  else
  {
    if ( !(unsigned __int8)IsQueryUserTokenPresent() )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x17E,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageproviderutils.cpp",
        (const char *)0x522,
        ReturnLength);
    v6 = wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::addressof<wistd::integral_constant<unsigned __int64,0>,0>(a1);
    if ( !(unsigned int)QueryUserToken(TokenInformation, v6) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x17A,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageproviderutils.cpp",
        v7);
  }
  return a1;
}

```

## disassembly

```asm
0x180036318  mov     [rsp-8+arg_8], rbx
0x18003631d  push    rbp
0x18003631e  mov     rbp, rsp
0x180036321  sub     rsp, 60h
0x180036325  mov     rax, cs:__security_cookie
0x18003632c  xor     rax, rsp
0x18003632f  mov     [rbp+var_10], rax
0x180036333  mov     rbx, rcx
0x180036336  mov     [rbp+var_20], rcx
0x18003633a  mov     [rbp+var_30], 0
0x180036341  mov     [rbp+TokenInformation], 0
0x180036348  mov     [rbp+var_14], 0
0x18003634f  lea     rcx, [rbp+hObject]
0x180036353  call    ?GetCallerTokenHandleForIdentification@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; GetCallerTokenHandleForIdentification(void)
0x180036358  nop
0x180036359  lea     rcx, [rbp+var_14]
0x18003635d  mov     qword ptr [rsp+60h+ReturnLength], rcx; unsigned int
0x180036362  mov     r9d, 4; TokenInformationLength
0x180036368  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18003636c  lea     edx, [r9+8]; TokenInformationClass
0x180036370  mov     rcx, [rax]; TokenHandle
0x180036373  call    cs:__imp_GetTokenInformation
0x180036379  mov     rcx, [rbp+8]; this
0x18003637d  test    eax, eax
0x18003637f  jz      loc_18003645B
0x180036385  mov     rcx, [rbp+hObject]; hObject
0x180036389  lea     rax, [rcx-1]
0x18003638d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180036391  ja      short loc_180036399
0x180036393  call    cs:__imp_CloseHandle
0x180036399  xorps   xmm0, xmm0
0x18003639c  movups  xmmword ptr [rbx], xmm0
0x18003639f  mov     qword ptr [rbx], 0
0x1800363a6  mov     qword ptr [rbx+8], 0
0x1800363ae  mov     [rbp+var_30], 1
0x1800363b5  call    IsWTSEnumerateSessionsWPresent
0x1800363ba  test    al, al
0x1800363bc  jz      short loc_1800363D8
0x1800363be  mov     rcx, rbx
0x1800363c1  call    ??$addressof@U?$integral_constant@_K$0A@@wistd@@$0A@@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAPEAPEAXXZ; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::addressof<wistd::integral_constant<unsigned __int64,0>,0>(void)
0x1800363c6  mov     rdx, rax; phToken
0x1800363c9  mov     ecx, [rbp+TokenInformation]; SessionId
0x1800363cc  call    cs:__imp_WTSQueryUserToken
0x1800363d2  test    eax, eax
0x1800363d4  jz      short loc_180036429
0x1800363d6  jmp     short loc_1800363F9
0x1800363d8  call    IsQueryUserTokenPresent
0x1800363dd  test    al, al
0x1800363df  jz      short loc_18003643F
0x1800363e1  mov     rcx, rbx
0x1800363e4  call    ??$addressof@U?$integral_constant@_K$0A@@wistd@@$0A@@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAPEAPEAXXZ; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::addressof<wistd::integral_constant<unsigned __int64,0>,0>(void)
0x1800363e9  mov     rdx, rax
0x1800363ec  mov     ecx, [rbp+TokenInformation]
0x1800363ef  call    cs:__imp_QueryUserToken
0x1800363f5  test    eax, eax
0x1800363f7  jz      short loc_180036413
0x1800363f9  mov     rax, rbx
0x1800363fc  mov     rcx, [rbp+var_10]
0x180036400  xor     rcx, rsp; StackCookie
0x180036403  call    __security_check_cookie
0x180036408  mov     rbx, [rsp+60h+arg_8]
0x18003640d  add     rsp, 60h
0x180036411  pop     rbp
0x180036412  retn
0x180036413  mov     rcx, [rbp+8]; this
0x180036417  lea     r8, aOnecoreBaseLan_17; "onecore\\base\\languageoverlay\\service"...
0x18003641e  mov     edx, 17Ah; void *
0x180036423  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180036429  mov     rcx, [rbp+8]; this
0x18003642d  lea     r8, aOnecoreBaseLan_17; "onecore\\base\\languageoverlay\\service"...
0x180036434  mov     edx, 176h; void *
0x180036439  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18003643f  mov     rcx, [rbp+8]; this
0x180036443  mov     r9d, 522h; char *
0x180036449  lea     r8, aOnecoreBaseLan_17; "onecore\\base\\languageoverlay\\service"...
0x180036450  mov     edx, 17Eh; void *
0x180036455  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18003645b  lea     r8, aOnecoreBaseLan_17; "onecore\\base\\languageoverlay\\service"...
0x180036462  mov     edx, 171h; void *
0x180036467  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
