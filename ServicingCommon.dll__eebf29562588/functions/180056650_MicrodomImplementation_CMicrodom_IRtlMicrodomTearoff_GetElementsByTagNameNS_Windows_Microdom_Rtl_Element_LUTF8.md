# MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetElementsByTagNameNS(Windows::Microdom::Rtl::Element,_LUTF8_STRING const *,_LUTF8_STRING const *,Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>> *)

- ea: `0x180056650`
- end: `0x1800567f8`
- name: `?GetElementsByTagNameNS@CMicrodom_IRtlMicrodomTearoff@MicrodomImplementation@@UEAAJUElement@Rtl@Microdom@Windows@@PEBU_LUTF8_STRING@@1PEAV?$Auto@U?$Vector@UElement@Rtl@Microdom@Windows@@@Windows@@@6@@Z`
- size: `424`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000f860`
- `0x18001f4ac`
- `0x1800293a0`
- `0x180053f74`
- `0x180055c60`
- `0x180056650`

## string_xrefs

- `0x1800566a2`: `onecore\base\xml\udom_microdom.cpp`
- `0x1800566dd`: `onecore\base\xml\udom_microdom.cpp`
- `0x180056726`: `onecore\base\xml\udom_microdom.cpp`
- `0x18005675a`: `onecore\base\xml\udom_microdom.cpp`
- `0x1800566ff`: `RtlIsLUtf8StringValid(NamespaceURI)`

## pseudocode

```c
__int64 __fastcall MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetElementsByTagNameNS(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int128 *a5)
{
  int v5; // r14d
  int v7; // edi
  _QWORD *v9; // rdx
  int ElementsByTagName; // eax
  unsigned int v11; // ebx
  __int128 v12; // xmm0
  __int128 v14; // [rsp+30h] [rbp-81h] BYREF
  _QWORD v15[4]; // [rsp+40h] [rbp-71h] BYREF
  _QWORD v16[4]; // [rsp+60h] [rbp-51h] BYREF
  _QWORD v17[4]; // [rsp+80h] [rbp-31h] BYREF
  _QWORD v18[4]; // [rsp+A0h] [rbp-11h] BYREF
  int v19; // [rsp+C0h] [rbp+Fh] BYREF

  v5 = *(_DWORD *)(a2 + 8);
  v7 = a3;
  v19 = 0;
  v14 = 0u;
  if ( v5 == -1 )
  {
    v15[2] = 3393;
    v15[0] = "onecore\\base\\xml\\udom_microdom.cpp";
    v9 = v15;
    v15[1] = "MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetElementsByTagNameNS";
    v15[3] = "TheElement != TheElement.InvalidValue()";
LABEL_5:
    ElementsByTagName = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
                          &v19,
                          v9);
    goto LABEL_6;
  }
  if ( !(unsigned __int8)RtlIsLUtf8StringValid(a3) )
  {
    v16[2] = 3394;
    v16[0] = "onecore\\base\\xml\\udom_microdom.cpp";
    v9 = v16;
    v16[1] = "MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetElementsByTagNameNS";
    v16[3] = "RtlIsLUtf8StringValid(NamespaceURI)";
    goto LABEL_5;
  }
  if ( !(unsigned __int8)RtlIsLUtf8StringValid(a4) )
  {
    v17[2] = 3395;
    v17[0] = "onecore\\base\\xml\\udom_microdom.cpp";
    v9 = v17;
    v17[1] = "MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetElementsByTagNameNS";
    v17[3] = "RtlIsLUtf8StringValid(LocalName)";
    goto LABEL_5;
  }
  if ( a5 )
  {
    ElementsByTagName = MicrodomImplementation::CMicrodom::GetElementsByTagName(
                          *(_QWORD *)(a1 - 8),
                          v5,
                          v7,
                          a4,
                          1,
                          (__int64)&v14);
    if ( ElementsByTagName >= 0 )
    {
      v12 = *a5;
      *a5 = v14;
      v11 = 0;
      v14 = v12;
      goto LABEL_13;
    }
  }
  else
  {
    v18[2] = 3396;
    v18[0] = "onecore\\base\\xml\\udom_microdom.cpp";
    v18[1] = "MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetElementsByTagNameNS";
    v18[3] = "Not-null check failed: Matches";
    ElementsByTagName = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
                          &v19,
                          v18);
  }
LABEL_6:
  v11 = ElementsByTagName;
LABEL_13:
  Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>((__int64)&v14);
  return v11;
}

```

## disassembly

```asm
0x180056650  push    rbp
0x180056652  push    rbx
0x180056653  push    rsi
0x180056654  push    rdi
0x180056655  push    r14
0x180056657  push    r15
0x180056659  lea     rbp, [rsp-27h]
0x18005665e  sub     rsp, 0D8h
0x180056665  mov     rax, cs:__security_cookie
0x18005666c  xor     rax, rsp
0x18005666f  mov     [rbp+4Fh+var_38], rax
0x180056673  mov     r14d, [rdx+8]
0x180056677  mov     rsi, r9
0x18005667a  mov     rbx, [rbp+4Fh+arg_20]
0x18005667e  mov     rdi, r8
0x180056681  mov     [rbp+4Fh+var_40], 0
0x180056688  mov     r15, rcx
0x18005668b  mov     qword ptr [rsp+100h+var_D0], 0
0x180056694  mov     qword ptr [rbp+4Fh+var_D0+8], 0
0x18005669c  cmp     r14d, 0FFFFFFFFh
0x1800566a0  jnz     short loc_1800566D1
0x1800566a2  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x1800566a9  mov     [rbp+4Fh+var_B0], 0D41h
0x1800566b1  mov     [rbp+4Fh+var_C0], rax
0x1800566b5  lea     rdx, [rbp+4Fh+var_C0]
0x1800566b9  lea     rax, aMicrodomimplem_34; "MicrodomImplementation::CMicrodom_IRtlM"...
0x1800566c0  mov     [rbp+4Fh+var_B8], rax
0x1800566c4  lea     rax, aTheelementThee; "TheElement != TheElement.InvalidValue()"
0x1800566cb  mov     [rbp+4Fh+var_A8], rax
0x1800566cf  jmp     short loc_18005670A
0x1800566d1  mov     rcx, rdi
0x1800566d4  call    RtlIsLUtf8StringValid
0x1800566d9  test    al, al
0x1800566db  jnz     short loc_18005671A
0x1800566dd  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x1800566e4  mov     [rbp+4Fh+var_90], 0D42h
0x1800566ec  mov     [rbp+4Fh+var_A0], rax
0x1800566f0  lea     rdx, [rbp+4Fh+var_A0]
0x1800566f4  lea     rax, aMicrodomimplem_34; "MicrodomImplementation::CMicrodom_IRtlM"...
0x1800566fb  mov     [rbp+4Fh+var_98], rax
0x1800566ff  lea     rax, aRtlislutf8stri_12; "RtlIsLUtf8StringValid(NamespaceURI)"
0x180056706  mov     [rbp+4Fh+var_88], rax
0x18005670a  lea     rcx, [rbp+4Fh+var_40]
0x18005670e  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180056713  mov     ebx, eax
0x180056715  jmp     loc_1800567CF
0x18005671a  mov     rcx, rsi
0x18005671d  call    RtlIsLUtf8StringValid
0x180056722  test    al, al
0x180056724  jnz     short loc_180056755
0x180056726  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x18005672d  mov     [rbp+4Fh+var_70], 0D43h
0x180056735  mov     [rbp+4Fh+var_80], rax
0x180056739  lea     rdx, [rbp+4Fh+var_80]
0x18005673d  lea     rax, aMicrodomimplem_34; "MicrodomImplementation::CMicrodom_IRtlM"...
0x180056744  mov     [rbp+4Fh+var_78], rax
0x180056748  lea     rax, aRtlislutf8stri_0; "RtlIsLUtf8StringValid(LocalName)"
0x18005674f  mov     [rbp+4Fh+var_68], rax
0x180056753  jmp     short loc_18005670A
0x180056755  test    rbx, rbx
0x180056758  jnz     short loc_180056792
0x18005675a  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x180056761  mov     [rbp+4Fh+var_50], 0D44h
0x180056769  mov     [rbp+4Fh+var_60], rax
0x18005676d  lea     rdx, [rbp+4Fh+var_60]
0x180056771  lea     rax, aMicrodomimplem_34; "MicrodomImplementation::CMicrodom_IRtlM"...
0x180056778  mov     [rbp+4Fh+var_58], rax
0x18005677c  lea     rcx, [rbp+4Fh+var_40]
0x180056780  lea     rax, aNotNullCheckFa_121; "Not-null check failed: Matches"
0x180056787  mov     [rbp+4Fh+var_48], rax
0x18005678b  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180056790  jmp     short loc_180056713
0x180056792  mov     rcx, [r15-8]
0x180056796  lea     rax, [rsp+100h+var_D0]
0x18005679b  mov     [rsp+100h+var_D8], rax
0x1800567a0  mov     r9, rsi
0x1800567a3  mov     r8, rdi
0x1800567a6  mov     [rsp+100h+var_E0], 1
0x1800567ab  mov     edx, r14d
0x1800567ae  call    ?GetElementsByTagName@CMicrodom@MicrodomImplementation@@QEAAJKPEBU_LUTF8_STRING@@0_NPEAV?$Auto@U?$Vector@UElement@Rtl@Microdom@Windows@@@Windows@@@Windows@@@Z; MicrodomImplementation::CMicrodom::GetElementsByTagName(ulong,_LUTF8_STRING const *,_LUTF8_STRING const *,bool,Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Element>> *)
0x1800567b3  test    eax, eax
0x1800567b5  js      loc_180056713
0x1800567bb  movups  xmm0, xmmword ptr [rbx]
0x1800567be  movaps  xmm1, [rsp+100h+var_D0]
0x1800567c3  movdqu  xmmword ptr [rbx], xmm1
0x1800567c7  xor     ebx, ebx
0x1800567c9  movdqu  [rsp+100h+var_D0], xmm0
0x1800567cf  lea     rcx, [rsp+100h+var_D0]
0x1800567d4  call    ??1?$Auto@U?$Vector@UNode@Rtl@Microdom@Windows@@@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>::~Auto<Windows::Vector<Windows::Microdom::Rtl::Node>>(void)
0x1800567d9  mov     eax, ebx
0x1800567db  mov     rcx, [rbp+4Fh+var_38]
0x1800567df  xor     rcx, rsp; StackCookie
0x1800567e2  call    __security_check_cookie
0x1800567e7  add     rsp, 0D8h
0x1800567ee  pop     r15
0x1800567f0  pop     r14
0x1800567f2  pop     rdi
0x1800567f3  pop     rsi
0x1800567f4  pop     rbx
0x1800567f5  pop     rbp
0x1800567f6  retn
```
