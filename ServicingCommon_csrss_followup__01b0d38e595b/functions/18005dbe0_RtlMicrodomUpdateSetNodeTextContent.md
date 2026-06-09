# RtlMicrodomUpdateSetNodeTextContent

- ea: `0x18005dbe0`
- end: `0x18005dd0a`
- name: `RtlMicrodomUpdateSetNodeTextContent`
- size: `298`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180002630`
- `0x18001f1d8`
- `0x18002d2b0`
- `0x18005dbe0`
- `0x18009e020`

## string_xrefs

- `0x18005dc0b`: `onecore\base\xml\udom_modify.cpp`
- `0x18005dc4b`: `onecore\base\xml\udom_modify.cpp`
- `0x18005dc83`: `onecore\base\xml\udom_modify.cpp`
- `0x18005dcb3`: `onecore\base\xml\udom_modify.cpp`
- `0x18005dc29`: `RtlIsMicrodomUpdateContextValid(HostUpdate)`
- `0x18005dc1e`: `Windows::uDom::Rtl::RtlMicrodomUpdateSetNodeTextContent`
- `0x18005dc5e`: `Windows::uDom::Rtl::RtlMicrodomUpdateSetNodeTextContent`
- `0x18005dc96`: `Windows::uDom::Rtl::RtlMicrodomUpdateSetNodeTextContent`
- `0x18005dcc6`: `Windows::uDom::Rtl::RtlMicrodomUpdateSetNodeTextContent`

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
0x18005dbe0  push    rbp
0x18005dbe2  push    rbx
0x18005dbe3  push    rdi
0x18005dbe4  mov     rbp, rsp
0x18005dbe7  sub     rsp, 50h
0x18005dbeb  mov     rax, cs:__security_cookie
0x18005dbf2  xor     rax, rsp
0x18005dbf5  mov     [rbp+var_8], rax
0x18005dbf9  mov     [rbp+var_10], 0
0x18005dc00  mov     rdi, r8
0x18005dc03  mov     rbx, rdx
0x18005dc06  test    rcx, rcx
0x18005dc09  jnz     short loc_18005DC46
0x18005dc0b  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005dc12  mov     [rbp+var_20], 68Dh
0x18005dc1a  mov     [rbp+var_30], rax
0x18005dc1e  lea     rax, aWindowsUdomRtl_9; "Windows::uDom::Rtl::RtlMicrodomUpdateSe"...
0x18005dc25  mov     [rbp+var_28], rax
0x18005dc29  lea     rax, aRtlismicrodomu_0; "RtlIsMicrodomUpdateContextValid(HostUpd"...
0x18005dc30  lea     rdx, [rbp+var_30]
0x18005dc34  mov     [rbp+var_18], rax
0x18005dc38  lea     rcx, [rbp+var_10]
0x18005dc3c  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005dc41  jmp     loc_18005DCF5
0x18005dc46  test    rbx, rbx
0x18005dc49  jnz     short loc_18005DC72
0x18005dc4b  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005dc52  mov     [rbp+var_20], 68Eh
0x18005dc5a  mov     [rbp+var_30], rax
0x18005dc5e  lea     rax, aWindowsUdomRtl_9; "Windows::uDom::Rtl::RtlMicrodomUpdateSe"...
0x18005dc65  mov     [rbp+var_28], rax
0x18005dc69  lea     rax, aObjectcookieOp; "ObjectCookie.Opaque != 0"
0x18005dc70  jmp     short loc_18005DC30
0x18005dc72  test    rdi, rdi
0x18005dc75  jz      short loc_18005DCAA
0x18005dc77  mov     rcx, rdi
0x18005dc7a  call    RtlIsLUtf8StringValid
0x18005dc7f  test    al, al
0x18005dc81  jnz     short loc_18005DCAA
0x18005dc83  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005dc8a  mov     [rbp+var_20], 68Fh
0x18005dc92  mov     [rbp+var_30], rax
0x18005dc96  lea     rax, aWindowsUdomRtl_9; "Windows::uDom::Rtl::RtlMicrodomUpdateSe"...
0x18005dc9d  mov     [rbp+var_28], rax
0x18005dca1  lea     rax, aValue0Rtlislut; "(Value == 0) || RtlIsLUtf8StringValid(V"...
0x18005dca8  jmp     short loc_18005DC30
0x18005dcaa  mov     rcx, [rbx+38h]
0x18005dcae  test    rcx, rcx
0x18005dcb1  jnz     short loc_18005DCDD
0x18005dcb3  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005dcba  mov     [rbp+var_20], 691h
0x18005dcc2  mov     [rbp+var_30], rax
0x18005dcc6  lea     rax, aWindowsUdomRtl_9; "Windows::uDom::Rtl::RtlMicrodomUpdateSe"...
0x18005dccd  mov     [rbp+var_28], rax
0x18005dcd1  lea     rax, aPchildPbasicno; "pChild->pBasicNode != 0"
0x18005dcd8  jmp     loc_18005DC30
0x18005dcdd  mov     rax, [rcx]
0x18005dce0  mov     rdx, rdi
0x18005dce3  mov     rax, [rax+48h]
0x18005dce7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dcec  xor     ecx, ecx
0x18005dcee  test    eax, eax
0x18005dcf0  cmovs   ecx, eax
0x18005dcf3  mov     eax, ecx
0x18005dcf5  mov     rcx, [rbp+var_8]
0x18005dcf9  xor     rcx, rsp; StackCookie
0x18005dcfc  call    __security_check_cookie
0x18005dd01  add     rsp, 50h
0x18005dd05  pop     rdi
0x18005dd06  pop     rbx
0x18005dd07  pop     rbp
0x18005dd08  retn
```
