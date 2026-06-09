# Windows::COM::CIdentityAuthority::Matches(ulong,IDefinitionIdentity *,IReferenceIdentity *,int *)

- ea: `0x1800792dc`
- end: `0x1800794a3`
- name: `?Matches@CIdentityAuthority@COM@Windows@@IEAAJKPEAUIDefinitionIdentity@@PEAUIReferenceIdentity@@PEAH@Z`
- size: `455`
- prototype: `int(Windows::COM::CIdentityAuthority *__hidden this, unsigned int, struct IDefinitionIdentity *, struct IReferenceIdentity *, int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180079060`

## callees

- `0x18001af00`
- `0x18002175c`
- `0x180021794`
- `0x18002d2b0`
- `0x18006b3e0`
- `0x1800792dc`
- `0x180084a10`
- `0x180084acc`
- `0x18009255c`
- `0x18009e020`

## string_xrefs

- `0x180079320`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x180079360`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x1800793a0`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x1800793cc`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x180079337`: `Windows::COM::CIdentityAuthority::Matches`
- `0x180079373`: `Windows::COM::CIdentityAuthority::Matches`
- `0x1800793b3`: `Windows::COM::CIdentityAuthority::Matches`
- `0x1800793df`: `Windows::COM::CIdentityAuthority::Matches`

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
  __int64 v19; // [rsp+68h] [rbp-18h] BYREF

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
             &v12,
             a3);
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
            IdentityAuthority = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, _BYTE *))(*(_QWORD *)v19 + 64LL))(
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
0x1800792dc  mov     [rsp-8+arg_0], rbx
0x1800792e1  mov     [rsp-8+arg_8], rdi
0x1800792e6  push    rbp
0x1800792e7  mov     rbp, rsp
0x1800792ea  sub     rsp, 80h
0x1800792f1  mov     rax, cs:__security_cookie
0x1800792f8  xor     rax, rsp
0x1800792fb  mov     [rbp+var_10], rax
0x1800792ff  mov     rbx, [rbp+arg_20]
0x180079303  mov     rdi, r9
0x180079306  mov     dword ptr [rbp+var_18], 0
0x18007930d  test    rbx, rbx
0x180079310  jz      short loc_180079318
0x180079312  mov     dword ptr [rbx], 0
0x180079318  test    edx, 0FFFFFFFEh
0x18007931e  jz      short loc_18007935B
0x180079320  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x180079327  mov     [rbp+var_40], 180h
0x18007932f  mov     [rbp+var_50], rax
0x180079333  lea     rdx, [rbp+var_50]
0x180079337  lea     rax, aWindowsComCide_4; "Windows::COM::CIdentityAuthority::Match"...
0x18007933e  mov     [rbp+var_48], rax
0x180079342  lea     rcx, [rbp+var_18]
0x180079346  lea     rax, aValidFlagsChec_0; "Valid flags check failed: dwFlags"
0x18007934d  mov     [rbp+var_38], rax
0x180079351  call    ?OriginateInvalidParameter@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180079356  jmp     loc_180079481
0x18007935b  test    rdi, rdi
0x18007935e  jnz     short loc_18007939B
0x180079360  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x180079367  mov     [rbp+var_40], 181h
0x18007936f  mov     [rbp+var_50], rax
0x180079373  lea     rax, aWindowsComCide_4; "Windows::COM::CIdentityAuthority::Match"...
0x18007937a  mov     [rbp+var_48], rax
0x18007937e  lea     rax, aNotNullCheckFa_50; "Not-null check failed: pIReferenceIdent"...
0x180079385  lea     rdx, [rbp+var_50]
0x180079389  mov     [rbp+var_38], rax
0x18007938d  lea     rcx, [rbp+var_18]
0x180079391  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180079396  jmp     loc_180079481
0x18007939b  test    r8, r8
0x18007939e  jnz     short loc_1800793C7
0x1800793a0  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x1800793a7  mov     [rbp+var_40], 182h
0x1800793af  mov     [rbp+var_50], rax
0x1800793b3  lea     rax, aWindowsComCide_4; "Windows::COM::CIdentityAuthority::Match"...
0x1800793ba  mov     [rbp+var_48], rax
0x1800793be  lea     rax, aNotNullCheckFa_25; "Not-null check failed: pIDefinitionIden"...
0x1800793c5  jmp     short loc_180079385
0x1800793c7  test    rbx, rbx
0x1800793ca  jnz     short loc_1800793F3
0x1800793cc  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x1800793d3  mov     [rbp+var_40], 183h
0x1800793db  mov     [rbp+var_50], rax
0x1800793df  lea     rax, aWindowsComCide_4; "Windows::COM::CIdentityAuthority::Match"...
0x1800793e6  mov     [rbp+var_48], rax
0x1800793ea  lea     rax, aNotNullCheckFa_66; "Not-null check failed: pfMatches"
0x1800793f1  jmp     short loc_180079385
0x1800793f3  lea     rdx, [rbp+var_28]; struct IDefinitionIdentity *
0x1800793f7  mov     [rbp+var_28], 0
0x1800793ff  mov     rcx, r8; this
0x180079402  call    ?ConvertIn@COM@Windows@@YAJPEAUIDefinitionIdentity@@PEAPEAUIRtlDefinitionIdentity@Rtl@Identity@2@@Z; Windows::COM::ConvertIn(IDefinitionIdentity *,Windows::Identity::Rtl::IRtlDefinitionIdentity * *)
0x180079407  test    eax, eax
0x180079409  js      short loc_180079481
0x18007940b  lea     rdx, [rbp+var_30]; struct IReferenceIdentity *
0x18007940f  mov     [rbp+var_30], 0
0x180079417  mov     rcx, rdi; this
0x18007941a  call    ?ConvertIn@COM@Windows@@YAJPEAUIReferenceIdentity@@PEAPEAUIRtlReferenceIdentity@Rtl@Identity@2@@Z; Windows::COM::ConvertIn(IReferenceIdentity *,Windows::Identity::Rtl::IRtlReferenceIdentity * *)
0x18007941f  test    eax, eax
0x180079421  js      short loc_180079481
0x180079423  lea     rdx, [rbp+var_18]
0x180079427  mov     [rbp+var_18], 0
0x18007942f  call    RtlGetIdentityAuthority
0x180079434  test    eax, eax
0x180079436  js      short loc_180079463
0x180079438  mov     rcx, [rbp+var_18]
0x18007943c  lea     rdx, [rbp+var_20]
0x180079440  mov     r9, [rbp+var_30]
0x180079444  mov     r8, [rbp+var_28]
0x180079448  mov     [rbp+var_20], 0
0x18007944c  mov     rax, [rcx]
0x18007944f  mov     [rsp+80h+var_60], rdx
0x180079454  xor     edx, edx
0x180079456  mov     rax, [rax+40h]
0x18007945a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007945f  test    eax, eax
0x180079461  jns     short loc_18007946E
0x180079463  mov     ecx, eax
0x180079465  call    ConvertNtStatusToHResult
0x18007946a  mov     ebx, eax
0x18007946c  jmp     short loc_180079476
0x18007946e  movzx   eax, [rbp+var_20]
0x180079472  mov     [rbx], eax
0x180079474  xor     ebx, ebx
0x180079476  lea     rcx, [rbp+var_18]
0x18007947a  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x18007947f  mov     eax, ebx
0x180079481  mov     rcx, [rbp+var_10]
0x180079485  xor     rcx, rsp; StackCookie
0x180079488  call    __security_check_cookie
0x18007948d  lea     r11, [rsp+80h+var_s0]
0x180079495  mov     rbx, [r11+10h]
0x180079499  mov     rdi, [r11+18h]
0x18007949d  mov     rsp, r11
0x1800794a0  pop     rbp
0x1800794a1  retn
```
