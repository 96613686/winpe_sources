# Windows::COM::CIdentityAuthority::AreEqual<IDefinitionIdentity>(ulong,IDefinitionIdentity *,IDefinitionIdentity *,int *)

- ea: `0x1800772b8`
- end: `0x180077457`
- name: `??$AreEqual@UIDefinitionIdentity@@@CIdentityAuthority@COM@Windows@@IEAAJKPEAUIDefinitionIdentity@@0PEAH@Z`
- size: `415`
- prototype: `__int64 __fastcall(__int64, unsigned int, Windows::COM *, Windows::COM *, _DWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180079230`

## callees

- `0x180010c10`
- `0x18001f51c`
- `0x1800293a0`
- `0x18006b1e0`
- `0x1800772b8`
- `0x18007943c`
- `0x18008597c`
- `0x180093bdc`
- `0x1800a0020`

## string_xrefs

- `0x180077315`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x180077355`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x180077381`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x180077328`: `Windows::COM::CIdentityAuthority::AreEqual`
- `0x180077368`: `Windows::COM::CIdentityAuthority::AreEqual`
- `0x180077394`: `Windows::COM::CIdentityAuthority::AreEqual`

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
  struct Windows::Identity::Rtl::IRtlDefinitionIdentity **v8; // r8
  const char *v9; // rax
  struct Windows::Identity::Rtl::IRtlDefinitionIdentity **v10; // r8
  __int64 v11; // rcx
  int IdentityAuthority; // eax
  unsigned int v13; // ebx
  unsigned int v14; // [rsp+30h] [rbp-50h] BYREF
  const char *v15; // [rsp+38h] [rbp-48h] BYREF
  const char *v16; // [rsp+40h] [rbp-40h]
  __int64 v17; // [rsp+48h] [rbp-38h]
  const char *v18; // [rsp+50h] [rbp-30h]
  __int64 v19; // [rsp+58h] [rbp-28h] BYREF
  __int64 v20; // [rsp+60h] [rbp-20h] BYREF
  _BYTE v21[8]; // [rsp+68h] [rbp-18h] BYREF
  __int64 v22; // [rsp+70h] [rbp-10h] BYREF

  LODWORD(v22) = 0;
  if ( a5 )
    *a5 = 0;
  v14 = 0;
  result = Windows::COM::CCOMToRtlInterfaceMapper<IDefinitionIdentity>::MapAreEqualFlags(a2, &v14);
  if ( (int)result >= 0 )
  {
    if ( !a3 )
    {
      v17 = 307;
      v15 = "onecore\\base\\wcp\\identity\\com\\identity_authority.cpp";
      v16 = "Windows::COM::CIdentityAuthority::AreEqual";
      v9 = "Not-null check failed: pIdentity1";
LABEL_6:
      v18 = v9;
      return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
               &v22,
               &v15);
    }
    if ( !a4 )
    {
      v17 = 308;
      v15 = "onecore\\base\\wcp\\identity\\com\\identity_authority.cpp";
      v16 = "Windows::COM::CIdentityAuthority::AreEqual";
      v9 = "Not-null check failed: pIdentity2";
      goto LABEL_6;
    }
    if ( !a5 )
    {
      v17 = 309;
      v15 = "onecore\\base\\wcp\\identity\\com\\identity_authority.cpp";
      v16 = "Windows::COM::CIdentityAuthority::AreEqual";
      v9 = "Not-null check failed: pfAreEqual";
      goto LABEL_6;
    }
    v20 = 0;
    result = Windows::COM::ConvertIn(a3, (struct IDefinitionIdentity *)&v20, v8);
    if ( (int)result >= 0 )
    {
      v19 = 0;
      result = Windows::COM::ConvertIn(a4, (struct IDefinitionIdentity *)&v19, v10);
      if ( (int)result >= 0 )
      {
        v22 = 0;
        IdentityAuthority = RtlGetIdentityAuthority(v11, &v22);
        if ( IdentityAuthority >= 0
          && (v21[0] = 0,
              IdentityAuthority = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, _BYTE *))(*(_QWORD *)v22 + 56LL))(
                                    v22,
                                    v14,
                                    v20,
                                    v19,
                                    v21),
              IdentityAuthority >= 0) )
        {
          *a5 = v21[0];
          v13 = 0;
        }
        else
        {
          v13 = ConvertNtStatusToHResult((unsigned int)IdentityAuthority);
        }
        Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(&v22);
        return v13;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800772b8  mov     [rsp-18h+arg_0], rbx
0x1800772bd  push    rbp
0x1800772be  push    rsi
0x1800772bf  push    rdi
0x1800772c0  mov     rbp, rsp
0x1800772c3  sub     rsp, 80h
0x1800772ca  mov     rax, cs:__security_cookie
0x1800772d1  xor     rax, rsp
0x1800772d4  mov     [rbp+var_8], rax
0x1800772d8  mov     rbx, [rbp+arg_20]
0x1800772dc  mov     rsi, r9
0x1800772df  mov     dword ptr [rbp+var_10], 0
0x1800772e6  mov     rdi, r8
0x1800772e9  mov     eax, edx
0x1800772eb  test    rbx, rbx
0x1800772ee  jz      short loc_1800772F6
0x1800772f0  mov     dword ptr [rbx], 0
0x1800772f6  lea     rdx, [rbp+var_50]
0x1800772fa  mov     [rbp+var_50], 0
0x180077301  mov     ecx, eax
0x180077303  call    ?MapAreEqualFlags@?$CCOMToRtlInterfaceMapper@UIDefinitionIdentity@@@COM@Windows@@SAJKPEAK@Z; Windows::COM::CCOMToRtlInterfaceMapper<IDefinitionIdentity>::MapAreEqualFlags(ulong,ulong *)
0x180077308  test    eax, eax
0x18007730a  js      loc_180077437
0x180077310  test    rdi, rdi
0x180077313  jnz     short loc_180077350
0x180077315  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x18007731c  mov     [rbp+var_38], 133h
0x180077324  mov     [rbp+var_48], rax
0x180077328  lea     rax, aWindowsComCide_5; "Windows::COM::CIdentityAuthority::AreEq"...
0x18007732f  mov     [rbp+var_40], rax
0x180077333  lea     rax, aNotNullCheckFa_19; "Not-null check failed: pIdentity1"
0x18007733a  lea     rdx, [rbp+var_48]
0x18007733e  mov     [rbp+var_30], rax
0x180077342  lea     rcx, [rbp+var_10]
0x180077346  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18007734b  jmp     loc_180077437
0x180077350  test    rsi, rsi
0x180077353  jnz     short loc_18007737C
0x180077355  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x18007735c  mov     [rbp+var_38], 134h
0x180077364  mov     [rbp+var_48], rax
0x180077368  lea     rax, aWindowsComCide_5; "Windows::COM::CIdentityAuthority::AreEq"...
0x18007736f  mov     [rbp+var_40], rax
0x180077373  lea     rax, aNotNullCheckFa_128; "Not-null check failed: pIdentity2"
0x18007737a  jmp     short loc_18007733A
0x18007737c  test    rbx, rbx
0x18007737f  jnz     short loc_1800773A8
0x180077381  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x180077388  mov     [rbp+var_38], 135h
0x180077390  mov     [rbp+var_48], rax
0x180077394  lea     rax, aWindowsComCide_5; "Windows::COM::CIdentityAuthority::AreEq"...
0x18007739b  mov     [rbp+var_40], rax
0x18007739f  lea     rax, aNotNullCheckFa_64; "Not-null check failed: pfAreEqual"
0x1800773a6  jmp     short loc_18007733A
0x1800773a8  lea     rdx, [rbp+var_20]; struct IDefinitionIdentity *
0x1800773ac  mov     [rbp+var_20], 0
0x1800773b4  mov     rcx, rdi; this
0x1800773b7  call    ?ConvertIn@COM@Windows@@YAJPEAUIDefinitionIdentity@@PEAPEAUIRtlDefinitionIdentity@Rtl@Identity@2@@Z; Windows::COM::ConvertIn(IDefinitionIdentity *,Windows::Identity::Rtl::IRtlDefinitionIdentity * *)
0x1800773bc  test    eax, eax
0x1800773be  js      short loc_180077437
0x1800773c0  lea     rdx, [rbp+var_28]; struct IDefinitionIdentity *
0x1800773c4  mov     [rbp+var_28], 0
0x1800773cc  mov     rcx, rsi; this
0x1800773cf  call    ?ConvertIn@COM@Windows@@YAJPEAUIDefinitionIdentity@@PEAPEAUIRtlDefinitionIdentity@Rtl@Identity@2@@Z; Windows::COM::ConvertIn(IDefinitionIdentity *,Windows::Identity::Rtl::IRtlDefinitionIdentity * *)
0x1800773d4  test    eax, eax
0x1800773d6  js      short loc_180077437
0x1800773d8  lea     rdx, [rbp+var_10]
0x1800773dc  mov     [rbp+var_10], 0
0x1800773e4  call    RtlGetIdentityAuthority
0x1800773e9  test    eax, eax
0x1800773eb  js      short loc_180077419
0x1800773ed  mov     rcx, [rbp+var_10]
0x1800773f1  lea     rdx, [rbp+var_18]
0x1800773f5  mov     r9, [rbp+var_28]
0x1800773f9  mov     r8, [rbp+var_20]
0x1800773fd  mov     [rbp+var_18], 0
0x180077401  mov     rax, [rcx]
0x180077404  mov     [rsp+80h+var_60], rdx
0x180077409  mov     edx, [rbp+var_50]
0x18007740c  mov     rax, [rax+38h]
0x180077410  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077415  test    eax, eax
0x180077417  jns     short loc_180077424
0x180077419  mov     ecx, eax
0x18007741b  call    ConvertNtStatusToHResult
0x180077420  mov     ebx, eax
0x180077422  jmp     short loc_18007742C
0x180077424  movzx   eax, [rbp+var_18]
0x180077428  mov     [rbx], eax
0x18007742a  xor     ebx, ebx
0x18007742c  lea     rcx, [rbp+var_10]
0x180077430  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x180077435  mov     eax, ebx
0x180077437  mov     rcx, [rbp+var_8]
0x18007743b  xor     rcx, rsp; StackCookie
0x18007743e  call    __security_check_cookie
0x180077443  mov     rbx, [rsp+80h+arg_0]
0x18007744b  add     rsp, 80h
0x180077452  pop     rdi
0x180077453  pop     rsi
0x180077454  pop     rbp
0x180077455  retn
```
