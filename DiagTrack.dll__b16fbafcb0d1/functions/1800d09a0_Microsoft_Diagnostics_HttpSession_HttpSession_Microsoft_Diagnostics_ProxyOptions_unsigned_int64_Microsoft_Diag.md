# Microsoft::Diagnostics::HttpSession::HttpSession(Microsoft::Diagnostics::ProxyOptions,unsigned __int64,Microsoft::Diagnostics::HttpTimeouts *)

- ea: `0x1800d09a0`
- end: `0x1800d0c19`
- name: `??0HttpSession@Diagnostics@Microsoft@@QEAA@VProxyOptions@12@_KPEAUHttpTimeouts@12@@Z`
- size: `633`
- prototype: `_QWORD __high(struct Microsoft::Diagnostics::ProxyOptions, unsigned __int64, struct Microsoft::Diagnostics::HttpTimeouts *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800cff50`

## callees

- `0x180024cd8`
- `0x18002abb4`
- `0x180064e34`
- `0x18008a4ec`
- `0x1800bc658`
- `0x1800d09a0`
- `0x1800d0e8c`
- `0x1800d0ed4`
- `0x1800d0f9c`
- `0x1801b2084`
- `0x1801c2d0c`
- `0x18020aac0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800d0b1d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800d0b1d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800d0a34`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800d0a34`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1800d0b87`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1800d0b87`
- `WINHTTP!WinHttpSetOption` at `0x1800d0afa`
- `WINHTTP!WinHttpSetOption` at `0x1800d0afa`
- `WINHTTP!WinHttpSetTimeouts` at `0x1800d0ab1`
- `WINHTTP!WinHttpSetTimeouts` at `0x1800d0ab1`
- `WINHTTP!WinHttpOpen` at `0x1800d0a70`
- `WINHTTP!WinHttpOpen` at `0x1800d0a70`

## string_xrefs

- `0x1800d0bde`: `onecore\base\telemetry\utc\include\ImpersonationScope.h`
- `0x1800d0bf0`: `onecore\base\telemetry\utc\include\ImpersonationScope.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Microsoft::Diagnostics::HttpSession::HttpSession(
        __int64 a1,
        Microsoft::Diagnostics::ProxyOptions *a2,
        __int64 a3,
        int *a4)
{
  __int64 v7; // rdx
  __int64 v8; // r8
  HINTERNET *v9; // r15
  void *v10; // rcx
  const char *v11; // r9
  const WCHAR *ProxyName; // rbx
  DWORD AccessType; // eax
  HINTERNET v14; // rax
  const char *v15; // r9
  int v16; // edx
  int v17; // r8d
  int v18; // r9d
  int v19; // eax
  const char *v20; // r9
  DWORD v21; // edx
  _QWORD *i; // rbx
  const char *v23; // r9
  const char *v24; // r9
  int UserToken; // eax
  DWORD dwFlags; // [rsp+20h] [rbp-50h]
  _QWORD v28[3]; // [rsp+30h] [rbp-40h] BYREF
  _DWORD v29[6]; // [rsp+48h] [rbp-28h] BYREF
  __int64 v30; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v28[1] = a1;
  v28[2] = a2;
  std::wstring::wstring(a1, a2);
  *(_DWORD *)(a1 + 32) = *(_DWORD *)(v7 + 32);
  std::wstring::wstring(a1 + 40, v7 + 40);
  std::wstring::wstring(a1 + 72, (char *)a2 + 72);
  *(_BYTE *)(a1 + 104) = *((_BYTE *)a2 + 104);
  *(_QWORD *)(a1 + 112) = v8;
  *(_QWORD *)(a1 + 120) = 0;
  v9 = (HINTERNET *)(a1 + 128);
  *(_QWORD *)(a1 + 128) = 0;
  if ( v8 )
  {
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      a1 + 120,
      0);
    UserToken = UMgrQueryUserToken(*(_QWORD *)(a1 + 112), a1 + 120);
    if ( UserToken < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x18,
        (unsigned int)"onecore\\base\\telemetry\\http\\lib\\httpsession.cpp",
        (const char *)(unsigned int)UserToken,
        dwFlags);
      *(_QWORD *)(a1 + 112) = 0;
    }
  }
  v10 = *(void **)(a1 + 120);
  v28[0] = 0;
  if ( v10 && !ImpersonateLoggedOnUser(v10) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x18,
      (unsigned int)"onecore\\base\\telemetry\\utc\\include\\ImpersonationScope.h",
      v11);
  ProxyName = Microsoft::Diagnostics::ProxyOptions::GetProxyName((Microsoft::Diagnostics::ProxyOptions *)a1);
  AccessType = Microsoft::Diagnostics::ProxyOptions::GetAccessType((Microsoft::Diagnostics::ProxyOptions *)a1);
  v14 = WinHttpOpen(L"MSDW", AccessType, ProxyName, 0, 0x10000000u);
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    a1 + 128,
    v14);
  if ( !*v9 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x20,
      (unsigned int)"onecore\\base\\telemetry\\http\\lib\\httpsession.cpp",
      v15);
  if ( a4 )
  {
    v16 = *a4;
    v17 = a4[1];
    v18 = a4[2];
    v19 = a4[3];
  }
  else
  {
    v16 = 60000;
    v18 = 30000;
    v19 = 30000;
    v17 = 60000;
  }
  if ( !WinHttpSetTimeouts(*v9, v16, v17, v18, v19) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x2D,
      (unsigned int)"onecore\\base\\telemetry\\http\\lib\\httpsession.cpp",
      v20);
  v21 = 88;
  v29[0] = 88;
  v29[1] = 1;
  v29[2] = 73;
  v29[3] = 1;
  v29[4] = 84;
  v29[5] = 2048;
  for ( i = v29; ; v21 = *(_DWORD *)i )
  {
    if ( !WinHttpSetOption(*v9, v21, (char *)i + 4, 4u) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x38,
        (unsigned int)"onecore\\base\\telemetry\\http\\lib\\httpsession.cpp",
        v23);
    if ( ++i == &v30 )
      break;
  }
  if ( !RevertToSelf() )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x1E,
      (unsigned int)"onecore\\base\\telemetry\\utc\\include\\ImpersonationScope.h",
      v24);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v28);
  Microsoft::Diagnostics::ProxyOptions::~ProxyOptions(a2);
  return a1;
}

```

## disassembly

```asm
0x1800d09a0  mov     [rsp-28h+arg_10], rbx
0x1800d09a5  push    rbp
0x1800d09a6  push    rsi
0x1800d09a7  push    rdi
0x1800d09a8  push    r14
0x1800d09aa  push    r15
0x1800d09ac  mov     rbp, rsp
0x1800d09af  sub     rsp, 70h
0x1800d09b3  mov     rax, cs:__security_cookie
0x1800d09ba  xor     rax, rsp
0x1800d09bd  mov     [rbp+var_10], rax
0x1800d09c1  mov     rsi, r9
0x1800d09c4  mov     r14, rdx
0x1800d09c7  mov     rdi, rcx
0x1800d09ca  mov     [rbp+var_38], rcx
0x1800d09ce  mov     [rbp+var_30], rdx
0x1800d09d2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1800d09d7  mov     ecx, [rdx+20h]
0x1800d09da  mov     [rdi+20h], ecx
0x1800d09dd  add     rdx, 28h ; '('
0x1800d09e1  lea     rcx, [rdi+28h]
0x1800d09e5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1800d09ea  lea     rdx, [r14+48h]
0x1800d09ee  lea     rcx, [rdi+48h]
0x1800d09f2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1800d09f7  mov     cl, [r14+68h]
0x1800d09fb  mov     [rdi+68h], cl
0x1800d09fe  mov     [rdi+70h], r8
0x1800d0a02  lea     rbx, [rdi+78h]
0x1800d0a06  mov     qword ptr [rbx], 0
0x1800d0a0d  lea     r15, [rdi+80h]
0x1800d0a14  mov     qword ptr [r15], 0
0x1800d0a1b  test    r8, r8
0x1800d0a1e  jnz     loc_1800D0B76
0x1800d0a24  mov     rcx, [rbx]; hToken
0x1800d0a27  mov     [rbp+var_40], 0
0x1800d0a2f  test    rcx, rcx
0x1800d0a32  jz      short loc_1800D0A46
0x1800d0a34  call    cs:__imp_ImpersonateLoggedOnUser
0x1800d0a3a  mov     rcx, [rbp+28h]; this
0x1800d0a3e  test    eax, eax
0x1800d0a40  jz      loc_1800D0BF0
0x1800d0a46  mov     rcx, rdi; this
0x1800d0a49  call    ?GetProxyName@ProxyOptions@Diagnostics@Microsoft@@QEBAPEB_WXZ; Microsoft::Diagnostics::ProxyOptions::GetProxyName(void)
0x1800d0a4e  mov     rbx, rax
0x1800d0a51  mov     rcx, rdi; this
0x1800d0a54  call    ?GetAccessType@ProxyOptions@Diagnostics@Microsoft@@QEBAKXZ; Microsoft::Diagnostics::ProxyOptions::GetAccessType(void)
0x1800d0a59  mov     [rsp+70h+dwFlags], 10000000h; dwFlags
0x1800d0a61  xor     r9d, r9d; pszProxyBypassW
0x1800d0a64  mov     r8, rbx; pszProxyW
0x1800d0a67  mov     edx, eax; dwAccessType
0x1800d0a69  lea     rcx, pszAgentW; "MSDW"
0x1800d0a70  call    cs:__imp_WinHttpOpen
0x1800d0a76  mov     rdx, rax
0x1800d0a79  mov     rcx, r15
0x1800d0a7c  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?WinHttpCloseHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1800d0a81  cmp     qword ptr [r15], 0
0x1800d0a85  setz    al
0x1800d0a88  mov     rcx, [rbp+28h]; this
0x1800d0a8c  test    al, al
0x1800d0a8e  jnz     loc_1800D0B64
0x1800d0a94  test    rsi, rsi
0x1800d0a97  jz      loc_1800D0C02
0x1800d0a9d  mov     edx, [rsi]; nResolveTimeout
0x1800d0a9f  mov     r8d, [rsi+4]; nConnectTimeout
0x1800d0aa3  mov     r9d, [rsi+8]; nSendTimeout
0x1800d0aa7  mov     eax, [rsi+0Ch]
0x1800d0aaa  mov     [rsp+70h+dwFlags], eax; nReceiveTimeout
0x1800d0aae  mov     rcx, [r15]; hInternet
0x1800d0ab1  call    cs:__imp_WinHttpSetTimeouts
0x1800d0ab7  mov     rcx, [rbp+28h]; this
0x1800d0abb  test    eax, eax
0x1800d0abd  jz      loc_1800D0BCC
0x1800d0ac3  mov     edx, 58h ; 'X'; dwOption
0x1800d0ac8  mov     [rbp+var_28], edx
0x1800d0acb  lea     eax, [rdx-57h]
0x1800d0ace  mov     [rbp+var_24], eax
0x1800d0ad1  mov     [rbp+var_20], 49h ; 'I'
0x1800d0ad8  mov     [rbp+var_1C], eax
0x1800d0adb  mov     [rbp+var_18], 54h ; 'T'
0x1800d0ae2  mov     [rbp+var_14], 800h
0x1800d0ae9  lea     rbx, [rbp+var_28]
0x1800d0aed  lea     r8, [rbx+4]; lpBuffer
0x1800d0af1  mov     r9d, 4; dwBufferLength
0x1800d0af7  mov     rcx, [r15]; hInternet
0x1800d0afa  call    cs:__imp_WinHttpSetOption
0x1800d0b00  mov     rcx, [rbp+28h]; this
0x1800d0b04  test    eax, eax
0x1800d0b06  jz      loc_1800D0BBA
0x1800d0b0c  add     rbx, 8
0x1800d0b10  lea     rax, [rbp+var_10]
0x1800d0b14  cmp     rbx, rax
0x1800d0b17  jz      short loc_1800D0B1D
0x1800d0b19  mov     edx, [rbx]
0x1800d0b1b  jmp     short loc_1800D0AED
0x1800d0b1d  call    cs:__imp_RevertToSelf
0x1800d0b23  mov     rcx, [rbp+28h]; this
0x1800d0b27  test    eax, eax
0x1800d0b29  jz      loc_1800D0BDE
0x1800d0b2f  lea     rcx, [rbp+var_40]
0x1800d0b33  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800d0b38  nop
0x1800d0b39  mov     rcx, r14; this
0x1800d0b3c  call    ??1ProxyOptions@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ProxyOptions::~ProxyOptions(void)
0x1800d0b41  mov     rax, rdi
0x1800d0b44  mov     rcx, [rbp+var_10]
0x1800d0b48  xor     rcx, rsp; StackCookie
0x1800d0b4b  call    __security_check_cookie
0x1800d0b50  mov     rbx, [rsp+70h+arg_10]
0x1800d0b58  add     rsp, 70h
0x1800d0b5c  pop     r15
0x1800d0b5e  pop     r14
0x1800d0b60  pop     rdi
0x1800d0b61  pop     rsi
0x1800d0b62  pop     rbp
0x1800d0b63  retn
0x1800d0b64  lea     r8, aOnecoreBaseTel_191; "onecore\\base\\telemetry\\http\\lib\\ht"...
0x1800d0b6b  mov     edx, 20h ; ' '; void *
0x1800d0b70  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800d0b76  xor     edx, edx
0x1800d0b78  mov     rcx, rbx
0x1800d0b7b  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800d0b80  mov     rdx, rbx
0x1800d0b83  mov     rcx, [rdi+70h]
0x1800d0b87  call    cs:__imp_UMgrQueryUserToken
0x1800d0b8d  mov     rcx, [rbp+28h]; this
0x1800d0b91  test    eax, eax
0x1800d0b93  jns     loc_1800D0A24
0x1800d0b99  mov     r9d, eax; char *
0x1800d0b9c  lea     r8, aOnecoreBaseTel_191; "onecore\\base\\telemetry\\http\\lib\\ht"...
0x1800d0ba3  mov     edx, 18h; void *
0x1800d0ba8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800d0bad  mov     qword ptr [rdi+70h], 0
0x1800d0bb5  jmp     loc_1800D0A24
0x1800d0bba  lea     r8, aOnecoreBaseTel_191; "onecore\\base\\telemetry\\http\\lib\\ht"...
0x1800d0bc1  mov     edx, 38h ; '8'; void *
0x1800d0bc6  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800d0bcc  lea     r8, aOnecoreBaseTel_191; "onecore\\base\\telemetry\\http\\lib\\ht"...
0x1800d0bd3  mov     edx, 2Dh ; '-'; void *
0x1800d0bd8  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800d0bde  lea     r8, aOnecoreBaseTel_174; "onecore\\base\\telemetry\\utc\\include"...
0x1800d0be5  mov     edx, 1Eh; void *
0x1800d0bea  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800d0bf0  lea     r8, aOnecoreBaseTel_174; "onecore\\base\\telemetry\\utc\\include"...
0x1800d0bf7  mov     edx, 18h; void *
0x1800d0bfc  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800d0c02  mov     edx, 0EA60h
0x1800d0c07  mov     r9d, 7530h
0x1800d0c0d  mov     eax, r9d
0x1800d0c10  mov     r8d, edx
0x1800d0c13  jmp     loc_1800D0AAA
```
