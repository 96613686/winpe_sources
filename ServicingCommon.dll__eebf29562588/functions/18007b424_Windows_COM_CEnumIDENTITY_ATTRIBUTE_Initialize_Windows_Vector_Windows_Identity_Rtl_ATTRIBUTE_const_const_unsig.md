# Windows::COM::CEnumIDENTITY_ATTRIBUTE::Initialize(Windows::Vector<Windows::Identity::Rtl::_ATTRIBUTE const> const *,unsigned __int64)

- ea: `0x18007b424`
- end: `0x18007b600`
- name: `?Initialize@CEnumIDENTITY_ATTRIBUTE@COM@Windows@@IEAAJPEBU?$Vector@$$CBU_ATTRIBUTE@Rtl@Identity@Windows@@@3@_K@Z`
- size: `476`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18007b04c`

## callees

- `0x18001f4e4`
- `0x18001f604`
- `0x18001fd10`
- `0x1800293a0`
- `0x1800661b0`
- `0x18006b1e0`
- `0x18007ae80`
- `0x18007b424`

## string_xrefs

- `0x18007b466`: `onecore\base\wcp\identity\com\enum_idattribute.cpp`
- `0x18007b4b3`: `onecore\base\wcp\identity\com\enum_idattribute.cpp`
- `0x18007b597`: `onecore\base\wcp\identity\com\enum_idattribute.cpp`
- `0x18007b479`: `Windows::COM::CEnumIDENTITY_ATTRIBUTE::Initialize`
- `0x18007b4ca`: `Windows::COM::CEnumIDENTITY_ATTRIBUTE::Initialize`
- `0x18007b5aa`: `Windows::COM::CEnumIDENTITY_ATTRIBUTE::Initialize`

## pseudocode

```c
__int64 __fastcall Windows::COM::CEnumIDENTITY_ATTRIBUTE::Initialize(_QWORD *a1, _QWORD *a2, unsigned __int64 a3)
{
  unsigned __int64 v3; // r14
  const char *v6; // rax
  __int64 v8; // rsi
  __int64 v9; // rcx
  __int64 v10; // r15
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rcx
  const char *v14; // [rsp+20h] [rbp-30h] BYREF
  const char *v15; // [rsp+28h] [rbp-28h]
  __int64 v16; // [rsp+30h] [rbp-20h]
  const char *v17; // [rsp+38h] [rbp-18h]
  int v18; // [rsp+40h] [rbp-10h] BYREF

  v3 = a3;
  v18 = 0;
  if ( !a2 )
  {
    if ( a3 )
    {
      v16 = 44;
      v14 = "onecore\\base\\wcp\\identity\\com\\enum_idattribute.cpp";
      v15 = "Windows::COM::CEnumIDENTITY_ATTRIBUTE::Initialize";
      v6 = "(IdentityAttributeList != 0) || (CurrentPosition == 0)";
      goto LABEL_4;
    }
    if ( a1[4] )
    {
      INTERNAL_ERROR_ACTION(-1073741595);
      JUMPOUT(0x18007B5FFLL);
    }
    v3 = 0;
LABEL_21:
    a1[5] = v3;
    return 0;
  }
  if ( a2[1] < a3 )
  {
    v16 = 43;
    v14 = "onecore\\base\\wcp\\identity\\com\\enum_idattribute.cpp";
    v15 = "Windows::COM::CEnumIDENTITY_ATTRIBUTE::Initialize";
    v6 = "(IdentityAttributeList == 0) || (IdentityAttributeList->Length >= CurrentPosition)";
LABEL_4:
    v17 = v6;
    return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter(
             &v18,
             &v14);
  }
  if ( !Windows::AutoVectorBase<Windows::VectorTraits<Windows::COM::CEnumIDENTITY_ATTRIBUTE::AutoAttribute>,Windows::Auto<Windows::Vector<Windows::COM::CEnumIDENTITY_ATTRIBUTE::AutoAttribute>>>::Allocate(
          a1 + 3,
          a2[1]) )
  {
    v16 = 48;
    v14 = "onecore\\base\\wcp\\identity\\com\\enum_idattribute.cpp";
    v15 = "Windows::COM::CEnumIDENTITY_ATTRIBUTE::Initialize";
    v17 = "m_IdentityAttributeList.Allocate(IdentityAttributeList->Length)";
    return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(
             &v18,
             &v14,
             2147942414LL);
  }
  v8 = 0;
  if ( !a2[1] )
    goto LABEL_21;
  while ( 1 )
  {
    v9 = *(_QWORD *)(*a2 + 24 * v8);
    v10 = 72 * v8;
    if ( v9 )
    {
      v11 = RtlDuplicateLUnicodeString(v9, v10 + a1[3]);
      if ( v11 < 0 )
        break;
    }
    v12 = *(_QWORD *)(*a2 + 24 * v8 + 8);
    if ( v12 )
    {
      v10 = 72 * v8;
      v11 = RtlDuplicateLUnicodeString(v12, 72 * v8 + a1[3] + 24LL);
      if ( v11 < 0 )
        break;
    }
    v13 = *(_QWORD *)(*a2 + 24 * v8 + 16);
    if ( v13 )
    {
      v11 = RtlDuplicateLUnicodeString(v13, v10 + a1[3] + 48LL);
      if ( v11 < 0 )
        break;
    }
    if ( (unsigned __int64)++v8 >= a2[1] )
      goto LABEL_21;
  }
  return ConvertNtStatusToHResult((unsigned int)v11);
}

```

## disassembly

```asm
0x18007b424  mov     [rsp-38h+arg_10], rbx
0x18007b429  push    rbp
0x18007b42a  push    rsi
0x18007b42b  push    rdi
0x18007b42c  push    r12
0x18007b42e  push    r13
0x18007b430  push    r14
0x18007b432  push    r15
0x18007b434  mov     rbp, rsp
0x18007b437  sub     rsp, 50h
0x18007b43b  mov     rax, cs:__security_cookie
0x18007b442  xor     rax, rsp
0x18007b445  mov     [rbp+var_8], rax
0x18007b449  xor     ebx, ebx
0x18007b44b  mov     r14, r8
0x18007b44e  mov     [rbp+var_10], ebx
0x18007b451  mov     rdi, rdx
0x18007b454  mov     r13, rcx
0x18007b457  test    rdx, rdx
0x18007b45a  jz      loc_18007B592
0x18007b460  cmp     [rdx+8], r8
0x18007b464  jnb     short loc_18007B4A1
0x18007b466  lea     rax, aOnecoreBaseWcp_7; "onecore\\base\\wcp\\identity\\com\\enum"...
0x18007b46d  mov     [rbp+var_20], 2Bh ; '+'
0x18007b475  mov     [rbp+var_30], rax
0x18007b479  lea     rax, aWindowsComCenu_2; "Windows::COM::CEnumIDENTITY_ATTRIBUTE::"...
0x18007b480  mov     [rbp+var_28], rax
0x18007b484  lea     rax, aIdentityattrib_1; "(IdentityAttributeList == 0) || (Identi"...
0x18007b48b  lea     rdx, [rbp+var_30]
0x18007b48f  mov     [rbp+var_18], rax
0x18007b493  lea     rcx, [rbp+var_10]
0x18007b497  call    ?OriginateInvalidParameter@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18007b49c  jmp     loc_18007B5D0
0x18007b4a1  mov     rdx, [rdx+8]
0x18007b4a5  add     rcx, 18h
0x18007b4a9  call    ?Allocate@?$AutoVectorBase@V?$VectorTraits@UAutoAttribute@CEnumIDENTITY_ATTRIBUTE@COM@Windows@@@Windows@@V?$Auto@U?$Vector@UAutoAttribute@CEnumIDENTITY_ATTRIBUTE@COM@Windows@@@Windows@@@2@@Windows@@QEAAPEAUAutoAttribute@CEnumIDENTITY_ATTRIBUTE@COM@2@_K@Z; Windows::AutoVectorBase<Windows::VectorTraits<Windows::COM::CEnumIDENTITY_ATTRIBUTE::AutoAttribute>,Windows::Auto<Windows::Vector<Windows::COM::CEnumIDENTITY_ATTRIBUTE::AutoAttribute>>>::Allocate(unsigned __int64)
0x18007b4ae  test    rax, rax
0x18007b4b1  jnz     short loc_18007B4F4
0x18007b4b3  lea     rax, aOnecoreBaseWcp_7; "onecore\\base\\wcp\\identity\\com\\enum"...
0x18007b4ba  mov     [rbp+var_20], 30h ; '0'
0x18007b4c2  mov     [rbp+var_30], rax
0x18007b4c6  lea     rdx, [rbp+var_30]
0x18007b4ca  lea     rax, aWindowsComCenu_2; "Windows::COM::CEnumIDENTITY_ATTRIBUTE::"...
0x18007b4d1  mov     r8d, 8007000Eh
0x18007b4d7  mov     [rbp+var_28], rax
0x18007b4db  lea     rcx, [rbp+var_10]
0x18007b4df  lea     rax, aMIdentityattri; "m_IdentityAttributeList.Allocate(Identi"...
0x18007b4e6  mov     [rbp+var_18], rax
0x18007b4ea  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18007b4ef  jmp     loc_18007B5D0
0x18007b4f4  xor     esi, esi
0x18007b4f6  cmp     [rdi+8], rbx
0x18007b4fa  jbe     loc_18007B5CA
0x18007b500  mov     rax, [rdi]
0x18007b503  lea     r12, [rsi+rsi*2]
0x18007b507  mov     rcx, [rax+r12*8]
0x18007b50b  lea     rax, [rsi+rsi*8]
0x18007b50f  lea     r15, ds:0[rax*8]
0x18007b517  test    rcx, rcx
0x18007b51a  jz      short loc_18007B52C
0x18007b51c  mov     rdx, [r13+18h]
0x18007b520  add     rdx, r15
0x18007b523  call    RtlDuplicateLUnicodeString
0x18007b528  test    eax, eax
0x18007b52a  js      short loc_18007B589
0x18007b52c  mov     rax, [rdi]
0x18007b52f  mov     rcx, [rax+r12*8+8]
0x18007b534  test    rcx, rcx
0x18007b537  jz      short loc_18007B559
0x18007b539  mov     rdx, [r13+18h]
0x18007b53d  lea     rax, [rsi+rsi*8]
0x18007b541  lea     r15, ds:0[rax*8]
0x18007b549  add     rdx, 18h
0x18007b54d  add     rdx, r15
0x18007b550  call    RtlDuplicateLUnicodeString
0x18007b555  test    eax, eax
0x18007b557  js      short loc_18007B589
0x18007b559  mov     rax, [rdi]
0x18007b55c  mov     rcx, [rax+r12*8+10h]
0x18007b561  test    rcx, rcx
0x18007b564  jz      short loc_18007B57A
0x18007b566  mov     rdx, [r13+18h]
0x18007b56a  add     rdx, 30h ; '0'
0x18007b56e  add     rdx, r15
0x18007b571  call    RtlDuplicateLUnicodeString
0x18007b576  test    eax, eax
0x18007b578  js      short loc_18007B589
0x18007b57a  inc     rsi
0x18007b57d  cmp     rsi, [rdi+8]
0x18007b581  jb      loc_18007B500
0x18007b587  jmp     short loc_18007B5CA
0x18007b589  mov     ecx, eax
0x18007b58b  call    ConvertNtStatusToHResult
0x18007b590  jmp     short loc_18007B5D0
0x18007b592  test    r8, r8
0x18007b595  jz      short loc_18007B5C1
0x18007b597  lea     rax, aOnecoreBaseWcp_7; "onecore\\base\\wcp\\identity\\com\\enum"...
0x18007b59e  mov     [rbp+var_20], 2Ch ; ','
0x18007b5a6  mov     [rbp+var_30], rax
0x18007b5aa  lea     rax, aWindowsComCenu_2; "Windows::COM::CEnumIDENTITY_ATTRIBUTE::"...
0x18007b5b1  mov     [rbp+var_28], rax
0x18007b5b5  lea     rax, aIdentityattrib_0; "(IdentityAttributeList != 0) || (Curren"...
0x18007b5bc  jmp     loc_18007B48B
0x18007b5c1  cmp     [rcx+20h], rbx
0x18007b5c5  jnz     short loc_18007B5F5
0x18007b5c7  xor     r14d, r14d
0x18007b5ca  mov     [r13+28h], r14
0x18007b5ce  mov     eax, ebx
0x18007b5d0  mov     rcx, [rbp+var_8]
0x18007b5d4  xor     rcx, rsp; StackCookie
0x18007b5d7  call    __security_check_cookie
0x18007b5dc  mov     rbx, [rsp+50h+arg_10]
0x18007b5e4  add     rsp, 50h
0x18007b5e8  pop     r15
0x18007b5ea  pop     r14
0x18007b5ec  pop     r13
0x18007b5ee  pop     r12
0x18007b5f0  pop     rdi
0x18007b5f1  pop     rsi
0x18007b5f2  pop     rbp
0x18007b5f3  retn
0x18007b5f5  mov     ecx, 0C00000E5h; int
0x18007b5fa  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
