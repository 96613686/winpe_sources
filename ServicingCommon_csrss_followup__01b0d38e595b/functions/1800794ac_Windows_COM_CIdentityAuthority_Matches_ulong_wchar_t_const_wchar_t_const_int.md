# Windows::COM::CIdentityAuthority::Matches(ulong,wchar_t const *,wchar_t const *,int *)

- ea: `0x1800794ac`
- end: `0x180079716`
- name: `?Matches@CIdentityAuthority@COM@Windows@@IEAAJKPEB_W0PEAH@Z`
- size: `618`
- prototype: `int(Windows::COM::CIdentityAuthority *__hidden this, unsigned int, const wchar_t *, const wchar_t *, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180079070`

## callees

- `0x18001af00`
- `0x18002175c`
- `0x180021794`
- `0x18002d2b0`
- `0x18006b3e0`
- `0x1800794ac`
- `0x180084b88`
- `0x18009255c`
- `0x18009e020`

## string_xrefs

- `0x1800794f2`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x180079532`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x180079572`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x18007959e`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x180079509`: `Windows::COM::CIdentityAuthority::Matches`
- `0x180079545`: `Windows::COM::CIdentityAuthority::Matches`
- `0x180079585`: `Windows::COM::CIdentityAuthority::Matches`
- `0x1800795b1`: `Windows::COM::CIdentityAuthority::Matches`

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
0x1800794ac  mov     [rsp-8+arg_0], rbx
0x1800794b1  mov     [rsp-8+arg_8], rdi
0x1800794b6  push    rbp
0x1800794b7  lea     rbp, [rsp-4Fh]
0x1800794bc  sub     rsp, 0B0h
0x1800794c3  mov     rax, cs:__security_cookie
0x1800794ca  xor     rax, rsp
0x1800794cd  mov     [rbp+4Fh+var_10], rax
0x1800794d1  mov     rbx, [rbp+4Fh+arg_20]
0x1800794d5  mov     rdi, r9
0x1800794d8  mov     dword ptr [rbp+4Fh+var_58], 0
0x1800794df  test    rbx, rbx
0x1800794e2  jz      short loc_1800794EA
0x1800794e4  mov     dword ptr [rbx], 0
0x1800794ea  test    edx, 0FFFFFFFEh
0x1800794f0  jz      short loc_18007952D
0x1800794f2  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x1800794f9  mov     [rbp+4Fh+var_70], 1A7h
0x180079501  mov     [rbp+4Fh+var_80], rax
0x180079505  lea     rdx, [rbp+4Fh+var_80]
0x180079509  lea     rax, aWindowsComCide_4; "Windows::COM::CIdentityAuthority::Match"...
0x180079510  mov     [rbp+4Fh+var_78], rax
0x180079514  lea     rcx, [rbp+4Fh+var_58]
0x180079518  lea     rax, aValidFlagsChec_0; "Valid flags check failed: dwFlags"
0x18007951f  mov     [rbp+4Fh+var_68], rax
0x180079523  call    ?OriginateInvalidParameter@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180079528  jmp     loc_1800796F4
0x18007952d  test    r8, r8
0x180079530  jnz     short loc_18007956D
0x180079532  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x180079539  mov     [rbp+4Fh+var_70], 1A8h
0x180079541  mov     [rbp+4Fh+var_80], rax
0x180079545  lea     rax, aWindowsComCide_4; "Windows::COM::CIdentityAuthority::Match"...
0x18007954c  mov     [rbp+4Fh+var_78], rax
0x180079550  lea     rax, aNotNullCheckFa_78; "Not-null check failed: pszDefinition"
0x180079557  lea     rdx, [rbp+4Fh+var_80]
0x18007955b  mov     [rbp+4Fh+var_68], rax
0x18007955f  lea     rcx, [rbp+4Fh+var_58]
0x180079563  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180079568  jmp     loc_1800796F4
0x18007956d  test    rdi, rdi
0x180079570  jnz     short loc_180079599
0x180079572  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x180079579  mov     [rbp+4Fh+var_70], 1A9h
0x180079581  mov     [rbp+4Fh+var_80], rax
0x180079585  lea     rax, aWindowsComCide_4; "Windows::COM::CIdentityAuthority::Match"...
0x18007958c  mov     [rbp+4Fh+var_78], rax
0x180079590  lea     rax, aNotNullCheckFa_17; "Not-null check failed: pszReference"
0x180079597  jmp     short loc_180079557
0x180079599  test    rbx, rbx
0x18007959c  jnz     short loc_1800795C5
0x18007959e  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x1800795a5  mov     [rbp+4Fh+var_70], 1AAh
0x1800795ad  mov     [rbp+4Fh+var_80], rax
0x1800795b1  lea     rax, aWindowsComCide_4; "Windows::COM::CIdentityAuthority::Match"...
0x1800795b8  mov     [rbp+4Fh+var_78], rax
0x1800795bc  lea     rax, aNotNullCheckFa_66; "Not-null check failed: pfMatches"
0x1800795c3  jmp     short loc_180079557
0x1800795c5  xor     eax, eax
0x1800795c7  lea     rdx, [rbp+4Fh+var_40]; wchar_t *
0x1800795cb  xorps   xmm0, xmm0
0x1800795ce  mov     [rbp+4Fh+var_30], rax
0x1800795d2  xorps   xmm1, xmm1
0x1800795d5  mov     [rbp+4Fh+var_18], rax
0x1800795d9  mov     rcx, r8; this
0x1800795dc  movups  xmmword ptr [rbp+4Fh+var_40], xmm0
0x1800795e0  movups  xmmword ptr [rbp+4Fh+var_28], xmm1
0x1800795e4  call    ?ConvertIn@COM@Windows@@YAJPEB_WPEAU_LUNICODE_STRING@@@Z; Windows::COM::ConvertIn(wchar_t const *,_LUNICODE_STRING *)
0x1800795e9  test    eax, eax
0x1800795eb  js      loc_1800796F4
0x1800795f1  lea     rdx, [rbp+4Fh+var_28]; wchar_t *
0x1800795f5  mov     rcx, rdi; this
0x1800795f8  call    ?ConvertIn@COM@Windows@@YAJPEB_WPEAU_LUNICODE_STRING@@@Z; Windows::COM::ConvertIn(wchar_t const *,_LUNICODE_STRING *)
0x1800795fd  test    eax, eax
0x1800795ff  js      loc_1800796F4
0x180079605  lea     rdx, [rbp+4Fh+var_58]
0x180079609  mov     [rbp+4Fh+var_58], 0
0x180079611  call    RtlGetIdentityAuthority
0x180079616  test    eax, eax
0x180079618  jns     short loc_180079628
0x18007961a  mov     ecx, eax
0x18007961c  call    ConvertNtStatusToHResult
0x180079621  mov     ebx, eax
0x180079623  jmp     loc_1800796E9
0x180079628  mov     rdi, [rbp+4Fh+var_58]
0x18007962c  lea     r9, [rbp+4Fh+var_50]
0x180079630  mov     [rbp+4Fh+var_50], 0
0x180079638  lea     r8, [rbp+4Fh+var_40]
0x18007963c  xor     edx, edx
0x18007963e  mov     rcx, rdi
0x180079641  mov     rax, [rdi]
0x180079644  mov     rax, [rax+18h]
0x180079648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007964d  test    eax, eax
0x18007964f  jns     short loc_180079668
0x180079651  mov     ecx, eax
0x180079653  call    ConvertNtStatusToHResult
0x180079658  mov     ebx, eax
0x18007965a  lea     rcx, [rbp+4Fh+var_50]
0x18007965e  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x180079663  jmp     loc_1800796E9
0x180079668  mov     [rbp+4Fh+var_48], 0
0x180079670  lea     r9, [rbp+4Fh+var_48]
0x180079674  mov     rax, [rdi]
0x180079677  lea     r8, [rbp+4Fh+var_28]
0x18007967b  xor     edx, edx
0x18007967d  mov     rcx, rdi
0x180079680  mov     rax, [rax+10h]
0x180079684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079689  test    eax, eax
0x18007968b  jns     short loc_1800796A1
0x18007968d  mov     ecx, eax
0x18007968f  call    ConvertNtStatusToHResult
0x180079694  lea     rcx, [rbp+4Fh+var_48]
0x180079698  mov     ebx, eax
0x18007969a  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x18007969f  jmp     short loc_18007965A
0x1800796a1  mov     r9, [rbp+4Fh+var_48]
0x1800796a5  lea     rcx, [rbp+4Fh+var_60]
0x1800796a9  mov     r8, [rbp+4Fh+var_50]
0x1800796ad  xor     edx, edx
0x1800796af  mov     [rbp+4Fh+var_60], 0
0x1800796b3  mov     rax, [rdi]
0x1800796b6  mov     [rsp+0B0h+var_90], rcx
0x1800796bb  mov     rcx, rdi
0x1800796be  mov     rax, [rax+40h]
0x1800796c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800796c7  test    eax, eax
0x1800796c9  js      short loc_18007968D
0x1800796cb  xor     eax, eax
0x1800796cd  lea     rcx, [rbp+4Fh+var_48]
0x1800796d1  cmp     [rbp+4Fh+var_60], al
0x1800796d4  setnz   al
0x1800796d7  mov     [rbx], eax
0x1800796d9  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x1800796de  lea     rcx, [rbp+4Fh+var_50]
0x1800796e2  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x1800796e7  xor     ebx, ebx
0x1800796e9  lea     rcx, [rbp+4Fh+var_58]
0x1800796ed  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x1800796f2  mov     eax, ebx
0x1800796f4  mov     rcx, [rbp+4Fh+var_10]
0x1800796f8  xor     rcx, rsp; StackCookie
0x1800796fb  call    __security_check_cookie
0x180079700  lea     r11, [rsp+0B0h+var_s0]
0x180079708  mov     rbx, [r11+10h]
0x18007970c  mov     rdi, [r11+18h]
0x180079710  mov     rsp, r11
0x180079713  pop     rbp
0x180079714  retn
```
