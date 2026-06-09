# Windows::COM::CIdentityAuthority::GenerateKey<IDefinitionIdentity>(ulong,ulong,IDefinitionIdentity *,wchar_t * *)

- ea: `0x1800786bc`
- end: `0x180078888`
- name: `??$GenerateKey@UIDefinitionIdentity@@@CIdentityAuthority@COM@Windows@@IEAAJKKPEAUIDefinitionIdentity@@PEAPEA_W@Z`
- size: `460`
- prototype: `__int64 __fastcall(__int64, int, struct Windows::Identity::Rtl::IRtlDefinitionIdentity **, Windows::COM *, struct _LUNICODE_STRING *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800793e0`

## callees

- `0x180010c10`
- `0x18001f4e4`
- `0x18001f51c`
- `0x1800293a0`
- `0x18006b1e0`
- `0x1800786bc`
- `0x1800857b4`
- `0x18008597c`
- `0x180093bdc`
- `0x1800a0020`

## string_xrefs

- `0x18007870c`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x180078752`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x180078798`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x180078773`: `Not-null check failed: pICOMIdentity`
- `0x180078726`: `Windows::COM::CIdentityAuthority::GenerateKey`
- `0x180078767`: `Windows::COM::CIdentityAuthority::GenerateKey`
- `0x1800787ad`: `Windows::COM::CIdentityAuthority::GenerateKey`

## pseudocode

```c
__int64 __fastcall Windows::COM::CIdentityAuthority::GenerateKey<IDefinitionIdentity>(
        __int64 a1,
        int a2,
        struct Windows::Identity::Rtl::IRtlDefinitionIdentity **a3,
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
  result = Windows::COM::ConvertIn(a4, (struct IDefinitionIdentity *)&v16, a3);
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
                                2 * (v5 & 1u),
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
0x1800786bc  mov     [rsp-8+arg_0], rbx
0x1800786c1  mov     [rsp-8+arg_8], rdi
0x1800786c6  push    rbp
0x1800786c7  lea     rbp, [rsp-0B0h]
0x1800786cf  sub     rsp, 1B0h
0x1800786d6  mov     rax, cs:__security_cookie
0x1800786dd  xor     rax, rsp
0x1800786e0  mov     [rbp+0B0h+var_10], rax
0x1800786e7  mov     rbx, [rbp+0B0h+arg_20]
0x1800786ee  mov     edi, edx
0x1800786f0  mov     dword ptr [rsp+1B0h+var_140], 0
0x1800786f8  test    rbx, rbx
0x1800786fb  jz      short loc_180078704
0x1800786fd  mov     qword ptr [rbx], 0
0x180078704  test    edi, 0FFFFFFFEh
0x18007870a  jz      short loc_18007874D
0x18007870c  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x180078713  mov     [rsp+1B0h+var_170], 1F7h
0x18007871c  mov     [rsp+1B0h+var_180], rax
0x180078721  lea     rdx, [rsp+1B0h+var_180]
0x180078726  lea     rax, aWindowsComCide; "Windows::COM::CIdentityAuthority::Gener"...
0x18007872d  mov     [rsp+1B0h+var_178], rax
0x180078732  lea     rcx, [rsp+1B0h+var_140]
0x180078737  lea     rax, aValidFlagsChec_0; "Valid flags check failed: dwFlags"
0x18007873e  mov     [rsp+1B0h+var_168], rax
0x180078743  call    ?OriginateInvalidParameter@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180078748  jmp     loc_180078863
0x18007874d  test    r9, r9
0x180078750  jnz     short loc_180078793
0x180078752  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x180078759  mov     [rsp+1B0h+var_170], 1F8h
0x180078762  mov     [rsp+1B0h+var_180], rax
0x180078767  lea     rax, aWindowsComCide; "Windows::COM::CIdentityAuthority::Gener"...
0x18007876e  mov     [rsp+1B0h+var_178], rax
0x180078773  lea     rax, aNotNullCheckFa_41; "Not-null check failed: pICOMIdentity"
0x18007877a  lea     rdx, [rsp+1B0h+var_180]
0x18007877f  mov     [rsp+1B0h+var_168], rax
0x180078784  lea     rcx, [rsp+1B0h+var_140]
0x180078789  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18007878e  jmp     loc_180078863
0x180078793  test    rbx, rbx
0x180078796  jnz     short loc_1800787C2
0x180078798  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x18007879f  mov     [rsp+1B0h+var_170], 1F9h
0x1800787a8  mov     [rsp+1B0h+var_180], rax
0x1800787ad  lea     rax, aWindowsComCide; "Windows::COM::CIdentityAuthority::Gener"...
0x1800787b4  mov     [rsp+1B0h+var_178], rax
0x1800787b9  lea     rax, aNotNullCheckFa_118; "Not-null check failed: ppszKeyForm"
0x1800787c0  jmp     short loc_18007877A
0x1800787c2  lea     rdx, [rsp+1B0h+var_160]; struct IDefinitionIdentity *
0x1800787c7  mov     [rsp+1B0h+var_160], 0
0x1800787d0  mov     rcx, r9; this
0x1800787d3  call    ?ConvertIn@COM@Windows@@YAJPEAUIDefinitionIdentity@@PEAPEAUIRtlDefinitionIdentity@Rtl@Identity@2@@Z; Windows::COM::ConvertIn(IDefinitionIdentity *,Windows::Identity::Rtl::IRtlDefinitionIdentity * *)
0x1800787d8  test    eax, eax
0x1800787da  js      loc_180078863
0x1800787e0  lea     rdx, [rsp+1B0h+var_140]
0x1800787e5  mov     [rsp+1B0h+var_140], 0
0x1800787ee  call    RtlGetIdentityAuthority
0x1800787f3  test    eax, eax
0x1800787f5  js      short loc_180078837
0x1800787f7  mov     rcx, [rsp+1B0h+var_140]
0x1800787fc  lea     rax, [rbp+0B0h+var_130]
0x180078800  mov     r8, [rsp+1B0h+var_160]
0x180078805  lea     r9, [rsp+1B0h+var_158]
0x18007880a  mov     [rsp+1B0h+var_148], rax
0x18007880f  and     edi, 1
0x180078812  mov     [rsp+1B0h+var_158], 0
0x18007881b  mov     [rsp+1B0h+var_150], 118h
0x180078824  mov     rax, [rcx]
0x180078827  lea     edx, [rdi+rdi]
0x18007882a  mov     rax, [rax+58h]
0x18007882e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078833  test    eax, eax
0x180078835  jns     short loc_180078842
0x180078837  mov     ecx, eax
0x180078839  call    ConvertNtStatusToHResult
0x18007883e  mov     ebx, eax
0x180078840  jmp     short loc_180078857
0x180078842  mov     rdx, rbx; struct _LUNICODE_STRING *
0x180078845  lea     rcx, [rsp+1B0h+var_158]; this
0x18007884a  call    ?CopyOut@COM@Windows@@YAJPEBU_LUNICODE_STRING@@PEAPEA_W@Z; Windows::COM::CopyOut(_LUNICODE_STRING const *,wchar_t * *)
0x18007884f  mov     ebx, eax
0x180078851  test    eax, eax
0x180078853  js      short loc_180078857
0x180078855  xor     ebx, ebx
0x180078857  lea     rcx, [rsp+1B0h+var_140]
0x18007885c  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x180078861  mov     eax, ebx
0x180078863  mov     rcx, [rbp+0B0h+var_10]
0x18007886a  xor     rcx, rsp; StackCookie
0x18007886d  call    __security_check_cookie
0x180078872  lea     r11, [rsp+1B0h+var_s0]
0x18007887a  mov     rbx, [r11+10h]
0x18007887e  mov     rdi, [r11+18h]
0x180078882  mov     rsp, r11
0x180078885  pop     rbp
0x180078886  retn
```
