# Windows::COM::CIdentityAuthority::Matches(ulong,IDefinitionIdentity *,IReferenceIdentity *,int *)

- ea: `0x18007963c`
- end: `0x180079803`
- name: `?Matches@CIdentityAuthority@COM@Windows@@IEAAJKPEAUIDefinitionIdentity@@PEAUIReferenceIdentity@@PEAH@Z`
- size: `455`
- prototype: `int(Windows::COM::CIdentityAuthority *__hidden this, unsigned int, struct IDefinitionIdentity *, struct IReferenceIdentity *, int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800793c0`

## callees

- `0x180010c10`
- `0x18001f4e4`
- `0x18001f51c`
- `0x1800293a0`
- `0x18006b1e0`
- `0x18007963c`
- `0x18008597c`
- `0x180085a38`
- `0x180093bdc`
- `0x1800a0020`

## string_xrefs

- `0x180079680`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x1800796c0`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x180079700`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x18007972c`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x180079697`: `Windows::COM::CIdentityAuthority::Matches`
- `0x1800796d3`: `Windows::COM::CIdentityAuthority::Matches`
- `0x180079713`: `Windows::COM::CIdentityAuthority::Matches`
- `0x18007973f`: `Windows::COM::CIdentityAuthority::Matches`

## pseudocode

```c
__int64 __fastcall Windows::COM::CIdentityAuthority::Matches(
        Windows::COM::CIdentityAuthority *this,
        int a2,
        struct IDefinitionIdentity *a3,
        struct IReferenceIdentity *a4,
        int *a5)
{
  __int64 result; // rax
  const char *v7; // rax
  struct Windows::Identity::Rtl::IRtlReferenceIdentity **v8; // r8
  __int64 v9; // rcx
  int IdentityAuthority; // eax
  unsigned int v11; // ebx
  const char *v12; // [rsp+30h] [rbp-50h] BYREF
  const char *v13; // [rsp+38h] [rbp-48h]
  __int64 v14; // [rsp+40h] [rbp-40h]
  const char *v15; // [rsp+48h] [rbp-38h]
  __int64 v16; // [rsp+50h] [rbp-30h] BYREF
  __int64 v17; // [rsp+58h] [rbp-28h] BYREF
  _BYTE v18[8]; // [rsp+60h] [rbp-20h] BYREF
  __int64 (__fastcall ***v19)(_QWORD); // [rsp+68h] [rbp-18h] BYREF

  LODWORD(v19) = 0;
  if ( a5 )
    *a5 = 0;
  if ( (a2 & 0xFFFFFFFE) != 0 )
  {
    v14 = 384;
    v12 = "onecore\\base\\wcp\\identity\\com\\identity_authority.cpp";
    v13 = "Windows::COM::CIdentityAuthority::Matches";
    v15 = "Valid flags check failed: dwFlags";
    return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter(
             &v19,
             &v12);
  }
  if ( !a4 )
  {
    v14 = 385;
    v12 = "onecore\\base\\wcp\\identity\\com\\identity_authority.cpp";
    v13 = "Windows::COM::CIdentityAuthority::Matches";
    v7 = "Not-null check failed: pIReferenceIdentity";
LABEL_7:
    v15 = v7;
    return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v19,
             &v12);
  }
  if ( !a3 )
  {
    v14 = 386;
    v12 = "onecore\\base\\wcp\\identity\\com\\identity_authority.cpp";
    v13 = "Windows::COM::CIdentityAuthority::Matches";
    v7 = "Not-null check failed: pIDefinitionIdentity";
    goto LABEL_7;
  }
  if ( !a5 )
  {
    v14 = 387;
    v12 = "onecore\\base\\wcp\\identity\\com\\identity_authority.cpp";
    v13 = "Windows::COM::CIdentityAuthority::Matches";
    v7 = "Not-null check failed: pfMatches";
    goto LABEL_7;
  }
  v17 = 0;
  result = Windows::COM::ConvertIn(
             a3,
             (struct IDefinitionIdentity *)&v17,
             (struct Windows::Identity::Rtl::IRtlDefinitionIdentity **)a3);
  if ( (int)result >= 0 )
  {
    v16 = 0;
    result = Windows::COM::ConvertIn(a4, (struct IReferenceIdentity *)&v16, v8);
    if ( (int)result >= 0 )
    {
      v19 = 0;
      IdentityAuthority = RtlGetIdentityAuthority(v9, &v19);
      if ( IdentityAuthority >= 0
        && (v18[0] = 0,
            IdentityAuthority = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD), _QWORD, __int64, __int64, _BYTE *))(*v19)[8])(
                                  v19,
                                  0,
                                  v17,
                                  v16,
                                  v18),
            IdentityAuthority >= 0) )
      {
        *a5 = v18[0];
        v11 = 0;
      }
      else
      {
        v11 = ConvertNtStatusToHResult((unsigned int)IdentityAuthority);
      }
      Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(&v19);
      return v11;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18007963c  mov     [rsp-8+arg_0], rbx
0x180079641  mov     [rsp-8+arg_8], rdi
0x180079646  push    rbp
0x180079647  mov     rbp, rsp
0x18007964a  sub     rsp, 80h
0x180079651  mov     rax, cs:__security_cookie
0x180079658  xor     rax, rsp
0x18007965b  mov     [rbp+var_10], rax
0x18007965f  mov     rbx, [rbp+arg_20]
0x180079663  mov     rdi, r9
0x180079666  mov     dword ptr [rbp+var_18], 0
0x18007966d  test    rbx, rbx
0x180079670  jz      short loc_180079678
0x180079672  mov     dword ptr [rbx], 0
0x180079678  test    edx, 0FFFFFFFEh
0x18007967e  jz      short loc_1800796BB
0x180079680  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x180079687  mov     [rbp+var_40], 180h
0x18007968f  mov     [rbp+var_50], rax
0x180079693  lea     rdx, [rbp+var_50]
0x180079697  lea     rax, aWindowsComCide_4; "Windows::COM::CIdentityAuthority::Match"...
0x18007969e  mov     [rbp+var_48], rax
0x1800796a2  lea     rcx, [rbp+var_18]
0x1800796a6  lea     rax, aValidFlagsChec_0; "Valid flags check failed: dwFlags"
0x1800796ad  mov     [rbp+var_38], rax
0x1800796b1  call    ?OriginateInvalidParameter@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x1800796b6  jmp     loc_1800797E1
0x1800796bb  test    rdi, rdi
0x1800796be  jnz     short loc_1800796FB
0x1800796c0  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x1800796c7  mov     [rbp+var_40], 181h
0x1800796cf  mov     [rbp+var_50], rax
0x1800796d3  lea     rax, aWindowsComCide_4; "Windows::COM::CIdentityAuthority::Match"...
0x1800796da  mov     [rbp+var_48], rax
0x1800796de  lea     rax, aNotNullCheckFa_50; "Not-null check failed: pIReferenceIdent"...
0x1800796e5  lea     rdx, [rbp+var_50]
0x1800796e9  mov     [rbp+var_38], rax
0x1800796ed  lea     rcx, [rbp+var_18]
0x1800796f1  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x1800796f6  jmp     loc_1800797E1
0x1800796fb  test    r8, r8
0x1800796fe  jnz     short loc_180079727
0x180079700  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x180079707  mov     [rbp+var_40], 182h
0x18007970f  mov     [rbp+var_50], rax
0x180079713  lea     rax, aWindowsComCide_4; "Windows::COM::CIdentityAuthority::Match"...
0x18007971a  mov     [rbp+var_48], rax
0x18007971e  lea     rax, aNotNullCheckFa_25; "Not-null check failed: pIDefinitionIden"...
0x180079725  jmp     short loc_1800796E5
0x180079727  test    rbx, rbx
0x18007972a  jnz     short loc_180079753
0x18007972c  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x180079733  mov     [rbp+var_40], 183h
0x18007973b  mov     [rbp+var_50], rax
0x18007973f  lea     rax, aWindowsComCide_4; "Windows::COM::CIdentityAuthority::Match"...
0x180079746  mov     [rbp+var_48], rax
0x18007974a  lea     rax, aNotNullCheckFa_66; "Not-null check failed: pfMatches"
0x180079751  jmp     short loc_1800796E5
0x180079753  lea     rdx, [rbp+var_28]; struct IDefinitionIdentity *
0x180079757  mov     [rbp+var_28], 0
0x18007975f  mov     rcx, r8; this
0x180079762  call    ?ConvertIn@COM@Windows@@YAJPEAUIDefinitionIdentity@@PEAPEAUIRtlDefinitionIdentity@Rtl@Identity@2@@Z; Windows::COM::ConvertIn(IDefinitionIdentity *,Windows::Identity::Rtl::IRtlDefinitionIdentity * *)
0x180079767  test    eax, eax
0x180079769  js      short loc_1800797E1
0x18007976b  lea     rdx, [rbp+var_30]; struct IReferenceIdentity *
0x18007976f  mov     [rbp+var_30], 0
0x180079777  mov     rcx, rdi; this
0x18007977a  call    ?ConvertIn@COM@Windows@@YAJPEAUIReferenceIdentity@@PEAPEAUIRtlReferenceIdentity@Rtl@Identity@2@@Z; Windows::COM::ConvertIn(IReferenceIdentity *,Windows::Identity::Rtl::IRtlReferenceIdentity * *)
0x18007977f  test    eax, eax
0x180079781  js      short loc_1800797E1
0x180079783  lea     rdx, [rbp+var_18]
0x180079787  mov     [rbp+var_18], 0
0x18007978f  call    RtlGetIdentityAuthority
0x180079794  test    eax, eax
0x180079796  js      short loc_1800797C3
0x180079798  mov     rcx, [rbp+var_18]
0x18007979c  lea     rdx, [rbp+var_20]
0x1800797a0  mov     r9, [rbp+var_30]
0x1800797a4  mov     r8, [rbp+var_28]
0x1800797a8  mov     [rbp+var_20], 0
0x1800797ac  mov     rax, [rcx]
0x1800797af  mov     [rsp+80h+var_60], rdx
0x1800797b4  xor     edx, edx
0x1800797b6  mov     rax, [rax+40h]
0x1800797ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800797bf  test    eax, eax
0x1800797c1  jns     short loc_1800797CE
0x1800797c3  mov     ecx, eax
0x1800797c5  call    ConvertNtStatusToHResult
0x1800797ca  mov     ebx, eax
0x1800797cc  jmp     short loc_1800797D6
0x1800797ce  movzx   eax, [rbp+var_20]
0x1800797d2  mov     [rbx], eax
0x1800797d4  xor     ebx, ebx
0x1800797d6  lea     rcx, [rbp+var_18]
0x1800797da  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x1800797df  mov     eax, ebx
0x1800797e1  mov     rcx, [rbp+var_10]
0x1800797e5  xor     rcx, rsp; StackCookie
0x1800797e8  call    __security_check_cookie
0x1800797ed  lea     r11, [rsp+80h+var_s0]
0x1800797f5  mov     rbx, [r11+10h]
0x1800797f9  mov     rdi, [r11+18h]
0x1800797fd  mov     rsp, r11
0x180079800  pop     rbp
0x180079801  retn
```
