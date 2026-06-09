# Windows::COM::CIdentityAuthority::AreEqual<IReferenceIdentity>(ulong,IReferenceIdentity *,IReferenceIdentity *,int *)

- ea: `0x1800776a0`
- end: `0x18007783f`
- name: `??$AreEqual@UIReferenceIdentity@@@CIdentityAuthority@COM@Windows@@IEAAJKPEAUIReferenceIdentity@@0PEAH@Z`
- size: `415`
- prototype: `__int64 __fastcall(__int64, unsigned int, Windows::COM *, Windows::COM *, _DWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180079240`

## callees

- `0x180010c10`
- `0x18001f51c`
- `0x1800293a0`
- `0x18006b1e0`
- `0x1800776a0`
- `0x1800794bc`
- `0x180085a38`
- `0x180093bdc`
- `0x1800a0020`

## string_xrefs

- `0x1800776fd`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x18007773d`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x180077769`: `onecore\base\wcp\identity\com\identity_authority.cpp`
- `0x180077710`: `Windows::COM::CIdentityAuthority::AreEqual`
- `0x180077750`: `Windows::COM::CIdentityAuthority::AreEqual`
- `0x18007777c`: `Windows::COM::CIdentityAuthority::AreEqual`

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
  struct Windows::Identity::Rtl::IRtlReferenceIdentity **v8; // r8
  const char *v9; // rax
  struct Windows::Identity::Rtl::IRtlReferenceIdentity **v10; // r8
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
  result = Windows::COM::CCOMToRtlInterfaceMapper<IReferenceIdentity>::MapAreEqualFlags(a2, &v14);
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
    result = Windows::COM::ConvertIn(a3, (struct IReferenceIdentity *)&v20, v8);
    if ( (int)result >= 0 )
    {
      v19 = 0;
      result = Windows::COM::ConvertIn(a4, (struct IReferenceIdentity *)&v19, v10);
      if ( (int)result >= 0 )
      {
        v22 = 0;
        IdentityAuthority = RtlGetIdentityAuthority(v11, &v22);
        if ( IdentityAuthority >= 0
          && (v21[0] = 0,
              IdentityAuthority = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, _BYTE *))(*(_QWORD *)v22 + 48LL))(
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
0x1800776a0  mov     [rsp-18h+arg_0], rbx
0x1800776a5  push    rbp
0x1800776a6  push    rsi
0x1800776a7  push    rdi
0x1800776a8  mov     rbp, rsp
0x1800776ab  sub     rsp, 80h
0x1800776b2  mov     rax, cs:__security_cookie
0x1800776b9  xor     rax, rsp
0x1800776bc  mov     [rbp+var_8], rax
0x1800776c0  mov     rbx, [rbp+arg_20]
0x1800776c4  mov     rsi, r9
0x1800776c7  mov     dword ptr [rbp+var_10], 0
0x1800776ce  mov     rdi, r8
0x1800776d1  mov     eax, edx
0x1800776d3  test    rbx, rbx
0x1800776d6  jz      short loc_1800776DE
0x1800776d8  mov     dword ptr [rbx], 0
0x1800776de  lea     rdx, [rbp+var_50]
0x1800776e2  mov     [rbp+var_50], 0
0x1800776e9  mov     ecx, eax
0x1800776eb  call    ?MapAreEqualFlags@?$CCOMToRtlInterfaceMapper@UIReferenceIdentity@@@COM@Windows@@SAJKPEAK@Z; Windows::COM::CCOMToRtlInterfaceMapper<IReferenceIdentity>::MapAreEqualFlags(ulong,ulong *)
0x1800776f0  test    eax, eax
0x1800776f2  js      loc_18007781F
0x1800776f8  test    rdi, rdi
0x1800776fb  jnz     short loc_180077738
0x1800776fd  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x180077704  mov     [rbp+var_38], 133h
0x18007770c  mov     [rbp+var_48], rax
0x180077710  lea     rax, aWindowsComCide_5; "Windows::COM::CIdentityAuthority::AreEq"...
0x180077717  mov     [rbp+var_40], rax
0x18007771b  lea     rax, aNotNullCheckFa_19; "Not-null check failed: pIdentity1"
0x180077722  lea     rdx, [rbp+var_48]
0x180077726  mov     [rbp+var_30], rax
0x18007772a  lea     rcx, [rbp+var_10]
0x18007772e  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180077733  jmp     loc_18007781F
0x180077738  test    rsi, rsi
0x18007773b  jnz     short loc_180077764
0x18007773d  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x180077744  mov     [rbp+var_38], 134h
0x18007774c  mov     [rbp+var_48], rax
0x180077750  lea     rax, aWindowsComCide_5; "Windows::COM::CIdentityAuthority::AreEq"...
0x180077757  mov     [rbp+var_40], rax
0x18007775b  lea     rax, aNotNullCheckFa_128; "Not-null check failed: pIdentity2"
0x180077762  jmp     short loc_180077722
0x180077764  test    rbx, rbx
0x180077767  jnz     short loc_180077790
0x180077769  lea     rax, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\identity\\com\\iden"...
0x180077770  mov     [rbp+var_38], 135h
0x180077778  mov     [rbp+var_48], rax
0x18007777c  lea     rax, aWindowsComCide_5; "Windows::COM::CIdentityAuthority::AreEq"...
0x180077783  mov     [rbp+var_40], rax
0x180077787  lea     rax, aNotNullCheckFa_64; "Not-null check failed: pfAreEqual"
0x18007778e  jmp     short loc_180077722
0x180077790  lea     rdx, [rbp+var_20]; struct IReferenceIdentity *
0x180077794  mov     [rbp+var_20], 0
0x18007779c  mov     rcx, rdi; this
0x18007779f  call    ?ConvertIn@COM@Windows@@YAJPEAUIReferenceIdentity@@PEAPEAUIRtlReferenceIdentity@Rtl@Identity@2@@Z; Windows::COM::ConvertIn(IReferenceIdentity *,Windows::Identity::Rtl::IRtlReferenceIdentity * *)
0x1800777a4  test    eax, eax
0x1800777a6  js      short loc_18007781F
0x1800777a8  lea     rdx, [rbp+var_28]; struct IReferenceIdentity *
0x1800777ac  mov     [rbp+var_28], 0
0x1800777b4  mov     rcx, rsi; this
0x1800777b7  call    ?ConvertIn@COM@Windows@@YAJPEAUIReferenceIdentity@@PEAPEAUIRtlReferenceIdentity@Rtl@Identity@2@@Z; Windows::COM::ConvertIn(IReferenceIdentity *,Windows::Identity::Rtl::IRtlReferenceIdentity * *)
0x1800777bc  test    eax, eax
0x1800777be  js      short loc_18007781F
0x1800777c0  lea     rdx, [rbp+var_10]
0x1800777c4  mov     [rbp+var_10], 0
0x1800777cc  call    RtlGetIdentityAuthority
0x1800777d1  test    eax, eax
0x1800777d3  js      short loc_180077801
0x1800777d5  mov     rcx, [rbp+var_10]
0x1800777d9  lea     rdx, [rbp+var_18]
0x1800777dd  mov     r9, [rbp+var_28]
0x1800777e1  mov     r8, [rbp+var_20]
0x1800777e5  mov     [rbp+var_18], 0
0x1800777e9  mov     rax, [rcx]
0x1800777ec  mov     [rsp+80h+var_60], rdx
0x1800777f1  mov     edx, [rbp+var_50]
0x1800777f4  mov     rax, [rax+30h]
0x1800777f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800777fd  test    eax, eax
0x1800777ff  jns     short loc_18007780C
0x180077801  mov     ecx, eax
0x180077803  call    ConvertNtStatusToHResult
0x180077808  mov     ebx, eax
0x18007780a  jmp     short loc_180077814
0x18007780c  movzx   eax, [rbp+var_18]
0x180077810  mov     [rbx], eax
0x180077812  xor     ebx, ebx
0x180077814  lea     rcx, [rbp+var_10]
0x180077818  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x18007781d  mov     eax, ebx
0x18007781f  mov     rcx, [rbp+var_8]
0x180077823  xor     rcx, rsp; StackCookie
0x180077826  call    __security_check_cookie
0x18007782b  mov     rbx, [rsp+80h+arg_0]
0x180077833  add     rsp, 80h
0x18007783a  pop     rdi
0x18007783b  pop     rsi
0x18007783c  pop     rbp
0x18007783d  retn
```
