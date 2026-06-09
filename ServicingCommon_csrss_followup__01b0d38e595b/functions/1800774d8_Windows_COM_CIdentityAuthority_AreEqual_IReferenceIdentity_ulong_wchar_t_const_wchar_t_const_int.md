# Windows::COM::CIdentityAuthority::AreEqual<IReferenceIdentity>(ulong,wchar_t const *,wchar_t const *,int *)

- ea: `0x1800774d8`
- end: `0x180077711`
- name: `??$AreEqual@UIReferenceIdentity@@@CIdentityAuthority@COM@Windows@@IEAAJKPEB_W0PEAH@Z`
- size: `569`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180078f00`

## callees

- `0x18001af00`
- `0x180021794`
- `0x18002d2b0`
- `0x18006b3e0`
- `0x1800774d8`
- `0x18007915c`
- `0x180084b88`
- `0x18009255c`
- `0x18009e020`

## string_xrefs

- `0x180077537`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x180077577`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x1800775a3`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x18007754a`: `Windows::COM::CIdentityAuthority::AreEqual`
- `0x18007758a`: `Windows::COM::CIdentityAuthority::AreEqual`
- `0x1800775b6`: `Windows::COM::CIdentityAuthority::AreEqual`

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
0x1800774d8  mov     [rsp-8+arg_0], rbx
0x1800774dd  push    rbp
0x1800774de  push    rsi
0x1800774df  push    rdi
0x1800774e0  lea     rbp, [rsp-3Fh]
0x1800774e5  sub     rsp, 0B0h
0x1800774ec  mov     rax, cs:__security_cookie
0x1800774f3  xor     rax, rsp
0x1800774f6  mov     [rbp+4Fh+var_20], rax
0x1800774fa  mov     rbx, [rbp+4Fh+arg_20]
0x1800774fe  mov     rdi, r9
0x180077501  mov     [rbp+4Fh+var_64], 0
0x180077508  mov     rsi, r8
0x18007750b  mov     eax, edx
0x18007750d  test    rbx, rbx
0x180077510  jz      short loc_180077518
0x180077512  mov     dword ptr [rbx], 0
0x180077518  lea     rdx, [rbp+4Fh+var_90]
0x18007751c  mov     dword ptr [rbp+4Fh+var_90], 0
0x180077523  mov     ecx, eax
0x180077525  call    ?MapAreEqualFlags@?$CCOMToRtlInterfaceMapper@UIReferenceIdentity@@@COM@Windows@@SAJKPEAK@Z; Windows::COM::CCOMToRtlInterfaceMapper<IReferenceIdentity>::MapAreEqualFlags(ulong,ulong *)
0x18007752a  test    eax, eax
0x18007752c  js      loc_1800776F1
0x180077532  test    rsi, rsi
0x180077535  jnz     short loc_180077572
0x180077537  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x18007753e  mov     [rbp+4Fh+var_78], 15Bh
0x180077546  mov     [rbp+4Fh+var_88], rax
0x18007754a  lea     rax, aWindowsComCide_5; "Windows::COM::CIdentityAuthority::AreEq"...
0x180077551  mov     [rbp+4Fh+var_80], rax
0x180077555  lea     rax, aNotNullCheckFa_49; "Not-null check failed: pszIdentityLeft"
0x18007755c  lea     rdx, [rbp+4Fh+var_88]
0x180077560  mov     [rbp+4Fh+var_70], rax
0x180077564  lea     rcx, [rbp+4Fh+var_64]
0x180077568  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18007756d  jmp     loc_1800776F1
0x180077572  test    rdi, rdi
0x180077575  jnz     short loc_18007759E
0x180077577  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x18007757e  mov     [rbp+4Fh+var_78], 15Ch
0x180077586  mov     [rbp+4Fh+var_88], rax
0x18007758a  lea     rax, aWindowsComCide_5; "Windows::COM::CIdentityAuthority::AreEq"...
0x180077591  mov     [rbp+4Fh+var_80], rax
0x180077595  lea     rax, aNotNullCheckFa_75; "Not-null check failed: pszIdentityRight"
0x18007759c  jmp     short loc_18007755C
0x18007759e  test    rbx, rbx
0x1800775a1  jnz     short loc_1800775CA
0x1800775a3  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x1800775aa  mov     [rbp+4Fh+var_78], 15Dh
0x1800775b2  mov     [rbp+4Fh+var_88], rax
0x1800775b6  lea     rax, aWindowsComCide_5; "Windows::COM::CIdentityAuthority::AreEq"...
0x1800775bd  mov     [rbp+4Fh+var_80], rax
0x1800775c1  lea     rax, aNotNullCheckFa_64; "Not-null check failed: pfAreEqual"
0x1800775c8  jmp     short loc_18007755C
0x1800775ca  xor     eax, eax
0x1800775cc  lea     rdx, [rbp+4Fh+var_50]; wchar_t *
0x1800775d0  xorps   xmm0, xmm0
0x1800775d3  mov     [rbp+4Fh+var_40], rax
0x1800775d7  xorps   xmm1, xmm1
0x1800775da  mov     [rbp+4Fh+var_28], rax
0x1800775de  mov     rcx, rsi; this
0x1800775e1  movups  xmmword ptr [rbp+4Fh+var_50], xmm0
0x1800775e5  movups  xmmword ptr [rbp+4Fh+var_38], xmm1
0x1800775e9  call    ?ConvertIn@COM@Windows@@YAJPEB_WPEAU_LUNICODE_STRING@@@Z; Windows::COM::ConvertIn(wchar_t const *,_LUNICODE_STRING *)
0x1800775ee  test    eax, eax
0x1800775f0  js      loc_1800776F1
0x1800775f6  lea     rdx, [rbp+4Fh+var_38]; wchar_t *
0x1800775fa  mov     rcx, rdi; this
0x1800775fd  call    ?ConvertIn@COM@Windows@@YAJPEB_WPEAU_LUNICODE_STRING@@@Z; Windows::COM::ConvertIn(wchar_t const *,_LUNICODE_STRING *)
0x180077602  test    eax, eax
0x180077604  js      loc_1800776F1
0x18007760a  lea     rdx, [rbp+4Fh+var_90]
0x18007760e  mov     [rbp+4Fh+var_90], 0
0x180077616  call    RtlGetIdentityAuthority
0x18007761b  test    eax, eax
0x18007761d  jns     short loc_18007762D
0x18007761f  mov     ecx, eax
0x180077621  call    ConvertNtStatusToHResult
0x180077626  mov     ebx, eax
0x180077628  jmp     loc_1800776E6
0x18007762d  mov     rdi, [rbp+4Fh+var_90]
0x180077631  lea     r9, [rbp+4Fh+var_60]
0x180077635  mov     [rbp+4Fh+var_60], 0
0x18007763d  lea     r8, [rbp+4Fh+var_50]
0x180077641  xor     edx, edx
0x180077643  mov     rcx, rdi
0x180077646  mov     rax, [rdi]
0x180077649  mov     rax, [rax+10h]
0x18007764d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077652  test    eax, eax
0x180077654  jns     short loc_18007766A
0x180077656  mov     ecx, eax
0x180077658  call    ConvertNtStatusToHResult
0x18007765d  mov     ebx, eax
0x18007765f  lea     rcx, [rbp+4Fh+var_60]
0x180077663  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x180077668  jmp     short loc_1800776E6
0x18007766a  mov     [rbp+4Fh+var_58], 0
0x180077672  lea     r9, [rbp+4Fh+var_58]
0x180077676  mov     rax, [rdi]
0x180077679  lea     r8, [rbp+4Fh+var_38]
0x18007767d  xor     edx, edx
0x18007767f  mov     rcx, rdi
0x180077682  mov     rax, [rax+10h]
0x180077686  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007768b  test    eax, eax
0x18007768d  jns     short loc_1800776A3
0x18007768f  mov     ecx, eax
0x180077691  call    ConvertNtStatusToHResult
0x180077696  lea     rcx, [rbp+4Fh+var_58]
0x18007769a  mov     ebx, eax
0x18007769c  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x1800776a1  jmp     short loc_18007765F
0x1800776a3  mov     r8, [rbp+4Fh+var_60]
0x1800776a7  lea     rcx, [rbp+4Fh+var_68]
0x1800776ab  mov     [rbp+4Fh+var_68], 0
0x1800776af  mov     r9, r8
0x1800776b2  mov     rax, [rdi]
0x1800776b5  xor     edx, edx
0x1800776b7  mov     [rsp+0C0h+var_A0], rcx
0x1800776bc  mov     rcx, rdi
0x1800776bf  mov     rax, [rax+30h]
0x1800776c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800776c8  test    eax, eax
0x1800776ca  js      short loc_18007768F
0x1800776cc  movzx   eax, [rbp+4Fh+var_68]
0x1800776d0  lea     rcx, [rbp+4Fh+var_58]
0x1800776d4  mov     [rbx], eax
0x1800776d6  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x1800776db  lea     rcx, [rbp+4Fh+var_60]
0x1800776df  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x1800776e4  xor     ebx, ebx
0x1800776e6  lea     rcx, [rbp+4Fh+var_90]
0x1800776ea  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x1800776ef  mov     eax, ebx
0x1800776f1  mov     rcx, [rbp+4Fh+var_20]
0x1800776f5  xor     rcx, rsp; StackCookie
0x1800776f8  call    __security_check_cookie
0x1800776fd  mov     rbx, [rsp+0C0h+arg_0]
0x180077705  add     rsp, 0B0h
0x18007770c  pop     rdi
0x18007770d  pop     rsi
0x18007770e  pop     rbp
0x18007770f  retn
```
