# AppReadiness::Api::DoesCallerHaveAdminRights(void)

- ea: `0x1800371d8`
- end: `0x180037345`
- name: `?DoesCallerHaveAdminRights@Api@AppReadiness@@AEAA_NXZ`
- size: `365`
- prototype: `char __fastcall(AppReadiness::Api *this)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180045f74`
- `0x18004630c`

## callees

- `0x1800041e0`
- `0x180012124`
- `0x180027a4c`
- `0x1800371d8`
- `0x18003e210`
- `0x18003ecb4`
- `0x1800473d8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003730e`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003730e`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180037299`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180037299`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800372f9`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800372f9`

## string_xrefs

- `0x180037223`: `onecoreuap\shell\appreadiness\src\core\api.cpp`
- `0x1800372b4`: `onecoreuap\shell\appreadiness\src\core\api.cpp`
- `0x18003722f`: `AppReadiness::Api::DoesCallerHaveAdminRights`
- `0x1800372c0`: `AppReadiness::Api::DoesCallerHaveAdminRights`
- `0x180037236`: `GetCallingUserToken(TOKEN_QUERY, callingUser.GetAddressOf())`
- `0x1800372c7`: `AllocateAndInitializeSid(&sidAuth, 2, SECURITY_BUILTIN_DOMAIN_RID, DOMAIN_ALIAS_RID_ADMINS, 0, 0, 0, 0, 0, 0, &sidGroup)`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall AppReadiness::Api::DoesCallerHaveAdminRights(AppReadiness::Api *this)
{
  char v1; // bl
  int CallingUserToken; // eax
  int Error; // eax
  WINBOOL IsMember; // [rsp+60h] [rbp-9h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-1h] BYREF
  void **v7; // [rsp+70h] [rbp+7h] BYREF
  HANDLE TokenHandle; // [rsp+78h] [rbp+Fh] BYREF
  _BYTE pExceptionObject[40]; // [rsp+80h] [rbp+17h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+A8h] [rbp+3Fh] BYREF

  v7 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  v1 = 0;
  TokenHandle = 0;
  CallingUserToken = AppReadiness::GetCallingUserToken(this, &TokenHandle);
  if ( CallingUserToken < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      CallingUserToken,
      "GetCallingUserToken(TOKEN_QUERY, callingUser.GetAddressOf())",
      "AppReadiness::Api::DoesCallerHaveAdminRights",
      "onecoreuap\\shell\\appreadiness\\src\\core\\api.cpp",
      340);
    throw (Windows::HResultException *)pExceptionObject;
  }
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  SidToCheck = 0;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pExceptionObject,
        Error,
        "AllocateAndInitializeSid(&sidAuth, 2, SECURITY_BUILTIN_DOMAIN_RID, DOMAIN_ALIAS_RID_ADMINS, 0, 0, 0, 0, 0, 0, &sidGroup)",
        "AppReadiness::Api::DoesCallerHaveAdminRights",
        "onecoreuap\\shell\\appreadiness\\src\\core\\api.cpp",
        344);
      throw (Windows::HResultException *)pExceptionObject;
    }
  }
  IsMember = 0;
  if ( CheckTokenMembership(TokenHandle, SidToCheck, &IsMember) && IsMember )
    v1 = 1;
  FreeSid(SidToCheck);
  v7 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(&v7);
  return v1;
}

```

## disassembly

```asm
0x1800371d8  mov     [rsp-8+arg_0], rbx
0x1800371dd  mov     [rsp-8+arg_8], rdi
0x1800371e2  push    rbp
0x1800371e3  lea     rbp, [rsp-57h]
0x1800371e8  sub     rsp, 0C0h
0x1800371ef  mov     rax, cs:__security_cookie
0x1800371f6  xor     rax, rsp
0x1800371f9  mov     [rbp+57h+var_10], rax
0x1800371fd  lea     rdi, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180037204  mov     [rbp+57h+var_50], rdi
0x180037208  xor     ebx, ebx
0x18003720a  mov     [rbp+57h+TokenHandle], rbx
0x18003720e  lea     rdx, [rbp+57h+TokenHandle]
0x180037212  call    AppReadiness__GetCallingUserToken
0x180037217  test    eax, eax
0x180037219  jns     short loc_180037259
0x18003721b  mov     [rsp+0C0h+nSubAuthority3], 154h; int
0x180037223  lea     rcx, aOnecoreuapShel_38; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18003722a  mov     qword ptr [rsp+0C0h+nSubAuthority2], rcx; char *
0x18003722f  lea     r9, aAppreadinessAp_4; "AppReadiness::Api::DoesCallerHaveAdminR"...
0x180037236  lea     r8, aGetcallinguser; "GetCallingUserToken(TOKEN_QUERY, callin"...
0x18003723d  mov     edx, eax; int
0x18003723f  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180037243  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180037248  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18003724f  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180037253  call    _CxxThrowException_0
0x180037259  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], ebx
0x18003725c  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180037262  mov     [rbp+57h+SidToCheck], rbx
0x180037266  lea     rax, [rbp+57h+SidToCheck]
0x18003726a  mov     [rsp+0C0h+pSid], rax; pSid
0x18003726f  mov     [rsp+0C0h+nSubAuthority7], ebx; nSubAuthority7
0x180037273  mov     [rsp+0C0h+nSubAuthority6], ebx; nSubAuthority6
0x180037277  mov     [rsp+0C0h+nSubAuthority5], ebx; nSubAuthority5
0x18003727b  mov     [rsp+0C0h+nSubAuthority4], ebx; nSubAuthority4
0x18003727f  mov     [rsp+0C0h+nSubAuthority3], ebx; nSubAuthority3
0x180037283  mov     [rsp+0C0h+nSubAuthority2], ebx; nSubAuthority2
0x180037287  mov     r9d, 220h; nSubAuthority1
0x18003728d  mov     r8d, 20h ; ' '; nSubAuthority0
0x180037293  mov     dl, 2; nSubAuthorityCount
0x180037295  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180037299  call    cs:__imp_AllocateAndInitializeSid
0x18003729f  test    eax, eax
0x1800372a1  jnz     short loc_1800372EA
0x1800372a3  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800372a8  test    eax, eax
0x1800372aa  jns     short loc_1800372EA
0x1800372ac  mov     [rsp+0C0h+nSubAuthority3], 158h; int
0x1800372b4  lea     rcx, aOnecoreuapShel_38; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x1800372bb  mov     qword ptr [rsp+0C0h+nSubAuthority2], rcx; char *
0x1800372c0  lea     r9, aAppreadinessAp_4; "AppReadiness::Api::DoesCallerHaveAdminR"...
0x1800372c7  lea     r8, aAllocateandini; "AllocateAndInitializeSid(&sidAuth, 2, S"...
0x1800372ce  mov     edx, eax; int
0x1800372d0  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800372d4  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x1800372d9  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x1800372e0  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800372e4  call    _CxxThrowException_0
0x1800372ea  mov     [rbp+57h+IsMember], ebx
0x1800372ed  lea     r8, [rbp+57h+IsMember]; IsMember
0x1800372f1  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x1800372f5  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800372f9  call    cs:__imp_CheckTokenMembership
0x1800372ff  test    eax, eax
0x180037301  jz      short loc_18003730A
0x180037303  cmp     [rbp+57h+IsMember], ebx
0x180037306  jz      short loc_18003730A
0x180037308  mov     bl, 1
0x18003730a  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x18003730e  call    cs:__imp_FreeSid
0x180037314  nop
0x180037315  mov     [rbp+57h+var_50], rdi
0x180037319  lea     rcx, [rbp+57h+var_50]
0x18003731d  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x180037322  mov     al, bl
0x180037324  mov     rcx, [rbp+57h+var_10]
0x180037328  xor     rcx, rsp; StackCookie
0x18003732b  call    __security_check_cookie
0x180037330  lea     r11, [rsp+0C0h+var_s0]
0x180037338  mov     rbx, [r11+10h]
0x18003733c  mov     rdi, [r11+18h]
0x180037340  mov     rsp, r11
0x180037343  pop     rbp
0x180037344  retn
```
