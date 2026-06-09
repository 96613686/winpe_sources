# BitsHelper::IsLocalSystem(bool *)

- ea: `0x140011418`
- end: `0x1400115e5`
- name: `?IsLocalSystem@BitsHelper@@AEAAJPEA_N@Z`
- size: `461`
- prototype: `__int64 __fastcall(BitsHelper *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14000ff7c`

## callees

- `0x140002f40`
- `0x14000a49c`
- `0x14000a4bc`
- `0x14000f538`
- `0x14000fa20`
- `0x14000fa64`
- `0x140011418`
- `0x140011a4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001149c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001149c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140011456`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140011456`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140011446`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140011446`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x140011598`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x140011598`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x140011561`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x140011561`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140011496`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400114f7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140011496`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400114f7`

## string_xrefs

- `0x140011464`: `onecore\windows\directx\database\updater\exe\bitshelper.cpp`
- `0x1400114b3`: `onecore\windows\directx\database\updater\exe\bitshelper.cpp`
- `0x140011505`: `onecore\windows\directx\database\updater\exe\bitshelper.cpp`
- `0x14001156f`: `onecore\windows\directx\database\updater\exe\bitshelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BitsHelper::IsLocalSystem(BitsHelper *this, bool *a2)
{
  HANDLE CurrentProcess; // rax
  const char *v4; // r9
  unsigned int LastError; // ebx
  const char *v6; // r9
  const char *v7; // r9
  int ReturnLength; // [rsp+20h] [rbp-29h]
  _BYTE v10[4]; // [rsp+60h] [rbp+17h] BYREF
  DWORD TokenInformationLength; // [rsp+64h] [rbp+1Bh] BYREF
  PSID pSid1; // [rsp+68h] [rbp+1Fh] BYREF
  HANDLE TokenHandle; // [rsp+70h] [rbp+27h] BYREF
  LPVOID TokenInformation[3]; // [rsp+78h] [rbp+2Fh] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+90h] [rbp+47h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    TokenInformationLength = 0;
    GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
    if ( GetLastError() == 122 )
    {
      v10[0] = 0;
      std::vector<unsigned char>::vector<unsigned char>(TokenInformation, TokenInformationLength, v10);
      if ( GetTokenInformation(
             TokenHandle,
             TokenUser,
             TokenInformation[0],
             TokenInformationLength,
             &TokenInformationLength) )
      {
        *(_DWORD *)pIdentifierAuthority.Value = 0;
        *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
        pSid1 = 0;
        if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid1) )
        {
          *a2 = EqualSid(pSid1, *(PSID *)TokenInformation[0]);
          wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pSid1);
          std::vector<unsigned char>::_Tidy(TokenInformation);
          LastError = 0;
          goto LABEL_11;
        }
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x1D7,
                      (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
                      v7);
        wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pSid1);
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x1C7,
                      (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
                      v6);
      }
      std::vector<unsigned char>::_Tidy(TokenInformation);
    }
    else
    {
      LastError = -2147418113;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1BF,
        (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
        (const char *)0x8000FFFFLL,
        ReturnLength);
    }
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1B7,
                  (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\bitshelper.cpp",
                  v4);
  }
LABEL_11:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x140011418  mov     [rsp-8+arg_0], rbx
0x14001141d  mov     [rsp-8+arg_10], rdi
0x140011422  push    rbp
0x140011423  lea     rbp, [rsp-57h]
0x140011428  sub     rsp, 0A0h
0x14001142f  mov     rax, cs:__security_cookie
0x140011436  xor     rax, rsp
0x140011439  mov     [rbp+57h+var_8], rax
0x14001143d  mov     rbx, rdx
0x140011440  xor     edi, edi
0x140011442  mov     [rbp+57h+TokenHandle], rdi
0x140011446  call    cs:__imp_GetCurrentProcess
0x14001144c  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x140011450  lea     edx, [rdi+8]; DesiredAccess
0x140011453  mov     rcx, rax; ProcessHandle
0x140011456  call    cs:__imp_OpenProcessToken
0x14001145c  test    eax, eax
0x14001145e  jnz     short loc_14001147C
0x140011460  mov     rcx, [rbp+5Fh]; this
0x140011464  lea     r8, aOnecoreWindows; "onecore\\windows\\directx\\database\\up"...
0x14001146b  mov     edx, 1B7h; void *
0x140011470  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140011475  mov     ebx, eax
0x140011477  jmp     loc_1400115B9
0x14001147c  mov     [rbp+57h+TokenInformationLength], edi
0x14001147f  lea     rax, [rbp+57h+TokenInformationLength]
0x140011483  mov     [rsp+0A0h+ReturnLength], rax; int
0x140011488  xor     r9d, r9d; TokenInformationLength
0x14001148b  xor     r8d, r8d; TokenInformation
0x14001148e  lea     edx, [r9+1]; TokenInformationClass
0x140011492  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x140011496  call    cs:__imp_GetTokenInformation
0x14001149c  call    cs:__imp_GetLastError
0x1400114a2  cmp     eax, 7Ah ; 'z'
0x1400114a5  jz      short loc_1400114C9
0x1400114a7  mov     rcx, [rbp+5Fh]; this
0x1400114ab  mov     ebx, 8000FFFFh
0x1400114b0  mov     r9d, ebx; char *
0x1400114b3  lea     r8, aOnecoreWindows; "onecore\\windows\\directx\\database\\up"...
0x1400114ba  mov     edx, 1BFh; void *
0x1400114bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400114c4  jmp     loc_1400115B9
0x1400114c9  mov     [rbp+57h+var_40], dil
0x1400114cd  mov     edx, [rbp+57h+TokenInformationLength]
0x1400114d0  lea     r8, [rbp+57h+var_40]
0x1400114d4  lea     rcx, [rbp+57h+TokenInformation]
0x1400114d8  call    ??$?0V?$allocator@E@std@@$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBEAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,uchar const &,std::allocator<uchar> const &)
0x1400114dd  lea     rax, [rbp+57h+TokenInformationLength]
0x1400114e1  mov     [rsp+0A0h+ReturnLength], rax; ReturnLength
0x1400114e6  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x1400114ea  mov     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1400114ee  mov     edx, 1; TokenInformationClass
0x1400114f3  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1400114f7  call    cs:__imp_GetTokenInformation
0x1400114fd  test    eax, eax
0x1400114ff  jnz     short loc_140011526
0x140011501  mov     rcx, [rbp+5Fh]; this
0x140011505  lea     r8, aOnecoreWindows; "onecore\\windows\\directx\\database\\up"...
0x14001150c  mov     edx, 1C7h; void *
0x140011511  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140011516  mov     ebx, eax
0x140011518  lea     rcx, [rbp+57h+TokenInformation]
0x14001151c  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140011521  jmp     loc_1400115B9
0x140011526  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], edi
0x140011529  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x14001152f  mov     [rbp+57h+pSid1], rdi
0x140011533  lea     rax, [rbp+57h+pSid1]
0x140011537  mov     [rsp+0A0h+pSid], rax; pSid
0x14001153c  mov     [rsp+0A0h+nSubAuthority7], edi; nSubAuthority7
0x140011540  mov     [rsp+0A0h+nSubAuthority6], edi; nSubAuthority6
0x140011544  mov     [rsp+0A0h+nSubAuthority5], edi; nSubAuthority5
0x140011548  mov     [rsp+0A0h+nSubAuthority4], edi; nSubAuthority4
0x14001154c  mov     [rsp+0A0h+nSubAuthority3], edi; nSubAuthority3
0x140011550  mov     dword ptr [rsp+0A0h+ReturnLength], edi; nSubAuthority2
0x140011554  xor     r9d, r9d; nSubAuthority1
0x140011557  lea     r8d, [r9+12h]; nSubAuthority0
0x14001155b  mov     dl, 1; nSubAuthorityCount
0x14001155d  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x140011561  call    cs:__imp_AllocateAndInitializeSid
0x140011567  test    eax, eax
0x140011569  jnz     short loc_14001158D
0x14001156b  mov     rcx, [rbp+5Fh]; this
0x14001156f  lea     r8, aOnecoreWindows; "onecore\\windows\\directx\\database\\up"...
0x140011576  mov     edx, 1D7h; void *
0x14001157b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140011580  mov     ebx, eax
0x140011582  lea     rcx, [rbp+57h+pSid1]
0x140011586  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14001158b  jmp     short loc_140011518
0x14001158d  mov     rdx, [rbp+57h+TokenInformation]
0x140011591  mov     rdx, [rdx]; pSid2
0x140011594  mov     rcx, [rbp+57h+pSid1]; pSid1
0x140011598  call    cs:__imp_EqualSid
0x14001159e  test    eax, eax
0x1400115a0  setnz   al
0x1400115a3  mov     [rbx], al
0x1400115a5  lea     rcx, [rbp+57h+pSid1]
0x1400115a9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1400115ae  lea     rcx, [rbp+57h+TokenInformation]
0x1400115b2  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1400115b7  mov     ebx, edi
0x1400115b9  lea     rcx, [rbp+57h+TokenHandle]
0x1400115bd  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400115c2  mov     eax, ebx
0x1400115c4  mov     rcx, [rbp+57h+var_8]
0x1400115c8  xor     rcx, rsp; StackCookie
0x1400115cb  call    __security_check_cookie
0x1400115d0  lea     r11, [rsp+0A0h+var_s0]
0x1400115d8  mov     rbx, [r11+10h]
0x1400115dc  mov     rdi, [r11+20h]
0x1400115e0  mov     rsp, r11
0x1400115e3  pop     rbp
0x1400115e4  retn
```
