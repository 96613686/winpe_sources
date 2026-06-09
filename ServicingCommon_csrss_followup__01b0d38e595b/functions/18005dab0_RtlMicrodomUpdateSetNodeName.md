# RtlMicrodomUpdateSetNodeName

- ea: `0x18005dab0`
- end: `0x18005dbd5`
- name: `RtlMicrodomUpdateSetNodeName`
- size: `293`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180002630`
- `0x18001f1d8`
- `0x18002d2b0`
- `0x18005dab0`
- `0x18009e020`

## string_xrefs

- `0x18005dadb`: `onecore\base\xml\udom_modify.cpp`
- `0x18005db1b`: `onecore\base\xml\udom_modify.cpp`
- `0x18005db4e`: `onecore\base\xml\udom_modify.cpp`
- `0x18005db7e`: `onecore\base\xml\udom_modify.cpp`
- `0x18005daf9`: `RtlIsMicrodomUpdateContextValid(HostUpdate)`
- `0x18005daee`: `Windows::uDom::Rtl::RtlMicrodomUpdateSetNodeName`
- `0x18005db2e`: `Windows::uDom::Rtl::RtlMicrodomUpdateSetNodeName`
- `0x18005db61`: `Windows::uDom::Rtl::RtlMicrodomUpdateSetNodeName`
- `0x18005db91`: `Windows::uDom::Rtl::RtlMicrodomUpdateSetNodeName`

## pseudocode

```c
__int64 __fastcall RtlMicrodomUpdateSetNodeName(__int64 a1, __int64 a2, __int64 a3)
{
  const char *v5; // rax
  __int64 v7; // rcx
  int v8; // eax
  unsigned int v9; // ecx
  const char *v10; // [rsp+20h] [rbp-30h] BYREF
  const char *v11; // [rsp+28h] [rbp-28h]
  __int64 v12; // [rsp+30h] [rbp-20h]
  const char *v13; // [rsp+38h] [rbp-18h]
  int v14; // [rsp+40h] [rbp-10h] BYREF

  v14 = 0;
  if ( !a1 )
  {
    v12 = 1700;
    v10 = "onecore\\base\\xml\\udom_modify.cpp";
    v11 = "Windows::uDom::Rtl::RtlMicrodomUpdateSetNodeName";
    v5 = "RtlIsMicrodomUpdateContextValid(HostUpdate)";
LABEL_3:
    v13 = v5;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v14,
             &v10);
  }
  if ( !a2 )
  {
    v12 = 1701;
    v10 = "onecore\\base\\xml\\udom_modify.cpp";
    v11 = "Windows::uDom::Rtl::RtlMicrodomUpdateSetNodeName";
    v5 = "ObjectCookie.Opaque != 0";
    goto LABEL_3;
  }
  if ( !(unsigned __int8)RtlIsLUtf8StringValid(a3) )
  {
    v12 = 1702;
    v10 = "onecore\\base\\xml\\udom_modify.cpp";
    v11 = "Windows::uDom::Rtl::RtlMicrodomUpdateSetNodeName";
    v5 = "RtlIsLUtf8StringValid(Name)";
    goto LABEL_3;
  }
  v7 = *(_QWORD *)(a2 + 56);
  if ( !v7 )
  {
    v12 = 1704;
    v10 = "onecore\\base\\xml\\udom_modify.cpp";
    v11 = "Windows::uDom::Rtl::RtlMicrodomUpdateSetNodeName";
    v5 = "pChild->pBasicNode != 0";
    goto LABEL_3;
  }
  v8 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v7 + 48LL))(v7, a3);
  v9 = 0;
  if ( v8 < 0 )
    return (unsigned int)v8;
  return v9;
}

```

## disassembly

```asm
0x18005dab0  push    rbp
0x18005dab2  push    rbx
0x18005dab3  push    rdi
0x18005dab4  mov     rbp, rsp
0x18005dab7  sub     rsp, 50h
0x18005dabb  mov     rax, cs:__security_cookie
0x18005dac2  xor     rax, rsp
0x18005dac5  mov     [rbp+var_8], rax
0x18005dac9  mov     [rbp+var_10], 0
0x18005dad0  mov     rdi, r8
0x18005dad3  mov     rbx, rdx
0x18005dad6  test    rcx, rcx
0x18005dad9  jnz     short loc_18005DB16
0x18005dadb  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005dae2  mov     [rbp+var_20], 6A4h
0x18005daea  mov     [rbp+var_30], rax
0x18005daee  lea     rax, aWindowsUdomRtl; "Windows::uDom::Rtl::RtlMicrodomUpdateSe"...
0x18005daf5  mov     [rbp+var_28], rax
0x18005daf9  lea     rax, aRtlismicrodomu_0; "RtlIsMicrodomUpdateContextValid(HostUpd"...
0x18005db00  lea     rdx, [rbp+var_30]
0x18005db04  mov     [rbp+var_18], rax
0x18005db08  lea     rcx, [rbp+var_10]
0x18005db0c  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005db11  jmp     loc_18005DBC0
0x18005db16  test    rbx, rbx
0x18005db19  jnz     short loc_18005DB42
0x18005db1b  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005db22  mov     [rbp+var_20], 6A5h
0x18005db2a  mov     [rbp+var_30], rax
0x18005db2e  lea     rax, aWindowsUdomRtl; "Windows::uDom::Rtl::RtlMicrodomUpdateSe"...
0x18005db35  mov     [rbp+var_28], rax
0x18005db39  lea     rax, aObjectcookieOp; "ObjectCookie.Opaque != 0"
0x18005db40  jmp     short loc_18005DB00
0x18005db42  mov     rcx, rdi
0x18005db45  call    RtlIsLUtf8StringValid
0x18005db4a  test    al, al
0x18005db4c  jnz     short loc_18005DB75
0x18005db4e  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005db55  mov     [rbp+var_20], 6A6h
0x18005db5d  mov     [rbp+var_30], rax
0x18005db61  lea     rax, aWindowsUdomRtl; "Windows::uDom::Rtl::RtlMicrodomUpdateSe"...
0x18005db68  mov     [rbp+var_28], rax
0x18005db6c  lea     rax, aRtlislutf8stri_13; "RtlIsLUtf8StringValid(Name)"
0x18005db73  jmp     short loc_18005DB00
0x18005db75  mov     rcx, [rbx+38h]
0x18005db79  test    rcx, rcx
0x18005db7c  jnz     short loc_18005DBA8
0x18005db7e  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005db85  mov     [rbp+var_20], 6A8h
0x18005db8d  mov     [rbp+var_30], rax
0x18005db91  lea     rax, aWindowsUdomRtl; "Windows::uDom::Rtl::RtlMicrodomUpdateSe"...
0x18005db98  mov     [rbp+var_28], rax
0x18005db9c  lea     rax, aPchildPbasicno; "pChild->pBasicNode != 0"
0x18005dba3  jmp     loc_18005DB00
0x18005dba8  mov     rax, [rcx]
0x18005dbab  mov     rdx, rdi
0x18005dbae  mov     rax, [rax+30h]
0x18005dbb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dbb7  xor     ecx, ecx
0x18005dbb9  test    eax, eax
0x18005dbbb  cmovs   ecx, eax
0x18005dbbe  mov     eax, ecx
0x18005dbc0  mov     rcx, [rbp+var_8]
0x18005dbc4  xor     rcx, rsp; StackCookie
0x18005dbc7  call    __security_check_cookie
0x18005dbcc  add     rsp, 50h
0x18005dbd0  pop     rdi
0x18005dbd1  pop     rbx
0x18005dbd2  pop     rbp
0x18005dbd3  retn
```
