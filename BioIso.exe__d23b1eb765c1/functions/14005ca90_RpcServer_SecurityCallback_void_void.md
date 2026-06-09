# RpcServer::SecurityCallback(void *,void *)

- ea: `0x14005ca90`
- end: `0x14005cd13`
- name: `?SecurityCallback@RpcServer@@CAJPEAX0@Z`
- size: `643`
- prototype: `unsigned int __fastcall(RPC_IF_HANDLE InterfaceUuid, void *Context)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x14000a420`
- `0x14001bd40`
- `0x14002826c`
- `0x14002aa74`
- `0x140057b50`
- `0x14005866c`
- `0x14005c8b0`
- `0x14005c8c8`
- `0x14005c8d8`
- `0x14005ca90`
- `0x14005ce5c`
- `0x14005cf00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005cbc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005cbc1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14005cb40`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14005cbaa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14005cc60`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14005cb40`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14005cbaa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14005cc60`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x14005ccb1`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x14005ccb1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005cc05`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005cc05`
- `RPCRT4!RpcImpersonateClient` at `0x14005cabc`
- `RPCRT4!RpcImpersonateClient` at `0x14005cabc`

## string_xrefs

- `0x14005cad2`: `onecore\ds\security\biometrics\service\trustlet\exe\rpcserver.cpp`
- `0x14005cb54`: `onecore\ds\security\biometrics\service\trustlet\exe\rpcserver.cpp`
- `0x14005cb82`: `onecore\ds\security\biometrics\service\trustlet\exe\rpcserver.cpp`
- `0x14005cc28`: `onecore\ds\security\biometrics\service\trustlet\exe\rpcserver.cpp`
- `0x14005cc74`: `onecore\ds\security\biometrics\service\trustlet\exe\rpcserver.cpp`

## pseudocode

```c
unsigned int __fastcall RpcServer::SecurityCallback(RPC_IF_HANDLE InterfaceUuid, void *Context)
{
  unsigned int v2; // eax
  __int64 v4; // rax
  int v5; // eax
  unsigned int LastError; // ebx
  __int64 v7; // r9
  __int64 v8; // rdx
  const char *v9; // r9
  __int64 *unique_hlocal; // rax
  __int64 v11; // rdx
  HLOCAL v12; // rcx
  PSID *v13; // rbx
  __int64 v14; // rdx
  const char *v15; // r9
  unsigned int ReturnLength; // [rsp+20h] [rbp-19h]
  DWORD TokenInformationLength; // [rsp+30h] [rbp-9h] BYREF
  LPVOID v18; // [rsp+38h] [rbp-1h] BYREF
  int TokenInformation; // [rsp+40h] [rbp+7h] BYREF
  HANDLE TokenHandle; // [rsp+48h] [rbp+Fh] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp+17h] BYREF
  void *v22; // [rsp+58h] [rbp+1Fh] BYREF
  _BYTE v23[16]; // [rsp+60h] [rbp+27h] BYREF
  _DWORD pSid2[4]; // [rsp+70h] [rbp+37h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+5Fh]

  v22 = Context;
  v2 = RpcImpersonateClient(Context);
  if ( v2 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x73,
             (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\rpcserver.cpp",
             (const char *)v2,
             ReturnLength);
  v4 = lambda_bf25de864d02f14d70572f3f2647544a_::_lambda_bf25de864d02f14d70572f3f2647544a_(&hMem, &v22);
  wil::ScopeExit__lambda_2a78cf31826150e3ef2b73dff3ec3e0f___(v23, v4);
  TokenHandle = 0;
  v5 = wil::open_current_access_token_nothrow(&TokenHandle);
  LastError = v5;
  if ( v5 < 0 )
  {
    v7 = (unsigned int)v5;
    v8 = 125;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\rpcserver.cpp",
      (const char *)v7,
      ReturnLength);
    goto LABEL_29;
  }
  TokenInformation = 0;
  TokenInformationLength = 0;
  if ( GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &TokenInformationLength) )
  {
    if ( TokenInformation )
    {
      v8 = 137;
LABEL_9:
      LastError = -2147417829;
      v7 = 2147549467LL;
      goto LABEL_10;
    }
    if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
    {
      v8 = 148;
      goto LABEL_9;
    }
    if ( GetLastError() != 122 )
    {
      v8 = 149;
      goto LABEL_9;
    }
    v18 = 0;
    unique_hlocal = (__int64 *)wil::make_unique_hlocal_nothrow<unsigned char [0]>(&hMem, TokenInformationLength);
    v11 = *unique_hlocal;
    *unique_hlocal = 0;
    wistd::unique_ptr<_TOKEN_USER,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(&v18, v11);
    v12 = hMem;
    hMem = 0;
    if ( v12 )
      LocalFree(v12);
    v13 = (PSID *)v18;
    if ( v18 )
    {
      if ( !GetTokenInformation(TokenHandle, TokenUser, v18, TokenInformationLength, &TokenInformationLength) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0xA3,
                      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\rpcserver.cpp",
                      v15);
        goto LABEL_21;
      }
      if ( *v13 )
      {
        pSid2[0] = 257;
        pSid2[1] = 83886080;
        pSid2[2] = 18;
        if ( EqualSid(*v13, pSid2) )
        {
          wistd::unique_ptr<_TOKEN_USER,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
            &v18,
            0);
          LastError = 0;
          goto LABEL_29;
        }
        LastError = -2147417829;
        v14 = 170;
        goto LABEL_20;
      }
      v14 = 165;
    }
    else
    {
      v14 = 154;
    }
    LastError = -2147024882;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\rpcserver.cpp",
      (const char *)LastError,
      ReturnLength);
LABEL_21:
    wistd::unique_ptr<_TOKEN_USER,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(&v18, 0);
    goto LABEL_29;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x88,
                (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\rpcserver.cpp",
                v9);
LABEL_29:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  wil::details::ScopeExitFn__lambda_65d401589f009ed61ac15122311f92f7___::_ScopeExitFn__lambda_65d401589f009ed61ac15122311f92f7___(v23);
  return LastError;
}

```

## disassembly

```asm
0x14005ca90  mov     [rsp-8+arg_0], rbx
0x14005ca95  mov     [rsp-8+arg_10], rdi
0x14005ca9a  push    rbp
0x14005ca9b  lea     rbp, [rsp-57h]
0x14005caa0  sub     rsp, 90h
0x14005caa7  mov     rax, cs:__security_cookie
0x14005caae  xor     rax, rsp
0x14005cab1  mov     [rbp+57h+var_10], rax
0x14005cab5  mov     rcx, rdx; BindingHandle
0x14005cab8  mov     [rbp+57h+var_38], rdx
0x14005cabc  call    cs:__imp_RpcImpersonateClient
0x14005cac3  nop     dword ptr [rax+rax+00h]
0x14005cac8  xor     edi, edi
0x14005caca  test    eax, eax
0x14005cacc  jz      short loc_14005CAE9
0x14005cace  mov     rcx, [rbp+5Fh]; this
0x14005cad2  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\biometrics\\serv"...
0x14005cad9  mov     r9d, eax; char *
0x14005cadc  lea     edx, [rdi+73h]; void *
0x14005cadf  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14005cae4  jmp     loc_14005CCF1
0x14005cae9  lea     rdx, [rbp+57h+var_38]
0x14005caed  lea     rcx, [rbp+57h+hMem]
0x14005caf1  call    _lambda_bf25de864d02f14d70572f3f2647544a____lambda_bf25de864d02f14d70572f3f2647544a_
0x14005caf6  mov     rdx, rax
0x14005caf9  lea     rcx, [rbp+57h+var_30]
0x14005cafd  call    wil__ScopeExit__lambda_2a78cf31826150e3ef2b73dff3ec3e0f___
0x14005cb02  lea     rcx, [rbp+57h+TokenHandle]
0x14005cb06  mov     [rbp+57h+TokenHandle], rdi
0x14005cb0a  call    ?open_current_access_token_nothrow@wil@@YAJPEAPEAXKW4OpenThreadTokenAs@1@@Z; wil::open_current_access_token_nothrow(void * *,ulong,wil::OpenThreadTokenAs)
0x14005cb0f  mov     ebx, eax
0x14005cb11  test    eax, eax
0x14005cb13  jns     short loc_14005CB1F
0x14005cb15  mov     r9d, eax
0x14005cb18  mov     edx, 7Dh ; '}'
0x14005cb1d  jmp     short loc_14005CB7E
0x14005cb1f  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x14005cb23  lea     rax, [rbp+57h+TokenInformationLength]
0x14005cb27  mov     r9d, 4; TokenInformationLength
0x14005cb2d  mov     [rbp+57h+TokenInformation], edi
0x14005cb30  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x14005cb34  mov     [rbp+57h+TokenInformationLength], edi
0x14005cb37  mov     qword ptr [rsp+90h+ReturnLength], rax; int
0x14005cb3c  lea     edx, [r9+19h]; TokenInformationClass
0x14005cb40  call    cs:__imp_GetTokenInformation
0x14005cb47  nop     dword ptr [rax+rax+00h]
0x14005cb4c  test    eax, eax
0x14005cb4e  jnz     short loc_14005CB6C
0x14005cb50  mov     rcx, [rbp+5Fh]; this
0x14005cb54  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\biometrics\\serv"...
0x14005cb5b  mov     edx, 88h; void *
0x14005cb60  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14005cb65  mov     ebx, eax
0x14005cb67  jmp     loc_14005CCDD
0x14005cb6c  cmp     [rbp+57h+TokenInformation], edi
0x14005cb6f  jz      short loc_14005CB93
0x14005cb71  mov     edx, 89h; void *
0x14005cb76  mov     ebx, 8001011Bh
0x14005cb7b  mov     r9d, ebx; char *
0x14005cb7e  mov     rcx, [rbp+5Fh]; this
0x14005cb82  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\biometrics\\serv"...
0x14005cb89  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005cb8e  jmp     loc_14005CCDD
0x14005cb93  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x14005cb97  lea     rax, [rbp+57h+TokenInformationLength]
0x14005cb9b  xor     r9d, r9d; TokenInformationLength
0x14005cb9e  mov     qword ptr [rsp+90h+ReturnLength], rax; int
0x14005cba3  xor     r8d, r8d; TokenInformation
0x14005cba6  lea     edx, [r9+1]; TokenInformationClass
0x14005cbaa  call    cs:__imp_GetTokenInformation
0x14005cbb1  nop     dword ptr [rax+rax+00h]
0x14005cbb6  test    eax, eax
0x14005cbb8  jz      short loc_14005CBC1
0x14005cbba  mov     edx, 94h
0x14005cbbf  jmp     short loc_14005CB76
0x14005cbc1  call    cs:__imp_GetLastError
0x14005cbc8  nop     dword ptr [rax+rax+00h]
0x14005cbcd  cmp     eax, 7Ah ; 'z'
0x14005cbd0  jz      short loc_14005CBD9
0x14005cbd2  mov     edx, 95h
0x14005cbd7  jmp     short loc_14005CB76
0x14005cbd9  mov     edx, [rbp+57h+TokenInformationLength]
0x14005cbdc  lea     rcx, [rbp+57h+hMem]
0x14005cbe0  mov     [rbp+57h+var_58], rdi
0x14005cbe4  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x14005cbe9  lea     rcx, [rbp+57h+var_58]
0x14005cbed  mov     rdx, [rax]
0x14005cbf0  mov     [rax], rdi
0x14005cbf3  call    ?reset@?$unique_ptr@U_TOKEN_USER@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAU_TOKEN_USER@@@Z; wistd::unique_ptr<_TOKEN_USER,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(_TOKEN_USER *)
0x14005cbf8  mov     rcx, [rbp+57h+hMem]; hMem
0x14005cbfc  mov     [rbp+57h+hMem], rdi
0x14005cc00  test    rcx, rcx
0x14005cc03  jz      short loc_14005CC11
0x14005cc05  call    cs:__imp_LocalFree
0x14005cc0c  nop     dword ptr [rax+rax+00h]
0x14005cc11  mov     rbx, [rbp+57h+var_58]
0x14005cc15  test    rbx, rbx
0x14005cc18  jnz     short loc_14005CC47
0x14005cc1a  mov     edx, 9Ah; void *
0x14005cc1f  mov     ebx, 8007000Eh
0x14005cc24  mov     rcx, [rbp+5Fh]; this
0x14005cc28  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\biometrics\\serv"...
0x14005cc2f  mov     r9d, ebx; char *
0x14005cc32  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005cc37  xor     edx, edx
0x14005cc39  lea     rcx, [rbp+57h+var_58]
0x14005cc3d  call    ?reset@?$unique_ptr@U_TOKEN_USER@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAU_TOKEN_USER@@@Z; wistd::unique_ptr<_TOKEN_USER,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(_TOKEN_USER *)
0x14005cc42  jmp     loc_14005CCDD
0x14005cc47  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x14005cc4b  lea     rax, [rbp+57h+TokenInformationLength]
0x14005cc4f  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x14005cc53  mov     r8, rbx; TokenInformation
0x14005cc56  mov     edx, 1; TokenInformationClass
0x14005cc5b  mov     qword ptr [rsp+90h+ReturnLength], rax; ReturnLength
0x14005cc60  call    cs:__imp_GetTokenInformation
0x14005cc67  nop     dword ptr [rax+rax+00h]
0x14005cc6c  test    eax, eax
0x14005cc6e  jnz     short loc_14005CC89
0x14005cc70  mov     rcx, [rbp+5Fh]; this
0x14005cc74  lea     r8, aOnecoreDsSecur_20; "onecore\\ds\\security\\biometrics\\serv"...
0x14005cc7b  mov     edx, 0A3h; void *
0x14005cc80  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14005cc85  mov     ebx, eax
0x14005cc87  jmp     short loc_14005CC37
0x14005cc89  cmp     [rbx], rdi
0x14005cc8c  jnz     short loc_14005CC95
0x14005cc8e  mov     edx, 0A5h
0x14005cc93  jmp     short loc_14005CC1F
0x14005cc95  mov     [rbp+57h+pSid2], 101h
0x14005cc9c  lea     rdx, [rbp+57h+pSid2]; pSid2
0x14005cca0  mov     [rbp+57h+var_1C], 5000000h
0x14005cca7  mov     [rbp+57h+var_18], 12h
0x14005ccae  mov     rcx, [rbx]; pSid1
0x14005ccb1  call    cs:__imp_EqualSid
0x14005ccb8  nop     dword ptr [rax+rax+00h]
0x14005ccbd  test    eax, eax
0x14005ccbf  jnz     short loc_14005CCD0
0x14005ccc1  mov     ebx, 8001011Bh
0x14005ccc6  mov     edx, 0AAh
0x14005cccb  jmp     loc_14005CC24
0x14005ccd0  xor     edx, edx
0x14005ccd2  lea     rcx, [rbp+57h+var_58]
0x14005ccd6  call    ?reset@?$unique_ptr@U_TOKEN_USER@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAU_TOKEN_USER@@@Z; wistd::unique_ptr<_TOKEN_USER,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(_TOKEN_USER *)
0x14005ccdb  mov     ebx, edi
0x14005ccdd  lea     rcx, [rbp+57h+TokenHandle]
0x14005cce1  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14005cce6  lea     rcx, [rbp+57h+var_30]
0x14005ccea  call    wil__details__ScopeExitFn__lambda_65d401589f009ed61ac15122311f92f7______ScopeExitFn__lambda_65d401589f009ed61ac15122311f92f7___
0x14005ccef  mov     eax, ebx
0x14005ccf1  mov     rcx, [rbp+57h+var_10]
0x14005ccf5  xor     rcx, rsp; StackCookie
0x14005ccf8  call    __security_check_cookie
0x14005ccfd  lea     r11, [rsp+90h+var_s0]
0x14005cd05  mov     rbx, [r11+10h]
0x14005cd09  mov     rdi, [r11+20h]
0x14005cd0d  mov     rsp, r11
0x14005cd10  pop     rbp
0x14005cd11  retn
```
