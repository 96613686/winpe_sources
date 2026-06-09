# Windows::COM::CReferenceIdentity::Clone(unsigned __int64,_IDENTITY_ATTRIBUTE const * const,IReferenceIdentity * *)

- ea: `0x18007a360`
- end: `0x18007a59a`
- name: `?Clone@CReferenceIdentity@COM@Windows@@MEAAJ_KQEBU_IDENTITY_ATTRIBUTE@@PEAPEAUIReferenceIdentity@@@Z`
- size: `570`
- prototype: `int(Windows::COM::CReferenceIdentity *__hidden this, unsigned __int64, const struct _IDENTITY_ATTRIBUTE *const, struct IReferenceIdentity **)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x1800052ac`
- `0x1800098bc`
- `0x18001af00`
- `0x1800211f0`
- `0x18002175c`
- `0x180021794`
- `0x18002d2b0`
- `0x18006b3e0`
- `0x18007a360`
- `0x18007a5a0`
- `0x180084b88`
- `0x18009e020`

## string_xrefs

- `0x18007a3ac`: `onecore\base\wcp\identity\com\identity_ref.cpp`
- `0x18007a3ec`: `onecore\base\wcp\identity\com\identity_ref.cpp`
- `0x18007a43d`: `onecore\base\wcp\identity\com\identity_ref.cpp`
- `0x18007a3c3`: `Windows::COM::CReferenceIdentity::Clone`
- `0x18007a403`: `Windows::COM::CReferenceIdentity::Clone`
- `0x18007a456`: `Windows::COM::CReferenceIdentity::Clone`

## pseudocode

```c
__int64 __fastcall Windows::COM::CReferenceIdentity::Clone(
        Windows::COM::CReferenceIdentity *this,
        unsigned __int64 a2,
        const struct _IDENTITY_ATTRIBUTE *const a3,
        struct IUnknown **a4)
{
  struct _LUNICODE_STRING *v9; // r8
  int v10; // eax
  int v11; // ebx
  unsigned __int64 v12; // rbx
  __int64 v13; // rdi
  Windows::COM *v14; // rcx
  struct _LUNICODE_STRING *v15; // r8
  Windows::COM *v16; // rcx
  struct _LUNICODE_STRING *v17; // r8
  Windows::COM *v18; // rcx
  __int64 v19; // rcx
  int v20; // eax
  const struct _GUID *v21; // rdx
  _QWORD v22[4]; // [rsp+30h] [rbp-89h] BYREF
  wchar_t v23[4]; // [rsp+50h] [rbp-69h] BYREF
  const char *v24; // [rsp+58h] [rbp-61h]
  __int64 v25; // [rsp+60h] [rbp-59h]
  const char *v26; // [rsp+68h] [rbp-51h]
  wchar_t v27[4]; // [rsp+70h] [rbp-49h] BYREF
  __int64 v28; // [rsp+78h] [rbp-41h]
  __int64 v29; // [rsp+80h] [rbp-39h]
  wchar_t v30[4]; // [rsp+88h] [rbp-31h] BYREF
  __int64 v31; // [rsp+90h] [rbp-29h]
  __int64 v32; // [rsp+98h] [rbp-21h]
  int v33; // [rsp+A0h] [rbp-19h] BYREF
  struct Windows::Identity::Rtl::IRtlReferenceIdentity *v34; // [rsp+A8h] [rbp-11h] BYREF
  _QWORD v35[2]; // [rsp+B0h] [rbp-9h] BYREF

  v33 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a2 && !a3 )
  {
    v25 = 173;
    *(_QWORD *)v23 = "onecore\\base\\wcp\\identity\\com\\identity_ref.cpp";
    v24 = "Windows::COM::CReferenceIdentity::Clone";
    v26 = "(cDeltas == 0) || (rgDeltas != 0)";
    return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter(
             &v33,
             v23,
             0);
  }
  if ( !a4 )
  {
    v25 = 174;
    *(_QWORD *)v23 = "onecore\\base\\wcp\\identity\\com\\identity_ref.cpp";
    v24 = "Windows::COM::CReferenceIdentity::Clone";
    v26 = "Not-null check failed: ppIReferenceIdentity";
    return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v33,
             v23);
  }
  v35[0] = 0;
  v35[1] = 0;
  if ( !Windows::AutoVectorBase<Windows::VectorTraits<Windows::Identity::Rtl::_ATTRIBUTE>,Windows::Auto<Windows::Vector<Windows::Identity::Rtl::_ATTRIBUTE>>>::Allocate(
          v35,
          a2) )
  {
    v22[2] = 177;
    v22[0] = "onecore\\base\\wcp\\identity\\com\\identity_ref.cpp";
    v22[1] = "Windows::COM::CReferenceIdentity::Clone";
    v22[3] = "Attributes.Allocate(cDeltas)";
    v10 = Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(
            &v33,
            v22,
            2147942414LL);
LABEL_10:
    v11 = v10;
    goto LABEL_22;
  }
  v12 = 0;
  while ( v12 < a2 )
  {
    v13 = 3 * v12;
    *(_QWORD *)v27 = 0;
    v14 = (Windows::COM *)*((_QWORD *)a3 + 3 * v12);
    v28 = 0;
    v29 = 0;
    v10 = Windows::COM::ConvertIn(v14, v27, v9);
    if ( v10 < 0 )
      goto LABEL_10;
    v16 = (Windows::COM *)*((_QWORD *)a3 + 3 * v12 + 1);
    *(_QWORD *)v30 = 0;
    v31 = 0;
    v32 = 0;
    v10 = Windows::COM::ConvertIn(v16, v30, v15);
    if ( v10 < 0 )
      goto LABEL_10;
    v18 = (Windows::COM *)*((_QWORD *)a3 + 3 * v12 + 2);
    *(_QWORD *)v23 = 0;
    v24 = 0;
    v25 = 0;
    v10 = Windows::COM::ConvertIn(v18, v23, v17);
    if ( v10 < 0 )
      goto LABEL_10;
    ++v12;
    *(_QWORD *)(v35[0] + 8 * v13) = v27;
    *(_QWORD *)(v35[0] + 8 * v13 + 8) = v30;
    *(_QWORD *)(v35[0] + 8 * v13 + 16) = v23;
  }
  v19 = *((_QWORD *)this + 1);
  v34 = 0;
  v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *, struct Windows::Identity::Rtl::IRtlReferenceIdentity **))(*(_QWORD *)v19 + 88LL))(
          v19,
          0,
          v35,
          &v34);
  if ( v20 >= 0 )
  {
    v11 = Windows::COM::CReferenceIdentity::Create(v34, v21, a4);
    if ( v11 >= 0 )
    {
      Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(&v34);
      v11 = 0;
      goto LABEL_22;
    }
  }
  else
  {
    v11 = ConvertNtStatusToHResult((unsigned int)v20);
  }
  Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(&v34);
LABEL_22:
  Windows::Auto<Windows::Vector<_LUNICODE_STRING const *>>::~Auto<Windows::Vector<_LUNICODE_STRING const *>>(v35);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18007a360  push    rbp
0x18007a362  push    rbx
0x18007a363  push    rsi
0x18007a364  push    rdi
0x18007a365  push    r12
0x18007a367  push    r13
0x18007a369  push    r14
0x18007a36b  push    r15
0x18007a36d  lea     rbp, [rsp-1Fh]
0x18007a372  sub     rsp, 0D8h
0x18007a379  mov     rax, cs:__security_cookie
0x18007a380  xor     rax, rsp
0x18007a383  mov     [rbp+57h+var_50], rax
0x18007a387  xor     r12d, r12d
0x18007a38a  mov     rsi, r9
0x18007a38d  mov     [rbp+57h+var_70], r12d
0x18007a391  mov     r15, r8
0x18007a394  mov     r14, rdx
0x18007a397  mov     r13, rcx
0x18007a39a  test    r9, r9
0x18007a39d  jz      short loc_18007A3A2
0x18007a39f  mov     [r9], r12
0x18007a3a2  test    r14, r14
0x18007a3a5  jz      short loc_18007A3E7
0x18007a3a7  test    r15, r15
0x18007a3aa  jnz     short loc_18007A3E7
0x18007a3ac  lea     rax, aOnecoreBaseWcp_15; "onecore\\base\\wcp\\identity\\com\\iden"...
0x18007a3b3  mov     [rbp+57h+var_B0], 0ADh
0x18007a3bb  mov     qword ptr [rbp+57h+var_C0], rax
0x18007a3bf  lea     rdx, [rbp+57h+var_C0]
0x18007a3c3  lea     rax, aWindowsComCref_0; "Windows::COM::CReferenceIdentity::Clone"
0x18007a3ca  mov     [rbp+57h+var_B8], rax
0x18007a3ce  lea     rcx, [rbp+57h+var_70]
0x18007a3d2  lea     rax, aCdeltas0Rgdelt; "(cDeltas == 0) || (rgDeltas != 0)"
0x18007a3d9  mov     [rbp+57h+var_A8], rax
0x18007a3dd  call    ?OriginateInvalidParameter@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18007a3e2  jmp     loc_18007A579
0x18007a3e7  test    rsi, rsi
0x18007a3ea  jnz     short loc_18007A427
0x18007a3ec  lea     rax, aOnecoreBaseWcp_15; "onecore\\base\\wcp\\identity\\com\\iden"...
0x18007a3f3  mov     [rbp+57h+var_B0], 0AEh
0x18007a3fb  mov     qword ptr [rbp+57h+var_C0], rax
0x18007a3ff  lea     rdx, [rbp+57h+var_C0]
0x18007a403  lea     rax, aWindowsComCref_0; "Windows::COM::CReferenceIdentity::Clone"
0x18007a40a  mov     [rbp+57h+var_B8], rax
0x18007a40e  lea     rcx, [rbp+57h+var_70]
0x18007a412  lea     rax, aNotNullCheckFa_122; "Not-null check failed: ppIReferenceIden"...
0x18007a419  mov     [rbp+57h+var_A8], rax
0x18007a41d  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18007a422  jmp     loc_18007A579
0x18007a427  lea     rcx, [rbp+57h+var_60]
0x18007a42b  mov     [rbp+57h+var_60], r12
0x18007a42f  mov     [rbp+57h+var_58], r12
0x18007a433  call    ?Allocate@?$AutoVectorBase@V?$VectorTraits@U_ATTRIBUTE@Rtl@Identity@Windows@@@Windows@@V?$Auto@U?$Vector@U_ATTRIBUTE@Rtl@Identity@Windows@@@Windows@@@2@@Windows@@QEAAPEAU_ATTRIBUTE@Rtl@Identity@2@_K@Z; Windows::AutoVectorBase<Windows::VectorTraits<Windows::Identity::Rtl::_ATTRIBUTE>,Windows::Auto<Windows::Vector<Windows::Identity::Rtl::_ATTRIBUTE>>>::Allocate(unsigned __int64)
0x18007a438  test    rax, rax
0x18007a43b  jnz     short loc_18007A483
0x18007a43d  lea     rax, aOnecoreBaseWcp_15; "onecore\\base\\wcp\\identity\\com\\iden"...
0x18007a444  mov     [rbp+57h+var_D0], 0B1h
0x18007a44c  mov     [rsp+110h+var_E0], rax
0x18007a451  lea     rdx, [rsp+110h+var_E0]
0x18007a456  lea     rax, aWindowsComCref_0; "Windows::COM::CReferenceIdentity::Clone"
0x18007a45d  mov     r8d, 8007000Eh
0x18007a463  mov     [rsp+110h+var_D8], rax
0x18007a468  lea     rcx, [rbp+57h+var_70]
0x18007a46c  lea     rax, aAttributesAllo; "Attributes.Allocate(cDeltas)"
0x18007a473  mov     [rbp+57h+var_C8], rax
0x18007a477  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18007a47c  mov     ebx, eax
0x18007a47e  jmp     loc_18007A56E
0x18007a483  mov     rbx, r12
0x18007a486  cmp     rbx, r14
0x18007a489  jnb     loc_18007A51A
0x18007a48f  lea     rdi, [rbx+rbx*2]
0x18007a493  mov     qword ptr [rbp+57h+var_A0], r12
0x18007a497  mov     rcx, [r15+rdi*8]; this
0x18007a49b  lea     rdx, [rbp+57h+var_A0]; wchar_t *
0x18007a49f  mov     [rbp+57h+var_98], r12
0x18007a4a3  mov     [rbp+57h+var_90], r12
0x18007a4a7  call    ?ConvertIn@COM@Windows@@YAJPEB_WPEAU_LUNICODE_STRING@@@Z; Windows::COM::ConvertIn(wchar_t const *,_LUNICODE_STRING *)
0x18007a4ac  test    eax, eax
0x18007a4ae  js      short loc_18007A47C
0x18007a4b0  mov     rcx, [r15+rdi*8+8]; this
0x18007a4b5  lea     rdx, [rbp+57h+var_88]; wchar_t *
0x18007a4b9  mov     qword ptr [rbp+57h+var_88], r12
0x18007a4bd  mov     [rbp+57h+var_80], r12
0x18007a4c1  mov     [rbp+57h+var_78], r12
0x18007a4c5  call    ?ConvertIn@COM@Windows@@YAJPEB_WPEAU_LUNICODE_STRING@@@Z; Windows::COM::ConvertIn(wchar_t const *,_LUNICODE_STRING *)
0x18007a4ca  test    eax, eax
0x18007a4cc  js      short loc_18007A47C
0x18007a4ce  mov     rcx, [r15+rdi*8+10h]; this
0x18007a4d3  lea     rdx, [rbp+57h+var_C0]; wchar_t *
0x18007a4d7  mov     qword ptr [rbp+57h+var_C0], r12
0x18007a4db  mov     [rbp+57h+var_B8], r12
0x18007a4df  mov     [rbp+57h+var_B0], r12
0x18007a4e3  call    ?ConvertIn@COM@Windows@@YAJPEB_WPEAU_LUNICODE_STRING@@@Z; Windows::COM::ConvertIn(wchar_t const *,_LUNICODE_STRING *)
0x18007a4e8  test    eax, eax
0x18007a4ea  js      short loc_18007A47C
0x18007a4ec  mov     rax, [rbp+57h+var_60]
0x18007a4f0  lea     rcx, [rbp+57h+var_A0]
0x18007a4f4  inc     rbx
0x18007a4f7  mov     [rax+rdi*8], rcx
0x18007a4fb  lea     rcx, [rbp+57h+var_88]
0x18007a4ff  mov     rax, [rbp+57h+var_60]
0x18007a503  mov     [rax+rdi*8+8], rcx
0x18007a508  lea     rcx, [rbp+57h+var_C0]
0x18007a50c  mov     rax, [rbp+57h+var_60]
0x18007a510  mov     [rax+rdi*8+10h], rcx
0x18007a515  jmp     loc_18007A486
0x18007a51a  mov     rcx, [r13+8]
0x18007a51e  lea     r9, [rbp+57h+var_68]
0x18007a522  mov     [rbp+57h+var_68], r12
0x18007a526  lea     r8, [rbp+57h+var_60]
0x18007a52a  xor     edx, edx
0x18007a52c  mov     rax, [rcx]
0x18007a52f  mov     rax, [rax+58h]
0x18007a533  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a538  test    eax, eax
0x18007a53a  jns     short loc_18007A550
0x18007a53c  mov     ecx, eax
0x18007a53e  call    ConvertNtStatusToHResult
0x18007a543  mov     ebx, eax
0x18007a545  lea     rcx, [rbp+57h+var_68]
0x18007a549  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x18007a54e  jmp     short loc_18007A56E
0x18007a550  mov     rcx, [rbp+57h+var_68]; struct Windows::Identity::Rtl::IRtlReferenceIdentity *
0x18007a554  mov     r8, rsi; struct IUnknown **
0x18007a557  call    ?Create@CReferenceIdentity@COM@Windows@@KAJPEAUIRtlReferenceIdentity@Rtl@Identity@3@AEBU_GUID@@PEAPEAUIUnknown@@@Z; Windows::COM::CReferenceIdentity::Create(Windows::Identity::Rtl::IRtlReferenceIdentity *,_GUID const &,IUnknown * *)
0x18007a55c  lea     rcx, [rbp+57h+var_68]
0x18007a560  mov     ebx, eax
0x18007a562  test    eax, eax
0x18007a564  js      short loc_18007A549
0x18007a566  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x18007a56b  mov     ebx, r12d
0x18007a56e  lea     rcx, [rbp+57h+var_60]
0x18007a572  call    ??1?$Auto@U?$Vector@PEBU_LUNICODE_STRING@@@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Vector<_LUNICODE_STRING const *>>::~Auto<Windows::Vector<_LUNICODE_STRING const *>>(void)
0x18007a577  mov     eax, ebx
0x18007a579  mov     rcx, [rbp+57h+var_50]
0x18007a57d  xor     rcx, rsp; StackCookie
0x18007a580  call    __security_check_cookie
0x18007a585  add     rsp, 0D8h
0x18007a58c  pop     r15
0x18007a58e  pop     r14
0x18007a590  pop     r13
0x18007a592  pop     r12
0x18007a594  pop     rdi
0x18007a595  pop     rsi
0x18007a596  pop     rbx
0x18007a597  pop     rbp
0x18007a598  retn
```
