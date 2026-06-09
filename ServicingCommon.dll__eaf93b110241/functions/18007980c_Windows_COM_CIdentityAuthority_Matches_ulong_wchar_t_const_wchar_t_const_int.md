# Windows::COM::CIdentityAuthority::Matches(ulong,wchar_t const *,wchar_t const *,int *)

- ea: `0x18007980c`
- end: `0x180079a76`
- name: `?Matches@CIdentityAuthority@COM@Windows@@IEAAJKPEB_W0PEAH@Z`
- size: `618`
- prototype: `int(Windows::COM::CIdentityAuthority *__hidden this, unsigned int, const wchar_t *, const wchar_t *, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800793d0`

## callees

- `0x180010c10`
- `0x18001f4e4`
- `0x18001f51c`
- `0x1800293a0`
- `0x18006b1e0`
- `0x18007980c`
- `0x180085af4`
- `0x180093bdc`
- `0x1800a0020`

## string_xrefs

- `0x180079852`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x180079892`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x1800798d2`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x1800798fe`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x180079869`: `Windows::COM::CIdentityAuthority::Matches`
- `0x1800798a5`: `Windows::COM::CIdentityAuthority::Matches`
- `0x1800798e5`: `Windows::COM::CIdentityAuthority::Matches`
- `0x180079911`: `Windows::COM::CIdentityAuthority::Matches`

## pseudocode

```c
__int64 __fastcall Windows::COM::CIdentityAuthority::Matches(
        Windows::COM::CIdentityAuthority *this,
        int a2,
        wchar_t *a3,
        wchar_t *a4,
        int *a5)
{
  __int64 result; // rax
  const char *v7; // rax
  struct _LUNICODE_STRING *v8; // r8
  __int64 v9; // rcx
  int IdentityAuthority; // eax
  unsigned int v11; // ebx
  __int64 v12; // rdi
  int v13; // eax
  int v14; // eax
  const char *v15; // [rsp+30h] [rbp-31h] BYREF
  const char *v16; // [rsp+38h] [rbp-29h]
  __int64 v17; // [rsp+40h] [rbp-21h]
  const char *v18; // [rsp+48h] [rbp-19h]
  _BYTE v19[8]; // [rsp+50h] [rbp-11h] BYREF
  __int64 v20; // [rsp+58h] [rbp-9h] BYREF
  __int64 v21; // [rsp+60h] [rbp-1h] BYREF
  __int64 v22; // [rsp+68h] [rbp+7h] BYREF
  wchar_t v23[8]; // [rsp+70h] [rbp+Fh] BYREF
  __int64 v24; // [rsp+80h] [rbp+1Fh]
  wchar_t v25[8]; // [rsp+88h] [rbp+27h] BYREF
  __int64 v26; // [rsp+98h] [rbp+37h]

  LODWORD(v20) = 0;
  if ( a5 )
    *a5 = 0;
  if ( (a2 & 0xFFFFFFFE) != 0 )
  {
    v17 = 423;
    v15 = "onecore\\base\\wcp\\identity\\com\\identity_authority.cpp";
    v16 = "Windows::COM::CIdentityAuthority::Matches";
    v18 = "Valid flags check failed: dwFlags";
    return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter(
             &v20,
             &v15,
             a3);
  }
  if ( !a3 )
  {
    v17 = 424;
    v15 = "onecore\\base\\wcp\\identity\\com\\identity_authority.cpp";
    v16 = "Windows::COM::CIdentityAuthority::Matches";
    v7 = "Not-null check failed: pszDefinition";
LABEL_7:
    v18 = v7;
    return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v20,
             &v15);
  }
  if ( !a4 )
  {
    v17 = 425;
    v15 = "onecore\\base\\wcp\\identity\\com\\identity_authority.cpp";
    v16 = "Windows::COM::CIdentityAuthority::Matches";
    v7 = "Not-null check failed: pszReference";
    goto LABEL_7;
  }
  if ( !a5 )
  {
    v17 = 426;
    v15 = "onecore\\base\\wcp\\identity\\com\\identity_authority.cpp";
    v16 = "Windows::COM::CIdentityAuthority::Matches";
    v7 = "Not-null check failed: pfMatches";
    goto LABEL_7;
  }
  v24 = 0;
  v26 = 0;
  *(_OWORD *)v23 = 0;
  *(_OWORD *)v25 = 0;
  result = Windows::COM::ConvertIn((Windows::COM *)a3, v23, (struct _LUNICODE_STRING *)a3);
  if ( (int)result >= 0 )
  {
    result = Windows::COM::ConvertIn((Windows::COM *)a4, v25, v8);
    if ( (int)result >= 0 )
    {
      v20 = 0;
      IdentityAuthority = RtlGetIdentityAuthority(v9, &v20);
      if ( IdentityAuthority >= 0 )
      {
        v12 = v20;
        v21 = 0;
        v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, wchar_t *, __int64 *))(*(_QWORD *)v20 + 24LL))(
                v20,
                0,
                v23,
                &v21);
        if ( v13 >= 0 )
        {
          v22 = 0;
          v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, wchar_t *, __int64 *))(*(_QWORD *)v12 + 16LL))(
                  v12,
                  0,
                  v25,
                  &v22);
          if ( v14 >= 0 )
          {
            v19[0] = 0;
            v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, _BYTE *))(*(_QWORD *)v12 + 64LL))(
                    v12,
                    0,
                    v21,
                    v22,
                    v19);
            if ( v14 >= 0 )
            {
              *a5 = v19[0] != 0;
              Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(&v22);
              Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(&v21);
              v11 = 0;
              goto LABEL_23;
            }
          }
          v11 = ConvertNtStatusToHResult((unsigned int)v14);
          Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(&v22);
        }
        else
        {
          v11 = ConvertNtStatusToHResult((unsigned int)v13);
        }
        Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(&v21);
      }
      else
      {
        v11 = ConvertNtStatusToHResult((unsigned int)IdentityAuthority);
      }
LABEL_23:
      Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(&v20);
      return v11;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18007980c  mov     [rsp-8+arg_0], rbx
0x180079811  mov     [rsp-8+arg_8], rdi
0x180079816  push    rbp
0x180079817  lea     rbp, [rsp-4Fh]
0x18007981c  sub     rsp, 0B0h
0x180079823  mov     rax, cs:__security_cookie
0x18007982a  xor     rax, rsp
0x18007982d  mov     [rbp+4Fh+var_10], rax
0x180079831  mov     rbx, [rbp+4Fh+arg_20]
0x180079835  mov     rdi, r9
0x180079838  mov     dword ptr [rbp+4Fh+var_58], 0
0x18007983f  test    rbx, rbx
0x180079842  jz      short loc_18007984A
0x180079844  mov     dword ptr [rbx], 0
0x18007984a  test    edx, 0FFFFFFFEh
0x180079850  jz      short loc_18007988D
0x180079852  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x180079859  mov     [rbp+4Fh+var_70], 1A7h
0x180079861  mov     [rbp+4Fh+var_80], rax
0x180079865  lea     rdx, [rbp+4Fh+var_80]
0x180079869  lea     rax, aWindowsComCide_4; "Windows::COM::CIdentityAuthority::Match"...
0x180079870  mov     [rbp+4Fh+var_78], rax
0x180079874  lea     rcx, [rbp+4Fh+var_58]
0x180079878  lea     rax, aValidFlagsChec_0; "Valid flags check failed: dwFlags"
0x18007987f  mov     [rbp+4Fh+var_68], rax
0x180079883  call    ?OriginateInvalidParameter@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180079888  jmp     loc_180079A54
0x18007988d  test    r8, r8
0x180079890  jnz     short loc_1800798CD
0x180079892  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x180079899  mov     [rbp+4Fh+var_70], 1A8h
0x1800798a1  mov     [rbp+4Fh+var_80], rax
0x1800798a5  lea     rax, aWindowsComCide_4; "Windows::COM::CIdentityAuthority::Match"...
0x1800798ac  mov     [rbp+4Fh+var_78], rax
0x1800798b0  lea     rax, aNotNullCheckFa_78; "Not-null check failed: pszDefinition"
0x1800798b7  lea     rdx, [rbp+4Fh+var_80]
0x1800798bb  mov     [rbp+4Fh+var_68], rax
0x1800798bf  lea     rcx, [rbp+4Fh+var_58]
0x1800798c3  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x1800798c8  jmp     loc_180079A54
0x1800798cd  test    rdi, rdi
0x1800798d0  jnz     short loc_1800798F9
0x1800798d2  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x1800798d9  mov     [rbp+4Fh+var_70], 1A9h
0x1800798e1  mov     [rbp+4Fh+var_80], rax
0x1800798e5  lea     rax, aWindowsComCide_4; "Windows::COM::CIdentityAuthority::Match"...
0x1800798ec  mov     [rbp+4Fh+var_78], rax
0x1800798f0  lea     rax, aNotNullCheckFa_17; "Not-null check failed: pszReference"
0x1800798f7  jmp     short loc_1800798B7
0x1800798f9  test    rbx, rbx
0x1800798fc  jnz     short loc_180079925
0x1800798fe  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x180079905  mov     [rbp+4Fh+var_70], 1AAh
0x18007990d  mov     [rbp+4Fh+var_80], rax
0x180079911  lea     rax, aWindowsComCide_4; "Windows::COM::CIdentityAuthority::Match"...
0x180079918  mov     [rbp+4Fh+var_78], rax
0x18007991c  lea     rax, aNotNullCheckFa_66; "Not-null check failed: pfMatches"
0x180079923  jmp     short loc_1800798B7
0x180079925  xor     eax, eax
0x180079927  lea     rdx, [rbp+4Fh+var_40]; wchar_t *
0x18007992b  xorps   xmm0, xmm0
0x18007992e  mov     [rbp+4Fh+var_30], rax
0x180079932  xorps   xmm1, xmm1
0x180079935  mov     [rbp+4Fh+var_18], rax
0x180079939  mov     rcx, r8; this
0x18007993c  movups  xmmword ptr [rbp+4Fh+var_40], xmm0
0x180079940  movups  xmmword ptr [rbp+4Fh+var_28], xmm1
0x180079944  call    ?ConvertIn@COM@Windows@@YAJPEB_WPEAU_LUNICODE_STRING@@@Z; Windows::COM::ConvertIn(wchar_t const *,_LUNICODE_STRING *)
0x180079949  test    eax, eax
0x18007994b  js      loc_180079A54
0x180079951  lea     rdx, [rbp+4Fh+var_28]; wchar_t *
0x180079955  mov     rcx, rdi; this
0x180079958  call    ?ConvertIn@COM@Windows@@YAJPEB_WPEAU_LUNICODE_STRING@@@Z; Windows::COM::ConvertIn(wchar_t const *,_LUNICODE_STRING *)
0x18007995d  test    eax, eax
0x18007995f  js      loc_180079A54
0x180079965  lea     rdx, [rbp+4Fh+var_58]
0x180079969  mov     [rbp+4Fh+var_58], 0
0x180079971  call    RtlGetIdentityAuthority
0x180079976  test    eax, eax
0x180079978  jns     short loc_180079988
0x18007997a  mov     ecx, eax
0x18007997c  call    ConvertNtStatusToHResult
0x180079981  mov     ebx, eax
0x180079983  jmp     loc_180079A49
0x180079988  mov     rdi, [rbp+4Fh+var_58]
0x18007998c  lea     r9, [rbp+4Fh+var_50]
0x180079990  mov     [rbp+4Fh+var_50], 0
0x180079998  lea     r8, [rbp+4Fh+var_40]
0x18007999c  xor     edx, edx
0x18007999e  mov     rcx, rdi
0x1800799a1  mov     rax, [rdi]
0x1800799a4  mov     rax, [rax+18h]
0x1800799a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800799ad  test    eax, eax
0x1800799af  jns     short loc_1800799C8
0x1800799b1  mov     ecx, eax
0x1800799b3  call    ConvertNtStatusToHResult
0x1800799b8  mov     ebx, eax
0x1800799ba  lea     rcx, [rbp+4Fh+var_50]
0x1800799be  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x1800799c3  jmp     loc_180079A49
0x1800799c8  mov     [rbp+4Fh+var_48], 0
0x1800799d0  lea     r9, [rbp+4Fh+var_48]
0x1800799d4  mov     rax, [rdi]
0x1800799d7  lea     r8, [rbp+4Fh+var_28]
0x1800799db  xor     edx, edx
0x1800799dd  mov     rcx, rdi
0x1800799e0  mov     rax, [rax+10h]
0x1800799e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800799e9  test    eax, eax
0x1800799eb  jns     short loc_180079A01
0x1800799ed  mov     ecx, eax
0x1800799ef  call    ConvertNtStatusToHResult
0x1800799f4  lea     rcx, [rbp+4Fh+var_48]
0x1800799f8  mov     ebx, eax
0x1800799fa  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x1800799ff  jmp     short loc_1800799BA
0x180079a01  mov     r9, [rbp+4Fh+var_48]
0x180079a05  lea     rcx, [rbp+4Fh+var_60]
0x180079a09  mov     r8, [rbp+4Fh+var_50]
0x180079a0d  xor     edx, edx
0x180079a0f  mov     [rbp+4Fh+var_60], 0
0x180079a13  mov     rax, [rdi]
0x180079a16  mov     [rsp+0B0h+var_90], rcx
0x180079a1b  mov     rcx, rdi
0x180079a1e  mov     rax, [rax+40h]
0x180079a22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079a27  test    eax, eax
0x180079a29  js      short loc_1800799ED
0x180079a2b  xor     eax, eax
0x180079a2d  lea     rcx, [rbp+4Fh+var_48]
0x180079a31  cmp     [rbp+4Fh+var_60], al
0x180079a34  setnz   al
0x180079a37  mov     [rbx], eax
0x180079a39  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x180079a3e  lea     rcx, [rbp+4Fh+var_50]
0x180079a42  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x180079a47  xor     ebx, ebx
0x180079a49  lea     rcx, [rbp+4Fh+var_58]
0x180079a4d  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x180079a52  mov     eax, ebx
0x180079a54  mov     rcx, [rbp+4Fh+var_10]
0x180079a58  xor     rcx, rsp; StackCookie
0x180079a5b  call    __security_check_cookie
0x180079a60  lea     r11, [rsp+0B0h+var_s0]
0x180079a68  mov     rbx, [r11+10h]
0x180079a6c  mov     rdi, [r11+18h]
0x180079a70  mov     rsp, r11
0x180079a73  pop     rbp
0x180079a74  retn
```
