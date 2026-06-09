# Windows::COM::CIdentityAuthority::AreEqual<IDefinitionIdentity>(ulong,wchar_t const *,wchar_t const *,int *)

- ea: `0x1800770f0`
- end: `0x180077329`
- name: `??$AreEqual@UIDefinitionIdentity@@@CIdentityAuthority@COM@Windows@@IEAAJKPEB_W0PEAH@Z`
- size: `569`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180078ef0`

## callees

- `0x18001af00`
- `0x180021794`
- `0x18002d2b0`
- `0x18006b3e0`
- `0x1800770f0`
- `0x1800790dc`
- `0x180084b88`
- `0x18009255c`
- `0x18009e020`

## string_xrefs

- `0x18007714f`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x18007718f`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x1800771bb`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x180077162`: `Windows::COM::CIdentityAuthority::AreEqual`
- `0x1800771a2`: `Windows::COM::CIdentityAuthority::AreEqual`
- `0x1800771ce`: `Windows::COM::CIdentityAuthority::AreEqual`

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
0x1800770f0  mov     [rsp-8+arg_0], rbx
0x1800770f5  push    rbp
0x1800770f6  push    rsi
0x1800770f7  push    rdi
0x1800770f8  lea     rbp, [rsp-3Fh]
0x1800770fd  sub     rsp, 0B0h
0x180077104  mov     rax, cs:__security_cookie
0x18007710b  xor     rax, rsp
0x18007710e  mov     [rbp+4Fh+var_20], rax
0x180077112  mov     rbx, [rbp+4Fh+arg_20]
0x180077116  mov     rdi, r9
0x180077119  mov     [rbp+4Fh+var_64], 0
0x180077120  mov     rsi, r8
0x180077123  mov     eax, edx
0x180077125  test    rbx, rbx
0x180077128  jz      short loc_180077130
0x18007712a  mov     dword ptr [rbx], 0
0x180077130  lea     rdx, [rbp+4Fh+var_90]
0x180077134  mov     dword ptr [rbp+4Fh+var_90], 0
0x18007713b  mov     ecx, eax
0x18007713d  call    ?MapAreEqualFlags@?$CCOMToRtlInterfaceMapper@UIDefinitionIdentity@@@COM@Windows@@SAJKPEAK@Z; Windows::COM::CCOMToRtlInterfaceMapper<IDefinitionIdentity>::MapAreEqualFlags(ulong,ulong *)
0x180077142  test    eax, eax
0x180077144  js      loc_180077309
0x18007714a  test    rsi, rsi
0x18007714d  jnz     short loc_18007718A
0x18007714f  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x180077156  mov     [rbp+4Fh+var_78], 15Bh
0x18007715e  mov     [rbp+4Fh+var_88], rax
0x180077162  lea     rax, aWindowsComCide_5; "Windows::COM::CIdentityAuthority::AreEq"...
0x180077169  mov     [rbp+4Fh+var_80], rax
0x18007716d  lea     rax, aNotNullCheckFa_49; "Not-null check failed: pszIdentityLeft"
0x180077174  lea     rdx, [rbp+4Fh+var_88]
0x180077178  mov     [rbp+4Fh+var_70], rax
0x18007717c  lea     rcx, [rbp+4Fh+var_64]
0x180077180  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180077185  jmp     loc_180077309
0x18007718a  test    rdi, rdi
0x18007718d  jnz     short loc_1800771B6
0x18007718f  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x180077196  mov     [rbp+4Fh+var_78], 15Ch
0x18007719e  mov     [rbp+4Fh+var_88], rax
0x1800771a2  lea     rax, aWindowsComCide_5; "Windows::COM::CIdentityAuthority::AreEq"...
0x1800771a9  mov     [rbp+4Fh+var_80], rax
0x1800771ad  lea     rax, aNotNullCheckFa_75; "Not-null check failed: pszIdentityRight"
0x1800771b4  jmp     short loc_180077174
0x1800771b6  test    rbx, rbx
0x1800771b9  jnz     short loc_1800771E2
0x1800771bb  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x1800771c2  mov     [rbp+4Fh+var_78], 15Dh
0x1800771ca  mov     [rbp+4Fh+var_88], rax
0x1800771ce  lea     rax, aWindowsComCide_5; "Windows::COM::CIdentityAuthority::AreEq"...
0x1800771d5  mov     [rbp+4Fh+var_80], rax
0x1800771d9  lea     rax, aNotNullCheckFa_64; "Not-null check failed: pfAreEqual"
0x1800771e0  jmp     short loc_180077174
0x1800771e2  xor     eax, eax
0x1800771e4  lea     rdx, [rbp+4Fh+var_50]; wchar_t *
0x1800771e8  xorps   xmm0, xmm0
0x1800771eb  mov     [rbp+4Fh+var_40], rax
0x1800771ef  xorps   xmm1, xmm1
0x1800771f2  mov     [rbp+4Fh+var_28], rax
0x1800771f6  mov     rcx, rsi; this
0x1800771f9  movups  xmmword ptr [rbp+4Fh+var_50], xmm0
0x1800771fd  movups  xmmword ptr [rbp+4Fh+var_38], xmm1
0x180077201  call    ?ConvertIn@COM@Windows@@YAJPEB_WPEAU_LUNICODE_STRING@@@Z; Windows::COM::ConvertIn(wchar_t const *,_LUNICODE_STRING *)
0x180077206  test    eax, eax
0x180077208  js      loc_180077309
0x18007720e  lea     rdx, [rbp+4Fh+var_38]; wchar_t *
0x180077212  mov     rcx, rdi; this
0x180077215  call    ?ConvertIn@COM@Windows@@YAJPEB_WPEAU_LUNICODE_STRING@@@Z; Windows::COM::ConvertIn(wchar_t const *,_LUNICODE_STRING *)
0x18007721a  test    eax, eax
0x18007721c  js      loc_180077309
0x180077222  lea     rdx, [rbp+4Fh+var_90]
0x180077226  mov     [rbp+4Fh+var_90], 0
0x18007722e  call    RtlGetIdentityAuthority
0x180077233  test    eax, eax
0x180077235  jns     short loc_180077245
0x180077237  mov     ecx, eax
0x180077239  call    ConvertNtStatusToHResult
0x18007723e  mov     ebx, eax
0x180077240  jmp     loc_1800772FE
0x180077245  mov     rdi, [rbp+4Fh+var_90]
0x180077249  lea     r9, [rbp+4Fh+var_60]
0x18007724d  mov     [rbp+4Fh+var_60], 0
0x180077255  lea     r8, [rbp+4Fh+var_50]
0x180077259  xor     edx, edx
0x18007725b  mov     rcx, rdi
0x18007725e  mov     rax, [rdi]
0x180077261  mov     rax, [rax+18h]
0x180077265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007726a  test    eax, eax
0x18007726c  jns     short loc_180077282
0x18007726e  mov     ecx, eax
0x180077270  call    ConvertNtStatusToHResult
0x180077275  mov     ebx, eax
0x180077277  lea     rcx, [rbp+4Fh+var_60]
0x18007727b  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x180077280  jmp     short loc_1800772FE
0x180077282  mov     [rbp+4Fh+var_58], 0
0x18007728a  lea     r9, [rbp+4Fh+var_58]
0x18007728e  mov     rax, [rdi]
0x180077291  lea     r8, [rbp+4Fh+var_38]
0x180077295  xor     edx, edx
0x180077297  mov     rcx, rdi
0x18007729a  mov     rax, [rax+18h]
0x18007729e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800772a3  test    eax, eax
0x1800772a5  jns     short loc_1800772BB
0x1800772a7  mov     ecx, eax
0x1800772a9  call    ConvertNtStatusToHResult
0x1800772ae  lea     rcx, [rbp+4Fh+var_58]
0x1800772b2  mov     ebx, eax
0x1800772b4  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x1800772b9  jmp     short loc_180077277
0x1800772bb  mov     r8, [rbp+4Fh+var_60]
0x1800772bf  lea     rcx, [rbp+4Fh+var_68]
0x1800772c3  mov     [rbp+4Fh+var_68], 0
0x1800772c7  mov     r9, r8
0x1800772ca  mov     rax, [rdi]
0x1800772cd  xor     edx, edx
0x1800772cf  mov     [rsp+0C0h+var_A0], rcx
0x1800772d4  mov     rcx, rdi
0x1800772d7  mov     rax, [rax+38h]
0x1800772db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800772e0  test    eax, eax
0x1800772e2  js      short loc_1800772A7
0x1800772e4  movzx   eax, [rbp+4Fh+var_68]
0x1800772e8  lea     rcx, [rbp+4Fh+var_58]
0x1800772ec  mov     [rbx], eax
0x1800772ee  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x1800772f3  lea     rcx, [rbp+4Fh+var_60]
0x1800772f7  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x1800772fc  xor     ebx, ebx
0x1800772fe  lea     rcx, [rbp+4Fh+var_90]
0x180077302  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x180077307  mov     eax, ebx
0x180077309  mov     rcx, [rbp+4Fh+var_20]
0x18007730d  xor     rcx, rsp; StackCookie
0x180077310  call    __security_check_cookie
0x180077315  mov     rbx, [rsp+0C0h+arg_0]
0x18007731d  add     rsp, 0B0h
0x180077324  pop     rdi
0x180077325  pop     rsi
0x180077326  pop     rbp
0x180077327  retn
```
