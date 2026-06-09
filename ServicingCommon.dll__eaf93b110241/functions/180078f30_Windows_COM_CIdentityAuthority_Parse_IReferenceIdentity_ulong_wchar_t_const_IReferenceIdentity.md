# Windows::COM::CIdentityAuthority::Parse<IReferenceIdentity>(ulong,wchar_t const *,IReferenceIdentity * *)

- ea: `0x180078f30`
- end: `0x180079128`
- name: `??$Parse@UIReferenceIdentity@@@CIdentityAuthority@COM@Windows@@IEAAJKPEB_WPEAPEAUIReferenceIdentity@@@Z`
- size: `504`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180079b30`

## callees

- `0x180010c10`
- `0x18001f4e4`
- `0x18001f51c`
- `0x1800293a0`
- `0x18006b1e0`
- `0x180078f30`
- `0x18007a8a4`
- `0x180085af4`
- `0x180093bdc`
- `0x1800a0020`

## string_xrefs

- `0x180078f77`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x180078fb7`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x180078f8e`: `Windows::COM::CIdentityAuthority::Parse`
- `0x180078fce`: `Windows::COM::CIdentityAuthority::Parse`
- `0x180078fdd`: `Not-null check failed: ppICOMIdentity`

## pseudocode

```c
__int64 __fastcall Windows::COM::CIdentityAuthority::Parse<IReferenceIdentity>(
        __int64 a1,
        unsigned int a2,
        Windows::COM *a3,
        struct IUnknown **a4)
{
  int IdentityAuthority; // eax
  struct _LUNICODE_STRING *v9; // r8
  int v10; // ebx
  int v11; // eax
  const struct _GUID *v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // [rsp+40h] [rbp-49h] BYREF
  int v15; // [rsp+48h] [rbp-41h]
  __int128 v16; // [rsp+50h] [rbp-39h]
  __int64 v17; // [rsp+60h] [rbp-29h]
  __int64 v18; // [rsp+68h] [rbp-21h]
  int v19; // [rsp+70h] [rbp-19h]
  __int64 v20; // [rsp+78h] [rbp-11h]
  __int64 v21; // [rsp+80h] [rbp-9h]
  int v22; // [rsp+88h] [rbp-1h]
  struct Windows::Identity::Rtl::IRtlReferenceIdentity *v23; // [rsp+90h] [rbp+7h] BYREF
  __int64 v24; // [rsp+98h] [rbp+Fh] BYREF
  wchar_t v25[8]; // [rsp+A0h] [rbp+17h] BYREF
  __int64 v26; // [rsp+B0h] [rbp+27h]
  const char *v27; // [rsp+B8h] [rbp+2Fh]

  LODWORD(v24) = 0;
  if ( a4 )
    *a4 = 0;
  if ( (a2 & 0xFFFFFFFC) != 0 )
  {
    v26 = 127;
    *(_QWORD *)v25 = "onecore\\base\\wcp\\identity\\com\\identity_authority.cpp";
    *(_QWORD *)&v25[4] = "Windows::COM::CIdentityAuthority::Parse";
    v27 = "Valid flags check failed: dwFlags";
    return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter(
             &v24,
             v25,
             a3);
  }
  if ( !a4 )
  {
    v26 = 128;
    *(_QWORD *)v25 = "onecore\\base\\wcp\\identity\\com\\identity_authority.cpp";
    *(_QWORD *)&v25[4] = "Windows::COM::CIdentityAuthority::Parse";
    v27 = "Not-null check failed: ppICOMIdentity";
    return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v24,
             v25);
  }
  v24 = 0;
  IdentityAuthority = RtlGetIdentityAuthority(a1, &v24);
  if ( IdentityAuthority >= 0 )
  {
    v23 = 0;
    if ( a3 )
    {
      v26 = 0;
      *(_OWORD *)v25 = 0;
      v10 = Windows::COM::ConvertIn(a3, v25, v9);
      if ( v10 < 0 )
      {
LABEL_13:
        Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(&v23);
        goto LABEL_20;
      }
      v13 = (a2 >> 1) & 1 | 2;
      if ( (a2 & 1) == 0 )
        v13 = (a2 >> 1) & 1;
      v11 = (*(__int64 (__fastcall **)(__int64, __int64, wchar_t *, struct Windows::Identity::Rtl::IRtlReferenceIdentity **))(*(_QWORD *)v24 + 16LL))(
              v24,
              v13,
              v25,
              &v23);
    }
    else
    {
      v14 = 0;
      v15 = 0;
      v16 = 0;
      v17 = 0;
      v18 = 0;
      v19 = -1;
      v20 = 0;
      v21 = 0;
      v22 = 0;
      v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *, _QWORD, struct Windows::Identity::Rtl::IRtlReferenceIdentity **))(*(_QWORD *)v24 + 152LL))(
              v24,
              (a2 >> 1) & 1,
              0,
              &v14,
              0,
              &v23);
    }
    if ( v11 >= 0 )
    {
      v10 = Windows::COM::CReferenceIdentity::Create(v23, v12, a4);
      if ( v10 >= 0 )
      {
        Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(&v23);
        v10 = 0;
        goto LABEL_20;
      }
    }
    else
    {
      v10 = ConvertNtStatusToHResult((unsigned int)v11);
    }
    goto LABEL_13;
  }
  v10 = ConvertNtStatusToHResult((unsigned int)IdentityAuthority);
LABEL_20:
  Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(&v24);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180078f30  mov     [rsp-8+arg_0], rbx
0x180078f35  mov     [rsp-8+arg_8], rsi
0x180078f3a  push    rbp
0x180078f3b  push    rdi
0x180078f3c  push    r14
0x180078f3e  lea     rbp, [rsp-47h]
0x180078f43  sub     rsp, 0D0h
0x180078f4a  mov     rax, cs:__security_cookie
0x180078f51  xor     rax, rsp
0x180078f54  mov     [rbp+57h+var_20], rax
0x180078f58  xor     r14d, r14d
0x180078f5b  mov     rdi, r9
0x180078f5e  mov     dword ptr [rbp+57h+var_48], r14d
0x180078f62  mov     rbx, r8
0x180078f65  mov     esi, edx
0x180078f67  test    r9, r9
0x180078f6a  jz      short loc_180078F6F
0x180078f6c  mov     [r9], r14
0x180078f6f  test    esi, 0FFFFFFFCh
0x180078f75  jz      short loc_180078FB2
0x180078f77  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x180078f7e  mov     [rbp+57h+var_30], 7Fh
0x180078f86  mov     qword ptr [rbp+57h+var_40], rax
0x180078f8a  lea     rdx, [rbp+57h+var_40]
0x180078f8e  lea     rax, aWindowsComCide_8; "Windows::COM::CIdentityAuthority::Parse"
0x180078f95  mov     qword ptr [rbp+57h+var_40+8], rax
0x180078f99  lea     rcx, [rbp+57h+var_48]
0x180078f9d  lea     rax, aValidFlagsChec_0; "Valid flags check failed: dwFlags"
0x180078fa4  mov     [rbp+57h+var_28], rax
0x180078fa8  call    ?OriginateInvalidParameter@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180078fad  jmp     loc_180079103
0x180078fb2  test    rdi, rdi
0x180078fb5  jnz     short loc_180078FF2
0x180078fb7  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x180078fbe  mov     [rbp+57h+var_30], 80h
0x180078fc6  mov     qword ptr [rbp+57h+var_40], rax
0x180078fca  lea     rdx, [rbp+57h+var_40]
0x180078fce  lea     rax, aWindowsComCide_8; "Windows::COM::CIdentityAuthority::Parse"
0x180078fd5  mov     qword ptr [rbp+57h+var_40+8], rax
0x180078fd9  lea     rcx, [rbp+57h+var_48]
0x180078fdd  lea     rax, aNotNullCheckFa_16; "Not-null check failed: ppICOMIdentity"
0x180078fe4  mov     [rbp+57h+var_28], rax
0x180078fe8  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180078fed  jmp     loc_180079103
0x180078ff2  lea     rdx, [rbp+57h+var_48]
0x180078ff6  mov     [rbp+57h+var_48], r14
0x180078ffa  call    RtlGetIdentityAuthority
0x180078fff  test    eax, eax
0x180079001  jns     short loc_180079011
0x180079003  mov     ecx, eax
0x180079005  call    ConvertNtStatusToHResult
0x18007900a  mov     ebx, eax
0x18007900c  jmp     loc_1800790F8
0x180079011  mov     [rbp+57h+var_50], r14
0x180079015  xorps   xmm0, xmm0
0x180079018  test    rbx, rbx
0x18007901b  jnz     short loc_18007908C
0x18007901d  mov     rcx, [rbp+57h+var_48]
0x180079021  lea     rdx, [rbp+57h+var_50]
0x180079025  mov     [rsp+0E0h+var_B8], rdx
0x18007902a  lea     r9, [rbp+57h+var_A0]
0x18007902e  mov     [rbp+57h+var_A0], r14
0x180079032  xor     r8d, r8d
0x180079035  mov     [rbp+57h+var_98], r14d
0x180079039  movdqa  [rbp+57h+var_90], xmm0
0x18007903e  mov     [rbp+57h+var_80], r14
0x180079042  mov     [rbp+57h+var_78], r14
0x180079046  mov     [rbp+57h+var_70], 0FFFFFFFFh
0x18007904d  mov     [rbp+57h+var_68], r14
0x180079051  mov     [rbp+57h+var_60], r14
0x180079055  mov     [rbp+57h+var_58], r14d
0x180079059  mov     rax, [rcx]
0x18007905c  shr     esi, 1
0x18007905e  and     esi, 1
0x180079061  mov     [rsp+0E0h+var_C0], r14
0x180079066  mov     edx, esi
0x180079068  mov     rax, [rax+98h]
0x18007906f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079074  test    eax, eax
0x180079076  jns     short loc_1800790DA
0x180079078  mov     ecx, eax
0x18007907a  call    ConvertNtStatusToHResult
0x18007907f  mov     ebx, eax
0x180079081  lea     rcx, [rbp+57h+var_50]
0x180079085  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x18007908a  jmp     short loc_1800790F8
0x18007908c  xor     eax, eax
0x18007908e  lea     rdx, [rbp+57h+var_40]; wchar_t *
0x180079092  mov     rcx, rbx; this
0x180079095  mov     [rbp+57h+var_30], rax
0x180079099  movups  xmmword ptr [rbp+57h+var_40], xmm0
0x18007909d  call    ?ConvertIn@COM@Windows@@YAJPEB_WPEAU_LUNICODE_STRING@@@Z; Windows::COM::ConvertIn(wchar_t const *,_LUNICODE_STRING *)
0x1800790a2  mov     ebx, eax
0x1800790a4  test    eax, eax
0x1800790a6  js      short loc_180079081
0x1800790a8  mov     rcx, [rbp+57h+var_48]
0x1800790ac  lea     r9, [rbp+57h+var_50]
0x1800790b0  mov     r8d, esi
0x1800790b3  shr     r8d, 1
0x1800790b6  and     r8d, 1
0x1800790ba  mov     rax, [rcx]
0x1800790bd  mov     edx, r8d
0x1800790c0  or      edx, 2
0x1800790c3  test    sil, 1
0x1800790c7  mov     rax, [rax+10h]
0x1800790cb  cmovz   edx, r8d
0x1800790cf  lea     r8, [rbp+57h+var_40]
0x1800790d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800790d8  jmp     short loc_180079074
0x1800790da  mov     rcx, [rbp+57h+var_50]; struct Windows::Identity::Rtl::IRtlReferenceIdentity *
0x1800790de  mov     r8, rdi; struct IUnknown **
0x1800790e1  call    ?Create@CReferenceIdentity@COM@Windows@@KAJPEAUIRtlReferenceIdentity@Rtl@Identity@3@AEBU_GUID@@PEAPEAUIUnknown@@@Z; Windows::COM::CReferenceIdentity::Create(Windows::Identity::Rtl::IRtlReferenceIdentity *,_GUID const &,IUnknown * *)
0x1800790e6  lea     rcx, [rbp+57h+var_50]
0x1800790ea  mov     ebx, eax
0x1800790ec  test    eax, eax
0x1800790ee  js      short loc_180079085
0x1800790f0  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x1800790f5  mov     ebx, r14d
0x1800790f8  lea     rcx, [rbp+57h+var_48]
0x1800790fc  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x180079101  mov     eax, ebx
0x180079103  mov     rcx, [rbp+57h+var_20]
0x180079107  xor     rcx, rsp; StackCookie
0x18007910a  call    __security_check_cookie
0x18007910f  lea     r11, [rsp+0E0h+var_10]
0x180079117  mov     rbx, [r11+20h]
0x18007911b  mov     rsi, [r11+28h]
0x18007911f  mov     rsp, r11
0x180079122  pop     r14
0x180079124  pop     rdi
0x180079125  pop     rbp
0x180079126  retn
```
