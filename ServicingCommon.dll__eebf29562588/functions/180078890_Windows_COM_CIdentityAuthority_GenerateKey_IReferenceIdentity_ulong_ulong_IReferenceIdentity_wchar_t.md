# Windows::COM::CIdentityAuthority::GenerateKey<IReferenceIdentity>(ulong,ulong,IReferenceIdentity *,wchar_t * *)

- ea: `0x180078890`
- end: `0x180078a60`
- name: `??$GenerateKey@UIReferenceIdentity@@@CIdentityAuthority@COM@Windows@@IEAAJKKPEAUIReferenceIdentity@@PEAPEA_W@Z`
- size: `464`
- prototype: `__int64 __fastcall(__int64, int, struct Windows::Identity::Rtl::IRtlReferenceIdentity **, Windows::COM *, struct _LUNICODE_STRING *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180079400`

## callees

- `0x180010c10`
- `0x18001f4e4`
- `0x18001f51c`
- `0x1800293a0`
- `0x18006b1e0`
- `0x180078890`
- `0x1800857b4`
- `0x180085a38`
- `0x180093bdc`
- `0x1800a0020`

## string_xrefs

- `0x1800788e0`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x180078926`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x18007896c`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x180078947`: `Not-null check failed: pICOMIdentity`
- `0x1800788fa`: `Windows::COM::CIdentityAuthority::GenerateKey`
- `0x18007893b`: `Windows::COM::CIdentityAuthority::GenerateKey`
- `0x180078981`: `Windows::COM::CIdentityAuthority::GenerateKey`

## pseudocode

```c
__int64 __fastcall Windows::COM::CIdentityAuthority::GenerateKey<IReferenceIdentity>(
        __int64 a1,
        int a2,
        struct Windows::Identity::Rtl::IRtlReferenceIdentity **a3,
        Windows::COM *a4,
        struct _LUNICODE_STRING *a5)
{
  char v5; // di
  __int64 result; // rax
  const char *v7; // rax
  __int64 v8; // rcx
  int IdentityAuthority; // eax
  wchar_t **v10; // r8
  int v11; // ebx
  const char *v12; // [rsp+30h] [rbp-D0h] BYREF
  const char *v13; // [rsp+38h] [rbp-C8h]
  __int64 v14; // [rsp+40h] [rbp-C0h]
  const char *v15; // [rsp+48h] [rbp-B8h]
  __int64 v16; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v17[3]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v18[2]; // [rsp+70h] [rbp-90h] BYREF
  char v19; // [rsp+80h] [rbp-80h] BYREF

  v5 = a2;
  LODWORD(v18[0]) = 0;
  if ( a5 )
    *(_QWORD *)a5 = 0;
  if ( (a2 & 0xFFFFFFFE) != 0 )
  {
    v14 = 503;
    v12 = "onecore\\base\\wcp\\identity\\com\\identity_authority.cpp";
    v13 = "Windows::COM::CIdentityAuthority::GenerateKey";
    v15 = "Valid flags check failed: dwFlags";
    return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter(
             v18,
             &v12);
  }
  if ( !a4 )
  {
    v14 = 504;
    v12 = "onecore\\base\\wcp\\identity\\com\\identity_authority.cpp";
    v13 = "Windows::COM::CIdentityAuthority::GenerateKey";
    v7 = "Not-null check failed: pICOMIdentity";
LABEL_7:
    v15 = v7;
    return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             v18,
             &v12);
  }
  if ( !a5 )
  {
    v14 = 505;
    v12 = "onecore\\base\\wcp\\identity\\com\\identity_authority.cpp";
    v13 = "Windows::COM::CIdentityAuthority::GenerateKey";
    v7 = "Not-null check failed: ppszKeyForm";
    goto LABEL_7;
  }
  v16 = 0;
  result = Windows::COM::ConvertIn(a4, (struct IReferenceIdentity *)&v16, a3);
  if ( (int)result >= 0 )
  {
    v18[0] = 0;
    IdentityAuthority = RtlGetIdentityAuthority(v8, v18);
    if ( IdentityAuthority >= 0
      && (v17[2] = &v19,
          v17[0] = 0,
          v17[1] = 280,
          IdentityAuthority = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD *))(*(_QWORD *)v18[0] + 88LL))(
                                v18[0],
                                2 * (v5 & 1u) + 1,
                                v16,
                                v17),
          IdentityAuthority >= 0) )
    {
      v11 = Windows::COM::CopyOut((Windows::COM *)v17, a5, v10);
      if ( v11 >= 0 )
        v11 = 0;
    }
    else
    {
      v11 = ConvertNtStatusToHResult((unsigned int)IdentityAuthority);
    }
    Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(v18);
    return (unsigned int)v11;
  }
  return result;
}

```

## disassembly

```asm
0x180078890  mov     [rsp-8+arg_0], rbx
0x180078895  mov     [rsp-8+arg_8], rdi
0x18007889a  push    rbp
0x18007889b  lea     rbp, [rsp-0B0h]
0x1800788a3  sub     rsp, 1B0h
0x1800788aa  mov     rax, cs:__security_cookie
0x1800788b1  xor     rax, rsp
0x1800788b4  mov     [rbp+0B0h+var_10], rax
0x1800788bb  mov     rbx, [rbp+0B0h+arg_20]
0x1800788c2  mov     edi, edx
0x1800788c4  mov     dword ptr [rsp+1B0h+var_140], 0
0x1800788cc  test    rbx, rbx
0x1800788cf  jz      short loc_1800788D8
0x1800788d1  mov     qword ptr [rbx], 0
0x1800788d8  test    edi, 0FFFFFFFEh
0x1800788de  jz      short loc_180078921
0x1800788e0  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x1800788e7  mov     [rsp+1B0h+var_170], 1F7h
0x1800788f0  mov     [rsp+1B0h+var_180], rax
0x1800788f5  lea     rdx, [rsp+1B0h+var_180]
0x1800788fa  lea     rax, aWindowsComCide; "Windows::COM::CIdentityAuthority::Gener"...
0x180078901  mov     [rsp+1B0h+var_178], rax
0x180078906  lea     rcx, [rsp+1B0h+var_140]
0x18007890b  lea     rax, aValidFlagsChec_0; "Valid flags check failed: dwFlags"
0x180078912  mov     [rsp+1B0h+var_168], rax
0x180078917  call    ?OriginateInvalidParameter@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18007891c  jmp     loc_180078A3B
0x180078921  test    r9, r9
0x180078924  jnz     short loc_180078967
0x180078926  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x18007892d  mov     [rsp+1B0h+var_170], 1F8h
0x180078936  mov     [rsp+1B0h+var_180], rax
0x18007893b  lea     rax, aWindowsComCide; "Windows::COM::CIdentityAuthority::Gener"...
0x180078942  mov     [rsp+1B0h+var_178], rax
0x180078947  lea     rax, aNotNullCheckFa_41; "Not-null check failed: pICOMIdentity"
0x18007894e  lea     rdx, [rsp+1B0h+var_180]
0x180078953  mov     [rsp+1B0h+var_168], rax
0x180078958  lea     rcx, [rsp+1B0h+var_140]
0x18007895d  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180078962  jmp     loc_180078A3B
0x180078967  test    rbx, rbx
0x18007896a  jnz     short loc_180078996
0x18007896c  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x180078973  mov     [rsp+1B0h+var_170], 1F9h
0x18007897c  mov     [rsp+1B0h+var_180], rax
0x180078981  lea     rax, aWindowsComCide; "Windows::COM::CIdentityAuthority::Gener"...
0x180078988  mov     [rsp+1B0h+var_178], rax
0x18007898d  lea     rax, aNotNullCheckFa_118; "Not-null check failed: ppszKeyForm"
0x180078994  jmp     short loc_18007894E
0x180078996  lea     rdx, [rsp+1B0h+var_160]; struct IReferenceIdentity *
0x18007899b  mov     [rsp+1B0h+var_160], 0
0x1800789a4  mov     rcx, r9; this
0x1800789a7  call    ?ConvertIn@COM@Windows@@YAJPEAUIReferenceIdentity@@PEAPEAUIRtlReferenceIdentity@Rtl@Identity@2@@Z; Windows::COM::ConvertIn(IReferenceIdentity *,Windows::Identity::Rtl::IRtlReferenceIdentity * *)
0x1800789ac  test    eax, eax
0x1800789ae  js      loc_180078A3B
0x1800789b4  lea     rdx, [rsp+1B0h+var_140]
0x1800789b9  mov     [rsp+1B0h+var_140], 0
0x1800789c2  call    RtlGetIdentityAuthority
0x1800789c7  test    eax, eax
0x1800789c9  js      short loc_180078A0F
0x1800789cb  mov     rcx, [rsp+1B0h+var_140]
0x1800789d0  lea     rax, [rbp+0B0h+var_130]
0x1800789d4  mov     r8, [rsp+1B0h+var_160]
0x1800789d9  lea     r9, [rsp+1B0h+var_158]
0x1800789de  mov     [rsp+1B0h+var_148], rax
0x1800789e3  and     edi, 1
0x1800789e6  mov     [rsp+1B0h+var_158], 0
0x1800789ef  mov     [rsp+1B0h+var_150], 118h
0x1800789f8  mov     rax, [rcx]
0x1800789fb  lea     edx, ds:1[rdi*2]
0x180078a02  mov     rax, [rax+58h]
0x180078a06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078a0b  test    eax, eax
0x180078a0d  jns     short loc_180078A1A
0x180078a0f  mov     ecx, eax
0x180078a11  call    ConvertNtStatusToHResult
0x180078a16  mov     ebx, eax
0x180078a18  jmp     short loc_180078A2F
0x180078a1a  mov     rdx, rbx; struct _LUNICODE_STRING *
0x180078a1d  lea     rcx, [rsp+1B0h+var_158]; this
0x180078a22  call    ?CopyOut@COM@Windows@@YAJPEBU_LUNICODE_STRING@@PEAPEA_W@Z; Windows::COM::CopyOut(_LUNICODE_STRING const *,wchar_t * *)
0x180078a27  mov     ebx, eax
0x180078a29  test    eax, eax
0x180078a2b  js      short loc_180078A2F
0x180078a2d  xor     ebx, ebx
0x180078a2f  lea     rcx, [rsp+1B0h+var_140]
0x180078a34  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x180078a39  mov     eax, ebx
0x180078a3b  mov     rcx, [rbp+0B0h+var_10]
0x180078a42  xor     rcx, rsp; StackCookie
0x180078a45  call    __security_check_cookie
0x180078a4a  lea     r11, [rsp+1B0h+var_s0]
0x180078a52  mov     rbx, [r11+10h]
0x180078a56  mov     rdi, [r11+18h]
0x180078a5a  mov     rsp, r11
0x180078a5d  pop     rbp
0x180078a5e  retn
```
