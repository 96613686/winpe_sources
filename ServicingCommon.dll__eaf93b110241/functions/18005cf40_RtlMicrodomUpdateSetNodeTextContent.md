# RtlMicrodomUpdateSetNodeTextContent

- ea: `0x18005cf40`
- end: `0x18005d06a`
- name: `RtlMicrodomUpdateSetNodeTextContent`
- size: `298`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000f860`
- `0x18001f4ac`
- `0x1800293a0`
- `0x18005cf40`
- `0x1800a0020`

## string_xrefs

- `0x18005cf6b`: `onecore\base\xml\udom_modify.cpp`
- `0x18005cfab`: `onecore\base\xml\udom_modify.cpp`
- `0x18005cfe3`: `onecore\base\xml\udom_modify.cpp`
- `0x18005d013`: `onecore\base\xml\udom_modify.cpp`
- `0x18005cf89`: `RtlIsMicrodomUpdateContextValid(HostUpdate)`
- `0x18005cf7e`: `Windows::uDom::Rtl::RtlMicrodomUpdateSetNodeTextContent`
- `0x18005cfbe`: `Windows::uDom::Rtl::RtlMicrodomUpdateSetNodeTextContent`
- `0x18005cff6`: `Windows::uDom::Rtl::RtlMicrodomUpdateSetNodeTextContent`
- `0x18005d026`: `Windows::uDom::Rtl::RtlMicrodomUpdateSetNodeTextContent`

## pseudocode

```c
__int64 __fastcall RtlMicrodomUpdateSetNodeTextContent(__int64 a1, __int64 a2, __int64 a3)
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
    v12 = 1677;
    v10 = "onecore\\base\\xml\\udom_modify.cpp";
    v11 = "Windows::uDom::Rtl::RtlMicrodomUpdateSetNodeTextContent";
    v5 = "RtlIsMicrodomUpdateContextValid(HostUpdate)";
LABEL_3:
    v13 = v5;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v14,
             &v10);
  }
  if ( !a2 )
  {
    v12 = 1678;
    v10 = "onecore\\base\\xml\\udom_modify.cpp";
    v11 = "Windows::uDom::Rtl::RtlMicrodomUpdateSetNodeTextContent";
    v5 = "ObjectCookie.Opaque != 0";
    goto LABEL_3;
  }
  if ( a3 && !(unsigned __int8)RtlIsLUtf8StringValid(a3) )
  {
    v12 = 1679;
    v10 = "onecore\\base\\xml\\udom_modify.cpp";
    v11 = "Windows::uDom::Rtl::RtlMicrodomUpdateSetNodeTextContent";
    v5 = "(Value == 0) || RtlIsLUtf8StringValid(Value)";
    goto LABEL_3;
  }
  v7 = *(_QWORD *)(a2 + 56);
  if ( !v7 )
  {
    v12 = 1681;
    v10 = "onecore\\base\\xml\\udom_modify.cpp";
    v11 = "Windows::uDom::Rtl::RtlMicrodomUpdateSetNodeTextContent";
    v5 = "pChild->pBasicNode != 0";
    goto LABEL_3;
  }
  v8 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v7 + 72LL))(v7, a3);
  v9 = 0;
  if ( v8 < 0 )
    return (unsigned int)v8;
  return v9;
}

```

## disassembly

```asm
0x18005cf40  push    rbp
0x18005cf42  push    rbx
0x18005cf43  push    rdi
0x18005cf44  mov     rbp, rsp
0x18005cf47  sub     rsp, 50h
0x18005cf4b  mov     rax, cs:__security_cookie
0x18005cf52  xor     rax, rsp
0x18005cf55  mov     [rbp+var_8], rax
0x18005cf59  mov     [rbp+var_10], 0
0x18005cf60  mov     rdi, r8
0x18005cf63  mov     rbx, rdx
0x18005cf66  test    rcx, rcx
0x18005cf69  jnz     short loc_18005CFA6
0x18005cf6b  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005cf72  mov     [rbp+var_20], 68Dh
0x18005cf7a  mov     [rbp+var_30], rax
0x18005cf7e  lea     rax, aWindowsUdomRtl_9; "Windows::uDom::Rtl::RtlMicrodomUpdateSe"...
0x18005cf85  mov     [rbp+var_28], rax
0x18005cf89  lea     rax, aRtlismicrodomu_0; "RtlIsMicrodomUpdateContextValid(HostUpd"...
0x18005cf90  lea     rdx, [rbp+var_30]
0x18005cf94  mov     [rbp+var_18], rax
0x18005cf98  lea     rcx, [rbp+var_10]
0x18005cf9c  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005cfa1  jmp     loc_18005D055
0x18005cfa6  test    rbx, rbx
0x18005cfa9  jnz     short loc_18005CFD2
0x18005cfab  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005cfb2  mov     [rbp+var_20], 68Eh
0x18005cfba  mov     [rbp+var_30], rax
0x18005cfbe  lea     rax, aWindowsUdomRtl_9; "Windows::uDom::Rtl::RtlMicrodomUpdateSe"...
0x18005cfc5  mov     [rbp+var_28], rax
0x18005cfc9  lea     rax, aObjectcookieOp; "ObjectCookie.Opaque != 0"
0x18005cfd0  jmp     short loc_18005CF90
0x18005cfd2  test    rdi, rdi
0x18005cfd5  jz      short loc_18005D00A
0x18005cfd7  mov     rcx, rdi
0x18005cfda  call    RtlIsLUtf8StringValid
0x18005cfdf  test    al, al
0x18005cfe1  jnz     short loc_18005D00A
0x18005cfe3  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005cfea  mov     [rbp+var_20], 68Fh
0x18005cff2  mov     [rbp+var_30], rax
0x18005cff6  lea     rax, aWindowsUdomRtl_9; "Windows::uDom::Rtl::RtlMicrodomUpdateSe"...
0x18005cffd  mov     [rbp+var_28], rax
0x18005d001  lea     rax, aValue0Rtlislut; "(Value == 0) || RtlIsLUtf8StringValid(V"...
0x18005d008  jmp     short loc_18005CF90
0x18005d00a  mov     rcx, [rbx+38h]
0x18005d00e  test    rcx, rcx
0x18005d011  jnz     short loc_18005D03D
0x18005d013  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005d01a  mov     [rbp+var_20], 691h
0x18005d022  mov     [rbp+var_30], rax
0x18005d026  lea     rax, aWindowsUdomRtl_9; "Windows::uDom::Rtl::RtlMicrodomUpdateSe"...
0x18005d02d  mov     [rbp+var_28], rax
0x18005d031  lea     rax, aPchildPbasicno; "pChild->pBasicNode != 0"
0x18005d038  jmp     loc_18005CF90
0x18005d03d  mov     rax, [rcx]
0x18005d040  mov     rdx, rdi
0x18005d043  mov     rax, [rax+48h]
0x18005d047  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d04c  xor     ecx, ecx
0x18005d04e  test    eax, eax
0x18005d050  cmovs   ecx, eax
0x18005d053  mov     eax, ecx
0x18005d055  mov     rcx, [rbp+var_8]
0x18005d059  xor     rcx, rsp; StackCookie
0x18005d05c  call    __security_check_cookie
0x18005d061  add     rsp, 50h
0x18005d065  pop     rdi
0x18005d066  pop     rbx
0x18005d067  pop     rbp
0x18005d068  retn
```
