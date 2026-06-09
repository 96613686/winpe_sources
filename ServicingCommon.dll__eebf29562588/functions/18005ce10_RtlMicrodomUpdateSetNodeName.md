# RtlMicrodomUpdateSetNodeName

- ea: `0x18005ce10`
- end: `0x18005cf35`
- name: `RtlMicrodomUpdateSetNodeName`
- size: `293`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000f860`
- `0x18001f4ac`
- `0x1800293a0`
- `0x18005ce10`
- `0x1800a0020`

## string_xrefs

- `0x18005ce3b`: `onecore\base\xml\udom_modify.cpp`
- `0x18005ce7b`: `onecore\base\xml\udom_modify.cpp`
- `0x18005ceae`: `onecore\base\xml\udom_modify.cpp`
- `0x18005cede`: `onecore\base\xml\udom_modify.cpp`
- `0x18005ce59`: `RtlIsMicrodomUpdateContextValid(HostUpdate)`
- `0x18005ce4e`: `Windows::uDom::Rtl::RtlMicrodomUpdateSetNodeName`
- `0x18005ce8e`: `Windows::uDom::Rtl::RtlMicrodomUpdateSetNodeName`
- `0x18005cec1`: `Windows::uDom::Rtl::RtlMicrodomUpdateSetNodeName`
- `0x18005cef1`: `Windows::uDom::Rtl::RtlMicrodomUpdateSetNodeName`

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
0x18005ce10  push    rbp
0x18005ce12  push    rbx
0x18005ce13  push    rdi
0x18005ce14  mov     rbp, rsp
0x18005ce17  sub     rsp, 50h
0x18005ce1b  mov     rax, cs:__security_cookie
0x18005ce22  xor     rax, rsp
0x18005ce25  mov     [rbp+var_8], rax
0x18005ce29  mov     [rbp+var_10], 0
0x18005ce30  mov     rdi, r8
0x18005ce33  mov     rbx, rdx
0x18005ce36  test    rcx, rcx
0x18005ce39  jnz     short loc_18005CE76
0x18005ce3b  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005ce42  mov     [rbp+var_20], 6A4h
0x18005ce4a  mov     [rbp+var_30], rax
0x18005ce4e  lea     rax, aWindowsUdomRtl; "Windows::uDom::Rtl::RtlMicrodomUpdateSe"...
0x18005ce55  mov     [rbp+var_28], rax
0x18005ce59  lea     rax, aRtlismicrodomu_0; "RtlIsMicrodomUpdateContextValid(HostUpd"...
0x18005ce60  lea     rdx, [rbp+var_30]
0x18005ce64  mov     [rbp+var_18], rax
0x18005ce68  lea     rcx, [rbp+var_10]
0x18005ce6c  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005ce71  jmp     loc_18005CF20
0x18005ce76  test    rbx, rbx
0x18005ce79  jnz     short loc_18005CEA2
0x18005ce7b  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005ce82  mov     [rbp+var_20], 6A5h
0x18005ce8a  mov     [rbp+var_30], rax
0x18005ce8e  lea     rax, aWindowsUdomRtl; "Windows::uDom::Rtl::RtlMicrodomUpdateSe"...
0x18005ce95  mov     [rbp+var_28], rax
0x18005ce99  lea     rax, aObjectcookieOp; "ObjectCookie.Opaque != 0"
0x18005cea0  jmp     short loc_18005CE60
0x18005cea2  mov     rcx, rdi
0x18005cea5  call    RtlIsLUtf8StringValid
0x18005ceaa  test    al, al
0x18005ceac  jnz     short loc_18005CED5
0x18005ceae  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005ceb5  mov     [rbp+var_20], 6A6h
0x18005cebd  mov     [rbp+var_30], rax
0x18005cec1  lea     rax, aWindowsUdomRtl; "Windows::uDom::Rtl::RtlMicrodomUpdateSe"...
0x18005cec8  mov     [rbp+var_28], rax
0x18005cecc  lea     rax, aRtlislutf8stri_13; "RtlIsLUtf8StringValid(Name)"
0x18005ced3  jmp     short loc_18005CE60
0x18005ced5  mov     rcx, [rbx+38h]
0x18005ced9  test    rcx, rcx
0x18005cedc  jnz     short loc_18005CF08
0x18005cede  lea     rax, aOnecoreBaseXml_0; "onecore\\base\\xml\\udom_modify.cpp"
0x18005cee5  mov     [rbp+var_20], 6A8h
0x18005ceed  mov     [rbp+var_30], rax
0x18005cef1  lea     rax, aWindowsUdomRtl; "Windows::uDom::Rtl::RtlMicrodomUpdateSe"...
0x18005cef8  mov     [rbp+var_28], rax
0x18005cefc  lea     rax, aPchildPbasicno; "pChild->pBasicNode != 0"
0x18005cf03  jmp     loc_18005CE60
0x18005cf08  mov     rax, [rcx]
0x18005cf0b  mov     rdx, rdi
0x18005cf0e  mov     rax, [rax+30h]
0x18005cf12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cf17  xor     ecx, ecx
0x18005cf19  test    eax, eax
0x18005cf1b  cmovs   ecx, eax
0x18005cf1e  mov     eax, ecx
0x18005cf20  mov     rcx, [rbp+var_8]
0x18005cf24  xor     rcx, rsp; StackCookie
0x18005cf27  call    __security_check_cookie
0x18005cf2c  add     rsp, 50h
0x18005cf30  pop     rdi
0x18005cf31  pop     rbx
0x18005cf32  pop     rbp
0x18005cf33  retn
```
