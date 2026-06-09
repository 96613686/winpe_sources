# ScopedRpcListener::SecurityCallback(void *,void *)

- ea: `0x140018130`
- end: `0x1400183ff`
- name: `?SecurityCallback@ScopedRpcListener@@CAJPEAX0@Z`
- size: `719`
- prototype: `RPC_STATUS __fastcall(RPC_IF_HANDLE InterfaceUuid, void *Context)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x14000e034`
- `0x14000e52c`
- `0x14000ee38`
- `0x14000f6a0`
- `0x14000fc3c`
- `0x140017fb4`
- `0x1400180e8`
- `0x14001810c`
- `0x140018130`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400181a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400181e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400181a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400181e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400181c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400181c6`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400181d8`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400181d8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14001819b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14001819b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140018185`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140018185`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001827f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001827f`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x140018322`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x140018322`
- `RPCRT4!RpcImpersonateClient` at `0x140018156`
- `RPCRT4!RpcImpersonateClient` at `0x140018156`
- `RPCRT4!RpcRevertToSelfEx` at `0x14001821f`
- `RPCRT4!RpcRevertToSelfEx` at `0x14001836d`
- `RPCRT4!RpcRevertToSelfEx` at `0x1400183ba`
- `RPCRT4!RpcRevertToSelfEx` at `0x14001821f`
- `RPCRT4!RpcRevertToSelfEx` at `0x14001836d`
- `RPCRT4!RpcRevertToSelfEx` at `0x1400183ba`

## string_xrefs

- `0x14001828d`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`
- `0x140018164`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\server.cpp`
- `0x140018204`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\server.cpp`
- `0x14001822d`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\server.cpp`
- `0x1400182d7`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\server.cpp`
- `0x140018330`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\server.cpp`
- `0x14001837b`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\server.cpp`
- `0x140018397`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\server.cpp`
- `0x1400183c8`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\server.cpp`

## pseudocode

```c
RPC_STATUS __fastcall ScopedRpcListener::SecurityCallback(RPC_IF_HANDLE InterfaceUuid, void *Context)
{
  unsigned int v3; // eax
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  signed int v7; // ebx
  HANDLE CurrentProcess; // rax
  signed int v9; // eax
  __int64 v10; // rdx
  unsigned int v11; // eax
  __int64 v12; // rcx
  const char *v13; // r9
  int token_information; // eax
  void *v15; // rbx
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int ReturnLength; // [rsp+20h] [rbp-50h]
  unsigned int ReturnLengtha; // [rsp+20h] [rbp-50h]
  unsigned int ReturnLengthb; // [rsp+20h] [rbp-50h]
  HANDLE TokenHandle; // [rsp+30h] [rbp-40h] BYREF
  int TokenInformation; // [rsp+38h] [rbp-38h] BYREF
  DWORD v23[2]; // [rsp+40h] [rbp-30h] BYREF
  _DWORD pSid2[4]; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  v3 = RpcImpersonateClient(Context);
  if ( v3 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x31,
             (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\server.cpp",
             (const char *)v3,
             ReturnLength);
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( v7 == -2147023888 )
    {
      CurrentProcess = GetCurrentProcess();
      if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
        goto LABEL_16;
      v9 = GetLastError();
      v7 = v9;
      if ( v9 > 0 )
        v7 = (unsigned __int16)v9 | 0x80070000;
    }
    if ( v7 < 0 )
    {
      v10 = 56;
LABEL_12:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\server.cpp",
        (const char *)(unsigned int)v7,
        ReturnLength);
LABEL_13:
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      v11 = RpcRevertToSelfEx(Context);
      if ( v11 )
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x34,
          (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\server.cpp",
          (const char *)v11,
          ReturnLengtha);
      return v7;
    }
  }
LABEL_16:
  TokenInformation = 0;
  v23[0] = 0;
  v12 = -6;
  if ( TokenHandle )
    v12 = (__int64)TokenHandle;
  if ( GetTokenInformation((HANDLE)v12, TokenIsAppContainer, &TokenInformation, 4u, v23) )
  {
    if ( TokenInformation )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3C,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\server.cpp",
        (const char *)0x8001011BLL,
        ReturnLength);
LABEL_34:
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
      v17 = RpcRevertToSelfEx(Context);
      if ( v17 )
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x34,
          (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\server.cpp",
          (const char *)v17,
          ReturnLengthb);
      return -2147417829;
    }
  }
  else
  {
    v7 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x298,
           (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
           v13);
    if ( v7 < 0 )
    {
      v10 = 59;
      goto LABEL_12;
    }
  }
  *(_QWORD *)v23 = 0;
  token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(v23, TokenHandle);
  v7 = token_information;
  if ( token_information < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3F,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\server.cpp",
      (const char *)(unsigned int)token_information,
      ReturnLength);
    if ( *(_QWORD *)v23 )
      operator delete(*(void **)v23);
    goto LABEL_13;
  }
  v15 = *(void **)v23;
  pSid2[0] = 257;
  pSid2[1] = 83886080;
  pSid2[2] = 19;
  if ( !EqualSid(**(PSID **)v23, pSid2) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x42,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\server.cpp",
      (const char *)0x8001011BLL,
      ReturnLength);
    if ( v15 )
      operator delete(v15);
    goto LABEL_34;
  }
  if ( v15 )
    operator delete(v15);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  v16 = RpcRevertToSelfEx(Context);
  if ( v16 )
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x34,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\server.cpp",
      (const char *)v16,
      ReturnLength);
  return 0;
}

```

## disassembly

```asm
0x140018130  mov     [rsp-8+arg_0], rbx
0x140018135  mov     [rsp-8+arg_10], rdi
0x14001813a  push    rbp
0x14001813b  mov     rbp, rsp
0x14001813e  sub     rsp, 70h
0x140018142  mov     rax, cs:__security_cookie
0x140018149  xor     rax, rsp
0x14001814c  mov     [rbp+var_10], rax
0x140018150  mov     rcx, rdx; BindingHandle
0x140018153  mov     rdi, rdx
0x140018156  call    cs:__imp_RpcImpersonateClient
0x14001815c  test    eax, eax
0x14001815e  jz      short loc_14001817D
0x140018160  mov     rcx, [rbp+8]; this
0x140018164  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x14001816b  mov     r9d, eax; char *
0x14001816e  mov     edx, 31h ; '1'; void *
0x140018173  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140018178  jmp     loc_1400183E1
0x14001817d  mov     [rbp+TokenHandle], 0
0x140018185  call    cs:__imp_GetCurrentThread
0x14001818b  mov     edx, 8; DesiredAccess
0x140018190  lea     r9, [rbp+TokenHandle]; TokenHandle
0x140018194  mov     rcx, rax; ThreadHandle
0x140018197  lea     r8d, [rdx-7]; OpenAsSelf
0x14001819b  call    cs:__imp_OpenThreadToken
0x1400181a1  test    eax, eax
0x1400181a3  jnz     loc_140018248
0x1400181a9  call    cs:__imp_GetLastError
0x1400181af  mov     ebx, eax
0x1400181b1  test    eax, eax
0x1400181b3  jle     short loc_1400181BE
0x1400181b5  movzx   ebx, ax
0x1400181b8  or      ebx, 80070000h
0x1400181be  cmp     ebx, 800703F0h
0x1400181c4  jnz     short loc_1400181F7
0x1400181c6  call    cs:__imp_GetCurrentProcess
0x1400181cc  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1400181d0  mov     edx, 8; DesiredAccess
0x1400181d5  mov     rcx, rax; ProcessHandle
0x1400181d8  call    cs:__imp_OpenProcessToken
0x1400181de  test    eax, eax
0x1400181e0  jnz     short loc_140018248
0x1400181e2  call    cs:__imp_GetLastError
0x1400181e8  mov     ebx, eax
0x1400181ea  test    eax, eax
0x1400181ec  jle     short loc_1400181F7
0x1400181ee  movzx   ebx, ax
0x1400181f1  or      ebx, 80070000h
0x1400181f7  test    ebx, ebx
0x1400181f9  jns     short loc_140018248
0x1400181fb  mov     edx, 38h ; '8'; void *
0x140018200  mov     rcx, [rbp+8]; this
0x140018204  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x14001820b  mov     r9d, ebx; char *
0x14001820e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018213  lea     rcx, [rbp+TokenHandle]
0x140018217  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14001821c  mov     rcx, rdi; BindingHandle
0x14001821f  call    cs:__imp_RpcRevertToSelfEx
0x140018225  test    eax, eax
0x140018227  jz      short loc_140018241
0x140018229  mov     rcx, [rbp+8]; this
0x14001822d  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x140018234  mov     r9d, eax; char *
0x140018237  mov     edx, 34h ; '4'; void *
0x14001823c  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x140018241  mov     eax, ebx
0x140018243  jmp     loc_1400183E1
0x140018248  mov     rax, [rbp+TokenHandle]
0x14001824c  lea     r8, [rbp+TokenInformation]; TokenInformation
0x140018250  test    rax, rax
0x140018253  mov     [rbp+TokenInformation], 0
0x14001825a  mov     r9d, 4; TokenInformationLength
0x140018260  mov     [rbp+var_30], 0
0x140018267  mov     rcx, 0FFFFFFFFFFFFFFFAh
0x14001826e  cmovnz  rcx, rax; TokenHandle
0x140018272  lea     rax, [rbp+var_30]
0x140018276  mov     qword ptr [rsp+70h+ReturnLength], rax; unsigned int
0x14001827b  lea     edx, [r9+19h]; TokenInformationClass
0x14001827f  call    cs:__imp_GetTokenInformation
0x140018285  test    eax, eax
0x140018287  jnz     short loc_1400182AE
0x140018289  mov     rcx, [rbp+8]; this
0x14001828d  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140018294  mov     edx, 298h; void *
0x140018299  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14001829e  mov     ebx, eax
0x1400182a0  test    eax, eax
0x1400182a2  jns     short loc_1400182B8
0x1400182a4  mov     edx, 3Bh ; ';'
0x1400182a9  jmp     loc_140018200
0x1400182ae  cmp     [rbp+TokenInformation], 0
0x1400182b2  jnz     loc_140018393
0x1400182b8  mov     rdx, [rbp+TokenHandle]
0x1400182bc  lea     rcx, [rbp+var_30]
0x1400182c0  mov     qword ptr [rbp+var_30], 0
0x1400182c8  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x1400182cd  mov     ebx, eax
0x1400182cf  test    eax, eax
0x1400182d1  jns     short loc_140018302
0x1400182d3  mov     rcx, [rbp+8]; this
0x1400182d7  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x1400182de  mov     r9d, eax; char *
0x1400182e1  mov     edx, 3Fh ; '?'; void *
0x1400182e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400182eb  mov     rcx, qword ptr [rbp+var_30]; Block
0x1400182ef  test    rcx, rcx
0x1400182f2  jz      loc_140018213
0x1400182f8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400182fd  jmp     loc_140018213
0x140018302  mov     rbx, qword ptr [rbp+var_30]
0x140018306  lea     rdx, [rbp+pSid2]; pSid2
0x14001830a  mov     [rbp+pSid2], 101h
0x140018311  mov     [rbp+var_1C], 5000000h
0x140018318  mov     [rbp+var_18], 13h
0x14001831f  mov     rcx, [rbx]; pSid1
0x140018322  call    cs:__imp_EqualSid
0x140018328  test    eax, eax
0x14001832a  jnz     short loc_140018354
0x14001832c  mov     rcx, [rbp+8]; this
0x140018330  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x140018337  mov     r9d, 8001011Bh; char *
0x14001833d  lea     edx, [rax+42h]; void *
0x140018340  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018345  test    rbx, rbx
0x140018348  jz      short loc_1400183AE
0x14001834a  mov     rcx, rbx; Block
0x14001834d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140018352  jmp     short loc_1400183AE
0x140018354  test    rbx, rbx
0x140018357  jz      short loc_140018361
0x140018359  mov     rcx, rbx; Block
0x14001835c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140018361  lea     rcx, [rbp+TokenHandle]
0x140018365  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14001836a  mov     rcx, rdi; BindingHandle
0x14001836d  call    cs:__imp_RpcRevertToSelfEx
0x140018373  test    eax, eax
0x140018375  jz      short loc_14001838F
0x140018377  mov     rcx, [rbp+8]; this
0x14001837b  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x140018382  mov     r9d, eax; char *
0x140018385  mov     edx, 34h ; '4'; void *
0x14001838a  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x14001838f  xor     eax, eax
0x140018391  jmp     short loc_1400183E1
0x140018393  mov     rcx, [rbp+8]; this
0x140018397  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x14001839e  mov     r9d, 8001011Bh; char *
0x1400183a4  mov     edx, 3Ch ; '<'; void *
0x1400183a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400183ae  lea     rcx, [rbp+TokenHandle]
0x1400183b2  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400183b7  mov     rcx, rdi; BindingHandle
0x1400183ba  call    cs:__imp_RpcRevertToSelfEx
0x1400183c0  test    eax, eax
0x1400183c2  jz      short loc_1400183DC
0x1400183c4  mov     rcx, [rbp+8]; this
0x1400183c8  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x1400183cf  mov     r9d, eax; char *
0x1400183d2  mov     edx, 34h ; '4'; void *
0x1400183d7  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1400183dc  mov     eax, 8001011Bh
0x1400183e1  mov     rcx, [rbp+var_10]
0x1400183e5  xor     rcx, rsp; StackCookie
0x1400183e8  call    __security_check_cookie
0x1400183ed  lea     r11, [rsp+70h+var_s0]
0x1400183f2  mov     rbx, [r11+10h]
0x1400183f6  mov     rdi, [r11+20h]
0x1400183fa  mov     rsp, r11
0x1400183fd  pop     rbp
0x1400183fe  retn
```
