# Windows::Internal::AssignedAccess::AutoImpersonation::ImpersonateInternal(ushort const *)

- ea: `0x180084e6c`
- end: `0x180084f47`
- name: `?ImpersonateInternal@AutoImpersonation@AssignedAccess@Internal@Windows@@AEAAJPEBG@Z`
- size: `219`
- prototype: `__int64 __fastcall(Windows::Internal::AssignedAccess::AutoImpersonation *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800847e0`

## callees

- `0x180008e90`
- `0x18000b694`
- `0x18000b6b4`
- `0x18004f4d4`
- `0x180084e6c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180084f2b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180084f2b`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180084f14`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180084f14`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180084ef1`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180084ef1`

## string_xrefs

- `0x180084eb4`: `onecoreuap\base\embedded\sys\lockdown\runtime\inc\autoimpersonation.h`
- `0x180084f02`: `onecoreuap\base\embedded\sys\lockdown\runtime\inc\autoimpersonation.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
__int64 __fastcall Windows::Internal::AssignedAccess::AutoImpersonation::ImpersonateInternal(
        Windows::Internal::AssignedAccess::AutoImpersonation *this,
        const unsigned __int16 *a2)
{
  int v2; // ebx
  __int64 v3; // rdx
  const char *v5; // r9
  __int64 v6; // rdx
  unsigned __int64 v7; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+8h]
  Windows::Internal::AssignedAccess::AutoImpersonation *v9; // [rsp+40h] [rbp+10h] BYREF
  ULONG SessionId; // [rsp+50h] [rbp+20h] BYREF
  void *phToken; // [rsp+58h] [rbp+28h] BYREF

  v9 = this;
  LOBYTE(v9) = 0;
  SessionId = 0;
  v7 = 0;
  v2 = Windows::Internal::AssignedAccess::UserSessionHelper::LookupUserSession(a2, (bool *)&v9, &SessionId, &v7);
  if ( v2 < 0 )
  {
    v3 = 46;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\inc\\autoimpersonation.h",
      (const char *)(unsigned int)v2,
      v7);
    return (unsigned int)v2;
  }
  if ( !(_BYTE)v9 )
  {
    v2 = -2147467259;
    v3 = 47;
    goto LABEL_3;
  }
  phToken = 0;
  if ( (unsigned __int8)IsWTSEnumerateSessionsWPresent() )
  {
    if ( !WTSQueryUserToken(SessionId, &phToken) )
    {
      v6 = 51;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v6,
               (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\inc\\autoimpersonation.h",
               v5);
    }
  }
  else
  {
    v2 = UMgrQueryUserToken(v7, &phToken);
    if ( v2 < 0 )
    {
      v3 = 55;
      goto LABEL_3;
    }
  }
  if ( !ImpersonateLoggedOnUser(phToken) )
  {
    v6 = 58;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v6,
             (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\inc\\autoimpersonation.h",
             v5);
  }
  return 0;
}

```

## disassembly

```asm
0x180084e6c  mov     [rsp-8+arg_8], rbx
0x180084e71  mov     [rsp-8+arg_0], rcx
0x180084e76  push    rbp
0x180084e77  mov     rbp, rsp
0x180084e7a  sub     rsp, 30h
0x180084e7e  mov     rcx, rdx; unsigned __int16 *
0x180084e81  mov     byte ptr [rbp+arg_0], 0
0x180084e85  lea     rdx, [rbp+arg_0]; bool *
0x180084e89  mov     [rbp+SessionId], 0
0x180084e90  lea     r9, [rbp+var_10]; unsigned __int64 *
0x180084e94  mov     [rbp+var_10], 0
0x180084e9c  lea     r8, [rbp+SessionId]; unsigned int *
0x180084ea0  call    ?LookupUserSession@UserSessionHelper@AssignedAccess@Internal@Windows@@SAJPEBGAEA_NAEAKAEA_K@Z; Windows::Internal::AssignedAccess::UserSessionHelper::LookupUserSession(ushort const *,bool &,ulong &,unsigned __int64 &)
0x180084ea5  mov     ebx, eax
0x180084ea7  test    eax, eax
0x180084ea9  jns     short loc_180084EC7
0x180084eab  mov     edx, 2Eh ; '.'; void *
0x180084eb0  mov     rcx, [rbp+8]; this
0x180084eb4  lea     r8, aOnecoreuapBase_81; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180084ebb  mov     r9d, ebx; char *
0x180084ebe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084ec3  mov     eax, ebx
0x180084ec5  jmp     short loc_180084F3C
0x180084ec7  cmp     byte ptr [rbp+arg_0], 0
0x180084ecb  jnz     short loc_180084ED9
0x180084ecd  mov     ebx, 80004005h
0x180084ed2  mov     edx, 2Fh ; '/'
0x180084ed7  jmp     short loc_180084EB0
0x180084ed9  mov     [rbp+phToken], 0
0x180084ee1  call    IsWTSEnumerateSessionsWPresent
0x180084ee6  lea     rdx, [rbp+phToken]; phToken
0x180084eea  test    al, al
0x180084eec  jz      short loc_180084F10
0x180084eee  mov     ecx, [rbp+SessionId]; SessionId
0x180084ef1  call    cs:__imp_WTSQueryUserToken
0x180084ef7  test    eax, eax
0x180084ef9  jnz     short loc_180084F27
0x180084efb  lea     edx, [rax+33h]; void *
0x180084efe  mov     rcx, [rbp+8]; this
0x180084f02  lea     r8, aOnecoreuapBase_81; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180084f09  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180084f0e  jmp     short loc_180084F3C
0x180084f10  mov     rcx, [rbp+var_10]
0x180084f14  call    cs:__imp_UMgrQueryUserToken
0x180084f1a  mov     ebx, eax
0x180084f1c  test    eax, eax
0x180084f1e  jns     short loc_180084F27
0x180084f20  mov     edx, 37h ; '7'
0x180084f25  jmp     short loc_180084EB0
0x180084f27  mov     rcx, [rbp+phToken]; hToken
0x180084f2b  call    cs:__imp_ImpersonateLoggedOnUser
0x180084f31  test    eax, eax
0x180084f33  jnz     short loc_180084F3A
0x180084f35  lea     edx, [rax+3Ah]
0x180084f38  jmp     short loc_180084EFE
0x180084f3a  xor     eax, eax
0x180084f3c  mov     rbx, [rsp+30h+arg_8]
0x180084f41  add     rsp, 30h
0x180084f45  pop     rbp
0x180084f46  retn
```
