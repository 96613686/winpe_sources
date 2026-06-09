# Windows::COM::CIdentityAuthority::GenerateKey<IDefinitionIdentity>(ulong,ulong,IDefinitionIdentity *,wchar_t * *)

- ea: `0x18007834c`
- end: `0x180078518`
- name: `??$GenerateKey@UIDefinitionIdentity@@@CIdentityAuthority@COM@Windows@@IEAAJKKPEAUIDefinitionIdentity@@PEAPEA_W@Z`
- size: `460`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180079080`

## callees

- `0x18001af00`
- `0x18002175c`
- `0x180021794`
- `0x18002d2b0`
- `0x18006b3e0`
- `0x18007834c`
- `0x18008484c`
- `0x180084a10`
- `0x18009255c`
- `0x18009e020`

## string_xrefs

- `0x18007839c`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x1800783e2`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x180078428`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x180078403`: `Not-null check failed: pICOMIdentity`
- `0x1800783b6`: `Windows::COM::CIdentityAuthority::GenerateKey`
- `0x1800783f7`: `Windows::COM::CIdentityAuthority::GenerateKey`
- `0x18007843d`: `Windows::COM::CIdentityAuthority::GenerateKey`

## pseudocode

```c
__int64 __fastcall Windows::COM::CIdentityAuthority::GenerateKey<IDefinitionIdentity>(
        __int64 a1,
        int a2,
        struct Windows::Identity::Rtl::IRtlDefinitionIdentity **a3,
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
  result = Windows::COM::ConvertIn(a4, (struct IDefinitionIdentity *)&v16, a3);
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
                                2 * (v5 & 1u),
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
0x18007834c  mov     [rsp-8+arg_0], rbx
0x180078351  mov     [rsp-8+arg_8], rdi
0x180078356  push    rbp
0x180078357  lea     rbp, [rsp-0B0h]
0x18007835f  sub     rsp, 1B0h
0x180078366  mov     rax, cs:__security_cookie
0x18007836d  xor     rax, rsp
0x180078370  mov     [rbp+0B0h+var_10], rax
0x180078377  mov     rbx, [rbp+0B0h+arg_20]
0x18007837e  mov     edi, edx
0x180078380  mov     dword ptr [rsp+1B0h+var_140], 0
0x180078388  test    rbx, rbx
0x18007838b  jz      short loc_180078394
0x18007838d  mov     qword ptr [rbx], 0
0x180078394  test    edi, 0FFFFFFFEh
0x18007839a  jz      short loc_1800783DD
0x18007839c  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x1800783a3  mov     [rsp+1B0h+var_170], 1F7h
0x1800783ac  mov     [rsp+1B0h+var_180], rax
0x1800783b1  lea     rdx, [rsp+1B0h+var_180]
0x1800783b6  lea     rax, aWindowsComCide; "Windows::COM::CIdentityAuthority::Gener"...
0x1800783bd  mov     [rsp+1B0h+var_178], rax
0x1800783c2  lea     rcx, [rsp+1B0h+var_140]
0x1800783c7  lea     rax, aValidFlagsChec_0; "Valid flags check failed: dwFlags"
0x1800783ce  mov     [rsp+1B0h+var_168], rax
0x1800783d3  call    ?OriginateInvalidParameter@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x1800783d8  jmp     loc_1800784F3
0x1800783dd  test    r9, r9
0x1800783e0  jnz     short loc_180078423
0x1800783e2  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x1800783e9  mov     [rsp+1B0h+var_170], 1F8h
0x1800783f2  mov     [rsp+1B0h+var_180], rax
0x1800783f7  lea     rax, aWindowsComCide; "Windows::COM::CIdentityAuthority::Gener"...
0x1800783fe  mov     [rsp+1B0h+var_178], rax
0x180078403  lea     rax, aNotNullCheckFa_41; "Not-null check failed: pICOMIdentity"
0x18007840a  lea     rdx, [rsp+1B0h+var_180]
0x18007840f  mov     [rsp+1B0h+var_168], rax
0x180078414  lea     rcx, [rsp+1B0h+var_140]
0x180078419  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18007841e  jmp     loc_1800784F3
0x180078423  test    rbx, rbx
0x180078426  jnz     short loc_180078452
0x180078428  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x18007842f  mov     [rsp+1B0h+var_170], 1F9h
0x180078438  mov     [rsp+1B0h+var_180], rax
0x18007843d  lea     rax, aWindowsComCide; "Windows::COM::CIdentityAuthority::Gener"...
0x180078444  mov     [rsp+1B0h+var_178], rax
0x180078449  lea     rax, aNotNullCheckFa_118; "Not-null check failed: ppszKeyForm"
0x180078450  jmp     short loc_18007840A
0x180078452  lea     rdx, [rsp+1B0h+var_160]; struct IDefinitionIdentity *
0x180078457  mov     [rsp+1B0h+var_160], 0
0x180078460  mov     rcx, r9; this
0x180078463  call    ?ConvertIn@COM@Windows@@YAJPEAUIDefinitionIdentity@@PEAPEAUIRtlDefinitionIdentity@Rtl@Identity@2@@Z; Windows::COM::ConvertIn(IDefinitionIdentity *,Windows::Identity::Rtl::IRtlDefinitionIdentity * *)
0x180078468  test    eax, eax
0x18007846a  js      loc_1800784F3
0x180078470  lea     rdx, [rsp+1B0h+var_140]
0x180078475  mov     [rsp+1B0h+var_140], 0
0x18007847e  call    RtlGetIdentityAuthority
0x180078483  test    eax, eax
0x180078485  js      short loc_1800784C7
0x180078487  mov     rcx, [rsp+1B0h+var_140]
0x18007848c  lea     rax, [rbp+0B0h+var_130]
0x180078490  mov     r8, [rsp+1B0h+var_160]
0x180078495  lea     r9, [rsp+1B0h+var_158]
0x18007849a  mov     [rsp+1B0h+var_148], rax
0x18007849f  and     edi, 1
0x1800784a2  mov     [rsp+1B0h+var_158], 0
0x1800784ab  mov     [rsp+1B0h+var_150], 118h
0x1800784b4  mov     rax, [rcx]
0x1800784b7  lea     edx, [rdi+rdi]
0x1800784ba  mov     rax, [rax+58h]
0x1800784be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800784c3  test    eax, eax
0x1800784c5  jns     short loc_1800784D2
0x1800784c7  mov     ecx, eax
0x1800784c9  call    ConvertNtStatusToHResult
0x1800784ce  mov     ebx, eax
0x1800784d0  jmp     short loc_1800784E7
0x1800784d2  mov     rdx, rbx; struct _LUNICODE_STRING *
0x1800784d5  lea     rcx, [rsp+1B0h+var_158]; this
0x1800784da  call    ?CopyOut@COM@Windows@@YAJPEBU_LUNICODE_STRING@@PEAPEA_W@Z; Windows::COM::CopyOut(_LUNICODE_STRING const *,wchar_t * *)
0x1800784df  mov     ebx, eax
0x1800784e1  test    eax, eax
0x1800784e3  js      short loc_1800784E7
0x1800784e5  xor     ebx, ebx
0x1800784e7  lea     rcx, [rsp+1B0h+var_140]
0x1800784ec  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x1800784f1  mov     eax, ebx
0x1800784f3  mov     rcx, [rbp+0B0h+var_10]
0x1800784fa  xor     rcx, rsp; StackCookie
0x1800784fd  call    __security_check_cookie
0x180078502  lea     r11, [rsp+1B0h+var_s0]
0x18007850a  mov     rbx, [r11+10h]
0x18007850e  mov     rdi, [r11+18h]
0x180078512  mov     rsp, r11
0x180078515  pop     rbp
0x180078516  retn
```
