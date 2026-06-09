# AppReadiness::CreateUserTokenUsingWts

- ea: `0x180035f14`
- end: `0x180036133`
- name: `AppReadiness::CreateUserTokenUsingWts`
- size: `543`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180011cac`

## callees

- `0x1800041e0`
- `0x180027a4c`
- `0x180035f14`
- `0x18003ecb4`
- `0x18003eec0`
- `0x1800473d8`
- `0x180047eb0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800360c0`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800360c0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180035f62`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180035f62`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180035fe7`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180035fe7`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x18003603f`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x18003603f`

## string_xrefs

- `0x180035f7d`: `onecoreuap\shell\appreadiness\src\core\api.cpp`
- `0x180035ff9`: `onecoreuap\shell\appreadiness\src\core\api.cpp`
- `0x18003605a`: `onecoreuap\shell\appreadiness\src\core\api.cpp`
- `0x1800360db`: `onecoreuap\shell\appreadiness\src\core\api.cpp`
- `0x180035f89`: `AppReadiness::CreateUserTokenUsingWts`
- `0x180036005`: `AppReadiness::CreateUserTokenUsingWts`
- `0x180036066`: `AppReadiness::CreateUserTokenUsingWts`
- `0x1800360e7`: `AppReadiness::CreateUserTokenUsingWts`
- `0x180035f90`: `GetTokenInformation(userToken.Get(), TokenSessionId, &userSessionId, sizeof(userSessionId), &len)`
- `0x18003600c`: `UMgrQueryUserToken(userContextToken, temp.GetAddressOf())`
- `0x18003606d`: `QueryUserToken(userSessionId, temp.GetAddressOf())`
- `0x1800360ee`: `DuplicateTokenEx(temp.Get(), TOKEN_IMPERSONATE|TOKEN_QUERY|TOKEN_DUPLICATE, nullptr, SecurityImpersonation, TokenImpersonation, result.GetAddressOf())`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AppReadiness::CreateUserTokenUsingWts(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rcx
  int Error; // eax
  int v7; // eax
  HANDLE v8; // rcx
  int v9; // eax
  int v10; // eax
  void **v12; // [rsp+38h] [rbp-38h] BYREF
  HANDLE hExistingToken; // [rsp+40h] [rbp-30h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+48h] [rbp-28h] BYREF
  unsigned int TokenInformation; // [rsp+98h] [rbp+28h] BYREF
  DWORD ReturnLength; // [rsp+A8h] [rbp+38h] BYREF

  ReturnLength = 0;
  TokenInformation = 0;
  if ( !GetTokenInformation(*(HANDLE *)(a2 + 8), TokenSessionId, &TokenInformation, 4u, &ReturnLength) )
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pExceptionObject,
        Error,
        "GetTokenInformation(userToken.Get(), TokenSessionId, &userSessionId, sizeof(userSessionId), &len)",
        "AppReadiness::CreateUserTokenUsingWts",
        "onecoreuap\\shell\\appreadiness\\src\\core\\api.cpp",
        432);
      throw (Windows::HResultException *)pExceptionObject;
    }
  }
  v12 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  hExistingToken = 0;
  if ( !a3 )
    goto LABEL_20;
  if ( (unsigned __int8)IsUMgrEnumerateSessionUsersPresent(v5) )
  {
    if ( AppReadiness::Service::IsSessionShared(TokenInformation) )
    {
      v7 = UMgrQueryUserToken(a3, &hExistingToken);
      if ( v7 < 0 )
      {
        Windows::HResultException::HResultException(
          (Windows::HResultException *)pExceptionObject,
          v7,
          "UMgrQueryUserToken(userContextToken, temp.GetAddressOf())",
          "AppReadiness::CreateUserTokenUsingWts",
          "onecoreuap\\shell\\appreadiness\\src\\core\\api.cpp",
          437);
        throw (Windows::HResultException *)pExceptionObject;
      }
    }
  }
  v8 = hExistingToken;
  if ( !hExistingToken )
  {
LABEL_20:
    if ( !(unsigned int)QueryUserToken(TokenInformation, &hExistingToken) )
    {
      v9 = ResultFromKnownLastError();
      if ( v9 < 0 )
      {
        Windows::HResultException::HResultException(
          (Windows::HResultException *)pExceptionObject,
          v9,
          "QueryUserToken(userSessionId, temp.GetAddressOf())",
          "AppReadiness::CreateUserTokenUsingWts",
          "onecoreuap\\shell\\appreadiness\\src\\core\\api.cpp",
          447);
        throw (Windows::HResultException *)pExceptionObject;
      }
    }
    v8 = hExistingToken;
  }
  *(_QWORD *)a1 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  *(_QWORD *)(a1 + 8) = 0;
  if ( !DuplicateTokenEx(v8, 0xEu, 0, SecurityImpersonation, TokenImpersonation, (PHANDLE)(a1 + 8)) )
  {
    v10 = ResultFromKnownLastError();
    if ( v10 < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pExceptionObject,
        v10,
        "DuplicateTokenEx(temp.Get(), TOKEN_IMPERSONATE|TOKEN_QUERY|TOKEN_DUPLICATE, nullptr, SecurityImpersonation, Toke"
        "nImpersonation, result.GetAddressOf())",
        "AppReadiness::CreateUserTokenUsingWts",
        "onecoreuap\\shell\\appreadiness\\src\\core\\api.cpp",
        451);
      throw (Windows::HResultException *)pExceptionObject;
    }
  }
  v12 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(&v12);
  return a1;
}

```

## disassembly

```asm
0x180035f14  mov     [rsp-18h+arg_10], rbx
0x180035f19  mov     [rsp-18h+arg_0], rcx
0x180035f1e  push    rbp
0x180035f1f  push    rdi
0x180035f20  push    r14
0x180035f22  mov     rbp, rsp
0x180035f25  sub     rsp, 70h
0x180035f29  mov     rbx, r8
0x180035f2c  mov     rax, rdx
0x180035f2f  mov     rdi, rcx
0x180035f32  mov     [rbp+var_40], 0
0x180035f39  mov     [rbp+arg_18], 0
0x180035f40  mov     [rbp+TokenInformation], 0
0x180035f47  lea     rcx, [rbp+arg_18]
0x180035f4b  mov     [rsp+70h+ReturnLength], rcx; ReturnLength
0x180035f50  mov     r9d, 4; TokenInformationLength
0x180035f56  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180035f5a  lea     edx, [r9+8]; TokenInformationClass
0x180035f5e  mov     rcx, [rax+8]; TokenHandle
0x180035f62  call    cs:__imp_GetTokenInformation
0x180035f68  test    eax, eax
0x180035f6a  jnz     short loc_180035FB3
0x180035f6c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180035f71  test    eax, eax
0x180035f73  jns     short loc_180035FB3
0x180035f75  mov     dword ptr [rsp+70h+phNewToken], 1B0h; int
0x180035f7d  lea     rcx, aOnecoreuapShel_38; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180035f84  mov     [rsp+70h+ReturnLength], rcx; char *
0x180035f89  lea     r9, aAppreadinessCr; "AppReadiness::CreateUserTokenUsingWts"
0x180035f90  lea     r8, aGettokeninform_1; "GetTokenInformation(userToken.Get(), To"...
0x180035f97  mov     edx, eax; int
0x180035f99  lea     rcx, [rbp+pExceptionObject]; this
0x180035f9d  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180035fa2  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180035fa9  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180035fad  call    _CxxThrowException_0
0x180035fb3  lea     r14, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180035fba  mov     [rbp+var_38], r14
0x180035fbe  mov     [rbp+hExistingToken], 0
0x180035fc6  test    rbx, rbx
0x180035fc9  jz      short loc_180036038
0x180035fcb  call    IsUMgrEnumerateSessionUsersPresent
0x180035fd0  test    al, al
0x180035fd2  jz      short loc_18003602F
0x180035fd4  mov     ecx, [rbp+TokenInformation]; unsigned int
0x180035fd7  call    ?IsSessionShared@Service@AppReadiness@@SA_NK@Z; AppReadiness::Service::IsSessionShared(ulong)
0x180035fdc  test    al, al
0x180035fde  jz      short loc_18003602F
0x180035fe0  lea     rdx, [rbp+hExistingToken]
0x180035fe4  mov     rcx, rbx
0x180035fe7  call    cs:__imp_UMgrQueryUserToken
0x180035fed  test    eax, eax
0x180035fef  jns     short loc_18003602F
0x180035ff1  mov     dword ptr [rsp+70h+phNewToken], 1B5h; int
0x180035ff9  lea     rcx, aOnecoreuapShel_38; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180036000  mov     [rsp+70h+ReturnLength], rcx; char *
0x180036005  lea     r9, aAppreadinessCr; "AppReadiness::CreateUserTokenUsingWts"
0x18003600c  lea     r8, aUmgrqueryusert_0; "UMgrQueryUserToken(userContextToken, te"...
0x180036013  mov     edx, eax; int
0x180036015  lea     rcx, [rbp+pExceptionObject]; this
0x180036019  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18003601e  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180036025  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180036029  call    _CxxThrowException_0
0x18003602f  mov     rcx, [rbp+hExistingToken]
0x180036033  test    rcx, rcx
0x180036036  jnz     short loc_180036094
0x180036038  lea     rdx, [rbp+hExistingToken]
0x18003603c  mov     ecx, [rbp+TokenInformation]
0x18003603f  call    cs:__imp_QueryUserToken
0x180036045  test    eax, eax
0x180036047  jnz     short loc_180036090
0x180036049  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18003604e  test    eax, eax
0x180036050  jns     short loc_180036090
0x180036052  mov     dword ptr [rsp+70h+phNewToken], 1BFh; int
0x18003605a  lea     rcx, aOnecoreuapShel_38; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180036061  mov     [rsp+70h+ReturnLength], rcx; char *
0x180036066  lea     r9, aAppreadinessCr; "AppReadiness::CreateUserTokenUsingWts"
0x18003606d  lea     r8, aQueryusertoken_0; "QueryUserToken(userSessionId, temp.GetA"...
0x180036074  mov     edx, eax; int
0x180036076  lea     rcx, [rbp+pExceptionObject]; this
0x18003607a  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18003607f  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180036086  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003608a  call    _CxxThrowException_0
0x180036090  mov     rcx, [rbp+hExistingToken]; hExistingToken
0x180036094  mov     [rdi], r14
0x180036097  lea     rax, [rdi+8]
0x18003609b  mov     qword ptr [rax], 0
0x1800360a2  mov     [rbp+var_40], 1
0x1800360a9  mov     [rsp+70h+phNewToken], rax; phNewToken
0x1800360ae  mov     r9d, 2; ImpersonationLevel
0x1800360b4  mov     dword ptr [rsp+70h+ReturnLength], r9d; TokenType
0x1800360b9  xor     r8d, r8d; lpTokenAttributes
0x1800360bc  lea     edx, [r9+0Ch]; dwDesiredAccess
0x1800360c0  call    cs:__imp_DuplicateTokenEx
0x1800360c6  test    eax, eax
0x1800360c8  jnz     short loc_180036111
0x1800360ca  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800360cf  test    eax, eax
0x1800360d1  jns     short loc_180036111
0x1800360d3  mov     dword ptr [rsp+70h+phNewToken], 1C3h; int
0x1800360db  lea     rcx, aOnecoreuapShel_38; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x1800360e2  mov     [rsp+70h+ReturnLength], rcx; char *
0x1800360e7  lea     r9, aAppreadinessCr; "AppReadiness::CreateUserTokenUsingWts"
0x1800360ee  lea     r8, aDuplicatetoken; "DuplicateTokenEx(temp.Get(), TOKEN_IMPE"...
0x1800360f5  mov     edx, eax; int
0x1800360f7  lea     rcx, [rbp+pExceptionObject]; this
0x1800360fb  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180036100  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180036107  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003610b  call    _CxxThrowException_0
0x180036111  mov     [rbp+var_38], r14
0x180036115  lea     rcx, [rbp+var_38]
0x180036119  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x18003611e  mov     rax, rdi
0x180036121  mov     rbx, [rsp+70h+arg_10]
0x180036129  add     rsp, 70h
0x18003612d  pop     r14
0x18003612f  pop     rdi
0x180036130  pop     rbp
0x180036131  retn
```
