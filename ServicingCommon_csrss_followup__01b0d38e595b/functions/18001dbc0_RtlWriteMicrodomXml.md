# RtlWriteMicrodomXml

- ea: `0x18001dbc0`
- end: `0x18001dda7`
- name: `RtlWriteMicrodomXml`
- size: `487`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001efb0`

## callees

- `0x18001dbc0`
- `0x18001f1d8`
- `0x180023930`
- `0x18002d2b0`
- `0x180053864`
- `0x18009e020`

## string_xrefs

- `0x18001dc0c`: `RtlWriteMicrodomXml`
- `0x18001dc4c`: `RtlWriteMicrodomXml`
- `0x18001dc8c`: `RtlWriteMicrodomXml`
- `0x18001dcb8`: `RtlWriteMicrodomXml`
- `0x18001dd4d`: `RtlWriteMicrodomXml`
- `0x18001dbf9`: `onecore\base\xml\udom_writer.cpp`
- `0x18001dc39`: `onecore\base\xml\udom_writer.cpp`
- `0x18001dc79`: `onecore\base\xml\udom_writer.cpp`
- `0x18001dca5`: `onecore\base\xml\udom_writer.cpp`
- `0x18001dd3a`: `onecore\base\xml\udom_writer.cpp`
- `0x18001dc57`: `Not-null check failed: pWriter`

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
0x18001dbc0  push    rbp
0x18001dbc2  push    rbx
0x18001dbc3  push    rsi
0x18001dbc4  push    rdi
0x18001dbc5  push    r14
0x18001dbc7  lea     rbp, [rsp-2Fh]
0x18001dbcc  sub     rsp, 90h
0x18001dbd3  mov     rax, cs:__security_cookie
0x18001dbda  xor     rax, rsp
0x18001dbdd  mov     [rbp+4Fh+var_30], rax
0x18001dbe1  mov     rsi, [rbp+4Fh+arg_20]
0x18001dbe5  mov     r14, r9
0x18001dbe8  mov     [rbp+4Fh+var_60], 0
0x18001dbef  mov     rbx, r8
0x18001dbf2  mov     rdi, rdx
0x18001dbf5  test    ecx, ecx
0x18001dbf7  jz      short loc_18001DC34
0x18001dbf9  lea     rax, aOnecoreBaseXml_3; "onecore\\base\\xml\\udom_writer.cpp"
0x18001dc00  mov     [rbp+4Fh+var_70], 3DAh
0x18001dc08  mov     qword ptr [rbp+4Fh+var_80], rax
0x18001dc0c  lea     rax, aRtlwritemicrod_0; "RtlWriteMicrodomXml"
0x18001dc13  mov     qword ptr [rbp+4Fh+var_80+8], rax
0x18001dc17  lea     rax, aValidFlagsChec; "Valid flags check failed: Flags"
0x18001dc1e  lea     rdx, [rbp+4Fh+var_80]
0x18001dc22  mov     [rbp+4Fh+var_68], rax
0x18001dc26  lea     rcx, [rbp+4Fh+var_60]
0x18001dc2a  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18001dc2f  jmp     loc_18001DD8C
0x18001dc34  test    rdi, rdi
0x18001dc37  jnz     short loc_18001DC74
0x18001dc39  lea     rax, aOnecoreBaseXml_3; "onecore\\base\\xml\\udom_writer.cpp"
0x18001dc40  mov     [rbp+4Fh+var_70], 3DBh
0x18001dc48  mov     qword ptr [rbp+4Fh+var_80], rax
0x18001dc4c  lea     rax, aRtlwritemicrod_0; "RtlWriteMicrodomXml"
0x18001dc53  mov     qword ptr [rbp+4Fh+var_80+8], rax
0x18001dc57  lea     rax, aNotNullCheckFa_72; "Not-null check failed: pWriter"
0x18001dc5e  lea     rdx, [rbp+4Fh+var_80]
0x18001dc62  mov     [rbp+4Fh+var_68], rax
0x18001dc66  lea     rcx, [rbp+4Fh+var_60]
0x18001dc6a  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18001dc6f  jmp     loc_18001DD8C
0x18001dc74  test    rbx, rbx
0x18001dc77  jnz     short loc_18001DCA0
0x18001dc79  lea     rax, aOnecoreBaseXml_3; "onecore\\base\\xml\\udom_writer.cpp"
0x18001dc80  mov     [rbp+4Fh+var_70], 3DCh
0x18001dc88  mov     qword ptr [rbp+4Fh+var_80], rax
0x18001dc8c  lea     rax, aRtlwritemicrod_0; "RtlWriteMicrodomXml"
0x18001dc93  mov     qword ptr [rbp+4Fh+var_80+8], rax
0x18001dc97  lea     rax, aNotNullCheckFa_82; "Not-null check failed: pDocument"
0x18001dc9e  jmp     short loc_18001DC5E
0x18001dca0  test    rsi, rsi
0x18001dca3  jnz     short loc_18001DCCC
0x18001dca5  lea     rax, aOnecoreBaseXml_3; "onecore\\base\\xml\\udom_writer.cpp"
0x18001dcac  mov     [rbp+4Fh+var_70], 3DDh
0x18001dcb4  mov     qword ptr [rbp+4Fh+var_80], rax
0x18001dcb8  lea     rax, aRtlwritemicrod_0; "RtlWriteMicrodomXml"
0x18001dcbf  mov     qword ptr [rbp+4Fh+var_80+8], rax
0x18001dcc3  lea     rax, aNotNullCheckFa_119; "Not-null check failed: pOutputStream"
0x18001dcca  jmp     short loc_18001DC5E
0x18001dccc  mov     rax, [r8]
0x18001dccf  lea     rdx, [rbp+4Fh+var_40]
0x18001dcd3  xorps   xmm0, xmm0
0x18001dcd6  mov     rcx, rbx
0x18001dcd9  movups  [rbp+4Fh+var_40], xmm0
0x18001dcdd  mov     rax, [rax+18h]
0x18001dce1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dce6  test    eax, eax
0x18001dce8  js      loc_18001DD8C
0x18001dcee  mov     eax, [r14+8]
0x18001dcf2  cmp     dword ptr [rbp+4Fh+var_40+8], eax
0x18001dcf5  jnz     short loc_18001DD09
0x18001dcf7  mov     r9, rsi; struct Windows::Microdom::Rtl::IRtlMicrodom *
0x18001dcfa  mov     r8, rbx; struct Windows::Microdom::Rtl::IRtlMicrodomXmlWriter *
0x18001dcfd  mov     rdx, rdi; unsigned int
0x18001dd00  xor     ecx, ecx; this
0x18001dd02  call    ?WalkDocumentNodes@MicrodomWriterImplementation@@YAJKPEAUIRtlMicrodomXmlWriter@Rtl@Microdom@Windows@@PEAUIRtlMicrodom@345@PEAUIRtlWOFOStream@35@@Z; MicrodomWriterImplementation::WalkDocumentNodes(ulong,Windows::Microdom::Rtl::IRtlMicrodomXmlWriter *,Windows::Microdom::Rtl::IRtlMicrodom *,Windows::Rtl::IRtlWOFOStream *)
0x18001dd07  jmp     short loc_18001DD83
0x18001dd09  mov     rax, [rbx]
0x18001dd0c  lea     r8, [rbp+4Fh+var_50]
0x18001dd10  movups  xmm1, xmmword ptr [r14]
0x18001dd14  lea     rdx, [rbp+4Fh+var_80]
0x18001dd18  mov     rcx, rbx
0x18001dd1b  xorps   xmm0, xmm0
0x18001dd1e  mov     rax, [rax+58h]
0x18001dd22  movups  [rbp+4Fh+var_50], xmm0
0x18001dd26  movdqu  [rbp+4Fh+var_80], xmm1
0x18001dd2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd30  test    eax, eax
0x18001dd32  js      short loc_18001DD8C
0x18001dd34  cmp     dword ptr [rbp+4Fh+var_50+8], 0FFFFFFFFh
0x18001dd38  jnz     short loc_18001DD64
0x18001dd3a  lea     rax, aOnecoreBaseXml_3; "onecore\\base\\xml\\udom_writer.cpp"
0x18001dd41  mov     [rbp+4Fh+var_70], 3EBh
0x18001dd49  mov     qword ptr [rbp+4Fh+var_80], rax
0x18001dd4d  lea     rax, aRtlwritemicrod_0; "RtlWriteMicrodomXml"
0x18001dd54  mov     qword ptr [rbp+4Fh+var_80+8], rax
0x18001dd58  lea     rax, aTheelementThee; "TheElement != TheElement.InvalidValue()"
0x18001dd5f  jmp     loc_18001DC1E
0x18001dd64  movaps  xmm0, [rbp+4Fh+var_50]
0x18001dd68  lea     r9, [rbp+4Fh+var_80]
0x18001dd6c  mov     r8, rbx
0x18001dd6f  movdqa  [rbp+4Fh+var_80], xmm0
0x18001dd74  mov     rdx, rdi
0x18001dd77  mov     [rsp+0B0h+var_90], rsi
0x18001dd7c  xor     ecx, ecx
0x18001dd7e  call    ?WalkAndWriteElement@MicrodomWriterImplementation@@YAJKPEAUIRtlMicrodomXmlWriter@Rtl@Microdom@Windows@@PEAUIRtlMicrodom@345@UElement@345@PEAUIRtlWOFOStream@35@@Z; MicrodomWriterImplementation::WalkAndWriteElement(ulong,Windows::Microdom::Rtl::IRtlMicrodomXmlWriter *,Windows::Microdom::Rtl::IRtlMicrodom *,Windows::Microdom::Rtl::Element,Windows::Rtl::IRtlWOFOStream *)
0x18001dd83  xor     ecx, ecx
0x18001dd85  test    eax, eax
0x18001dd87  cmovs   ecx, eax
0x18001dd8a  mov     eax, ecx
0x18001dd8c  mov     rcx, [rbp+4Fh+var_30]
0x18001dd90  xor     rcx, rsp; StackCookie
0x18001dd93  call    __security_check_cookie
0x18001dd98  add     rsp, 90h
0x18001dd9f  pop     r14
0x18001dda1  pop     rdi
0x18001dda2  pop     rsi
0x18001dda3  pop     rbx
0x18001dda4  pop     rbp
0x18001dda5  retn
```
