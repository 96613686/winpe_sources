# RtlMicrodomUpdateRemoveChild

- ea: `0x18005cc30`
- end: `0x18005cd3d`
- name: `RtlMicrodomUpdateRemoveChild`
- size: `269`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18001f4ac`
- `0x1800293a0`
- `0x18005b57c`
- `0x18005cc30`

## string_xrefs

- `0x18005cc53`: `onecore\base\xml\udom_modify.cpp`
- `0x18005cc93`: `onecore\base\xml\udom_modify.cpp`
- `0x18005ccbf`: `onecore\base\xml\udom_modify.cpp`
- `0x18005ccef`: `onecore\base\xml\udom_modify.cpp`
- `0x18005cc71`: `RtlIsMicrodomUpdateContextValid(HostUpdate)`
- `0x18005cc66`: `Windows::uDom::Rtl::RtlMicrodomUpdateRemoveChild`
- `0x18005cca6`: `Windows::uDom::Rtl::RtlMicrodomUpdateRemoveChild`
- `0x18005ccd2`: `Windows::uDom::Rtl::RtlMicrodomUpdateRemoveChild`
- `0x18005cd02`: `Windows::uDom::Rtl::RtlMicrodomUpdateRemoveChild`
- `0x18005ccb1`: `pToRemoveFrom != 0`
- `0x18005ccdd`: `pToRemove != 0`
- `0x18005cd0d`: `pToRemoveFrom->Element != 0`

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
0x18005cc30  push    rbp
0x18005cc32  mov     rbp, rsp
0x18005cc35  sub     rsp, 50h
0x18005cc39  mov     rax, cs:__security_cookie
0x18005cc40  xor     rax, rsp
0x18005cc43  mov     [rbp+var_8], rax
0x18005cc47  mov     [rbp+var_10], 0
0x18005cc4e  test    rcx, rcx
0x18005cc51  jnz     short loc_18005CC8E
0x18005cc53  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005cc5a  mov     [rbp+var_20], 718h
0x18005cc62  mov     [rbp+var_30], rax
0x18005cc66  lea     rax, aWindowsUdomRtl_11; "Windows::uDom::Rtl::RtlMicrodomUpdateRe"...
0x18005cc6d  mov     [rbp+var_28], rax
0x18005cc71  lea     rax, aRtlismicrodomu_0; "RtlIsMicrodomUpdateContextValid(HostUpd"...
0x18005cc78  lea     rdx, [rbp+var_30]
0x18005cc7c  mov     [rbp+var_18], rax
0x18005cc80  lea     rcx, [rbp+var_10]
0x18005cc84  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005cc89  jmp     loc_18005CD2A
0x18005cc8e  test    rdx, rdx
0x18005cc91  jnz     short loc_18005CCBA
0x18005cc93  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005cc9a  mov     [rbp+var_20], 719h
0x18005cca2  mov     [rbp+var_30], rax
0x18005cca6  lea     rax, aWindowsUdomRtl_11; "Windows::uDom::Rtl::RtlMicrodomUpdateRe"...
0x18005ccad  mov     [rbp+var_28], rax
0x18005ccb1  lea     rax, aPtoremovefrom0; "pToRemoveFrom != 0"
0x18005ccb8  jmp     short loc_18005CC78
0x18005ccba  test    r8, r8
0x18005ccbd  jnz     short loc_18005CCE6
0x18005ccbf  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005ccc6  mov     [rbp+var_20], 71Ah
0x18005ccce  mov     [rbp+var_30], rax
0x18005ccd2  lea     rax, aWindowsUdomRtl_11; "Windows::uDom::Rtl::RtlMicrodomUpdateRe"...
0x18005ccd9  mov     [rbp+var_28], rax
0x18005ccdd  lea     rax, aPtoremove0; "pToRemove != 0"
0x18005cce4  jmp     short loc_18005CC78
0x18005cce6  mov     rcx, [rdx+28h]; this
0x18005ccea  test    rcx, rcx
0x18005cced  jnz     short loc_18005CD19
0x18005ccef  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005ccf6  mov     [rbp+var_20], 71Bh
0x18005ccfe  mov     [rbp+var_30], rax
0x18005cd02  lea     rax, aWindowsUdomRtl_11; "Windows::uDom::Rtl::RtlMicrodomUpdateRe"...
0x18005cd09  mov     [rbp+var_28], rax
0x18005cd0d  lea     rax, aPtoremovefromE; "pToRemoveFrom->Element != 0"
0x18005cd14  jmp     loc_18005CC78
0x18005cd19  mov     rdx, r8; struct CChildNode *
0x18005cd1c  call    ?RemoveChild@CElementModification@@QEAAJPEAVCChildNode@@@Z; CElementModification::RemoveChild(CChildNode *)
0x18005cd21  xor     ecx, ecx
0x18005cd23  test    eax, eax
0x18005cd25  cmovs   ecx, eax
0x18005cd28  mov     eax, ecx
0x18005cd2a  mov     rcx, [rbp+var_8]
0x18005cd2e  xor     rcx, rsp; StackCookie
0x18005cd31  call    __security_check_cookie
0x18005cd36  add     rsp, 50h
0x18005cd3a  pop     rbp
0x18005cd3b  retn
```
