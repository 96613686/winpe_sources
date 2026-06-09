# Windows::COM::CIdentityAuthority::Hash<IDefinitionIdentity>(ulong,IDefinitionIdentity *,unsigned __int64 *)

- ea: `0x180078a68`
- end: `0x180078bc6`
- name: `??$Hash@UIDefinitionIdentity@@@CIdentityAuthority@COM@Windows@@IEAAJKPEAUIDefinitionIdentity@@PEA_K@Z`
- size: `350`
- prototype: `__int64 __fastcall(__int64, int, Windows::COM *, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180079420`

## callees

- `0x180010c10`
- `0x18001f4e4`
- `0x18001f51c`
- `0x1800293a0`
- `0x18006b1e0`
- `0x180078a68`
- `0x18008597c`
- `0x180093bdc`
- `0x1800a0020`

## string_xrefs

- `0x180078a9d`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x180078add`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x180078b1d`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x180078afb`: `Not-null check failed: pICOMIdentity`
- `0x180078ab4`: `Windows::COM::CIdentityAuthority::Hash`
- `0x180078af0`: `Windows::COM::CIdentityAuthority::Hash`
- `0x180078b30`: `Windows::COM::CIdentityAuthority::Hash`

## pseudocode

```c
__int64 __fastcall Windows::COM::CIdentityAuthority::Hash<IDefinitionIdentity>(
        __int64 a1,
        int a2,
        Windows::COM *a3,
        _QWORD *a4)
{
  __int64 result; // rax
  const char *v6; // rax
  __int64 v7; // rcx
  int IdentityAuthority; // eax
  unsigned int v9; // ebx
  const char *v10; // [rsp+30h] [rbp-40h] BYREF
  const char *v11; // [rsp+38h] [rbp-38h]
  __int64 v12; // [rsp+40h] [rbp-30h]
  const char *v13; // [rsp+48h] [rbp-28h]
  __int64 v14; // [rsp+50h] [rbp-20h] BYREF
  __int64 v15; // [rsp+58h] [rbp-18h] BYREF

  LODWORD(v15) = 0;
  if ( a4 )
    *a4 = 0;
  if ( a2 )
  {
    v12 = 468;
    v10 = "onecore\\base\\wcp\\identity\\com\\identity_authority.cpp";
    v11 = "Windows::COM::CIdentityAuthority::Hash";
    v13 = "Valid flags check failed: dwFlags";
    return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter(
             &v15,
             &v10);
  }
  if ( !a3 )
  {
    v12 = 469;
    v10 = "onecore\\base\\wcp\\identity\\com\\identity_authority.cpp";
    v11 = "Windows::COM::CIdentityAuthority::Hash";
    v6 = "Not-null check failed: pICOMIdentity";
LABEL_7:
    v13 = v6;
    return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v15,
             &v10);
  }
  if ( !a4 )
  {
    v12 = 470;
    v10 = "onecore\\base\\wcp\\identity\\com\\identity_authority.cpp";
    v11 = "Windows::COM::CIdentityAuthority::Hash";
    v6 = "Not-null check failed: pPseudoKey";
    goto LABEL_7;
  }
  v14 = 0;
  result = Windows::COM::ConvertIn(
             a3,
             (struct IDefinitionIdentity *)&v14,
             (struct Windows::Identity::Rtl::IRtlDefinitionIdentity **)a3);
  if ( (int)result >= 0 )
  {
    v15 = 0;
    IdentityAuthority = RtlGetIdentityAuthority(v7, &v15);
    if ( IdentityAuthority >= 0
      && (IdentityAuthority = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64, _QWORD *))(*(_QWORD *)v15 + 80LL))(
                                v15,
                                0,
                                0,
                                v14,
                                a4),
          IdentityAuthority >= 0) )
    {
      v9 = 0;
    }
    else
    {
      v9 = ConvertNtStatusToHResult((unsigned int)IdentityAuthority);
    }
    Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(&v15);
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x180078a68  mov     [rsp-8+arg_0], rbx
0x180078a6d  push    rbp
0x180078a6e  mov     rbp, rsp
0x180078a71  sub     rsp, 70h
0x180078a75  mov     rax, cs:__security_cookie
0x180078a7c  xor     rax, rsp
0x180078a7f  mov     [rbp+var_10], rax
0x180078a83  mov     dword ptr [rbp+var_18], 0
0x180078a8a  mov     rbx, r9
0x180078a8d  test    r9, r9
0x180078a90  jz      short loc_180078A99
0x180078a92  mov     qword ptr [r9], 0
0x180078a99  test    edx, edx
0x180078a9b  jz      short loc_180078AD8
0x180078a9d  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x180078aa4  mov     [rbp+var_30], 1D4h
0x180078aac  mov     [rbp+var_40], rax
0x180078ab0  lea     rdx, [rbp+var_40]
0x180078ab4  lea     rax, aWindowsComCide_2; "Windows::COM::CIdentityAuthority::Hash"
0x180078abb  mov     [rbp+var_38], rax
0x180078abf  lea     rcx, [rbp+var_18]
0x180078ac3  lea     rax, aValidFlagsChec_0; "Valid flags check failed: dwFlags"
0x180078aca  mov     [rbp+var_28], rax
0x180078ace  call    ?OriginateInvalidParameter@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180078ad3  jmp     loc_180078BAB
0x180078ad8  test    r8, r8
0x180078adb  jnz     short loc_180078B18
0x180078add  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x180078ae4  mov     [rbp+var_30], 1D5h
0x180078aec  mov     [rbp+var_40], rax
0x180078af0  lea     rax, aWindowsComCide_2; "Windows::COM::CIdentityAuthority::Hash"
0x180078af7  mov     [rbp+var_38], rax
0x180078afb  lea     rax, aNotNullCheckFa_41; "Not-null check failed: pICOMIdentity"
0x180078b02  lea     rdx, [rbp+var_40]
0x180078b06  mov     [rbp+var_28], rax
0x180078b0a  lea     rcx, [rbp+var_18]
0x180078b0e  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180078b13  jmp     loc_180078BAB
0x180078b18  test    rbx, rbx
0x180078b1b  jnz     short loc_180078B44
0x180078b1d  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x180078b24  mov     [rbp+var_30], 1D6h
0x180078b2c  mov     [rbp+var_40], rax
0x180078b30  lea     rax, aWindowsComCide_2; "Windows::COM::CIdentityAuthority::Hash"
0x180078b37  mov     [rbp+var_38], rax
0x180078b3b  lea     rax, aNotNullCheckFa_60; "Not-null check failed: pPseudoKey"
0x180078b42  jmp     short loc_180078B02
0x180078b44  lea     rdx, [rbp+var_20]; struct IDefinitionIdentity *
0x180078b48  mov     [rbp+var_20], 0
0x180078b50  mov     rcx, r8; this
0x180078b53  call    ?ConvertIn@COM@Windows@@YAJPEAUIDefinitionIdentity@@PEAPEAUIRtlDefinitionIdentity@Rtl@Identity@2@@Z; Windows::COM::ConvertIn(IDefinitionIdentity *,Windows::Identity::Rtl::IRtlDefinitionIdentity * *)
0x180078b58  test    eax, eax
0x180078b5a  js      short loc_180078BAB
0x180078b5c  lea     rdx, [rbp+var_18]
0x180078b60  mov     [rbp+var_18], 0
0x180078b68  call    RtlGetIdentityAuthority
0x180078b6d  test    eax, eax
0x180078b6f  js      short loc_180078B93
0x180078b71  mov     rcx, [rbp+var_18]
0x180078b75  xor     r8d, r8d
0x180078b78  mov     r9, [rbp+var_20]
0x180078b7c  xor     edx, edx
0x180078b7e  mov     [rsp+70h+var_50], rbx
0x180078b83  mov     rax, [rcx]
0x180078b86  mov     rax, [rax+50h]
0x180078b8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078b8f  test    eax, eax
0x180078b91  jns     short loc_180078B9E
0x180078b93  mov     ecx, eax
0x180078b95  call    ConvertNtStatusToHResult
0x180078b9a  mov     ebx, eax
0x180078b9c  jmp     short loc_180078BA0
0x180078b9e  xor     ebx, ebx
0x180078ba0  lea     rcx, [rbp+var_18]
0x180078ba4  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x180078ba9  mov     eax, ebx
0x180078bab  mov     rcx, [rbp+var_10]
0x180078baf  xor     rcx, rsp; StackCookie
0x180078bb2  call    __security_check_cookie
0x180078bb7  mov     rbx, [rsp+70h+arg_0]
0x180078bbf  add     rsp, 70h
0x180078bc3  pop     rbp
0x180078bc4  retn
```
