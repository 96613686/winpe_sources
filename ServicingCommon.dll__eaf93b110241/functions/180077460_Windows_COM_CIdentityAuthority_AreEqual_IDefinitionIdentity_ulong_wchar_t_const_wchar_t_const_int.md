# Windows::COM::CIdentityAuthority::AreEqual<IDefinitionIdentity>(ulong,wchar_t const *,wchar_t const *,int *)

- ea: `0x180077460`
- end: `0x180077699`
- name: `??$AreEqual@UIDefinitionIdentity@@@CIdentityAuthority@COM@Windows@@IEAAJKPEB_W0PEAH@Z`
- size: `569`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180079250`

## callees

- `0x180010c10`
- `0x18001f51c`
- `0x1800293a0`
- `0x18006b1e0`
- `0x180077460`
- `0x18007943c`
- `0x180085af4`
- `0x180093bdc`
- `0x1800a0020`

## string_xrefs

- `0x1800774bf`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x1800774ff`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x18007752b`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x1800774d2`: `Windows::COM::CIdentityAuthority::AreEqual`
- `0x180077512`: `Windows::COM::CIdentityAuthority::AreEqual`
- `0x18007753e`: `Windows::COM::CIdentityAuthority::AreEqual`

## pseudocode

```c
__int64 __fastcall Windows::COM::CIdentityAuthority::AreEqual<IDefinitionIdentity>(
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
  result = Windows::COM::CCOMToRtlInterfaceMapper<IDefinitionIdentity>::MapAreEqualFlags(a2, &v17);
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
          v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, wchar_t *, __int64 *))(*(_QWORD *)v17 + 24LL))(
                  v17,
                  0,
                  v26,
                  &v24);
          if ( v15 >= 0 )
          {
            v25 = 0;
            v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, wchar_t *, __int64 *))(*(_QWORD *)v14 + 24LL))(
                    v14,
                    0,
                    v28,
                    &v25);
            if ( v16 >= 0 )
            {
              v22[0] = 0;
              v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, _BYTE *))(*(_QWORD *)v14 + 56LL))(
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
0x180077460  mov     [rsp-8+arg_0], rbx
0x180077465  push    rbp
0x180077466  push    rsi
0x180077467  push    rdi
0x180077468  lea     rbp, [rsp-3Fh]
0x18007746d  sub     rsp, 0B0h
0x180077474  mov     rax, cs:__security_cookie
0x18007747b  xor     rax, rsp
0x18007747e  mov     [rbp+4Fh+var_20], rax
0x180077482  mov     rbx, [rbp+4Fh+arg_20]
0x180077486  mov     rdi, r9
0x180077489  mov     [rbp+4Fh+var_64], 0
0x180077490  mov     rsi, r8
0x180077493  mov     eax, edx
0x180077495  test    rbx, rbx
0x180077498  jz      short loc_1800774A0
0x18007749a  mov     dword ptr [rbx], 0
0x1800774a0  lea     rdx, [rbp+4Fh+var_90]
0x1800774a4  mov     dword ptr [rbp+4Fh+var_90], 0
0x1800774ab  mov     ecx, eax
0x1800774ad  call    ?MapAreEqualFlags@?$CCOMToRtlInterfaceMapper@UIDefinitionIdentity@@@COM@Windows@@SAJKPEAK@Z; Windows::COM::CCOMToRtlInterfaceMapper<IDefinitionIdentity>::MapAreEqualFlags(ulong,ulong *)
0x1800774b2  test    eax, eax
0x1800774b4  js      loc_180077679
0x1800774ba  test    rsi, rsi
0x1800774bd  jnz     short loc_1800774FA
0x1800774bf  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x1800774c6  mov     [rbp+4Fh+var_78], 15Bh
0x1800774ce  mov     [rbp+4Fh+var_88], rax
0x1800774d2  lea     rax, aWindowsComCide_5; "Windows::COM::CIdentityAuthority::AreEq"...
0x1800774d9  mov     [rbp+4Fh+var_80], rax
0x1800774dd  lea     rax, aNotNullCheckFa_49; "Not-null check failed: pszIdentityLeft"
0x1800774e4  lea     rdx, [rbp+4Fh+var_88]
0x1800774e8  mov     [rbp+4Fh+var_70], rax
0x1800774ec  lea     rcx, [rbp+4Fh+var_64]
0x1800774f0  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x1800774f5  jmp     loc_180077679
0x1800774fa  test    rdi, rdi
0x1800774fd  jnz     short loc_180077526
0x1800774ff  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x180077506  mov     [rbp+4Fh+var_78], 15Ch
0x18007750e  mov     [rbp+4Fh+var_88], rax
0x180077512  lea     rax, aWindowsComCide_5; "Windows::COM::CIdentityAuthority::AreEq"...
0x180077519  mov     [rbp+4Fh+var_80], rax
0x18007751d  lea     rax, aNotNullCheckFa_75; "Not-null check failed: pszIdentityRight"
0x180077524  jmp     short loc_1800774E4
0x180077526  test    rbx, rbx
0x180077529  jnz     short loc_180077552
0x18007752b  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x180077532  mov     [rbp+4Fh+var_78], 15Dh
0x18007753a  mov     [rbp+4Fh+var_88], rax
0x18007753e  lea     rax, aWindowsComCide_5; "Windows::COM::CIdentityAuthority::AreEq"...
0x180077545  mov     [rbp+4Fh+var_80], rax
0x180077549  lea     rax, aNotNullCheckFa_64; "Not-null check failed: pfAreEqual"
0x180077550  jmp     short loc_1800774E4
0x180077552  xor     eax, eax
0x180077554  lea     rdx, [rbp+4Fh+var_50]; wchar_t *
0x180077558  xorps   xmm0, xmm0
0x18007755b  mov     [rbp+4Fh+var_40], rax
0x18007755f  xorps   xmm1, xmm1
0x180077562  mov     [rbp+4Fh+var_28], rax
0x180077566  mov     rcx, rsi; this
0x180077569  movups  xmmword ptr [rbp+4Fh+var_50], xmm0
0x18007756d  movups  xmmword ptr [rbp+4Fh+var_38], xmm1
0x180077571  call    ?ConvertIn@COM@Windows@@YAJPEB_WPEAU_LUNICODE_STRING@@@Z; Windows::COM::ConvertIn(wchar_t const *,_LUNICODE_STRING *)
0x180077576  test    eax, eax
0x180077578  js      loc_180077679
0x18007757e  lea     rdx, [rbp+4Fh+var_38]; wchar_t *
0x180077582  mov     rcx, rdi; this
0x180077585  call    ?ConvertIn@COM@Windows@@YAJPEB_WPEAU_LUNICODE_STRING@@@Z; Windows::COM::ConvertIn(wchar_t const *,_LUNICODE_STRING *)
0x18007758a  test    eax, eax
0x18007758c  js      loc_180077679
0x180077592  lea     rdx, [rbp+4Fh+var_90]
0x180077596  mov     [rbp+4Fh+var_90], 0
0x18007759e  call    RtlGetIdentityAuthority
0x1800775a3  test    eax, eax
0x1800775a5  jns     short loc_1800775B5
0x1800775a7  mov     ecx, eax
0x1800775a9  call    ConvertNtStatusToHResult
0x1800775ae  mov     ebx, eax
0x1800775b0  jmp     loc_18007766E
0x1800775b5  mov     rdi, [rbp+4Fh+var_90]
0x1800775b9  lea     r9, [rbp+4Fh+var_60]
0x1800775bd  mov     [rbp+4Fh+var_60], 0
0x1800775c5  lea     r8, [rbp+4Fh+var_50]
0x1800775c9  xor     edx, edx
0x1800775cb  mov     rcx, rdi
0x1800775ce  mov     rax, [rdi]
0x1800775d1  mov     rax, [rax+18h]
0x1800775d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800775da  test    eax, eax
0x1800775dc  jns     short loc_1800775F2
0x1800775de  mov     ecx, eax
0x1800775e0  call    ConvertNtStatusToHResult
0x1800775e5  mov     ebx, eax
0x1800775e7  lea     rcx, [rbp+4Fh+var_60]
0x1800775eb  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x1800775f0  jmp     short loc_18007766E
0x1800775f2  mov     [rbp+4Fh+var_58], 0
0x1800775fa  lea     r9, [rbp+4Fh+var_58]
0x1800775fe  mov     rax, [rdi]
0x180077601  lea     r8, [rbp+4Fh+var_38]
0x180077605  xor     edx, edx
0x180077607  mov     rcx, rdi
0x18007760a  mov     rax, [rax+18h]
0x18007760e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077613  test    eax, eax
0x180077615  jns     short loc_18007762B
0x180077617  mov     ecx, eax
0x180077619  call    ConvertNtStatusToHResult
0x18007761e  lea     rcx, [rbp+4Fh+var_58]
0x180077622  mov     ebx, eax
0x180077624  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x180077629  jmp     short loc_1800775E7
0x18007762b  mov     r8, [rbp+4Fh+var_60]
0x18007762f  lea     rcx, [rbp+4Fh+var_68]
0x180077633  mov     [rbp+4Fh+var_68], 0
0x180077637  mov     r9, r8
0x18007763a  mov     rax, [rdi]
0x18007763d  xor     edx, edx
0x18007763f  mov     [rsp+0C0h+var_A0], rcx
0x180077644  mov     rcx, rdi
0x180077647  mov     rax, [rax+38h]
0x18007764b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077650  test    eax, eax
0x180077652  js      short loc_180077617
0x180077654  movzx   eax, [rbp+4Fh+var_68]
0x180077658  lea     rcx, [rbp+4Fh+var_58]
0x18007765c  mov     [rbx], eax
0x18007765e  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x180077663  lea     rcx, [rbp+4Fh+var_60]
0x180077667  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x18007766c  xor     ebx, ebx
0x18007766e  lea     rcx, [rbp+4Fh+var_90]
0x180077672  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x180077677  mov     eax, ebx
0x180077679  mov     rcx, [rbp+4Fh+var_20]
0x18007767d  xor     rcx, rsp; StackCookie
0x180077680  call    __security_check_cookie
0x180077685  mov     rbx, [rsp+0C0h+arg_0]
0x18007768d  add     rsp, 0B0h
0x180077694  pop     rdi
0x180077695  pop     rsi
0x180077696  pop     rbp
0x180077697  retn
```
