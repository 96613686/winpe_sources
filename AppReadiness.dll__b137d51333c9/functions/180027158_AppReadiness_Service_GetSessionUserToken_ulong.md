# AppReadiness::Service::GetSessionUserToken(ulong)

- ea: `0x180027158`
- end: `0x180027338`
- name: `?GetSessionUserToken@Service@AppReadiness@@SA?AV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@K@Z`
- size: `480`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180026c10`

## callees

- `0x1800041e0`
- `0x180027158`
- `0x180027a4c`
- `0x18003ecb4`
- `0x18003eec0`
- `0x18003f110`
- `0x1800473d8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800272cc`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800272cc`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQuerySessionUserToken` at `0x1800271ff`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQuerySessionUserToken` at `0x1800271ff`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x18002724b`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x18002724b`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180027197`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180027197`

## string_xrefs

- `0x1800271ba`: `onecoreuap\shell\appreadiness\src\core\service.cpp`
- `0x180027215`: `onecoreuap\shell\appreadiness\src\core\service.cpp`
- `0x180027266`: `onecoreuap\shell\appreadiness\src\core\service.cpp`
- `0x1800272e7`: `onecoreuap\shell\appreadiness\src\core\service.cpp`
- `0x1800271c6`: `AppReadiness::Service::GetSessionUserToken`
- `0x180027221`: `AppReadiness::Service::GetSessionUserToken`
- `0x180027272`: `AppReadiness::Service::GetSessionUserToken`
- `0x1800272f3`: `AppReadiness::Service::GetSessionUserToken`
- `0x1800271cd`: `WTSQueryUserToken(sessionId, temp.GetAddressOf())`
- `0x180027228`: `UMgrQuerySessionUserToken(sessionId, temp.GetAddressOf())`
- `0x180027279`: `QueryUserToken(sessionId, temp.GetAddressOf())`
- `0x1800272fa`: `DuplicateTokenEx(temp.Get(), TOKEN_IMPERSONATE|TOKEN_QUERY|TOKEN_DUPLICATE, nullptr, SecurityImpersonation, TokenImpersonation, token.GetAddressOf())`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AppReadiness::Service::GetSessionUserToken(__int64 a1, ULONG a2)
{
  __int64 v4; // rcx
  int Error; // eax
  int v6; // eax
  int v7; // eax
  int v8; // eax
  void **v10; // [rsp+38h] [rbp-40h] BYREF
  void *phToken; // [rsp+40h] [rbp-38h] BYREF
  _BYTE pExceptionObject[48]; // [rsp+48h] [rbp-30h] BYREF

  v10 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  phToken = 0;
  if ( (unsigned __int8)IsWTSEnumerateSessionsWPresent() )
  {
    if ( !WTSQueryUserToken(a2, &phToken) )
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
      {
        Windows::HResultException::HResultException(
          (Windows::HResultException *)pExceptionObject,
          Error,
          "WTSQueryUserToken(sessionId, temp.GetAddressOf())",
          "AppReadiness::Service::GetSessionUserToken",
          "onecoreuap\\shell\\appreadiness\\src\\core\\service.cpp",
          627);
        throw (Windows::HResultException *)pExceptionObject;
      }
    }
  }
  else if ( (unsigned __int8)IsUMgrEnumerateSessionUsersPresent(v4) )
  {
    v6 = UMgrQuerySessionUserToken(a2, &phToken);
    if ( v6 < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pExceptionObject,
        v6,
        "UMgrQuerySessionUserToken(sessionId, temp.GetAddressOf())",
        "AppReadiness::Service::GetSessionUserToken",
        "onecoreuap\\shell\\appreadiness\\src\\core\\service.cpp",
        631);
      throw (Windows::HResultException *)pExceptionObject;
    }
  }
  else if ( !(unsigned int)QueryUserToken(a2, &phToken) )
  {
    v7 = ResultFromKnownLastError();
    if ( v7 < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pExceptionObject,
        v7,
        "QueryUserToken(sessionId, temp.GetAddressOf())",
        "AppReadiness::Service::GetSessionUserToken",
        "onecoreuap\\shell\\appreadiness\\src\\core\\service.cpp",
        635);
      throw (Windows::HResultException *)pExceptionObject;
    }
  }
  *(_QWORD *)a1 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  *(_QWORD *)(a1 + 8) = 0;
  if ( !DuplicateTokenEx(phToken, 0xEu, 0, SecurityImpersonation, TokenImpersonation, (PHANDLE)(a1 + 8)) )
  {
    v8 = ResultFromKnownLastError();
    if ( v8 < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pExceptionObject,
        v8,
        "DuplicateTokenEx(temp.Get(), TOKEN_IMPERSONATE|TOKEN_QUERY|TOKEN_DUPLICATE, nullptr, SecurityImpersonation, Toke"
        "nImpersonation, token.GetAddressOf())",
        "AppReadiness::Service::GetSessionUserToken",
        "onecoreuap\\shell\\appreadiness\\src\\core\\service.cpp",
        639);
      throw (Windows::HResultException *)pExceptionObject;
    }
  }
  v10 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(&v10);
  return a1;
}

```

## disassembly

```asm
0x180027158  mov     [rsp-20h+arg_0], rcx
0x18002715d  push    rbp
0x18002715e  push    rbx
0x18002715f  push    rdi
0x180027160  push    r14
0x180027162  mov     rbp, rsp
0x180027165  sub     rsp, 78h
0x180027169  mov     ebx, edx
0x18002716b  mov     rdi, rcx
0x18002716e  mov     [rbp+var_48], 0
0x180027175  lea     r14, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x18002717c  mov     [rbp+var_40], r14
0x180027180  mov     [rbp+phToken], 0
0x180027188  call    IsWTSEnumerateSessionsWPresent
0x18002718d  test    al, al
0x18002718f  jz      short loc_1800271F0
0x180027191  lea     rdx, [rbp+phToken]; phToken
0x180027195  mov     ecx, ebx; SessionId
0x180027197  call    cs:__imp_WTSQueryUserToken
0x18002719d  test    eax, eax
0x18002719f  jnz     loc_18002729C
0x1800271a5  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800271aa  test    eax, eax
0x1800271ac  jns     loc_18002729C
0x1800271b2  mov     dword ptr [rsp+78h+phNewToken], 273h; int
0x1800271ba  lea     rcx, aOnecoreuapShel_4; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x1800271c1  mov     qword ptr [rsp+78h+TokenType], rcx; char *
0x1800271c6  lea     r9, aAppreadinessSe_5; "AppReadiness::Service::GetSessionUserTo"...
0x1800271cd  lea     r8, aWtsqueryuserto_0; "WTSQueryUserToken(sessionId, temp.GetAd"...
0x1800271d4  mov     edx, eax; int
0x1800271d6  lea     rcx, [rbp+pExceptionObject]; this
0x1800271da  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x1800271df  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x1800271e6  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800271ea  call    _CxxThrowException_0
0x1800271f0  call    IsUMgrEnumerateSessionUsersPresent
0x1800271f5  lea     rdx, [rbp+phToken]
0x1800271f9  mov     ecx, ebx
0x1800271fb  test    al, al
0x1800271fd  jz      short loc_18002724B
0x1800271ff  call    cs:__imp_UMgrQuerySessionUserToken
0x180027205  test    eax, eax
0x180027207  jns     loc_18002729C
0x18002720d  mov     dword ptr [rsp+78h+phNewToken], 277h; int
0x180027215  lea     rcx, aOnecoreuapShel_4; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18002721c  mov     qword ptr [rsp+78h+TokenType], rcx; char *
0x180027221  lea     r9, aAppreadinessSe_5; "AppReadiness::Service::GetSessionUserTo"...
0x180027228  lea     r8, aUmgrquerysessi_0; "UMgrQuerySessionUserToken(sessionId, te"...
0x18002722f  mov     edx, eax; int
0x180027231  lea     rcx, [rbp+pExceptionObject]; this
0x180027235  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18002723a  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180027241  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180027245  call    _CxxThrowException_0
0x18002724b  call    cs:__imp_QueryUserToken
0x180027251  test    eax, eax
0x180027253  jnz     short loc_18002729C
0x180027255  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002725a  test    eax, eax
0x18002725c  jns     short loc_18002729C
0x18002725e  mov     dword ptr [rsp+78h+phNewToken], 27Bh; int
0x180027266  lea     rcx, aOnecoreuapShel_4; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18002726d  mov     qword ptr [rsp+78h+TokenType], rcx; char *
0x180027272  lea     r9, aAppreadinessSe_5; "AppReadiness::Service::GetSessionUserTo"...
0x180027279  lea     r8, aQueryusertoken_1; "QueryUserToken(sessionId, temp.GetAddre"...
0x180027280  mov     edx, eax; int
0x180027282  lea     rcx, [rbp+pExceptionObject]; this
0x180027286  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18002728b  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180027292  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180027296  call    _CxxThrowException_0
0x18002729c  mov     [rdi], r14
0x18002729f  lea     rax, [rdi+8]
0x1800272a3  mov     qword ptr [rax], 0
0x1800272aa  mov     [rbp+var_48], 1
0x1800272b1  mov     [rsp+78h+phNewToken], rax; phNewToken
0x1800272b6  mov     r9d, 2; ImpersonationLevel
0x1800272bc  mov     [rsp+78h+TokenType], r9d; TokenType
0x1800272c1  xor     r8d, r8d; lpTokenAttributes
0x1800272c4  lea     edx, [r9+0Ch]; dwDesiredAccess
0x1800272c8  mov     rcx, [rbp+phToken]; hExistingToken
0x1800272cc  call    cs:__imp_DuplicateTokenEx
0x1800272d2  test    eax, eax
0x1800272d4  jnz     short loc_18002731D
0x1800272d6  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800272db  test    eax, eax
0x1800272dd  jns     short loc_18002731D
0x1800272df  mov     dword ptr [rsp+78h+phNewToken], 27Fh; int
0x1800272e7  lea     rcx, aOnecoreuapShel_4; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x1800272ee  mov     qword ptr [rsp+78h+TokenType], rcx; char *
0x1800272f3  lea     r9, aAppreadinessSe_5; "AppReadiness::Service::GetSessionUserTo"...
0x1800272fa  lea     r8, aDuplicatetoken_0; "DuplicateTokenEx(temp.Get(), TOKEN_IMPE"...
0x180027301  mov     edx, eax; int
0x180027303  lea     rcx, [rbp+pExceptionObject]; this
0x180027307  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18002730c  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180027313  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180027317  call    _CxxThrowException_0
0x18002731d  mov     [rbp+var_40], r14
0x180027321  lea     rcx, [rbp+var_40]
0x180027325  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x18002732a  mov     rax, rdi
0x18002732d  add     rsp, 78h
0x180027331  pop     r14
0x180027333  pop     rdi
0x180027334  pop     rbx
0x180027335  pop     rbp
0x180027336  retn
```
