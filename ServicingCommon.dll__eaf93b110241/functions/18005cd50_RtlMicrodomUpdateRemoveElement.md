# RtlMicrodomUpdateRemoveElement

- ea: `0x18005cd50`
- end: `0x18005ce02`
- name: `RtlMicrodomUpdateRemoveElement`
- size: `178`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18001f4ac`
- `0x1800293a0`
- `0x18005b57c`
- `0x18005cd50`

## string_xrefs

- `0x18005cd73`: `onecore\base\xml\udom_modify.cpp`
- `0x18005cdb0`: `onecore\base\xml\udom_modify.cpp`
- `0x18005cd91`: `RtlIsMicrodomUpdateContextValid(HostUpdate)`
- `0x18005cdce`: `pToRemove != 0`
- `0x18005cd86`: `Windows::uDom::Rtl::RtlMicrodomUpdateRemoveElement`
- `0x18005cdc3`: `Windows::uDom::Rtl::RtlMicrodomUpdateRemoveElement`

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
0x18005cd50  push    rbp
0x18005cd52  mov     rbp, rsp
0x18005cd55  sub     rsp, 50h
0x18005cd59  mov     rax, cs:__security_cookie
0x18005cd60  xor     rax, rsp
0x18005cd63  mov     [rbp+var_8], rax
0x18005cd67  mov     [rbp+var_10], 0
0x18005cd6e  test    rcx, rcx
0x18005cd71  jnz     short loc_18005CDAB
0x18005cd73  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005cd7a  mov     [rbp+var_20], 72Eh
0x18005cd82  mov     [rbp+var_30], rax
0x18005cd86  lea     rax, aWindowsUdomRtl_1; "Windows::uDom::Rtl::RtlMicrodomUpdateRe"...
0x18005cd8d  mov     [rbp+var_28], rax
0x18005cd91  lea     rax, aRtlismicrodomu_0; "RtlIsMicrodomUpdateContextValid(HostUpd"...
0x18005cd98  lea     rdx, [rbp+var_30]
0x18005cd9c  mov     [rbp+var_18], rax
0x18005cda0  lea     rcx, [rbp+var_10]
0x18005cda4  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005cda9  jmp     short loc_18005CDEF
0x18005cdab  test    rdx, rdx
0x18005cdae  jnz     short loc_18005CDD7
0x18005cdb0  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005cdb7  mov     [rbp+var_20], 72Fh
0x18005cdbf  mov     [rbp+var_30], rax
0x18005cdc3  lea     rax, aWindowsUdomRtl_1; "Windows::uDom::Rtl::RtlMicrodomUpdateRe"...
0x18005cdca  mov     [rbp+var_28], rax
0x18005cdce  lea     rax, aPtoremove0; "pToRemove != 0"
0x18005cdd5  jmp     short loc_18005CD98
0x18005cdd7  mov     rax, [rdx+38h]
0x18005cddb  mov     rcx, [rax+70h]; this
0x18005cddf  test    rcx, rcx
0x18005cde2  jz      short loc_18005CDED
0x18005cde4  call    ?RemoveChild@CElementModification@@QEAAJPEAVCChildNode@@@Z; CElementModification::RemoveChild(CChildNode *)
0x18005cde9  test    eax, eax
0x18005cdeb  js      short loc_18005CDEF
0x18005cded  xor     eax, eax
0x18005cdef  mov     rcx, [rbp+var_8]
0x18005cdf3  xor     rcx, rsp; StackCookie
0x18005cdf6  call    __security_check_cookie
0x18005cdfb  add     rsp, 50h
0x18005cdff  pop     rbp
0x18005ce00  retn
```
