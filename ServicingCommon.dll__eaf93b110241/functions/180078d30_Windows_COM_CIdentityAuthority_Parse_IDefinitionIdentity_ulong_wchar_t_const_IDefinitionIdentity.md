# Windows::COM::CIdentityAuthority::Parse<IDefinitionIdentity>(ulong,wchar_t const *,IDefinitionIdentity * *)

- ea: `0x180078d30`
- end: `0x180078f28`
- name: `??$Parse@UIDefinitionIdentity@@@CIdentityAuthority@COM@Windows@@IEAAJKPEB_WPEAPEAUIDefinitionIdentity@@@Z`
- size: `504`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180079b20`

## callees

- `0x180010c10`
- `0x18001f4e4`
- `0x18001f51c`
- `0x1800293a0`
- `0x18006b1e0`
- `0x180078d30`
- `0x18007a0c4`
- `0x180085af4`
- `0x180093bdc`
- `0x1800a0020`

## string_xrefs

- `0x180078d77`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x180078db7`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x180078d8e`: `Windows::COM::CIdentityAuthority::Parse`
- `0x180078dce`: `Windows::COM::CIdentityAuthority::Parse`
- `0x180078ddd`: `Not-null check failed: ppICOMIdentity`

## pseudocode

```c
__int64 __fastcall Windows::COM::CIdentityAuthority::Parse<IDefinitionIdentity>(
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
  struct Windows::Identity::Rtl::IRtlDefinitionIdentity *v23; // [rsp+90h] [rbp+7h] BYREF
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
      v11 = (*(__int64 (__fastcall **)(__int64, __int64, wchar_t *, struct Windows::Identity::Rtl::IRtlDefinitionIdentity **))(*(_QWORD *)v24 + 24LL))(
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
      v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *, _QWORD, struct Windows::Identity::Rtl::IRtlDefinitionIdentity **))(*(_QWORD *)v24 + 160LL))(
              v24,
              (a2 >> 1) & 1,
              0,
              &v14,
              0,
              &v23);
    }
    if ( v11 >= 0 )
    {
      v10 = Windows::COM::CDefinitionIdentity::Create(v23, v12, a4);
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
0x180078d30  mov     [rsp-8+arg_0], rbx
0x180078d35  mov     [rsp-8+arg_8], rsi
0x180078d3a  push    rbp
0x180078d3b  push    rdi
0x180078d3c  push    r14
0x180078d3e  lea     rbp, [rsp-47h]
0x180078d43  sub     rsp, 0D0h
0x180078d4a  mov     rax, cs:__security_cookie
0x180078d51  xor     rax, rsp
0x180078d54  mov     [rbp+57h+var_20], rax
0x180078d58  xor     r14d, r14d
0x180078d5b  mov     rdi, r9
0x180078d5e  mov     dword ptr [rbp+57h+var_48], r14d
0x180078d62  mov     rbx, r8
0x180078d65  mov     esi, edx
0x180078d67  test    r9, r9
0x180078d6a  jz      short loc_180078D6F
0x180078d6c  mov     [r9], r14
0x180078d6f  test    esi, 0FFFFFFFCh
0x180078d75  jz      short loc_180078DB2
0x180078d77  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x180078d7e  mov     [rbp+57h+var_30], 7Fh
0x180078d86  mov     qword ptr [rbp+57h+var_40], rax
0x180078d8a  lea     rdx, [rbp+57h+var_40]
0x180078d8e  lea     rax, aWindowsComCide_8; "Windows::COM::CIdentityAuthority::Parse"
0x180078d95  mov     qword ptr [rbp+57h+var_40+8], rax
0x180078d99  lea     rcx, [rbp+57h+var_48]
0x180078d9d  lea     rax, aValidFlagsChec_0; "Valid flags check failed: dwFlags"
0x180078da4  mov     [rbp+57h+var_28], rax
0x180078da8  call    ?OriginateInvalidParameter@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180078dad  jmp     loc_180078F03
0x180078db2  test    rdi, rdi
0x180078db5  jnz     short loc_180078DF2
0x180078db7  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x180078dbe  mov     [rbp+57h+var_30], 80h
0x180078dc6  mov     qword ptr [rbp+57h+var_40], rax
0x180078dca  lea     rdx, [rbp+57h+var_40]
0x180078dce  lea     rax, aWindowsComCide_8; "Windows::COM::CIdentityAuthority::Parse"
0x180078dd5  mov     qword ptr [rbp+57h+var_40+8], rax
0x180078dd9  lea     rcx, [rbp+57h+var_48]
0x180078ddd  lea     rax, aNotNullCheckFa_16; "Not-null check failed: ppICOMIdentity"
0x180078de4  mov     [rbp+57h+var_28], rax
0x180078de8  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180078ded  jmp     loc_180078F03
0x180078df2  lea     rdx, [rbp+57h+var_48]
0x180078df6  mov     [rbp+57h+var_48], r14
0x180078dfa  call    RtlGetIdentityAuthority
0x180078dff  test    eax, eax
0x180078e01  jns     short loc_180078E11
0x180078e03  mov     ecx, eax
0x180078e05  call    ConvertNtStatusToHResult
0x180078e0a  mov     ebx, eax
0x180078e0c  jmp     loc_180078EF8
0x180078e11  mov     [rbp+57h+var_50], r14
0x180078e15  xorps   xmm0, xmm0
0x180078e18  test    rbx, rbx
0x180078e1b  jnz     short loc_180078E8C
0x180078e1d  mov     rcx, [rbp+57h+var_48]
0x180078e21  lea     rdx, [rbp+57h+var_50]
0x180078e25  mov     [rsp+0E0h+var_B8], rdx
0x180078e2a  lea     r9, [rbp+57h+var_A0]
0x180078e2e  mov     [rbp+57h+var_A0], r14
0x180078e32  xor     r8d, r8d
0x180078e35  mov     [rbp+57h+var_98], r14d
0x180078e39  movdqa  [rbp+57h+var_90], xmm0
0x180078e3e  mov     [rbp+57h+var_80], r14
0x180078e42  mov     [rbp+57h+var_78], r14
0x180078e46  mov     [rbp+57h+var_70], 0FFFFFFFFh
0x180078e4d  mov     [rbp+57h+var_68], r14
0x180078e51  mov     [rbp+57h+var_60], r14
0x180078e55  mov     [rbp+57h+var_58], r14d
0x180078e59  mov     rax, [rcx]
0x180078e5c  shr     esi, 1
0x180078e5e  and     esi, 1
0x180078e61  mov     [rsp+0E0h+var_C0], r14
0x180078e66  mov     edx, esi
0x180078e68  mov     rax, [rax+0A0h]
0x180078e6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078e74  test    eax, eax
0x180078e76  jns     short loc_180078EDA
0x180078e78  mov     ecx, eax
0x180078e7a  call    ConvertNtStatusToHResult
0x180078e7f  mov     ebx, eax
0x180078e81  lea     rcx, [rbp+57h+var_50]
0x180078e85  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x180078e8a  jmp     short loc_180078EF8
0x180078e8c  xor     eax, eax
0x180078e8e  lea     rdx, [rbp+57h+var_40]; wchar_t *
0x180078e92  mov     rcx, rbx; this
0x180078e95  mov     [rbp+57h+var_30], rax
0x180078e99  movups  xmmword ptr [rbp+57h+var_40], xmm0
0x180078e9d  call    ?ConvertIn@COM@Windows@@YAJPEB_WPEAU_LUNICODE_STRING@@@Z; Windows::COM::ConvertIn(wchar_t const *,_LUNICODE_STRING *)
0x180078ea2  mov     ebx, eax
0x180078ea4  test    eax, eax
0x180078ea6  js      short loc_180078E81
0x180078ea8  mov     rcx, [rbp+57h+var_48]
0x180078eac  lea     r9, [rbp+57h+var_50]
0x180078eb0  mov     r8d, esi
0x180078eb3  shr     r8d, 1
0x180078eb6  and     r8d, 1
0x180078eba  mov     rax, [rcx]
0x180078ebd  mov     edx, r8d
0x180078ec0  or      edx, 2
0x180078ec3  test    sil, 1
0x180078ec7  mov     rax, [rax+18h]
0x180078ecb  cmovz   edx, r8d
0x180078ecf  lea     r8, [rbp+57h+var_40]
0x180078ed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078ed8  jmp     short loc_180078E74
0x180078eda  mov     rcx, [rbp+57h+var_50]; struct Windows::Identity::Rtl::IRtlDefinitionIdentity *
0x180078ede  mov     r8, rdi; struct IUnknown **
0x180078ee1  call    ?Create@CDefinitionIdentity@COM@Windows@@KAJPEAUIRtlDefinitionIdentity@Rtl@Identity@3@AEBU_GUID@@PEAPEAUIUnknown@@@Z; Windows::COM::CDefinitionIdentity::Create(Windows::Identity::Rtl::IRtlDefinitionIdentity *,_GUID const &,IUnknown * *)
0x180078ee6  lea     rcx, [rbp+57h+var_50]
0x180078eea  mov     ebx, eax
0x180078eec  test    eax, eax
0x180078eee  js      short loc_180078E85
0x180078ef0  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x180078ef5  mov     ebx, r14d
0x180078ef8  lea     rcx, [rbp+57h+var_48]
0x180078efc  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x180078f01  mov     eax, ebx
0x180078f03  mov     rcx, [rbp+57h+var_20]
0x180078f07  xor     rcx, rsp; StackCookie
0x180078f0a  call    __security_check_cookie
0x180078f0f  lea     r11, [rsp+0E0h+var_10]
0x180078f17  mov     rbx, [r11+20h]
0x180078f1b  mov     rsi, [r11+28h]
0x180078f1f  mov     rsp, r11
0x180078f22  pop     r14
0x180078f24  pop     rdi
0x180078f25  pop     rbp
0x180078f26  retn
```
