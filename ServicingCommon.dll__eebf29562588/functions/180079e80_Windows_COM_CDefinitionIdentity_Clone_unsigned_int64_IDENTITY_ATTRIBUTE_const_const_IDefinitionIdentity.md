# Windows::COM::CDefinitionIdentity::Clone(unsigned __int64,_IDENTITY_ATTRIBUTE const * const,IDefinitionIdentity * *)

- ea: `0x180079e80`
- end: `0x18007a0be`
- name: `?Clone@CDefinitionIdentity@COM@Windows@@MEAAJ_KQEBU_IDENTITY_ATTRIBUTE@@PEAPEAUIDefinitionIdentity@@@Z`
- size: `574`
- prototype: `int(Windows::COM::CDefinitionIdentity *__hidden this, unsigned __int64, const struct _IDENTITY_ATTRIBUTE *const, struct IDefinitionIdentity **)`
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
- `0x180079e80`
- `0x18007a0c4`
- `0x180085af4`
- `0x1800a0020`

## string_xrefs

- `0x180079ecc`: `onecore\base\wcp\identity\com\identity_def.cpp`
- `0x180079f0c`: `onecore\base\wcp\identity\com\identity_def.cpp`
- `0x180079f5d`: `onecore\base\wcp\identity\com\identity_def.cpp`
- `0x180079ee3`: `Windows::COM::CDefinitionIdentity::Clone`
- `0x180079f23`: `Windows::COM::CDefinitionIdentity::Clone`
- `0x180079f76`: `Windows::COM::CDefinitionIdentity::Clone`

## pseudocode

```c
__int64 __fastcall Windows::COM::CDefinitionIdentity::Clone(
        Windows::COM::CDefinitionIdentity *this,
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
  struct Windows::Identity::Rtl::IRtlDefinitionIdentity *v34; // [rsp+A8h] [rbp-11h] BYREF
  _QWORD v35[2]; // [rsp+B0h] [rbp-9h] BYREF

  v33 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a2 && !a3 )
  {
    v25 = 173;
    *(_QWORD *)v23 = "onecore\\base\\wcp\\identity\\com\\identity_def.cpp";
    v24 = "Windows::COM::CDefinitionIdentity::Clone";
    v26 = "(cDeltas == 0) || (rgDeltas != 0)";
    return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter(
             &v33,
             v23);
  }
  if ( !a4 )
  {
    v25 = 174;
    *(_QWORD *)v23 = "onecore\\base\\wcp\\identity\\com\\identity_def.cpp";
    v24 = "Windows::COM::CDefinitionIdentity::Clone";
    v26 = "Not-null check failed: ppIDefinitionIdentity";
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
    v22[0] = "onecore\\base\\wcp\\identity\\com\\identity_def.cpp";
    v22[1] = "Windows::COM::CDefinitionIdentity::Clone";
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
  v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *, struct Windows::Identity::Rtl::IRtlDefinitionIdentity **))(*(_QWORD *)v19 + 88LL))(
          v19,
          0,
          v35,
          &v34);
  if ( v20 >= 0 )
  {
    v11 = Windows::COM::CDefinitionIdentity::Create(v34, v21, a4);
    if ( v11 >= 0 )
    {
      Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>((__int64 (__fastcall ****)(_QWORD))&v34);
      v11 = 0;
      goto LABEL_21;
    }
  }
  else
  {
    v11 = ConvertNtStatusToHResult((unsigned int)v20);
  }
  Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>((__int64 (__fastcall ****)(_QWORD))&v34);
LABEL_21:
  Windows::Auto<Windows::Vector<_LUNICODE_STRING const *>>::~Auto<Windows::Vector<_LUNICODE_STRING const *>>(v35);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180079e80  push    rbp
0x180079e82  push    rbx
0x180079e83  push    rsi
0x180079e84  push    rdi
0x180079e85  push    r12
0x180079e87  push    r13
0x180079e89  push    r14
0x180079e8b  push    r15
0x180079e8d  lea     rbp, [rsp-1Fh]
0x180079e92  sub     rsp, 0D8h
0x180079e99  mov     rax, cs:__security_cookie
0x180079ea0  xor     rax, rsp
0x180079ea3  mov     [rbp+57h+var_50], rax
0x180079ea7  xor     r12d, r12d
0x180079eaa  mov     rsi, r9
0x180079ead  mov     [rbp+57h+var_70], r12d
0x180079eb1  mov     r15, r8
0x180079eb4  mov     rbx, rdx
0x180079eb7  mov     r13, rcx
0x180079eba  test    r9, r9
0x180079ebd  jz      short loc_180079EC2
0x180079ebf  mov     [r9], r12
0x180079ec2  test    rbx, rbx
0x180079ec5  jz      short loc_180079F07
0x180079ec7  test    r15, r15
0x180079eca  jnz     short loc_180079F07
0x180079ecc  lea     rax, aOnecoreBaseWcp_5; "onecore\\base\\wcp\\identity\\com\\iden"...
0x180079ed3  mov     [rbp+57h+var_B0], 0ADh
0x180079edb  mov     qword ptr [rbp+57h+var_C0], rax
0x180079edf  lea     rdx, [rbp+57h+var_C0]
0x180079ee3  lea     rax, aWindowsComCdef_3; "Windows::COM::CDefinitionIdentity::Clon"...
0x180079eea  mov     [rbp+57h+var_B8], rax
0x180079eee  lea     rcx, [rbp+57h+var_70]
0x180079ef2  lea     rax, aCdeltas0Rgdelt; "(cDeltas == 0) || (rgDeltas != 0)"
0x180079ef9  mov     [rbp+57h+var_A8], rax
0x180079efd  call    ?OriginateInvalidParameter@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180079f02  jmp     loc_18007A09D
0x180079f07  test    rsi, rsi
0x180079f0a  jnz     short loc_180079F47
0x180079f0c  lea     rax, aOnecoreBaseWcp_5; "onecore\\base\\wcp\\identity\\com\\iden"...
0x180079f13  mov     [rbp+57h+var_B0], 0AEh
0x180079f1b  mov     qword ptr [rbp+57h+var_C0], rax
0x180079f1f  lea     rdx, [rbp+57h+var_C0]
0x180079f23  lea     rax, aWindowsComCdef_3; "Windows::COM::CDefinitionIdentity::Clon"...
0x180079f2a  mov     [rbp+57h+var_B8], rax
0x180079f2e  lea     rcx, [rbp+57h+var_70]
0x180079f32  lea     rax, aNotNullCheckFa_129; "Not-null check failed: ppIDefinitionIde"...
0x180079f39  mov     [rbp+57h+var_A8], rax
0x180079f3d  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180079f42  jmp     loc_18007A09D
0x180079f47  lea     rcx, [rbp+57h+var_60]
0x180079f4b  mov     [rbp+57h+var_60], r12
0x180079f4f  mov     [rbp+57h+var_58], r12
0x180079f53  call    ?Allocate@?$AutoVectorBase@V?$VectorTraits@U_ATTRIBUTE@Rtl@Identity@Windows@@@Windows@@V?$Auto@U?$Vector@U_ATTRIBUTE@Rtl@Identity@Windows@@@Windows@@@2@@Windows@@QEAAPEAU_ATTRIBUTE@Rtl@Identity@2@_K@Z; Windows::AutoVectorBase<Windows::VectorTraits<Windows::Identity::Rtl::_ATTRIBUTE>,Windows::Auto<Windows::Vector<Windows::Identity::Rtl::_ATTRIBUTE>>>::Allocate(unsigned __int64)
0x180079f58  test    rax, rax
0x180079f5b  jnz     short loc_180079FA3
0x180079f5d  lea     rax, aOnecoreBaseWcp_5; "onecore\\base\\wcp\\identity\\com\\iden"...
0x180079f64  mov     [rbp+57h+var_D0], 0B1h
0x180079f6c  mov     [rsp+110h+var_E0], rax
0x180079f71  lea     rdx, [rsp+110h+var_E0]
0x180079f76  lea     rax, aWindowsComCdef_3; "Windows::COM::CDefinitionIdentity::Clon"...
0x180079f7d  mov     r8d, 8007000Eh
0x180079f83  mov     [rsp+110h+var_D8], rax
0x180079f88  lea     rcx, [rbp+57h+var_70]
0x180079f8c  lea     rax, aAttributesAllo; "Attributes.Allocate(cDeltas)"
0x180079f93  mov     [rbp+57h+var_C8], rax
0x180079f97  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180079f9c  mov     ebx, eax
0x180079f9e  jmp     loc_18007A092
0x180079fa3  mov     r14, r12
0x180079fa6  test    rbx, rbx
0x180079fa9  jz      loc_18007A03E
0x180079faf  lea     rdi, [r14+r14*2]
0x180079fb3  mov     qword ptr [rbp+57h+var_A0], r12
0x180079fb7  mov     rcx, [r15+rdi*8]; this
0x180079fbb  lea     rdx, [rbp+57h+var_A0]; wchar_t *
0x180079fbf  mov     [rbp+57h+var_98], r12
0x180079fc3  mov     [rbp+57h+var_90], r12
0x180079fc7  call    ?ConvertIn@COM@Windows@@YAJPEB_WPEAU_LUNICODE_STRING@@@Z; Windows::COM::ConvertIn(wchar_t const *,_LUNICODE_STRING *)
0x180079fcc  test    eax, eax
0x180079fce  js      short loc_180079F9C
0x180079fd0  mov     rcx, [r15+rdi*8+8]; this
0x180079fd5  lea     rdx, [rbp+57h+var_88]; wchar_t *
0x180079fd9  mov     qword ptr [rbp+57h+var_88], r12
0x180079fdd  mov     [rbp+57h+var_80], r12
0x180079fe1  mov     [rbp+57h+var_78], r12
0x180079fe5  call    ?ConvertIn@COM@Windows@@YAJPEB_WPEAU_LUNICODE_STRING@@@Z; Windows::COM::ConvertIn(wchar_t const *,_LUNICODE_STRING *)
0x180079fea  test    eax, eax
0x180079fec  js      short loc_180079F9C
0x180079fee  mov     rcx, [r15+rdi*8+10h]; this
0x180079ff3  lea     rdx, [rbp+57h+var_C0]; wchar_t *
0x180079ff7  mov     qword ptr [rbp+57h+var_C0], r12
0x180079ffb  mov     [rbp+57h+var_B8], r12
0x180079fff  mov     [rbp+57h+var_B0], r12
0x18007a003  call    ?ConvertIn@COM@Windows@@YAJPEB_WPEAU_LUNICODE_STRING@@@Z; Windows::COM::ConvertIn(wchar_t const *,_LUNICODE_STRING *)
0x18007a008  test    eax, eax
0x18007a00a  js      short loc_180079F9C
0x18007a00c  mov     rax, [rbp+57h+var_60]
0x18007a010  lea     rcx, [rbp+57h+var_A0]
0x18007a014  inc     r14
0x18007a017  mov     [rax+rdi*8], rcx
0x18007a01b  lea     rcx, [rbp+57h+var_88]
0x18007a01f  mov     rax, [rbp+57h+var_60]
0x18007a023  mov     [rax+rdi*8+8], rcx
0x18007a028  lea     rcx, [rbp+57h+var_C0]
0x18007a02c  mov     rax, [rbp+57h+var_60]
0x18007a030  mov     [rax+rdi*8+10h], rcx
0x18007a035  cmp     r14, rbx
0x18007a038  jb      loc_180079FAF
0x18007a03e  mov     rcx, [r13+8]
0x18007a042  lea     r9, [rbp+57h+var_68]
0x18007a046  mov     [rbp+57h+var_68], r12
0x18007a04a  lea     r8, [rbp+57h+var_60]
0x18007a04e  xor     edx, edx
0x18007a050  mov     rax, [rcx]
0x18007a053  mov     rax, [rax+58h]
0x18007a057  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a05c  test    eax, eax
0x18007a05e  jns     short loc_18007A074
0x18007a060  mov     ecx, eax
0x18007a062  call    ConvertNtStatusToHResult
0x18007a067  mov     ebx, eax
0x18007a069  lea     rcx, [rbp+57h+var_68]
0x18007a06d  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x18007a072  jmp     short loc_18007A092
0x18007a074  mov     rcx, [rbp+57h+var_68]; struct Windows::Identity::Rtl::IRtlDefinitionIdentity *
0x18007a078  mov     r8, rsi; struct IUnknown **
0x18007a07b  call    ?Create@CDefinitionIdentity@COM@Windows@@KAJPEAUIRtlDefinitionIdentity@Rtl@Identity@3@AEBU_GUID@@PEAPEAUIUnknown@@@Z; Windows::COM::CDefinitionIdentity::Create(Windows::Identity::Rtl::IRtlDefinitionIdentity *,_GUID const &,IUnknown * *)
0x18007a080  lea     rcx, [rbp+57h+var_68]
0x18007a084  mov     ebx, eax
0x18007a086  test    eax, eax
0x18007a088  js      short loc_18007A06D
0x18007a08a  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x18007a08f  mov     ebx, r12d
0x18007a092  lea     rcx, [rbp+57h+var_60]
0x18007a096  call    ??1?$Auto@U?$Vector@PEBU_LUNICODE_STRING@@@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Vector<_LUNICODE_STRING const *>>::~Auto<Windows::Vector<_LUNICODE_STRING const *>>(void)
0x18007a09b  mov     eax, ebx
0x18007a09d  mov     rcx, [rbp+57h+var_50]
0x18007a0a1  xor     rcx, rsp; StackCookie
0x18007a0a4  call    __security_check_cookie
0x18007a0a9  add     rsp, 0D8h
0x18007a0b0  pop     r15
0x18007a0b2  pop     r14
0x18007a0b4  pop     r13
0x18007a0b6  pop     r12
0x18007a0b8  pop     rdi
0x18007a0b9  pop     rsi
0x18007a0ba  pop     rbx
0x18007a0bb  pop     rbp
0x18007a0bc  retn
```
