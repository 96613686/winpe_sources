# Windows::COM::CIdentityAuthority::Hash<IReferenceIdentity>(ulong,IReferenceIdentity *,unsigned __int64 *)

- ea: `0x180078bcc`
- end: `0x180078d2a`
- name: `??$Hash@UIReferenceIdentity@@@CIdentityAuthority@COM@Windows@@IEAAJKPEAUIReferenceIdentity@@PEA_K@Z`
- size: `350`
- prototype: `__int64 __fastcall(__int64, int, Windows::COM *, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180079430`

## callees

- `0x180010c10`
- `0x18001f4e4`
- `0x18001f51c`
- `0x1800293a0`
- `0x18006b1e0`
- `0x180078bcc`
- `0x180085a38`
- `0x180093bdc`
- `0x1800a0020`

## string_xrefs

- `0x180078c01`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x180078c41`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x180078c81`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x180078c5f`: `Not-null check failed: pICOMIdentity`
- `0x180078c18`: `Windows::COM::CIdentityAuthority::Hash`
- `0x180078c54`: `Windows::COM::CIdentityAuthority::Hash`
- `0x180078c94`: `Windows::COM::CIdentityAuthority::Hash`

## pseudocode

```c
__int64 __fastcall Windows::COM::CIdentityAuthority::Hash<IReferenceIdentity>(
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
             (struct IReferenceIdentity *)&v14,
             (struct Windows::Identity::Rtl::IRtlReferenceIdentity **)a3);
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
0x180078bcc  mov     [rsp-8+arg_0], rbx
0x180078bd1  push    rbp
0x180078bd2  mov     rbp, rsp
0x180078bd5  sub     rsp, 70h
0x180078bd9  mov     rax, cs:__security_cookie
0x180078be0  xor     rax, rsp
0x180078be3  mov     [rbp+var_10], rax
0x180078be7  mov     dword ptr [rbp+var_18], 0
0x180078bee  mov     rbx, r9
0x180078bf1  test    r9, r9
0x180078bf4  jz      short loc_180078BFD
0x180078bf6  mov     qword ptr [r9], 0
0x180078bfd  test    edx, edx
0x180078bff  jz      short loc_180078C3C
0x180078c01  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x180078c08  mov     [rbp+var_30], 1D4h
0x180078c10  mov     [rbp+var_40], rax
0x180078c14  lea     rdx, [rbp+var_40]
0x180078c18  lea     rax, aWindowsComCide_2; "Windows::COM::CIdentityAuthority::Hash"
0x180078c1f  mov     [rbp+var_38], rax
0x180078c23  lea     rcx, [rbp+var_18]
0x180078c27  lea     rax, aValidFlagsChec_0; "Valid flags check failed: dwFlags"
0x180078c2e  mov     [rbp+var_28], rax
0x180078c32  call    ?OriginateInvalidParameter@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180078c37  jmp     loc_180078D0F
0x180078c3c  test    r8, r8
0x180078c3f  jnz     short loc_180078C7C
0x180078c41  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x180078c48  mov     [rbp+var_30], 1D5h
0x180078c50  mov     [rbp+var_40], rax
0x180078c54  lea     rax, aWindowsComCide_2; "Windows::COM::CIdentityAuthority::Hash"
0x180078c5b  mov     [rbp+var_38], rax
0x180078c5f  lea     rax, aNotNullCheckFa_41; "Not-null check failed: pICOMIdentity"
0x180078c66  lea     rdx, [rbp+var_40]
0x180078c6a  mov     [rbp+var_28], rax
0x180078c6e  lea     rcx, [rbp+var_18]
0x180078c72  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180078c77  jmp     loc_180078D0F
0x180078c7c  test    rbx, rbx
0x180078c7f  jnz     short loc_180078CA8
0x180078c81  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x180078c88  mov     [rbp+var_30], 1D6h
0x180078c90  mov     [rbp+var_40], rax
0x180078c94  lea     rax, aWindowsComCide_2; "Windows::COM::CIdentityAuthority::Hash"
0x180078c9b  mov     [rbp+var_38], rax
0x180078c9f  lea     rax, aNotNullCheckFa_60; "Not-null check failed: pPseudoKey"
0x180078ca6  jmp     short loc_180078C66
0x180078ca8  lea     rdx, [rbp+var_20]; struct IReferenceIdentity *
0x180078cac  mov     [rbp+var_20], 0
0x180078cb4  mov     rcx, r8; this
0x180078cb7  call    ?ConvertIn@COM@Windows@@YAJPEAUIReferenceIdentity@@PEAPEAUIRtlReferenceIdentity@Rtl@Identity@2@@Z; Windows::COM::ConvertIn(IReferenceIdentity *,Windows::Identity::Rtl::IRtlReferenceIdentity * *)
0x180078cbc  test    eax, eax
0x180078cbe  js      short loc_180078D0F
0x180078cc0  lea     rdx, [rbp+var_18]
0x180078cc4  mov     [rbp+var_18], 0
0x180078ccc  call    RtlGetIdentityAuthority
0x180078cd1  test    eax, eax
0x180078cd3  js      short loc_180078CF7
0x180078cd5  mov     rcx, [rbp+var_18]
0x180078cd9  xor     r8d, r8d
0x180078cdc  mov     r9, [rbp+var_20]
0x180078ce0  xor     edx, edx
0x180078ce2  mov     [rsp+70h+var_50], rbx
0x180078ce7  mov     rax, [rcx]
0x180078cea  mov     rax, [rax+50h]
0x180078cee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078cf3  test    eax, eax
0x180078cf5  jns     short loc_180078D02
0x180078cf7  mov     ecx, eax
0x180078cf9  call    ConvertNtStatusToHResult
0x180078cfe  mov     ebx, eax
0x180078d00  jmp     short loc_180078D04
0x180078d02  xor     ebx, ebx
0x180078d04  lea     rcx, [rbp+var_18]
0x180078d08  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x180078d0d  mov     eax, ebx
0x180078d0f  mov     rcx, [rbp+var_10]
0x180078d13  xor     rcx, rsp; StackCookie
0x180078d16  call    __security_check_cookie
0x180078d1b  mov     rbx, [rsp+70h+arg_0]
0x180078d23  add     rsp, 70h
0x180078d27  pop     rbp
0x180078d28  retn
```
