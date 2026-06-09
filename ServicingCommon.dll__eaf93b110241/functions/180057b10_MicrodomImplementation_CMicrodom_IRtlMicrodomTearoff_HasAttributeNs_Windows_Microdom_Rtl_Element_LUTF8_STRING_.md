# MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::HasAttributeNs(Windows::Microdom::Rtl::Element,_LUTF8_STRING const *,_LUTF8_STRING const *,bool *)

- ea: `0x180057b10`
- end: `0x180057c95`
- name: `?HasAttributeNs@CMicrodom_IRtlMicrodomTearoff@MicrodomImplementation@@UEAAJUElement@Rtl@Microdom@Windows@@PEBU_LUTF8_STRING@@1PEA_N@Z`
- size: `389`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000f860`
- `0x18001f4ac`
- `0x1800293a0`
- `0x180057b10`
- `0x1800a0020`

## string_xrefs

- `0x180057b61`: `onecore\base\xml\udom_microdom.cpp`
- `0x180057ba8`: `onecore\base\xml\udom_microdom.cpp`
- `0x180057bdb`: `onecore\base\xml\udom_microdom.cpp`
- `0x180057c07`: `onecore\base\xml\udom_microdom.cpp`
- `0x180057bc6`: `RtlIsLUtf8StringValid(NamespaceURI)`

## pseudocode

```c
__int64 __fastcall MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::HasAttributeNs(
        __int64 a1,
        __int128 *a2,
        __int64 a3,
        __int64 a4,
        _BYTE *a5)
{
  const char *v9; // rax
  __int64 result; // rax
  __int64 (__fastcall *v11)(__int64, __int128 *, __int64, __int64, __int128 *); // rax
  __int128 v12; // [rsp+30h] [rbp-48h] BYREF
  __int64 v13; // [rsp+40h] [rbp-38h]
  const char *v14; // [rsp+48h] [rbp-30h]
  int v15; // [rsp+50h] [rbp-28h] BYREF
  __int128 v16; // [rsp+58h] [rbp-20h] BYREF

  v15 = 0;
  v16 = 0;
  DWORD2(v16) = -1;
  if ( a5 )
    *a5 = 0;
  if ( *((_DWORD *)a2 + 2) == -1 )
  {
    v13 = 3443;
    *(_QWORD *)&v12 = "onecore\\base\\xml\\udom_microdom.cpp";
    *((_QWORD *)&v12 + 1) = "MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::HasAttributeNs";
    v9 = "TheElement != TheElement.InvalidValue()";
LABEL_5:
    v14 = v9;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v15,
             &v12);
  }
  if ( !(unsigned __int8)RtlIsLUtf8StringValid(a3) )
  {
    v13 = 3444;
    *(_QWORD *)&v12 = "onecore\\base\\xml\\udom_microdom.cpp";
    *((_QWORD *)&v12 + 1) = "MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::HasAttributeNs";
    v9 = "RtlIsLUtf8StringValid(NamespaceURI)";
    goto LABEL_5;
  }
  if ( !(unsigned __int8)RtlIsLUtf8StringValid(a4) )
  {
    v13 = 3445;
    *(_QWORD *)&v12 = "onecore\\base\\xml\\udom_microdom.cpp";
    *((_QWORD *)&v12 + 1) = "MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::HasAttributeNs";
    v9 = "RtlIsLUtf8StringValid(LocalName)";
    goto LABEL_5;
  }
  if ( a5 )
  {
    v11 = *(__int64 (__fastcall **)(__int64, __int128 *, __int64, __int64, __int128 *))(*(_QWORD *)a1 + 288LL);
    v12 = *a2;
    result = v11(a1, &v12, a3, a4, &v16);
    if ( (int)result >= 0 )
    {
      if ( DWORD2(v16) != -1 )
        *a5 = 1;
      return 0;
    }
  }
  else
  {
    v13 = 3446;
    *(_QWORD *)&v12 = "onecore\\base\\xml\\udom_microdom.cpp";
    *((_QWORD *)&v12 + 1) = "MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::HasAttributeNs";
    v14 = "Not-null check failed: fHasAttribute";
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v15,
             &v12);
  }
  return result;
}

```

## disassembly

```asm
0x180057b10  push    rbp
0x180057b12  push    rbx
0x180057b13  push    rsi
0x180057b14  push    rdi
0x180057b15  push    r14
0x180057b17  push    r15
0x180057b19  mov     rbp, rsp
0x180057b1c  sub     rsp, 78h
0x180057b20  mov     rax, cs:__security_cookie
0x180057b27  xor     rax, rsp
0x180057b2a  mov     [rbp+var_10], rax
0x180057b2e  mov     rbx, [rbp+arg_20]
0x180057b32  xorps   xmm0, xmm0
0x180057b35  mov     [rbp+var_28], 0
0x180057b3c  mov     r14, r9
0x180057b3f  mov     rsi, r8
0x180057b42  mov     rdi, rdx
0x180057b45  mov     r15, rcx
0x180057b48  movups  [rbp+var_20], xmm0
0x180057b4c  mov     dword ptr [rbp+var_20+8], 0FFFFFFFFh
0x180057b53  test    rbx, rbx
0x180057b56  jz      short loc_180057B5B
0x180057b58  mov     byte ptr [rbx], 0
0x180057b5b  cmp     dword ptr [rdx+8], 0FFFFFFFFh
0x180057b5f  jnz     short loc_180057B9C
0x180057b61  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x180057b68  mov     [rbp+var_38], 0D73h
0x180057b70  mov     qword ptr [rbp+var_48], rax
0x180057b74  lea     rax, aMicrodomimplem_6; "MicrodomImplementation::CMicrodom_IRtlM"...
0x180057b7b  mov     qword ptr [rbp+var_48+8], rax
0x180057b7f  lea     rax, aTheelementThee; "TheElement != TheElement.InvalidValue()"
0x180057b86  lea     rdx, [rbp+var_48]
0x180057b8a  mov     [rbp+var_30], rax
0x180057b8e  lea     rcx, [rbp+var_28]
0x180057b92  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180057b97  jmp     loc_180057C7B
0x180057b9c  mov     rcx, rsi
0x180057b9f  call    RtlIsLUtf8StringValid
0x180057ba4  test    al, al
0x180057ba6  jnz     short loc_180057BCF
0x180057ba8  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x180057baf  mov     [rbp+var_38], 0D74h
0x180057bb7  mov     qword ptr [rbp+var_48], rax
0x180057bbb  lea     rax, aMicrodomimplem_6; "MicrodomImplementation::CMicrodom_IRtlM"...
0x180057bc2  mov     qword ptr [rbp+var_48+8], rax
0x180057bc6  lea     rax, aRtlislutf8stri_12; "RtlIsLUtf8StringValid(NamespaceURI)"
0x180057bcd  jmp     short loc_180057B86
0x180057bcf  mov     rcx, r14
0x180057bd2  call    RtlIsLUtf8StringValid
0x180057bd7  test    al, al
0x180057bd9  jnz     short loc_180057C02
0x180057bdb  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x180057be2  mov     [rbp+var_38], 0D75h
0x180057bea  mov     qword ptr [rbp+var_48], rax
0x180057bee  lea     rax, aMicrodomimplem_6; "MicrodomImplementation::CMicrodom_IRtlM"...
0x180057bf5  mov     qword ptr [rbp+var_48+8], rax
0x180057bf9  lea     rax, aRtlislutf8stri_0; "RtlIsLUtf8StringValid(LocalName)"
0x180057c00  jmp     short loc_180057B86
0x180057c02  test    rbx, rbx
0x180057c05  jnz     short loc_180057C3F
0x180057c07  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x180057c0e  mov     [rbp+var_38], 0D76h
0x180057c16  mov     qword ptr [rbp+var_48], rax
0x180057c1a  lea     rdx, [rbp+var_48]
0x180057c1e  lea     rax, aMicrodomimplem_6; "MicrodomImplementation::CMicrodom_IRtlM"...
0x180057c25  mov     qword ptr [rbp+var_48+8], rax
0x180057c29  lea     rcx, [rbp+var_28]
0x180057c2d  lea     rax, aNotNullCheckFa_91; "Not-null check failed: fHasAttribute"
0x180057c34  mov     [rbp+var_30], rax
0x180057c38  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180057c3d  jmp     short loc_180057C7B
0x180057c3f  mov     rax, [r15]
0x180057c42  lea     rcx, [rbp+var_20]
0x180057c46  movups  xmm0, xmmword ptr [rdi]
0x180057c49  mov     [rsp+78h+var_58], rcx
0x180057c4e  lea     rdx, [rbp+var_48]
0x180057c52  mov     r9, r14
0x180057c55  mov     r8, rsi
0x180057c58  mov     rax, [rax+120h]
0x180057c5f  mov     rcx, r15
0x180057c62  movdqu  [rbp+var_48], xmm0
0x180057c67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057c6c  test    eax, eax
0x180057c6e  js      short loc_180057C7B
0x180057c70  cmp     dword ptr [rbp+var_20+8], 0FFFFFFFFh
0x180057c74  jz      short loc_180057C79
0x180057c76  mov     byte ptr [rbx], 1
0x180057c79  xor     eax, eax
0x180057c7b  mov     rcx, [rbp+var_10]
0x180057c7f  xor     rcx, rsp; StackCookie
0x180057c82  call    __security_check_cookie
0x180057c87  add     rsp, 78h
0x180057c8b  pop     r15
0x180057c8d  pop     r14
0x180057c8f  pop     rdi
0x180057c90  pop     rsi
0x180057c91  pop     rbx
0x180057c92  pop     rbp
0x180057c93  retn
```
