# Windows::COM::CReferenceIdentity::Clone(unsigned __int64,_IDENTITY_ATTRIBUTE const * const,IReferenceIdentity * *)

- ea: `0x18007a660`
- end: `0x18007a89e`
- name: `?Clone@CReferenceIdentity@COM@Windows@@MEAAJ_KQEBU_IDENTITY_ATTRIBUTE@@PEAPEAUIReferenceIdentity@@@Z`
- size: `574`
- prototype: `int(Windows::COM::CReferenceIdentity *__hidden this, unsigned __int64, const struct _IDENTITY_ATTRIBUTE *const, struct IReferenceIdentity **)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x18000f0ec`
- `0x1800105c4`
- `0x180010c10`
- `0x18001f4e4`
- `0x18001f51c`
- `0x18001f604`
- `0x1800293a0`
- `0x18006b1e0`
- `0x18007a660`
- `0x18007a8a4`
- `0x180085af4`
- `0x1800a0020`

## string_xrefs

- `0x18007a6ac`: `onecore\base\wcp\identity\com\identity_ref.cpp`
- `0x18007a6ec`: `onecore\base\wcp\identity\com\identity_ref.cpp`
- `0x18007a73d`: `onecore\base\wcp\identity\com\identity_ref.cpp`
- `0x18007a6c3`: `Windows::COM::CReferenceIdentity::Clone`
- `0x18007a703`: `Windows::COM::CReferenceIdentity::Clone`
- `0x18007a756`: `Windows::COM::CReferenceIdentity::Clone`

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
  unsigned __int64 i; // r14
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
    goto LABEL_21;
  }
  for ( i = 0; i < a2; *(_QWORD *)(v35[0] + 8 * v13 + 16) = v23 )
  {
    v13 = 3 * i;
    *(_QWORD *)v27 = 0;
    v14 = (Windows::COM *)*((_QWORD *)a3 + 3 * i);
    v28 = 0;
    v29 = 0;
    v10 = Windows::COM::ConvertIn(v14, v27, v9);
    if ( v10 < 0 )
      goto LABEL_10;
    v16 = (Windows::COM *)*((_QWORD *)a3 + 3 * i + 1);
    *(_QWORD *)v30 = 0;
    v31 = 0;
    v32 = 0;
    v10 = Windows::COM::ConvertIn(v16, v30, v15);
    if ( v10 < 0 )
      goto LABEL_10;
    v18 = (Windows::COM *)*((_QWORD *)a3 + 3 * i + 2);
    *(_QWORD *)v23 = 0;
    v24 = 0;
    v25 = 0;
    v10 = Windows::COM::ConvertIn(v18, v23, v17);
    if ( v10 < 0 )
      goto LABEL_10;
    ++i;
    *(_QWORD *)(v35[0] + 8 * v13) = v27;
    *(_QWORD *)(v35[0] + 8 * v13 + 8) = v30;
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
      goto LABEL_21;
    }
  }
  else
  {
    v11 = ConvertNtStatusToHResult((unsigned int)v20);
  }
  Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(&v34);
LABEL_21:
  Windows::Auto<Windows::Vector<_LUNICODE_STRING const *>>::~Auto<Windows::Vector<_LUNICODE_STRING const *>>(v35);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18007a660  push    rbp
0x18007a662  push    rbx
0x18007a663  push    rsi
0x18007a664  push    rdi
0x18007a665  push    r12
0x18007a667  push    r13
0x18007a669  push    r14
0x18007a66b  push    r15
0x18007a66d  lea     rbp, [rsp-1Fh]
0x18007a672  sub     rsp, 0D8h
0x18007a679  mov     rax, cs:__security_cookie
0x18007a680  xor     rax, rsp
0x18007a683  mov     [rbp+57h+var_50], rax
0x18007a687  xor     r12d, r12d
0x18007a68a  mov     rsi, r9
0x18007a68d  mov     [rbp+57h+var_70], r12d
0x18007a691  mov     r15, r8
0x18007a694  mov     rbx, rdx
0x18007a697  mov     r13, rcx
0x18007a69a  test    r9, r9
0x18007a69d  jz      short loc_18007A6A2
0x18007a69f  mov     [r9], r12
0x18007a6a2  test    rbx, rbx
0x18007a6a5  jz      short loc_18007A6E7
0x18007a6a7  test    r15, r15
0x18007a6aa  jnz     short loc_18007A6E7
0x18007a6ac  lea     rax, aOnecoreBaseWcp_15; "onecore\\base\\wcp\\identity\\com\\iden"...
0x18007a6b3  mov     [rbp+57h+var_B0], 0ADh
0x18007a6bb  mov     qword ptr [rbp+57h+var_C0], rax
0x18007a6bf  lea     rdx, [rbp+57h+var_C0]
0x18007a6c3  lea     rax, aWindowsComCref_0; "Windows::COM::CReferenceIdentity::Clone"
0x18007a6ca  mov     [rbp+57h+var_B8], rax
0x18007a6ce  lea     rcx, [rbp+57h+var_70]
0x18007a6d2  lea     rax, aCdeltas0Rgdelt; "(cDeltas == 0) || (rgDeltas != 0)"
0x18007a6d9  mov     [rbp+57h+var_A8], rax
0x18007a6dd  call    ?OriginateInvalidParameter@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18007a6e2  jmp     loc_18007A87D
0x18007a6e7  test    rsi, rsi
0x18007a6ea  jnz     short loc_18007A727
0x18007a6ec  lea     rax, aOnecoreBaseWcp_15; "onecore\\base\\wcp\\identity\\com\\iden"...
0x18007a6f3  mov     [rbp+57h+var_B0], 0AEh
0x18007a6fb  mov     qword ptr [rbp+57h+var_C0], rax
0x18007a6ff  lea     rdx, [rbp+57h+var_C0]
0x18007a703  lea     rax, aWindowsComCref_0; "Windows::COM::CReferenceIdentity::Clone"
0x18007a70a  mov     [rbp+57h+var_B8], rax
0x18007a70e  lea     rcx, [rbp+57h+var_70]
0x18007a712  lea     rax, aNotNullCheckFa_122; "Not-null check failed: ppIReferenceIden"...
0x18007a719  mov     [rbp+57h+var_A8], rax
0x18007a71d  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18007a722  jmp     loc_18007A87D
0x18007a727  lea     rcx, [rbp+57h+var_60]
0x18007a72b  mov     [rbp+57h+var_60], r12
0x18007a72f  mov     [rbp+57h+var_58], r12
0x18007a733  call    ?Allocate@?$AutoVectorBase@V?$VectorTraits@U_ATTRIBUTE@Rtl@Identity@Windows@@@Windows@@V?$Auto@U?$Vector@U_ATTRIBUTE@Rtl@Identity@Windows@@@Windows@@@2@@Windows@@QEAAPEAU_ATTRIBUTE@Rtl@Identity@2@_K@Z; Windows::AutoVectorBase<Windows::VectorTraits<Windows::Identity::Rtl::_ATTRIBUTE>,Windows::Auto<Windows::Vector<Windows::Identity::Rtl::_ATTRIBUTE>>>::Allocate(unsigned __int64)
0x18007a738  test    rax, rax
0x18007a73b  jnz     short loc_18007A783
0x18007a73d  lea     rax, aOnecoreBaseWcp_15; "onecore\\base\\wcp\\identity\\com\\iden"...
0x18007a744  mov     [rbp+57h+var_D0], 0B1h
0x18007a74c  mov     [rsp+110h+var_E0], rax
0x18007a751  lea     rdx, [rsp+110h+var_E0]
0x18007a756  lea     rax, aWindowsComCref_0; "Windows::COM::CReferenceIdentity::Clone"
0x18007a75d  mov     r8d, 8007000Eh
0x18007a763  mov     [rsp+110h+var_D8], rax
0x18007a768  lea     rcx, [rbp+57h+var_70]
0x18007a76c  lea     rax, aAttributesAllo; "Attributes.Allocate(cDeltas)"
0x18007a773  mov     [rbp+57h+var_C8], rax
0x18007a777  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18007a77c  mov     ebx, eax
0x18007a77e  jmp     loc_18007A872
0x18007a783  mov     r14, r12
0x18007a786  test    rbx, rbx
0x18007a789  jz      loc_18007A81E
0x18007a78f  lea     rdi, [r14+r14*2]
0x18007a793  mov     qword ptr [rbp+57h+var_A0], r12
0x18007a797  mov     rcx, [r15+rdi*8]; this
0x18007a79b  lea     rdx, [rbp+57h+var_A0]; wchar_t *
0x18007a79f  mov     [rbp+57h+var_98], r12
0x18007a7a3  mov     [rbp+57h+var_90], r12
0x18007a7a7  call    ?ConvertIn@COM@Windows@@YAJPEB_WPEAU_LUNICODE_STRING@@@Z; Windows::COM::ConvertIn(wchar_t const *,_LUNICODE_STRING *)
0x18007a7ac  test    eax, eax
0x18007a7ae  js      short loc_18007A77C
0x18007a7b0  mov     rcx, [r15+rdi*8+8]; this
0x18007a7b5  lea     rdx, [rbp+57h+var_88]; wchar_t *
0x18007a7b9  mov     qword ptr [rbp+57h+var_88], r12
0x18007a7bd  mov     [rbp+57h+var_80], r12
0x18007a7c1  mov     [rbp+57h+var_78], r12
0x18007a7c5  call    ?ConvertIn@COM@Windows@@YAJPEB_WPEAU_LUNICODE_STRING@@@Z; Windows::COM::ConvertIn(wchar_t const *,_LUNICODE_STRING *)
0x18007a7ca  test    eax, eax
0x18007a7cc  js      short loc_18007A77C
0x18007a7ce  mov     rcx, [r15+rdi*8+10h]; this
0x18007a7d3  lea     rdx, [rbp+57h+var_C0]; wchar_t *
0x18007a7d7  mov     qword ptr [rbp+57h+var_C0], r12
0x18007a7db  mov     [rbp+57h+var_B8], r12
0x18007a7df  mov     [rbp+57h+var_B0], r12
0x18007a7e3  call    ?ConvertIn@COM@Windows@@YAJPEB_WPEAU_LUNICODE_STRING@@@Z; Windows::COM::ConvertIn(wchar_t const *,_LUNICODE_STRING *)
0x18007a7e8  test    eax, eax
0x18007a7ea  js      short loc_18007A77C
0x18007a7ec  mov     rax, [rbp+57h+var_60]
0x18007a7f0  lea     rcx, [rbp+57h+var_A0]
0x18007a7f4  inc     r14
0x18007a7f7  mov     [rax+rdi*8], rcx
0x18007a7fb  lea     rcx, [rbp+57h+var_88]
0x18007a7ff  mov     rax, [rbp+57h+var_60]
0x18007a803  mov     [rax+rdi*8+8], rcx
0x18007a808  lea     rcx, [rbp+57h+var_C0]
0x18007a80c  mov     rax, [rbp+57h+var_60]
0x18007a810  mov     [rax+rdi*8+10h], rcx
0x18007a815  cmp     r14, rbx
0x18007a818  jb      loc_18007A78F
0x18007a81e  mov     rcx, [r13+8]
0x18007a822  lea     r9, [rbp+57h+var_68]
0x18007a826  mov     [rbp+57h+var_68], r12
0x18007a82a  lea     r8, [rbp+57h+var_60]
0x18007a82e  xor     edx, edx
0x18007a830  mov     rax, [rcx]
0x18007a833  mov     rax, [rax+58h]
0x18007a837  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a83c  test    eax, eax
0x18007a83e  jns     short loc_18007A854
0x18007a840  mov     ecx, eax
0x18007a842  call    ConvertNtStatusToHResult
0x18007a847  mov     ebx, eax
0x18007a849  lea     rcx, [rbp+57h+var_68]
0x18007a84d  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x18007a852  jmp     short loc_18007A872
0x18007a854  mov     rcx, [rbp+57h+var_68]; struct Windows::Identity::Rtl::IRtlReferenceIdentity *
0x18007a858  mov     r8, rsi; struct IUnknown **
0x18007a85b  call    ?Create@CReferenceIdentity@COM@Windows@@KAJPEAUIRtlReferenceIdentity@Rtl@Identity@3@AEBU_GUID@@PEAPEAUIUnknown@@@Z; Windows::COM::CReferenceIdentity::Create(Windows::Identity::Rtl::IRtlReferenceIdentity *,_GUID const &,IUnknown * *)
0x18007a860  lea     rcx, [rbp+57h+var_68]
0x18007a864  mov     ebx, eax
0x18007a866  test    eax, eax
0x18007a868  js      short loc_18007A84D
0x18007a86a  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x18007a86f  mov     ebx, r12d
0x18007a872  lea     rcx, [rbp+57h+var_60]
0x18007a876  call    ??1?$Auto@U?$Vector@PEBU_LUNICODE_STRING@@@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Vector<_LUNICODE_STRING const *>>::~Auto<Windows::Vector<_LUNICODE_STRING const *>>(void)
0x18007a87b  mov     eax, ebx
0x18007a87d  mov     rcx, [rbp+57h+var_50]
0x18007a881  xor     rcx, rsp; StackCookie
0x18007a884  call    __security_check_cookie
0x18007a889  add     rsp, 0D8h
0x18007a890  pop     r15
0x18007a892  pop     r14
0x18007a894  pop     r13
0x18007a896  pop     r12
0x18007a898  pop     rdi
0x18007a899  pop     rsi
0x18007a89a  pop     rbx
0x18007a89b  pop     rbp
0x18007a89c  retn
```
