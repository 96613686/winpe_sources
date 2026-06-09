# MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetNamedItemNs(Windows::Microdom::Rtl::NamedNodeMap,_LUTF8_STRING const *,_LUTF8_STRING const *,Windows::Microdom::Rtl::Node *)

- ea: `0x180056b20`
- end: `0x180056c9f`
- name: `?GetNamedItemNs@CMicrodom_IRtlMicrodomTearoff@MicrodomImplementation@@UEAAJUNamedNodeMap@Rtl@Microdom@Windows@@PEBU_LUTF8_STRING@@1PEAUNode@456@@Z`
- size: `383`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000f860`
- `0x180014b60`
- `0x18001f4ac`
- `0x1800293a0`
- `0x180056b20`

## string_xrefs

- `0x180056b7b`: `onecore\base\xml\udom_microdom.cpp`
- `0x180056bc2`: `onecore\base\xml\udom_microdom.cpp`
- `0x180056bf5`: `onecore\base\xml\udom_microdom.cpp`
- `0x180056c48`: `onecore\base\xml\udom_microdom.cpp`
- `0x180056c13`: `RtlIsLUtf8StringValid(NamespaceURI)`

## pseudocode

```c
__int64 __fastcall MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetNamedItemNs(
        __int64 a1,
        __int128 *a2,
        __int64 a3,
        __int64 a4,
        _OWORD *a5)
{
  const char *v9; // rax
  __int64 v11; // rcx
  int NodeMapNamedItem; // eax
  unsigned int v13; // ecx
  __int128 v14; // [rsp+30h] [rbp-30h] BYREF
  __int64 v15; // [rsp+40h] [rbp-20h]
  const char *v16; // [rsp+48h] [rbp-18h]
  int v17; // [rsp+50h] [rbp-10h] BYREF

  v17 = 0;
  if ( a5 )
  {
    v14 = 0;
    DWORD2(v14) = -1;
    *a5 = v14;
    if ( *((_DWORD *)a2 + 2) == -1 )
    {
      v15 = 3153;
      *(_QWORD *)&v14 = "onecore\\base\\xml\\udom_microdom.cpp";
      *((_QWORD *)&v14 + 1) = "MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetNamedItemNs";
      v9 = "NodeMap != Windows::Microdom::Rtl::NamedNodeMap::InvalidValue()";
LABEL_4:
      v16 = v9;
      return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
               &v17,
               &v14);
    }
    if ( !(unsigned __int8)RtlIsLUtf8StringValid(a4) )
    {
      v15 = 3154;
      *(_QWORD *)&v14 = "onecore\\base\\xml\\udom_microdom.cpp";
      *((_QWORD *)&v14 + 1) = "MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetNamedItemNs";
      v9 = "RtlIsLUtf8StringValid(LocalName)";
      goto LABEL_4;
    }
    if ( !(unsigned __int8)RtlIsLUtf8StringValid(a3) )
    {
      v15 = 3155;
      *(_QWORD *)&v14 = "onecore\\base\\xml\\udom_microdom.cpp";
      *((_QWORD *)&v14 + 1) = "MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetNamedItemNs";
      v9 = "RtlIsLUtf8StringValid(NamespaceURI)";
      goto LABEL_4;
    }
    v11 = *(_QWORD *)(a1 - 8);
    v14 = *a2;
    NodeMapNamedItem = MicrodomImplementation::CMicrodom::GetNodeMapNamedItem(v11, &v14, a3, a4, a5);
    v13 = 0;
    if ( NodeMapNamedItem < 0 )
      return (unsigned int)NodeMapNamedItem;
    return v13;
  }
  else
  {
    v15 = 3152;
    *(_QWORD *)&v14 = "onecore\\base\\xml\\udom_microdom.cpp";
    *((_QWORD *)&v14 + 1) = "MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetNamedItemNs";
    v16 = "Not-null check failed: Result";
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v17,
             &v14);
  }
}

```

## disassembly

```asm
0x180056b20  mov     [rsp-28h+arg_10], rbx
0x180056b25  push    rbp
0x180056b26  push    rsi
0x180056b27  push    rdi
0x180056b28  push    r14
0x180056b2a  push    r15
0x180056b2c  mov     rbp, rsp
0x180056b2f  sub     rsp, 60h
0x180056b33  mov     rax, cs:__security_cookie
0x180056b3a  xor     rax, rsp
0x180056b3d  mov     [rbp+var_8], rax
0x180056b41  mov     rbx, [rbp+arg_20]
0x180056b45  mov     rdi, r9
0x180056b48  mov     [rbp+var_10], 0
0x180056b4f  mov     rsi, r8
0x180056b52  mov     r14, rdx
0x180056b55  mov     r15, rcx
0x180056b58  test    rbx, rbx
0x180056b5b  jz      loc_180056C48
0x180056b61  xorps   xmm0, xmm0
0x180056b64  or      eax, 0FFFFFFFFh
0x180056b67  movups  [rbp+var_30], xmm0
0x180056b6b  mov     dword ptr [rbp+var_30+8], eax
0x180056b6e  movups  xmm0, [rbp+var_30]
0x180056b72  movdqu  xmmword ptr [rbx], xmm0
0x180056b76  cmp     [rdx+8], eax
0x180056b79  jnz     short loc_180056BB6
0x180056b7b  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x180056b82  mov     [rbp+var_20], 0C51h
0x180056b8a  mov     qword ptr [rbp+var_30], rax
0x180056b8e  lea     rax, aMicrodomimplem_21; "MicrodomImplementation::CMicrodom_IRtlM"...
0x180056b95  mov     qword ptr [rbp+var_30+8], rax
0x180056b99  lea     rax, aNodemapWindows; "NodeMap != Windows::Microdom::Rtl::Name"...
0x180056ba0  lea     rdx, [rbp+var_30]
0x180056ba4  mov     [rbp+var_18], rax
0x180056ba8  lea     rcx, [rbp+var_10]
0x180056bac  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180056bb1  jmp     loc_180056C7E
0x180056bb6  mov     rcx, rdi
0x180056bb9  call    RtlIsLUtf8StringValid
0x180056bbe  test    al, al
0x180056bc0  jnz     short loc_180056BE9
0x180056bc2  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x180056bc9  mov     [rbp+var_20], 0C52h
0x180056bd1  mov     qword ptr [rbp+var_30], rax
0x180056bd5  lea     rax, aMicrodomimplem_21; "MicrodomImplementation::CMicrodom_IRtlM"...
0x180056bdc  mov     qword ptr [rbp+var_30+8], rax
0x180056be0  lea     rax, aRtlislutf8stri_0; "RtlIsLUtf8StringValid(LocalName)"
0x180056be7  jmp     short loc_180056BA0
0x180056be9  mov     rcx, rsi
0x180056bec  call    RtlIsLUtf8StringValid
0x180056bf1  test    al, al
0x180056bf3  jnz     short loc_180056C1C
0x180056bf5  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x180056bfc  mov     [rbp+var_20], 0C53h
0x180056c04  mov     qword ptr [rbp+var_30], rax
0x180056c08  lea     rax, aMicrodomimplem_21; "MicrodomImplementation::CMicrodom_IRtlM"...
0x180056c0f  mov     qword ptr [rbp+var_30+8], rax
0x180056c13  lea     rax, aRtlislutf8stri_12; "RtlIsLUtf8StringValid(NamespaceURI)"
0x180056c1a  jmp     short loc_180056BA0
0x180056c1c  movups  xmm0, xmmword ptr [r14]
0x180056c20  mov     rcx, [r15-8]
0x180056c24  lea     rdx, [rbp+var_30]
0x180056c28  mov     r9, rdi
0x180056c2b  mov     [rsp+60h+var_40], rbx
0x180056c30  mov     r8, rsi
0x180056c33  movdqu  [rbp+var_30], xmm0
0x180056c38  call    ?GetNodeMapNamedItem@CMicrodom@MicrodomImplementation@@QEAAJUNamedNodeMap@Rtl@Microdom@Windows@@PEBU_LUTF8_STRING@@1PEAUNode@456@@Z; MicrodomImplementation::CMicrodom::GetNodeMapNamedItem(Windows::Microdom::Rtl::NamedNodeMap,_LUTF8_STRING const *,_LUTF8_STRING const *,Windows::Microdom::Rtl::Node *)
0x180056c3d  xor     ecx, ecx
0x180056c3f  test    eax, eax
0x180056c41  cmovs   ecx, eax
0x180056c44  mov     eax, ecx
0x180056c46  jmp     short loc_180056C7E
0x180056c48  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x180056c4f  mov     [rbp+var_20], 0C50h
0x180056c57  mov     qword ptr [rbp+var_30], rax
0x180056c5b  lea     rdx, [rbp+var_30]
0x180056c5f  lea     rax, aMicrodomimplem_21; "MicrodomImplementation::CMicrodom_IRtlM"...
0x180056c66  mov     qword ptr [rbp+var_30+8], rax
0x180056c6a  lea     rcx, [rbp+var_10]
0x180056c6e  lea     rax, aNotNullCheckFa_0; "Not-null check failed: Result"
0x180056c75  mov     [rbp+var_18], rax
0x180056c79  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180056c7e  mov     rcx, [rbp+var_8]
0x180056c82  xor     rcx, rsp; StackCookie
0x180056c85  call    __security_check_cookie
0x180056c8a  mov     rbx, [rsp+60h+arg_10]
0x180056c92  add     rsp, 60h
0x180056c96  pop     r15
0x180056c98  pop     r14
0x180056c9a  pop     rdi
0x180056c9b  pop     rsi
0x180056c9c  pop     rbp
0x180056c9d  retn
```
