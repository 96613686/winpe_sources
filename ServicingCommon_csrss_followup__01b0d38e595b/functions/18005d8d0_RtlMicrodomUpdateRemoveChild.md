# RtlMicrodomUpdateRemoveChild

- ea: `0x18005d8d0`
- end: `0x18005d9dd`
- name: `RtlMicrodomUpdateRemoveChild`
- size: `269`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18001f1d8`
- `0x18002d2b0`
- `0x18005c4ec`
- `0x18005d8d0`

## string_xrefs

- `0x18005d8f3`: `onecore\base\xml\udom_modify.cpp`
- `0x18005d933`: `onecore\base\xml\udom_modify.cpp`
- `0x18005d95f`: `onecore\base\xml\udom_modify.cpp`
- `0x18005d98f`: `onecore\base\xml\udom_modify.cpp`
- `0x18005d911`: `RtlIsMicrodomUpdateContextValid(HostUpdate)`
- `0x18005d906`: `Windows::uDom::Rtl::RtlMicrodomUpdateRemoveChild`
- `0x18005d946`: `Windows::uDom::Rtl::RtlMicrodomUpdateRemoveChild`
- `0x18005d972`: `Windows::uDom::Rtl::RtlMicrodomUpdateRemoveChild`
- `0x18005d9a2`: `Windows::uDom::Rtl::RtlMicrodomUpdateRemoveChild`
- `0x18005d951`: `pToRemoveFrom != 0`
- `0x18005d97d`: `pToRemove != 0`
- `0x18005d9ad`: `pToRemoveFrom->Element != 0`

## pseudocode

```c
__int64 __fastcall RtlMicrodomUpdateRemoveChild(__int64 a1, __int64 a2, struct CChildNode *a3)
{
  const char *v3; // rax
  CElementModification *v5; // rcx
  int v6; // eax
  unsigned int v7; // ecx
  const char *v8; // [rsp+20h] [rbp-30h] BYREF
  const char *v9; // [rsp+28h] [rbp-28h]
  __int64 v10; // [rsp+30h] [rbp-20h]
  const char *v11; // [rsp+38h] [rbp-18h]
  int v12; // [rsp+40h] [rbp-10h] BYREF

  v12 = 0;
  if ( !a1 )
  {
    v10 = 1816;
    v8 = "onecore\\base\\xml\\udom_modify.cpp";
    v9 = "Windows::uDom::Rtl::RtlMicrodomUpdateRemoveChild";
    v3 = "RtlIsMicrodomUpdateContextValid(HostUpdate)";
LABEL_3:
    v11 = v3;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v12,
             &v8);
  }
  if ( !a2 )
  {
    v10 = 1817;
    v8 = "onecore\\base\\xml\\udom_modify.cpp";
    v9 = "Windows::uDom::Rtl::RtlMicrodomUpdateRemoveChild";
    v3 = "pToRemoveFrom != 0";
    goto LABEL_3;
  }
  if ( !a3 )
  {
    v10 = 1818;
    v8 = "onecore\\base\\xml\\udom_modify.cpp";
    v9 = "Windows::uDom::Rtl::RtlMicrodomUpdateRemoveChild";
    v3 = "pToRemove != 0";
    goto LABEL_3;
  }
  v5 = *(CElementModification **)(a2 + 40);
  if ( !v5 )
  {
    v10 = 1819;
    v8 = "onecore\\base\\xml\\udom_modify.cpp";
    v9 = "Windows::uDom::Rtl::RtlMicrodomUpdateRemoveChild";
    v3 = "pToRemoveFrom->Element != 0";
    goto LABEL_3;
  }
  v6 = CElementModification::RemoveChild(v5, a3);
  v7 = 0;
  if ( v6 < 0 )
    return (unsigned int)v6;
  return v7;
}

```

## disassembly

```asm
0x18005d8d0  push    rbp
0x18005d8d2  mov     rbp, rsp
0x18005d8d5  sub     rsp, 50h
0x18005d8d9  mov     rax, cs:__security_cookie
0x18005d8e0  xor     rax, rsp
0x18005d8e3  mov     [rbp+var_8], rax
0x18005d8e7  mov     [rbp+var_10], 0
0x18005d8ee  test    rcx, rcx
0x18005d8f1  jnz     short loc_18005D92E
0x18005d8f3  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005d8fa  mov     [rbp+var_20], 718h
0x18005d902  mov     [rbp+var_30], rax
0x18005d906  lea     rax, aWindowsUdomRtl_11; "Windows::uDom::Rtl::RtlMicrodomUpdateRe"...
0x18005d90d  mov     [rbp+var_28], rax
0x18005d911  lea     rax, aRtlismicrodomu_0; "RtlIsMicrodomUpdateContextValid(HostUpd"...
0x18005d918  lea     rdx, [rbp+var_30]
0x18005d91c  mov     [rbp+var_18], rax
0x18005d920  lea     rcx, [rbp+var_10]
0x18005d924  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005d929  jmp     loc_18005D9CA
0x18005d92e  test    rdx, rdx
0x18005d931  jnz     short loc_18005D95A
0x18005d933  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005d93a  mov     [rbp+var_20], 719h
0x18005d942  mov     [rbp+var_30], rax
0x18005d946  lea     rax, aWindowsUdomRtl_11; "Windows::uDom::Rtl::RtlMicrodomUpdateRe"...
0x18005d94d  mov     [rbp+var_28], rax
0x18005d951  lea     rax, aPtoremovefrom0; "pToRemoveFrom != 0"
0x18005d958  jmp     short loc_18005D918
0x18005d95a  test    r8, r8
0x18005d95d  jnz     short loc_18005D986
0x18005d95f  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005d966  mov     [rbp+var_20], 71Ah
0x18005d96e  mov     [rbp+var_30], rax
0x18005d972  lea     rax, aWindowsUdomRtl_11; "Windows::uDom::Rtl::RtlMicrodomUpdateRe"...
0x18005d979  mov     [rbp+var_28], rax
0x18005d97d  lea     rax, aPtoremove0; "pToRemove != 0"
0x18005d984  jmp     short loc_18005D918
0x18005d986  mov     rcx, [rdx+28h]; this
0x18005d98a  test    rcx, rcx
0x18005d98d  jnz     short loc_18005D9B9
0x18005d98f  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005d996  mov     [rbp+var_20], 71Bh
0x18005d99e  mov     [rbp+var_30], rax
0x18005d9a2  lea     rax, aWindowsUdomRtl_11; "Windows::uDom::Rtl::RtlMicrodomUpdateRe"...
0x18005d9a9  mov     [rbp+var_28], rax
0x18005d9ad  lea     rax, aPtoremovefromE; "pToRemoveFrom->Element != 0"
0x18005d9b4  jmp     loc_18005D918
0x18005d9b9  mov     rdx, r8; struct CChildNode *
0x18005d9bc  call    ?RemoveChild@CElementModification@@QEAAJPEAVCChildNode@@@Z; CElementModification::RemoveChild(CChildNode *)
0x18005d9c1  xor     ecx, ecx
0x18005d9c3  test    eax, eax
0x18005d9c5  cmovs   ecx, eax
0x18005d9c8  mov     eax, ecx
0x18005d9ca  mov     rcx, [rbp+var_8]
0x18005d9ce  xor     rcx, rsp; StackCookie
0x18005d9d1  call    __security_check_cookie
0x18005d9d6  add     rsp, 50h
0x18005d9da  pop     rbp
0x18005d9db  retn
```
