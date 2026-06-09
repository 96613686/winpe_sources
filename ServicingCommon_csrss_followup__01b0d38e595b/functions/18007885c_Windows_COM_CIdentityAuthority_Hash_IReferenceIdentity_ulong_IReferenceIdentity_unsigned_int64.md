# Windows::COM::CIdentityAuthority::Hash<IReferenceIdentity>(ulong,IReferenceIdentity *,unsigned __int64 *)

- ea: `0x18007885c`
- end: `0x1800789ba`
- name: `??$Hash@UIReferenceIdentity@@@CIdentityAuthority@COM@Windows@@IEAAJKPEAUIReferenceIdentity@@PEA_K@Z`
- size: `350`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800790d0`

## callees

- `0x18001af00`
- `0x18002175c`
- `0x180021794`
- `0x18002d2b0`
- `0x18006b3e0`
- `0x18007885c`
- `0x180084acc`
- `0x18009255c`
- `0x18009e020`

## string_xrefs

- `0x180078891`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x1800788d1`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x180078911`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x1800788ef`: `Not-null check failed: pICOMIdentity`
- `0x1800788a8`: `Windows::COM::CIdentityAuthority::Hash`
- `0x1800788e4`: `Windows::COM::CIdentityAuthority::Hash`
- `0x180078924`: `Windows::COM::CIdentityAuthority::Hash`

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
             &v10,
             a3);
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
0x18007885c  mov     [rsp-8+arg_0], rbx
0x180078861  push    rbp
0x180078862  mov     rbp, rsp
0x180078865  sub     rsp, 70h
0x180078869  mov     rax, cs:__security_cookie
0x180078870  xor     rax, rsp
0x180078873  mov     [rbp+var_10], rax
0x180078877  mov     dword ptr [rbp+var_18], 0
0x18007887e  mov     rbx, r9
0x180078881  test    r9, r9
0x180078884  jz      short loc_18007888D
0x180078886  mov     qword ptr [r9], 0
0x18007888d  test    edx, edx
0x18007888f  jz      short loc_1800788CC
0x180078891  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x180078898  mov     [rbp+var_30], 1D4h
0x1800788a0  mov     [rbp+var_40], rax
0x1800788a4  lea     rdx, [rbp+var_40]
0x1800788a8  lea     rax, aWindowsComCide_2; "Windows::COM::CIdentityAuthority::Hash"
0x1800788af  mov     [rbp+var_38], rax
0x1800788b3  lea     rcx, [rbp+var_18]
0x1800788b7  lea     rax, aValidFlagsChec_0; "Valid flags check failed: dwFlags"
0x1800788be  mov     [rbp+var_28], rax
0x1800788c2  call    ?OriginateInvalidParameter@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x1800788c7  jmp     loc_18007899F
0x1800788cc  test    r8, r8
0x1800788cf  jnz     short loc_18007890C
0x1800788d1  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x1800788d8  mov     [rbp+var_30], 1D5h
0x1800788e0  mov     [rbp+var_40], rax
0x1800788e4  lea     rax, aWindowsComCide_2; "Windows::COM::CIdentityAuthority::Hash"
0x1800788eb  mov     [rbp+var_38], rax
0x1800788ef  lea     rax, aNotNullCheckFa_41; "Not-null check failed: pICOMIdentity"
0x1800788f6  lea     rdx, [rbp+var_40]
0x1800788fa  mov     [rbp+var_28], rax
0x1800788fe  lea     rcx, [rbp+var_18]
0x180078902  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180078907  jmp     loc_18007899F
0x18007890c  test    rbx, rbx
0x18007890f  jnz     short loc_180078938
0x180078911  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x180078918  mov     [rbp+var_30], 1D6h
0x180078920  mov     [rbp+var_40], rax
0x180078924  lea     rax, aWindowsComCide_2; "Windows::COM::CIdentityAuthority::Hash"
0x18007892b  mov     [rbp+var_38], rax
0x18007892f  lea     rax, aNotNullCheckFa_60; "Not-null check failed: pPseudoKey"
0x180078936  jmp     short loc_1800788F6
0x180078938  lea     rdx, [rbp+var_20]; struct IReferenceIdentity *
0x18007893c  mov     [rbp+var_20], 0
0x180078944  mov     rcx, r8; this
0x180078947  call    ?ConvertIn@COM@Windows@@YAJPEAUIReferenceIdentity@@PEAPEAUIRtlReferenceIdentity@Rtl@Identity@2@@Z; Windows::COM::ConvertIn(IReferenceIdentity *,Windows::Identity::Rtl::IRtlReferenceIdentity * *)
0x18007894c  test    eax, eax
0x18007894e  js      short loc_18007899F
0x180078950  lea     rdx, [rbp+var_18]
0x180078954  mov     [rbp+var_18], 0
0x18007895c  call    RtlGetIdentityAuthority
0x180078961  test    eax, eax
0x180078963  js      short loc_180078987
0x180078965  mov     rcx, [rbp+var_18]
0x180078969  xor     r8d, r8d
0x18007896c  mov     r9, [rbp+var_20]
0x180078970  xor     edx, edx
0x180078972  mov     [rsp+70h+var_50], rbx
0x180078977  mov     rax, [rcx]
0x18007897a  mov     rax, [rax+50h]
0x18007897e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078983  test    eax, eax
0x180078985  jns     short loc_180078992
0x180078987  mov     ecx, eax
0x180078989  call    ConvertNtStatusToHResult
0x18007898e  mov     ebx, eax
0x180078990  jmp     short loc_180078994
0x180078992  xor     ebx, ebx
0x180078994  lea     rcx, [rbp+var_18]
0x180078998  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x18007899d  mov     eax, ebx
0x18007899f  mov     rcx, [rbp+var_10]
0x1800789a3  xor     rcx, rsp; StackCookie
0x1800789a6  call    __security_check_cookie
0x1800789ab  mov     rbx, [rsp+70h+arg_0]
0x1800789b3  add     rsp, 70h
0x1800789b7  pop     rbp
0x1800789b8  retn
```
