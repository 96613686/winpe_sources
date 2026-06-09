# RtlMicrodomUpdateRemoveElement

- ea: `0x18005d9f0`
- end: `0x18005daa2`
- name: `RtlMicrodomUpdateRemoveElement`
- size: `178`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18001f1d8`
- `0x18002d2b0`
- `0x18005c4ec`
- `0x18005d9f0`

## string_xrefs

- `0x18005da13`: `onecore\base\xml\udom_modify.cpp`
- `0x18005da50`: `onecore\base\xml\udom_modify.cpp`
- `0x18005da31`: `RtlIsMicrodomUpdateContextValid(HostUpdate)`
- `0x18005da6e`: `pToRemove != 0`
- `0x18005da26`: `Windows::uDom::Rtl::RtlMicrodomUpdateRemoveElement`
- `0x18005da63`: `Windows::uDom::Rtl::RtlMicrodomUpdateRemoveElement`

## pseudocode

```c
__int64 __fastcall RtlMicrodomUpdateRemoveElement(__int64 a1, struct CChildNode *a2)
{
  const char *v2; // rax
  __int64 result; // rax
  CElementModification *v4; // rcx
  const char *v5; // [rsp+20h] [rbp-30h] BYREF
  const char *v6; // [rsp+28h] [rbp-28h]
  __int64 v7; // [rsp+30h] [rbp-20h]
  const char *v8; // [rsp+38h] [rbp-18h]
  int v9; // [rsp+40h] [rbp-10h] BYREF

  v9 = 0;
  if ( !a1 )
  {
    v7 = 1838;
    v5 = "onecore\\base\\xml\\udom_modify.cpp";
    v6 = "Windows::uDom::Rtl::RtlMicrodomUpdateRemoveElement";
    v2 = "RtlIsMicrodomUpdateContextValid(HostUpdate)";
LABEL_3:
    v8 = v2;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v9,
             &v5);
  }
  if ( !a2 )
  {
    v7 = 1839;
    v5 = "onecore\\base\\xml\\udom_modify.cpp";
    v6 = "Windows::uDom::Rtl::RtlMicrodomUpdateRemoveElement";
    v2 = "pToRemove != 0";
    goto LABEL_3;
  }
  v4 = *(CElementModification **)(*((_QWORD *)a2 + 7) + 112LL);
  if ( !v4 )
    return 0;
  result = CElementModification::RemoveChild(v4, a2);
  if ( (int)result >= 0 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x18005d9f0  push    rbp
0x18005d9f2  mov     rbp, rsp
0x18005d9f5  sub     rsp, 50h
0x18005d9f9  mov     rax, cs:__security_cookie
0x18005da00  xor     rax, rsp
0x18005da03  mov     [rbp+var_8], rax
0x18005da07  mov     [rbp+var_10], 0
0x18005da0e  test    rcx, rcx
0x18005da11  jnz     short loc_18005DA4B
0x18005da13  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005da1a  mov     [rbp+var_20], 72Eh
0x18005da22  mov     [rbp+var_30], rax
0x18005da26  lea     rax, aWindowsUdomRtl_1; "Windows::uDom::Rtl::RtlMicrodomUpdateRe"...
0x18005da2d  mov     [rbp+var_28], rax
0x18005da31  lea     rax, aRtlismicrodomu_0; "RtlIsMicrodomUpdateContextValid(HostUpd"...
0x18005da38  lea     rdx, [rbp+var_30]
0x18005da3c  mov     [rbp+var_18], rax
0x18005da40  lea     rcx, [rbp+var_10]
0x18005da44  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005da49  jmp     short loc_18005DA8F
0x18005da4b  test    rdx, rdx
0x18005da4e  jnz     short loc_18005DA77
0x18005da50  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005da57  mov     [rbp+var_20], 72Fh
0x18005da5f  mov     [rbp+var_30], rax
0x18005da63  lea     rax, aWindowsUdomRtl_1; "Windows::uDom::Rtl::RtlMicrodomUpdateRe"...
0x18005da6a  mov     [rbp+var_28], rax
0x18005da6e  lea     rax, aPtoremove0; "pToRemove != 0"
0x18005da75  jmp     short loc_18005DA38
0x18005da77  mov     rax, [rdx+38h]
0x18005da7b  mov     rcx, [rax+70h]; this
0x18005da7f  test    rcx, rcx
0x18005da82  jz      short loc_18005DA8D
0x18005da84  call    ?RemoveChild@CElementModification@@QEAAJPEAVCChildNode@@@Z; CElementModification::RemoveChild(CChildNode *)
0x18005da89  test    eax, eax
0x18005da8b  js      short loc_18005DA8F
0x18005da8d  xor     eax, eax
0x18005da8f  mov     rcx, [rbp+var_8]
0x18005da93  xor     rcx, rsp; StackCookie
0x18005da96  call    __security_check_cookie
0x18005da9b  add     rsp, 50h
0x18005da9f  pop     rbp
0x18005daa0  retn
```
