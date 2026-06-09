# Windows::COM::CIdentityAuthority::AreEqual<IReferenceIdentity>(ulong,wchar_t const *,wchar_t const *,int *)

- ea: `0x180077848`
- end: `0x180077a81`
- name: `??$AreEqual@UIReferenceIdentity@@@CIdentityAuthority@COM@Windows@@IEAAJKPEB_W0PEAH@Z`
- size: `569`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180079260`

## callees

- `0x180010c10`
- `0x18001f51c`
- `0x1800293a0`
- `0x18006b1e0`
- `0x180077848`
- `0x1800794bc`
- `0x180085af4`
- `0x180093bdc`
- `0x1800a0020`

## string_xrefs

- `0x1800778a7`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x1800778e7`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x180077913`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x1800778ba`: `Windows::COM::CIdentityAuthority::AreEqual`
- `0x1800778fa`: `Windows::COM::CIdentityAuthority::AreEqual`
- `0x180077926`: `Windows::COM::CIdentityAuthority::AreEqual`

## pseudocode

```c
__int64 __fastcall Windows::COM::CIdentityAuthority::AreEqual<IReferenceIdentity>(
        __int64 a1,
        unsigned int a2,
        Windows::COM *a3,
        Windows::COM *a4,
        _DWORD *a5)
{
  __int64 result; // rax
  struct _LUNICODE_STRING *v8; // r8
  const char *v9; // rax
  struct _LUNICODE_STRING *v10; // r8
  __int64 v11; // rcx
  int IdentityAuthority; // eax
  unsigned int v13; // ebx
  __int64 v14; // rdi
  int v15; // eax
  int v16; // eax
  __int64 v17; // [rsp+30h] [rbp-41h] BYREF
  const char *v18; // [rsp+38h] [rbp-39h] BYREF
  const char *v19; // [rsp+40h] [rbp-31h]
  __int64 v20; // [rsp+48h] [rbp-29h]
  const char *v21; // [rsp+50h] [rbp-21h]
  _BYTE v22[4]; // [rsp+58h] [rbp-19h] BYREF
  int v23; // [rsp+5Ch] [rbp-15h] BYREF
  __int64 v24; // [rsp+60h] [rbp-11h] BYREF
  __int64 v25; // [rsp+68h] [rbp-9h] BYREF
  wchar_t v26[8]; // [rsp+70h] [rbp-1h] BYREF
  __int64 v27; // [rsp+80h] [rbp+Fh]
  wchar_t v28[8]; // [rsp+88h] [rbp+17h] BYREF
  __int64 v29; // [rsp+98h] [rbp+27h]

  v23 = 0;
  if ( a5 )
    *a5 = 0;
  LODWORD(v17) = 0;
  result = Windows::COM::CCOMToRtlInterfaceMapper<IReferenceIdentity>::MapAreEqualFlags(a2, &v17);
  if ( (int)result >= 0 )
  {
    if ( !a3 )
    {
      v20 = 347;
      v18 = "onecore\\base\\wcp\\identity\\com\\identity_authority.cpp";
      v19 = "Windows::COM::CIdentityAuthority::AreEqual";
      v9 = "Not-null check failed: pszIdentityLeft";
LABEL_6:
      v21 = v9;
      return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
               &v23,
               &v18);
    }
    if ( !a4 )
    {
      v20 = 348;
      v18 = "onecore\\base\\wcp\\identity\\com\\identity_authority.cpp";
      v19 = "Windows::COM::CIdentityAuthority::AreEqual";
      v9 = "Not-null check failed: pszIdentityRight";
      goto LABEL_6;
    }
    if ( !a5 )
    {
      v20 = 349;
      v18 = "onecore\\base\\wcp\\identity\\com\\identity_authority.cpp";
      v19 = "Windows::COM::CIdentityAuthority::AreEqual";
      v9 = "Not-null check failed: pfAreEqual";
      goto LABEL_6;
    }
    v27 = 0;
    v29 = 0;
    *(_OWORD *)v26 = 0;
    *(_OWORD *)v28 = 0;
    result = Windows::COM::ConvertIn(a3, v26, v8);
    if ( (int)result >= 0 )
    {
      result = Windows::COM::ConvertIn(a4, v28, v10);
      if ( (int)result >= 0 )
      {
        v17 = 0;
        IdentityAuthority = RtlGetIdentityAuthority(v11, &v17);
        if ( IdentityAuthority >= 0 )
        {
          v14 = v17;
          v24 = 0;
          v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, wchar_t *, __int64 *))(*(_QWORD *)v17 + 16LL))(
                  v17,
                  0,
                  v26,
                  &v24);
          if ( v15 >= 0 )
          {
            v25 = 0;
            v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, wchar_t *, __int64 *))(*(_QWORD *)v14 + 16LL))(
                    v14,
                    0,
                    v28,
                    &v25);
            if ( v16 >= 0 )
            {
              v22[0] = 0;
              v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, _BYTE *))(*(_QWORD *)v14 + 48LL))(
                      v14,
                      0,
                      v24,
                      v24,
                      v22);
              if ( v16 >= 0 )
              {
                *a5 = v22[0];
                Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(&v25);
                Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(&v24);
                v13 = 0;
                goto LABEL_22;
              }
            }
            v13 = ConvertNtStatusToHResult((unsigned int)v16);
            Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(&v25);
          }
          else
          {
            v13 = ConvertNtStatusToHResult((unsigned int)v15);
          }
          Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(&v24);
        }
        else
        {
          v13 = ConvertNtStatusToHResult((unsigned int)IdentityAuthority);
        }
LABEL_22:
        Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(&v17);
        return v13;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180077848  mov     [rsp-8+arg_0], rbx
0x18007784d  push    rbp
0x18007784e  push    rsi
0x18007784f  push    rdi
0x180077850  lea     rbp, [rsp-3Fh]
0x180077855  sub     rsp, 0B0h
0x18007785c  mov     rax, cs:__security_cookie
0x180077863  xor     rax, rsp
0x180077866  mov     [rbp+4Fh+var_20], rax
0x18007786a  mov     rbx, [rbp+4Fh+arg_20]
0x18007786e  mov     rdi, r9
0x180077871  mov     [rbp+4Fh+var_64], 0
0x180077878  mov     rsi, r8
0x18007787b  mov     eax, edx
0x18007787d  test    rbx, rbx
0x180077880  jz      short loc_180077888
0x180077882  mov     dword ptr [rbx], 0
0x180077888  lea     rdx, [rbp+4Fh+var_90]
0x18007788c  mov     dword ptr [rbp+4Fh+var_90], 0
0x180077893  mov     ecx, eax
0x180077895  call    ?MapAreEqualFlags@?$CCOMToRtlInterfaceMapper@UIReferenceIdentity@@@COM@Windows@@SAJKPEAK@Z; Windows::COM::CCOMToRtlInterfaceMapper<IReferenceIdentity>::MapAreEqualFlags(ulong,ulong *)
0x18007789a  test    eax, eax
0x18007789c  js      loc_180077A61
0x1800778a2  test    rsi, rsi
0x1800778a5  jnz     short loc_1800778E2
0x1800778a7  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x1800778ae  mov     [rbp+4Fh+var_78], 15Bh
0x1800778b6  mov     [rbp+4Fh+var_88], rax
0x1800778ba  lea     rax, aWindowsComCide_5; "Windows::COM::CIdentityAuthority::AreEq"...
0x1800778c1  mov     [rbp+4Fh+var_80], rax
0x1800778c5  lea     rax, aNotNullCheckFa_49; "Not-null check failed: pszIdentityLeft"
0x1800778cc  lea     rdx, [rbp+4Fh+var_88]
0x1800778d0  mov     [rbp+4Fh+var_70], rax
0x1800778d4  lea     rcx, [rbp+4Fh+var_64]
0x1800778d8  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x1800778dd  jmp     loc_180077A61
0x1800778e2  test    rdi, rdi
0x1800778e5  jnz     short loc_18007790E
0x1800778e7  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x1800778ee  mov     [rbp+4Fh+var_78], 15Ch
0x1800778f6  mov     [rbp+4Fh+var_88], rax
0x1800778fa  lea     rax, aWindowsComCide_5; "Windows::COM::CIdentityAuthority::AreEq"...
0x180077901  mov     [rbp+4Fh+var_80], rax
0x180077905  lea     rax, aNotNullCheckFa_75; "Not-null check failed: pszIdentityRight"
0x18007790c  jmp     short loc_1800778CC
0x18007790e  test    rbx, rbx
0x180077911  jnz     short loc_18007793A
0x180077913  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x18007791a  mov     [rbp+4Fh+var_78], 15Dh
0x180077922  mov     [rbp+4Fh+var_88], rax
0x180077926  lea     rax, aWindowsComCide_5; "Windows::COM::CIdentityAuthority::AreEq"...
0x18007792d  mov     [rbp+4Fh+var_80], rax
0x180077931  lea     rax, aNotNullCheckFa_64; "Not-null check failed: pfAreEqual"
0x180077938  jmp     short loc_1800778CC
0x18007793a  xor     eax, eax
0x18007793c  lea     rdx, [rbp+4Fh+var_50]; wchar_t *
0x180077940  xorps   xmm0, xmm0
0x180077943  mov     [rbp+4Fh+var_40], rax
0x180077947  xorps   xmm1, xmm1
0x18007794a  mov     [rbp+4Fh+var_28], rax
0x18007794e  mov     rcx, rsi; this
0x180077951  movups  xmmword ptr [rbp+4Fh+var_50], xmm0
0x180077955  movups  xmmword ptr [rbp+4Fh+var_38], xmm1
0x180077959  call    ?ConvertIn@COM@Windows@@YAJPEB_WPEAU_LUNICODE_STRING@@@Z; Windows::COM::ConvertIn(wchar_t const *,_LUNICODE_STRING *)
0x18007795e  test    eax, eax
0x180077960  js      loc_180077A61
0x180077966  lea     rdx, [rbp+4Fh+var_38]; wchar_t *
0x18007796a  mov     rcx, rdi; this
0x18007796d  call    ?ConvertIn@COM@Windows@@YAJPEB_WPEAU_LUNICODE_STRING@@@Z; Windows::COM::ConvertIn(wchar_t const *,_LUNICODE_STRING *)
0x180077972  test    eax, eax
0x180077974  js      loc_180077A61
0x18007797a  lea     rdx, [rbp+4Fh+var_90]
0x18007797e  mov     [rbp+4Fh+var_90], 0
0x180077986  call    RtlGetIdentityAuthority
0x18007798b  test    eax, eax
0x18007798d  jns     short loc_18007799D
0x18007798f  mov     ecx, eax
0x180077991  call    ConvertNtStatusToHResult
0x180077996  mov     ebx, eax
0x180077998  jmp     loc_180077A56
0x18007799d  mov     rdi, [rbp+4Fh+var_90]
0x1800779a1  lea     r9, [rbp+4Fh+var_60]
0x1800779a5  mov     [rbp+4Fh+var_60], 0
0x1800779ad  lea     r8, [rbp+4Fh+var_50]
0x1800779b1  xor     edx, edx
0x1800779b3  mov     rcx, rdi
0x1800779b6  mov     rax, [rdi]
0x1800779b9  mov     rax, [rax+10h]
0x1800779bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800779c2  test    eax, eax
0x1800779c4  jns     short loc_1800779DA
0x1800779c6  mov     ecx, eax
0x1800779c8  call    ConvertNtStatusToHResult
0x1800779cd  mov     ebx, eax
0x1800779cf  lea     rcx, [rbp+4Fh+var_60]
0x1800779d3  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x1800779d8  jmp     short loc_180077A56
0x1800779da  mov     [rbp+4Fh+var_58], 0
0x1800779e2  lea     r9, [rbp+4Fh+var_58]
0x1800779e6  mov     rax, [rdi]
0x1800779e9  lea     r8, [rbp+4Fh+var_38]
0x1800779ed  xor     edx, edx
0x1800779ef  mov     rcx, rdi
0x1800779f2  mov     rax, [rax+10h]
0x1800779f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800779fb  test    eax, eax
0x1800779fd  jns     short loc_180077A13
0x1800779ff  mov     ecx, eax
0x180077a01  call    ConvertNtStatusToHResult
0x180077a06  lea     rcx, [rbp+4Fh+var_58]
0x180077a0a  mov     ebx, eax
0x180077a0c  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x180077a11  jmp     short loc_1800779CF
0x180077a13  mov     r8, [rbp+4Fh+var_60]
0x180077a17  lea     rcx, [rbp+4Fh+var_68]
0x180077a1b  mov     [rbp+4Fh+var_68], 0
0x180077a1f  mov     r9, r8
0x180077a22  mov     rax, [rdi]
0x180077a25  xor     edx, edx
0x180077a27  mov     [rsp+0C0h+var_A0], rcx
0x180077a2c  mov     rcx, rdi
0x180077a2f  mov     rax, [rax+30h]
0x180077a33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077a38  test    eax, eax
0x180077a3a  js      short loc_1800779FF
0x180077a3c  movzx   eax, [rbp+4Fh+var_68]
0x180077a40  lea     rcx, [rbp+4Fh+var_58]
0x180077a44  mov     [rbx], eax
0x180077a46  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x180077a4b  lea     rcx, [rbp+4Fh+var_60]
0x180077a4f  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x180077a54  xor     ebx, ebx
0x180077a56  lea     rcx, [rbp+4Fh+var_90]
0x180077a5a  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x180077a5f  mov     eax, ebx
0x180077a61  mov     rcx, [rbp+4Fh+var_20]
0x180077a65  xor     rcx, rsp; StackCookie
0x180077a68  call    __security_check_cookie
0x180077a6d  mov     rbx, [rsp+0C0h+arg_0]
0x180077a75  add     rsp, 0B0h
0x180077a7c  pop     rdi
0x180077a7d  pop     rsi
0x180077a7e  pop     rbp
0x180077a7f  retn
```
