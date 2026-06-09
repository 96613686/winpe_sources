# Windows::COM::CIdentityAuthority::GenerateKey<IReferenceIdentity>(ulong,ulong,IReferenceIdentity *,wchar_t * *)

- ea: `0x180078520`
- end: `0x1800786f0`
- name: `??$GenerateKey@UIReferenceIdentity@@@CIdentityAuthority@COM@Windows@@IEAAJKKPEAUIReferenceIdentity@@PEAPEA_W@Z`
- size: `464`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800790a0`

## callees

- `0x18001af00`
- `0x18002175c`
- `0x180021794`
- `0x18002d2b0`
- `0x18006b3e0`
- `0x180078520`
- `0x18008484c`
- `0x180084acc`
- `0x18009255c`
- `0x18009e020`

## string_xrefs

- `0x180078570`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x1800785b6`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x1800785fc`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x1800785d7`: `Not-null check failed: pICOMIdentity`
- `0x18007858a`: `Windows::COM::CIdentityAuthority::GenerateKey`
- `0x1800785cb`: `Windows::COM::CIdentityAuthority::GenerateKey`
- `0x180078611`: `Windows::COM::CIdentityAuthority::GenerateKey`

## pseudocode

```c
__int64 __fastcall Windows::COM::CIdentityAuthority::GenerateKey<IReferenceIdentity>(
        __int64 a1,
        int a2,
        struct Windows::Identity::Rtl::IRtlReferenceIdentity **a3,
        Windows::COM *a4,
        struct _LUNICODE_STRING *a5)
{
  char v5; // di
  __int64 result; // rax
  const char *v7; // rax
  __int64 v8; // rcx
  int IdentityAuthority; // eax
  wchar_t **v10; // r8
  int v11; // ebx
  const char *v12; // [rsp+30h] [rbp-D0h] BYREF
  const char *v13; // [rsp+38h] [rbp-C8h]
  __int64 v14; // [rsp+40h] [rbp-C0h]
  const char *v15; // [rsp+48h] [rbp-B8h]
  __int64 v16; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v17[3]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v18[2]; // [rsp+70h] [rbp-90h] BYREF
  char v19; // [rsp+80h] [rbp-80h] BYREF

  v5 = a2;
  LODWORD(v18[0]) = 0;
  if ( a5 )
    *(_QWORD *)a5 = 0;
  if ( (a2 & 0xFFFFFFFE) != 0 )
  {
    v14 = 503;
    v12 = "onecore\\base\\wcp\\identity\\com\\identity_authority.cpp";
    v13 = "Windows::COM::CIdentityAuthority::GenerateKey";
    v15 = "Valid flags check failed: dwFlags";
    return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter(
             v18,
             &v12,
             a3);
  }
  if ( !a4 )
  {
    v14 = 504;
    v12 = "onecore\\base\\wcp\\identity\\com\\identity_authority.cpp";
    v13 = "Windows::COM::CIdentityAuthority::GenerateKey";
    v7 = "Not-null check failed: pICOMIdentity";
LABEL_7:
    v15 = v7;
    return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             v18,
             &v12);
  }
  if ( !a5 )
  {
    v14 = 505;
    v12 = "onecore\\base\\wcp\\identity\\com\\identity_authority.cpp";
    v13 = "Windows::COM::CIdentityAuthority::GenerateKey";
    v7 = "Not-null check failed: ppszKeyForm";
    goto LABEL_7;
  }
  v16 = 0;
  result = Windows::COM::ConvertIn(a4, (struct IReferenceIdentity *)&v16, a3);
  if ( (int)result >= 0 )
  {
    v18[0] = 0;
    IdentityAuthority = RtlGetIdentityAuthority(v8, v18);
    if ( IdentityAuthority >= 0
      && (v17[2] = &v19,
          v17[0] = 0,
          v17[1] = 280,
          IdentityAuthority = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD *))(*(_QWORD *)v18[0] + 88LL))(
                                v18[0],
                                2 * (v5 & 1u) + 1,
                                v16,
                                v17),
          IdentityAuthority >= 0) )
    {
      v11 = Windows::COM::CopyOut((Windows::COM *)v17, a5, v10);
      if ( v11 >= 0 )
        v11 = 0;
    }
    else
    {
      v11 = ConvertNtStatusToHResult((unsigned int)IdentityAuthority);
    }
    Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(v18);
    return (unsigned int)v11;
  }
  return result;
}

```

## disassembly

```asm
0x180078520  mov     [rsp-8+arg_0], rbx
0x180078525  mov     [rsp-8+arg_8], rdi
0x18007852a  push    rbp
0x18007852b  lea     rbp, [rsp-0B0h]
0x180078533  sub     rsp, 1B0h
0x18007853a  mov     rax, cs:__security_cookie
0x180078541  xor     rax, rsp
0x180078544  mov     [rbp+0B0h+var_10], rax
0x18007854b  mov     rbx, [rbp+0B0h+arg_20]
0x180078552  mov     edi, edx
0x180078554  mov     dword ptr [rsp+1B0h+var_140], 0
0x18007855c  test    rbx, rbx
0x18007855f  jz      short loc_180078568
0x180078561  mov     qword ptr [rbx], 0
0x180078568  test    edi, 0FFFFFFFEh
0x18007856e  jz      short loc_1800785B1
0x180078570  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x180078577  mov     [rsp+1B0h+var_170], 1F7h
0x180078580  mov     [rsp+1B0h+var_180], rax
0x180078585  lea     rdx, [rsp+1B0h+var_180]
0x18007858a  lea     rax, aWindowsComCide; "Windows::COM::CIdentityAuthority::Gener"...
0x180078591  mov     [rsp+1B0h+var_178], rax
0x180078596  lea     rcx, [rsp+1B0h+var_140]
0x18007859b  lea     rax, aValidFlagsChec_0; "Valid flags check failed: dwFlags"
0x1800785a2  mov     [rsp+1B0h+var_168], rax
0x1800785a7  call    ?OriginateInvalidParameter@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x1800785ac  jmp     loc_1800786CB
0x1800785b1  test    r9, r9
0x1800785b4  jnz     short loc_1800785F7
0x1800785b6  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x1800785bd  mov     [rsp+1B0h+var_170], 1F8h
0x1800785c6  mov     [rsp+1B0h+var_180], rax
0x1800785cb  lea     rax, aWindowsComCide; "Windows::COM::CIdentityAuthority::Gener"...
0x1800785d2  mov     [rsp+1B0h+var_178], rax
0x1800785d7  lea     rax, aNotNullCheckFa_41; "Not-null check failed: pICOMIdentity"
0x1800785de  lea     rdx, [rsp+1B0h+var_180]
0x1800785e3  mov     [rsp+1B0h+var_168], rax
0x1800785e8  lea     rcx, [rsp+1B0h+var_140]
0x1800785ed  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x1800785f2  jmp     loc_1800786CB
0x1800785f7  test    rbx, rbx
0x1800785fa  jnz     short loc_180078626
0x1800785fc  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x180078603  mov     [rsp+1B0h+var_170], 1F9h
0x18007860c  mov     [rsp+1B0h+var_180], rax
0x180078611  lea     rax, aWindowsComCide; "Windows::COM::CIdentityAuthority::Gener"...
0x180078618  mov     [rsp+1B0h+var_178], rax
0x18007861d  lea     rax, aNotNullCheckFa_118; "Not-null check failed: ppszKeyForm"
0x180078624  jmp     short loc_1800785DE
0x180078626  lea     rdx, [rsp+1B0h+var_160]; struct IReferenceIdentity *
0x18007862b  mov     [rsp+1B0h+var_160], 0
0x180078634  mov     rcx, r9; this
0x180078637  call    ?ConvertIn@COM@Windows@@YAJPEAUIReferenceIdentity@@PEAPEAUIRtlReferenceIdentity@Rtl@Identity@2@@Z; Windows::COM::ConvertIn(IReferenceIdentity *,Windows::Identity::Rtl::IRtlReferenceIdentity * *)
0x18007863c  test    eax, eax
0x18007863e  js      loc_1800786CB
0x180078644  lea     rdx, [rsp+1B0h+var_140]
0x180078649  mov     [rsp+1B0h+var_140], 0
0x180078652  call    RtlGetIdentityAuthority
0x180078657  test    eax, eax
0x180078659  js      short loc_18007869F
0x18007865b  mov     rcx, [rsp+1B0h+var_140]
0x180078660  lea     rax, [rbp+0B0h+var_130]
0x180078664  mov     r8, [rsp+1B0h+var_160]
0x180078669  lea     r9, [rsp+1B0h+var_158]
0x18007866e  mov     [rsp+1B0h+var_148], rax
0x180078673  and     edi, 1
0x180078676  mov     [rsp+1B0h+var_158], 0
0x18007867f  mov     [rsp+1B0h+var_150], 118h
0x180078688  mov     rax, [rcx]
0x18007868b  lea     edx, ds:1[rdi*2]
0x180078692  mov     rax, [rax+58h]
0x180078696  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007869b  test    eax, eax
0x18007869d  jns     short loc_1800786AA
0x18007869f  mov     ecx, eax
0x1800786a1  call    ConvertNtStatusToHResult
0x1800786a6  mov     ebx, eax
0x1800786a8  jmp     short loc_1800786BF
0x1800786aa  mov     rdx, rbx; struct _LUNICODE_STRING *
0x1800786ad  lea     rcx, [rsp+1B0h+var_158]; this
0x1800786b2  call    ?CopyOut@COM@Windows@@YAJPEBU_LUNICODE_STRING@@PEAPEA_W@Z; Windows::COM::CopyOut(_LUNICODE_STRING const *,wchar_t * *)
0x1800786b7  mov     ebx, eax
0x1800786b9  test    eax, eax
0x1800786bb  js      short loc_1800786BF
0x1800786bd  xor     ebx, ebx
0x1800786bf  lea     rcx, [rsp+1B0h+var_140]
0x1800786c4  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x1800786c9  mov     eax, ebx
0x1800786cb  mov     rcx, [rbp+0B0h+var_10]
0x1800786d2  xor     rcx, rsp; StackCookie
0x1800786d5  call    __security_check_cookie
0x1800786da  lea     r11, [rsp+1B0h+var_s0]
0x1800786e2  mov     rbx, [r11+10h]
0x1800786e6  mov     rdi, [r11+18h]
0x1800786ea  mov     rsp, r11
0x1800786ed  pop     rbp
0x1800786ee  retn
```
