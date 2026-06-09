# Windows::COM::CIdentityAuthority::Hash<IDefinitionIdentity>(ulong,IDefinitionIdentity *,unsigned __int64 *)

- ea: `0x1800786f8`
- end: `0x180078856`
- name: `??$Hash@UIDefinitionIdentity@@@CIdentityAuthority@COM@Windows@@IEAAJKPEAUIDefinitionIdentity@@PEA_K@Z`
- size: `350`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800790c0`

## callees

- `0x18001af00`
- `0x18002175c`
- `0x180021794`
- `0x18002d2b0`
- `0x18006b3e0`
- `0x1800786f8`
- `0x180084a10`
- `0x18009255c`
- `0x18009e020`

## string_xrefs

- `0x18007872d`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x18007876d`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x1800787ad`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x18007878b`: `Not-null check failed: pICOMIdentity`
- `0x180078744`: `Windows::COM::CIdentityAuthority::Hash`
- `0x180078780`: `Windows::COM::CIdentityAuthority::Hash`
- `0x1800787c0`: `Windows::COM::CIdentityAuthority::Hash`

## pseudocode

```c
__int64 __fastcall Windows::COM::CIdentityAuthority::Hash<IDefinitionIdentity>(
        __int64 a1,
        int a2,
        Windows::COM *a3,
        _QWORD *a4)
{
  __int64 result; // rax
  const char *v6; // rax
  __int64 v7; // rcx
  int IdentityAuthority; // eax
  unsigned int v9; // ebx
  const char *v10; // [rsp+30h] [rbp-40h] BYREF
  const char *v11; // [rsp+38h] [rbp-38h]
  __int64 v12; // [rsp+40h] [rbp-30h]
  const char *v13; // [rsp+48h] [rbp-28h]
  __int64 v14; // [rsp+50h] [rbp-20h] BYREF
  __int64 v15; // [rsp+58h] [rbp-18h] BYREF

  LODWORD(v15) = 0;
  if ( a4 )
    *a4 = 0;
  if ( a2 )
  {
    v12 = 468;
    v10 = "onecore\\base\\wcp\\identity\\com\\identity_authority.cpp";
    v11 = "Windows::COM::CIdentityAuthority::Hash";
    v13 = "Valid flags check failed: dwFlags";
    return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter(
             &v15,
             &v10,
             a3);
  }
  if ( !a3 )
  {
    v12 = 469;
    v10 = "onecore\\base\\wcp\\identity\\com\\identity_authority.cpp";
    v11 = "Windows::COM::CIdentityAuthority::Hash";
    v6 = "Not-null check failed: pICOMIdentity";
LABEL_7:
    v13 = v6;
    return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v15,
             &v10);
  }
  if ( !a4 )
  {
    v12 = 470;
    v10 = "onecore\\base\\wcp\\identity\\com\\identity_authority.cpp";
    v11 = "Windows::COM::CIdentityAuthority::Hash";
    v6 = "Not-null check failed: pPseudoKey";
    goto LABEL_7;
  }
  v14 = 0;
  result = Windows::COM::ConvertIn(
             a3,
             (struct IDefinitionIdentity *)&v14,
             (struct Windows::Identity::Rtl::IRtlDefinitionIdentity **)a3);
  if ( (int)result >= 0 )
  {
    v15 = 0;
    IdentityAuthority = RtlGetIdentityAuthority(v7, &v15);
    if ( IdentityAuthority >= 0
      && (IdentityAuthority = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64, _QWORD *))(*(_QWORD *)v15 + 80LL))(
                                v15,
                                0,
                                0,
                                v14,
                                a4),
          IdentityAuthority >= 0) )
    {
      v9 = 0;
    }
    else
    {
      v9 = ConvertNtStatusToHResult((unsigned int)IdentityAuthority);
    }
    Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(&v15);
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x1800786f8  mov     [rsp-8+arg_0], rbx
0x1800786fd  push    rbp
0x1800786fe  mov     rbp, rsp
0x180078701  sub     rsp, 70h
0x180078705  mov     rax, cs:__security_cookie
0x18007870c  xor     rax, rsp
0x18007870f  mov     [rbp+var_10], rax
0x180078713  mov     dword ptr [rbp+var_18], 0
0x18007871a  mov     rbx, r9
0x18007871d  test    r9, r9
0x180078720  jz      short loc_180078729
0x180078722  mov     qword ptr [r9], 0
0x180078729  test    edx, edx
0x18007872b  jz      short loc_180078768
0x18007872d  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x180078734  mov     [rbp+var_30], 1D4h
0x18007873c  mov     [rbp+var_40], rax
0x180078740  lea     rdx, [rbp+var_40]
0x180078744  lea     rax, aWindowsComCide_2; "Windows::COM::CIdentityAuthority::Hash"
0x18007874b  mov     [rbp+var_38], rax
0x18007874f  lea     rcx, [rbp+var_18]
0x180078753  lea     rax, aValidFlagsChec_0; "Valid flags check failed: dwFlags"
0x18007875a  mov     [rbp+var_28], rax
0x18007875e  call    ?OriginateInvalidParameter@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180078763  jmp     loc_18007883B
0x180078768  test    r8, r8
0x18007876b  jnz     short loc_1800787A8
0x18007876d  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x180078774  mov     [rbp+var_30], 1D5h
0x18007877c  mov     [rbp+var_40], rax
0x180078780  lea     rax, aWindowsComCide_2; "Windows::COM::CIdentityAuthority::Hash"
0x180078787  mov     [rbp+var_38], rax
0x18007878b  lea     rax, aNotNullCheckFa_41; "Not-null check failed: pICOMIdentity"
0x180078792  lea     rdx, [rbp+var_40]
0x180078796  mov     [rbp+var_28], rax
0x18007879a  lea     rcx, [rbp+var_18]
0x18007879e  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x1800787a3  jmp     loc_18007883B
0x1800787a8  test    rbx, rbx
0x1800787ab  jnz     short loc_1800787D4
0x1800787ad  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x1800787b4  mov     [rbp+var_30], 1D6h
0x1800787bc  mov     [rbp+var_40], rax
0x1800787c0  lea     rax, aWindowsComCide_2; "Windows::COM::CIdentityAuthority::Hash"
0x1800787c7  mov     [rbp+var_38], rax
0x1800787cb  lea     rax, aNotNullCheckFa_60; "Not-null check failed: pPseudoKey"
0x1800787d2  jmp     short loc_180078792
0x1800787d4  lea     rdx, [rbp+var_20]; struct IDefinitionIdentity *
0x1800787d8  mov     [rbp+var_20], 0
0x1800787e0  mov     rcx, r8; this
0x1800787e3  call    ?ConvertIn@COM@Windows@@YAJPEAUIDefinitionIdentity@@PEAPEAUIRtlDefinitionIdentity@Rtl@Identity@2@@Z; Windows::COM::ConvertIn(IDefinitionIdentity *,Windows::Identity::Rtl::IRtlDefinitionIdentity * *)
0x1800787e8  test    eax, eax
0x1800787ea  js      short loc_18007883B
0x1800787ec  lea     rdx, [rbp+var_18]
0x1800787f0  mov     [rbp+var_18], 0
0x1800787f8  call    RtlGetIdentityAuthority
0x1800787fd  test    eax, eax
0x1800787ff  js      short loc_180078823
0x180078801  mov     rcx, [rbp+var_18]
0x180078805  xor     r8d, r8d
0x180078808  mov     r9, [rbp+var_20]
0x18007880c  xor     edx, edx
0x18007880e  mov     [rsp+70h+var_50], rbx
0x180078813  mov     rax, [rcx]
0x180078816  mov     rax, [rax+50h]
0x18007881a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007881f  test    eax, eax
0x180078821  jns     short loc_18007882E
0x180078823  mov     ecx, eax
0x180078825  call    ConvertNtStatusToHResult
0x18007882a  mov     ebx, eax
0x18007882c  jmp     short loc_180078830
0x18007882e  xor     ebx, ebx
0x180078830  lea     rcx, [rbp+var_18]
0x180078834  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x180078839  mov     eax, ebx
0x18007883b  mov     rcx, [rbp+var_10]
0x18007883f  xor     rcx, rsp; StackCookie
0x180078842  call    __security_check_cookie
0x180078847  mov     rbx, [rsp+70h+arg_0]
0x18007884f  add     rsp, 70h
0x180078853  pop     rbp
0x180078854  retn
```
