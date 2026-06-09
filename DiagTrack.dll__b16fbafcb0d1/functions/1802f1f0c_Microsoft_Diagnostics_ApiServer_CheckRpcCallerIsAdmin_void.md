# Microsoft::Diagnostics::ApiServer::CheckRpcCallerIsAdmin(void)

- ea: `0x1802f1f0c`
- end: `0x1802f206b`
- name: `?CheckRpcCallerIsAdmin@ApiServer@Diagnostics@Microsoft@@IEAAJXZ`
- size: `351`
- prototype: `__int64 __fastcall(Microsoft::Diagnostics::ApiServer *__hidden this)`
- caller_count: `7`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18012db3c`
- `0x1801eb220`
- `0x1802866dc`
- `0x1802869a4`
- `0x180287af0`
- `0x180298240`
- `0x180298ad0`

## callees

- `0x180064e6c`
- `0x180064e8c`
- `0x1801bbc78`
- `0x1802f1d34`
- `0x1802f1f0c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1802f1fac`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1802f1fac`
- `RPCRT4!RpcImpersonateClient` at `0x1802f1f1b`
- `RPCRT4!RpcImpersonateClient` at `0x1802f1f1b`
- `RPCRT4!RpcRevertToSelf` at `0x1802f1f78`
- `RPCRT4!RpcRevertToSelf` at `0x1802f1fce`
- `RPCRT4!RpcRevertToSelf` at `0x1802f2018`
- `RPCRT4!RpcRevertToSelf` at `0x1802f203d`
- `RPCRT4!RpcRevertToSelf` at `0x1802f1f78`
- `RPCRT4!RpcRevertToSelf` at `0x1802f1fce`
- `RPCRT4!RpcRevertToSelf` at `0x1802f2018`
- `RPCRT4!RpcRevertToSelf` at `0x1802f203d`

## string_xrefs

- `0x1802f1f2a`: `onecore\base\telemetry\utc\common\apiserver.cpp`
- `0x1802f1f64`: `onecore\base\telemetry\utc\common\apiserver.cpp`
- `0x1802f1f87`: `onecore\base\telemetry\utc\common\apiserver.cpp`
- `0x1802f1fbb`: `onecore\base\telemetry\utc\common\apiserver.cpp`
- `0x1802f1fe1`: `onecore\base\telemetry\utc\common\apiserver.cpp`
- `0x1802f1fff`: `onecore\base\telemetry\utc\common\apiserver.cpp`
- `0x1802f202b`: `onecore\base\telemetry\utc\common\apiserver.cpp`
- `0x1802f204c`: `onecore\base\telemetry\utc\common\apiserver.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::Diagnostics::ApiServer::CheckRpcCallerIsAdmin(Microsoft::Diagnostics::ApiServer *this)
{
  unsigned int LastError; // ebx
  int AdminSid; // eax
  const char *v5; // r9
  void *v6; // rdx
  const char *v7; // r9
  const char *v8; // r9
  const char *v9; // r9
  const char *v10; // r9
  int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  WINBOOL IsMember; // [rsp+38h] [rbp+10h] BYREF

  if ( RpcImpersonateClient(0) )
  {
    LastError = -2147024891;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC0,
      (unsigned int)"onecore\\base\\telemetry\\utc\\common\\apiserver.cpp",
      (const char *)0x80070005LL,
      v11);
    return LastError;
  }
  if ( !*((_QWORD *)this + 1) )
  {
    AdminSid = Microsoft::Diagnostics::ApiServer::AllocateAdminSid(this);
    LastError = AdminSid;
    if ( AdminSid < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD2,
        (unsigned int)"onecore\\base\\telemetry\\utc\\common\\apiserver.cpp",
        (const char *)(unsigned int)AdminSid,
        v11);
      if ( RpcRevertToSelf() )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xCB,
          (unsigned int)"onecore\\base\\telemetry\\utc\\common\\apiserver.cpp",
          v5);
      return LastError;
    }
  }
  v6 = (void *)*((_QWORD *)this + 1);
  IsMember = 0;
  if ( !CheckTokenMembership(0, v6, &IsMember) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xD6,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\common\\apiserver.cpp",
                  v7);
    if ( RpcRevertToSelf() )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xCB,
        (unsigned int)"onecore\\base\\telemetry\\utc\\common\\apiserver.cpp",
        v8);
    return LastError;
  }
  if ( !IsMember )
  {
    LastError = -2147024891;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD9,
      (unsigned int)"onecore\\base\\telemetry\\utc\\common\\apiserver.cpp",
      (const char *)0x80070005LL,
      v11);
    if ( RpcRevertToSelf() )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xCB,
        (unsigned int)"onecore\\base\\telemetry\\utc\\common\\apiserver.cpp",
        v9);
    return LastError;
  }
  if ( RpcRevertToSelf() )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xCB,
      (unsigned int)"onecore\\base\\telemetry\\utc\\common\\apiserver.cpp",
      v10);
  return 0;
}

```

## disassembly

```asm
0x1802f1f0c  mov     [rsp+arg_0], rbx
0x1802f1f11  push    rdi; int
0x1802f1f12  sub     rsp, 20h
0x1802f1f16  mov     rdi, rcx
0x1802f1f19  xor     ecx, ecx; BindingHandle
0x1802f1f1b  call    cs:__imp_RpcImpersonateClient
0x1802f1f21  test    eax, eax
0x1802f1f23  jz      short loc_1802F1F4A
0x1802f1f25  mov     rcx, [rsp+28h]; this
0x1802f1f2a  lea     r8, aOnecoreBaseTel_263; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802f1f31  mov     ebx, 80070005h
0x1802f1f36  mov     edx, 0C0h; void *
0x1802f1f3b  mov     r9d, ebx; char *
0x1802f1f3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802f1f43  mov     eax, ebx
0x1802f1f45  jmp     loc_1802F2060
0x1802f1f4a  cmp     qword ptr [rdi+8], 0
0x1802f1f4f  jnz     short loc_1802F1F99
0x1802f1f51  mov     rcx, rdi; this
0x1802f1f54  call    ?AllocateAdminSid@ApiServer@Diagnostics@Microsoft@@IEAAJXZ; Microsoft::Diagnostics::ApiServer::AllocateAdminSid(void)
0x1802f1f59  mov     ebx, eax
0x1802f1f5b  test    eax, eax
0x1802f1f5d  jns     short loc_1802F1F99
0x1802f1f5f  mov     rcx, [rsp+28h]; this
0x1802f1f64  lea     r8, aOnecoreBaseTel_263; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802f1f6b  mov     r9d, eax; char *
0x1802f1f6e  mov     edx, 0D2h; void *
0x1802f1f73  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802f1f78  call    cs:__imp_RpcRevertToSelf
0x1802f1f7e  test    eax, eax
0x1802f1f80  jz      short loc_1802F1F43
0x1802f1f82  mov     rcx, [rsp+28h]; this
0x1802f1f87  lea     r8, aOnecoreBaseTel_263; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802f1f8e  mov     edx, 0CBh; void *
0x1802f1f93  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1802f1f99  mov     rdx, [rdi+8]; SidToCheck
0x1802f1f9d  lea     r8, [rsp+28h+IsMember]; IsMember
0x1802f1fa2  xor     ecx, ecx; TokenHandle
0x1802f1fa4  mov     [rsp+28h+IsMember], 0
0x1802f1fac  call    cs:__imp_CheckTokenMembership
0x1802f1fb2  test    eax, eax
0x1802f1fb4  jnz     short loc_1802F1FF3
0x1802f1fb6  mov     rcx, [rsp+28h]; this
0x1802f1fbb  lea     r8, aOnecoreBaseTel_263; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802f1fc2  mov     edx, 0D6h; void *
0x1802f1fc7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1802f1fcc  mov     ebx, eax
0x1802f1fce  call    cs:__imp_RpcRevertToSelf
0x1802f1fd4  test    eax, eax
0x1802f1fd6  jz      loc_1802F1F43
0x1802f1fdc  mov     rcx, [rsp+28h]; this
0x1802f1fe1  lea     r8, aOnecoreBaseTel_263; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802f1fe8  mov     edx, 0CBh; void *
0x1802f1fed  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1802f1ff3  cmp     [rsp+28h+IsMember], 0
0x1802f1ff8  jnz     short loc_1802F203D
0x1802f1ffa  mov     rcx, [rsp+28h]; this
0x1802f1fff  lea     r8, aOnecoreBaseTel_263; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802f2006  mov     ebx, 80070005h
0x1802f200b  mov     edx, 0D9h; void *
0x1802f2010  mov     r9d, ebx; char *
0x1802f2013  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802f2018  call    cs:__imp_RpcRevertToSelf
0x1802f201e  test    eax, eax
0x1802f2020  jz      loc_1802F1F43
0x1802f2026  mov     rcx, [rsp+28h]; this
0x1802f202b  lea     r8, aOnecoreBaseTel_263; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802f2032  mov     edx, 0CBh; void *
0x1802f2037  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1802f203d  call    cs:__imp_RpcRevertToSelf
0x1802f2043  test    eax, eax
0x1802f2045  jz      short loc_1802F205E
0x1802f2047  mov     rcx, [rsp+28h]; this
0x1802f204c  lea     r8, aOnecoreBaseTel_263; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802f2053  mov     edx, 0CBh; void *
0x1802f2058  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1802f205e  xor     eax, eax
0x1802f2060  mov     rbx, [rsp+28h+arg_0]
0x1802f2065  add     rsp, 20h
0x1802f2069  pop     rdi
0x1802f206a  retn
```
