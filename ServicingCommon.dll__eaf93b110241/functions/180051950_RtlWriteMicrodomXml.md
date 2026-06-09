# RtlWriteMicrodomXml

- ea: `0x180051950`
- end: `0x180051b37`
- name: `RtlWriteMicrodomXml`
- size: `487`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180057790`

## callees

- `0x18001f4ac`
- `0x1800293a0`
- `0x180050784`
- `0x180050bb4`
- `0x180051950`
- `0x1800a0020`

## string_xrefs

- `0x180051989`: `onecore\base\xml\udom_writer.cpp`
- `0x1800519c9`: `onecore\base\xml\udom_writer.cpp`
- `0x180051a09`: `onecore\base\xml\udom_writer.cpp`
- `0x180051a35`: `onecore\base\xml\udom_writer.cpp`
- `0x180051aca`: `onecore\base\xml\udom_writer.cpp`
- `0x18005199c`: `RtlWriteMicrodomXml`
- `0x1800519dc`: `RtlWriteMicrodomXml`
- `0x180051a1c`: `RtlWriteMicrodomXml`
- `0x180051a48`: `RtlWriteMicrodomXml`
- `0x180051add`: `RtlWriteMicrodomXml`
- `0x1800519e7`: `Not-null check failed: pWriter`

## pseudocode

```c
__int64 __fastcall RtlWriteMicrodomXml(
        int a1,
        __int64 a2,
        struct Windows::Microdom::Rtl::IRtlMicrodomXmlWriter *a3,
        __int128 *a4,
        struct Windows::Microdom::Rtl::IRtlMicrodom *a5)
{
  const char *v8; // rax
  __int64 result; // rax
  __int64 v10; // rax
  int v11; // eax
  __int128 v12; // xmm1
  __int64 (__fastcall *v13)(struct Windows::Microdom::Rtl::IRtlMicrodomXmlWriter *, __int128 *, __int128 *); // rax
  unsigned int v14; // ecx
  struct Windows::Rtl::IRtlWOFOStream *v15; // [rsp+20h] [rbp-41h]
  __int128 v16; // [rsp+30h] [rbp-31h] BYREF
  __int64 v17; // [rsp+40h] [rbp-21h]
  const char *v18; // [rsp+48h] [rbp-19h]
  _DWORD v19[4]; // [rsp+50h] [rbp-11h] BYREF
  __int128 v20; // [rsp+60h] [rbp-1h] BYREF
  __int128 v21; // [rsp+70h] [rbp+Fh] BYREF

  v19[0] = 0;
  if ( a1 )
  {
    v17 = 986;
    *(_QWORD *)&v16 = "onecore\\base\\xml\\udom_writer.cpp";
    *((_QWORD *)&v16 + 1) = "RtlWriteMicrodomXml";
    v8 = "Valid flags check failed: Flags";
LABEL_3:
    v18 = v8;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             v19,
             &v16);
  }
  if ( !a2 )
  {
    v17 = 987;
    *(_QWORD *)&v16 = "onecore\\base\\xml\\udom_writer.cpp";
    *((_QWORD *)&v16 + 1) = "RtlWriteMicrodomXml";
    v8 = "Not-null check failed: pWriter";
    goto LABEL_3;
  }
  if ( !a3 )
  {
    v17 = 988;
    *(_QWORD *)&v16 = "onecore\\base\\xml\\udom_writer.cpp";
    *((_QWORD *)&v16 + 1) = "RtlWriteMicrodomXml";
    v8 = "Not-null check failed: pDocument";
    goto LABEL_3;
  }
  if ( !a5 )
  {
    v17 = 989;
    *(_QWORD *)&v16 = "onecore\\base\\xml\\udom_writer.cpp";
    *((_QWORD *)&v16 + 1) = "RtlWriteMicrodomXml";
    v8 = "Not-null check failed: pOutputStream";
    goto LABEL_3;
  }
  v10 = *(_QWORD *)a3;
  v21 = 0;
  result = (*(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlMicrodomXmlWriter *, __int128 *))(v10 + 24))(
             a3,
             &v21);
  if ( (int)result >= 0 )
  {
    if ( DWORD2(v21) == *((_DWORD *)a4 + 2) )
    {
      v11 = MicrodomWriterImplementation::WalkDocumentNodes(0, a2, a3, a5, v15);
    }
    else
    {
      v12 = *a4;
      v13 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlMicrodomXmlWriter *, __int128 *, __int128 *))(*(_QWORD *)a3 + 88LL);
      v20 = 0;
      v16 = v12;
      result = v13(a3, &v16, &v20);
      if ( (int)result < 0 )
        return result;
      if ( DWORD2(v20) == -1 )
      {
        v17 = 1003;
        *(_QWORD *)&v16 = "onecore\\base\\xml\\udom_writer.cpp";
        *((_QWORD *)&v16 + 1) = "RtlWriteMicrodomXml";
        v8 = "TheElement != TheElement.InvalidValue()";
        goto LABEL_3;
      }
      v16 = v20;
      v11 = MicrodomWriterImplementation::WalkAndWriteElement(0, a2, a3, &v16, a5);
    }
    v14 = 0;
    if ( v11 < 0 )
      return (unsigned int)v11;
    return v14;
  }
  return result;
}

```

## disassembly

```asm
0x180051950  push    rbp
0x180051952  push    rbx
0x180051953  push    rsi
0x180051954  push    rdi
0x180051955  push    r14
0x180051957  lea     rbp, [rsp-2Fh]
0x18005195c  sub     rsp, 90h
0x180051963  mov     rax, cs:__security_cookie
0x18005196a  xor     rax, rsp
0x18005196d  mov     [rbp+4Fh+var_30], rax
0x180051971  mov     rsi, [rbp+4Fh+arg_20]
0x180051975  mov     r14, r9
0x180051978  mov     [rbp+4Fh+var_60], 0
0x18005197f  mov     rbx, r8
0x180051982  mov     rdi, rdx
0x180051985  test    ecx, ecx
0x180051987  jz      short loc_1800519C4
0x180051989  lea     rax, aOnecoreBaseXml_3; "onecore\\base\\xml\\udom_writer.cpp"
0x180051990  mov     [rbp+4Fh+var_70], 3DAh
0x180051998  mov     qword ptr [rbp+4Fh+var_80], rax
0x18005199c  lea     rax, aRtlwritemicrod_0; "RtlWriteMicrodomXml"
0x1800519a3  mov     qword ptr [rbp+4Fh+var_80+8], rax
0x1800519a7  lea     rax, aValidFlagsChec; "Valid flags check failed: Flags"
0x1800519ae  lea     rdx, [rbp+4Fh+var_80]
0x1800519b2  mov     [rbp+4Fh+var_68], rax
0x1800519b6  lea     rcx, [rbp+4Fh+var_60]
0x1800519ba  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x1800519bf  jmp     loc_180051B1C
0x1800519c4  test    rdi, rdi
0x1800519c7  jnz     short loc_180051A04
0x1800519c9  lea     rax, aOnecoreBaseXml_3; "onecore\\base\\xml\\udom_writer.cpp"
0x1800519d0  mov     [rbp+4Fh+var_70], 3DBh
0x1800519d8  mov     qword ptr [rbp+4Fh+var_80], rax
0x1800519dc  lea     rax, aRtlwritemicrod_0; "RtlWriteMicrodomXml"
0x1800519e3  mov     qword ptr [rbp+4Fh+var_80+8], rax
0x1800519e7  lea     rax, aNotNullCheckFa_72; "Not-null check failed: pWriter"
0x1800519ee  lea     rdx, [rbp+4Fh+var_80]
0x1800519f2  mov     [rbp+4Fh+var_68], rax
0x1800519f6  lea     rcx, [rbp+4Fh+var_60]
0x1800519fa  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x1800519ff  jmp     loc_180051B1C
0x180051a04  test    rbx, rbx
0x180051a07  jnz     short loc_180051A30
0x180051a09  lea     rax, aOnecoreBaseXml_3; "onecore\\base\\xml\\udom_writer.cpp"
0x180051a10  mov     [rbp+4Fh+var_70], 3DCh
0x180051a18  mov     qword ptr [rbp+4Fh+var_80], rax
0x180051a1c  lea     rax, aRtlwritemicrod_0; "RtlWriteMicrodomXml"
0x180051a23  mov     qword ptr [rbp+4Fh+var_80+8], rax
0x180051a27  lea     rax, aNotNullCheckFa_82; "Not-null check failed: pDocument"
0x180051a2e  jmp     short loc_1800519EE
0x180051a30  test    rsi, rsi
0x180051a33  jnz     short loc_180051A5C
0x180051a35  lea     rax, aOnecoreBaseXml_3; "onecore\\base\\xml\\udom_writer.cpp"
0x180051a3c  mov     [rbp+4Fh+var_70], 3DDh
0x180051a44  mov     qword ptr [rbp+4Fh+var_80], rax
0x180051a48  lea     rax, aRtlwritemicrod_0; "RtlWriteMicrodomXml"
0x180051a4f  mov     qword ptr [rbp+4Fh+var_80+8], rax
0x180051a53  lea     rax, aNotNullCheckFa_119; "Not-null check failed: pOutputStream"
0x180051a5a  jmp     short loc_1800519EE
0x180051a5c  mov     rax, [r8]
0x180051a5f  lea     rdx, [rbp+4Fh+var_40]
0x180051a63  xorps   xmm0, xmm0
0x180051a66  mov     rcx, rbx
0x180051a69  movups  [rbp+4Fh+var_40], xmm0
0x180051a6d  mov     rax, [rax+18h]
0x180051a71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051a76  test    eax, eax
0x180051a78  js      loc_180051B1C
0x180051a7e  mov     eax, [r14+8]
0x180051a82  cmp     dword ptr [rbp+4Fh+var_40+8], eax
0x180051a85  jnz     short loc_180051A99
0x180051a87  mov     r9, rsi; struct Windows::Microdom::Rtl::IRtlMicrodom *
0x180051a8a  mov     r8, rbx; struct Windows::Microdom::Rtl::IRtlMicrodomXmlWriter *
0x180051a8d  mov     rdx, rdi; unsigned int
0x180051a90  xor     ecx, ecx; this
0x180051a92  call    ?WalkDocumentNodes@MicrodomWriterImplementation@@YAJKPEAUIRtlMicrodomXmlWriter@Rtl@Microdom@Windows@@PEAUIRtlMicrodom@345@PEAUIRtlWOFOStream@35@@Z; MicrodomWriterImplementation::WalkDocumentNodes(ulong,Windows::Microdom::Rtl::IRtlMicrodomXmlWriter *,Windows::Microdom::Rtl::IRtlMicrodom *,Windows::Rtl::IRtlWOFOStream *)
0x180051a97  jmp     short loc_180051B13
0x180051a99  mov     rax, [rbx]
0x180051a9c  lea     r8, [rbp+4Fh+var_50]
0x180051aa0  movups  xmm1, xmmword ptr [r14]
0x180051aa4  lea     rdx, [rbp+4Fh+var_80]
0x180051aa8  mov     rcx, rbx
0x180051aab  xorps   xmm0, xmm0
0x180051aae  mov     rax, [rax+58h]
0x180051ab2  movups  [rbp+4Fh+var_50], xmm0
0x180051ab6  movdqu  [rbp+4Fh+var_80], xmm1
0x180051abb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051ac0  test    eax, eax
0x180051ac2  js      short loc_180051B1C
0x180051ac4  cmp     dword ptr [rbp+4Fh+var_50+8], 0FFFFFFFFh
0x180051ac8  jnz     short loc_180051AF4
0x180051aca  lea     rax, aOnecoreBaseXml_3; "onecore\\base\\xml\\udom_writer.cpp"
0x180051ad1  mov     [rbp+4Fh+var_70], 3EBh
0x180051ad9  mov     qword ptr [rbp+4Fh+var_80], rax
0x180051add  lea     rax, aRtlwritemicrod_0; "RtlWriteMicrodomXml"
0x180051ae4  mov     qword ptr [rbp+4Fh+var_80+8], rax
0x180051ae8  lea     rax, aTheelementThee; "TheElement != TheElement.InvalidValue()"
0x180051aef  jmp     loc_1800519AE
0x180051af4  movaps  xmm0, [rbp+4Fh+var_50]
0x180051af8  lea     r9, [rbp+4Fh+var_80]
0x180051afc  mov     r8, rbx
0x180051aff  movdqa  [rbp+4Fh+var_80], xmm0
0x180051b04  mov     rdx, rdi
0x180051b07  mov     [rsp+0B0h+var_90], rsi
0x180051b0c  xor     ecx, ecx
0x180051b0e  call    ?WalkAndWriteElement@MicrodomWriterImplementation@@YAJKPEAUIRtlMicrodomXmlWriter@Rtl@Microdom@Windows@@PEAUIRtlMicrodom@345@UElement@345@PEAUIRtlWOFOStream@35@@Z; MicrodomWriterImplementation::WalkAndWriteElement(ulong,Windows::Microdom::Rtl::IRtlMicrodomXmlWriter *,Windows::Microdom::Rtl::IRtlMicrodom *,Windows::Microdom::Rtl::Element,Windows::Rtl::IRtlWOFOStream *)
0x180051b13  xor     ecx, ecx
0x180051b15  test    eax, eax
0x180051b17  cmovs   ecx, eax
0x180051b1a  mov     eax, ecx
0x180051b1c  mov     rcx, [rbp+4Fh+var_30]
0x180051b20  xor     rcx, rsp; StackCookie
0x180051b23  call    __security_check_cookie
0x180051b28  add     rsp, 90h
0x180051b2f  pop     r14
0x180051b31  pop     rdi
0x180051b32  pop     rsi
0x180051b33  pop     rbx
0x180051b34  pop     rbp
0x180051b35  retn
```
