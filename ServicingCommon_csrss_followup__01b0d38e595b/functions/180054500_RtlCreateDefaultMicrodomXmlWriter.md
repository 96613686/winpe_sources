# RtlCreateDefaultMicrodomXmlWriter

- ea: `0x180054500`
- end: `0x1800545f1`
- name: `RtlCreateDefaultMicrodomXmlWriter`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001efb0`

## callees

- `0x18001f1d8`
- `0x18002d2b0`
- `0x18005268c`
- `0x1800535ac`
- `0x180054500`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x1800545b7`
- `ntdll!RtlRaiseStatus` at `0x1800545b7`

## string_xrefs

- `0x180054529`: `onecore\base\xml\udom_writer.cpp`
- `0x180054566`: `onecore\base\xml\udom_writer.cpp`
- `0x180054540`: `RtlCreateDefaultMicrodomXmlWriter`
- `0x18005457d`: `RtlCreateDefaultMicrodomXmlWriter`
- `0x18005458c`: `Not-null check failed: Writer`

## pseudocode

```c
__int64 __fastcall RtlCreateDefaultMicrodomXmlWriter(int a1, __int64 a2)
{
  __int64 result; // rax
  __int64 v4; // rdx
  const char *v5; // [rsp+20h] [rbp-30h] BYREF
  const char *v6; // [rsp+28h] [rbp-28h]
  __int64 v7; // [rsp+30h] [rbp-20h]
  const char *v8; // [rsp+38h] [rbp-18h]
  int v9; // [rsp+40h] [rbp-10h] BYREF

  v9 = 0;
  if ( a1 )
  {
    v7 = 962;
    v5 = "onecore\\base\\xml\\udom_writer.cpp";
    v6 = "RtlCreateDefaultMicrodomXmlWriter";
    v8 = "Valid flags check failed: Flags";
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v9,
             &v5);
  }
  else if ( a2 )
  {
    result = Windows::Rtl::CRtlOneShotTypeDescriptionInit<MicrodomWriterImplementation::CMicrodomWriter>::Initialize();
    if ( (int)result >= 0 )
    {
      if ( dword_1800D2AB8 != 2 )
        RtlRaiseStatus(-1073741595);
      result = Windows::Rtl::CRtlObjectTypeDescription<MicrodomWriterImplementation::CMicrodomWriter>::CreateInstance<MicrodomWriterImplementation::CMicrodomWriter_IRtlMicrodomXmlWriter,int,Windows::Microdom::Rtl::IRtlMicrodomXmlWriter>(
                 MicrodomWriterImplementation::g_pMicrodomWriterTypeDescription,
                 v4,
                 a2);
      if ( (int)result >= 0 )
        return 0;
    }
  }
  else
  {
    v7 = 963;
    v5 = "onecore\\base\\xml\\udom_writer.cpp";
    v6 = "RtlCreateDefaultMicrodomXmlWriter";
    v8 = "Not-null check failed: Writer";
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v9,
             &v5);
  }
  return result;
}

```

## disassembly

```asm
0x180054500  mov     [rsp-8+arg_0], rbx
0x180054505  push    rbp
0x180054506  mov     rbp, rsp
0x180054509  sub     rsp, 50h
0x18005450d  mov     rax, cs:__security_cookie
0x180054514  xor     rax, rsp
0x180054517  mov     [rbp+var_8], rax
0x18005451b  mov     [rbp+var_10], 0
0x180054522  mov     rbx, rdx
0x180054525  test    ecx, ecx
0x180054527  jz      short loc_180054561
0x180054529  lea     rax, aOnecoreBaseXml_3; "onecore\\base\\xml\\udom_writer.cpp"
0x180054530  mov     [rbp+var_20], 3C2h
0x180054538  mov     [rbp+var_30], rax
0x18005453c  lea     rdx, [rbp+var_30]
0x180054540  lea     rax, aRtlcreatedefau_1; "RtlCreateDefaultMicrodomXmlWriter"
0x180054547  mov     [rbp+var_28], rax
0x18005454b  lea     rcx, [rbp+var_10]
0x18005454f  lea     rax, aValidFlagsChec; "Valid flags check failed: Flags"
0x180054556  mov     [rbp+var_18], rax
0x18005455a  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005455f  jmp     short loc_1800545D9
0x180054561  test    rbx, rbx
0x180054564  jnz     short loc_18005459E
0x180054566  lea     rax, aOnecoreBaseXml_3; "onecore\\base\\xml\\udom_writer.cpp"
0x18005456d  mov     [rbp+var_20], 3C3h
0x180054575  mov     [rbp+var_30], rax
0x180054579  lea     rdx, [rbp+var_30]
0x18005457d  lea     rax, aRtlcreatedefau_1; "RtlCreateDefaultMicrodomXmlWriter"
0x180054584  mov     [rbp+var_28], rax
0x180054588  lea     rcx, [rbp+var_10]
0x18005458c  lea     rax, aNotNullCheckFa_114; "Not-null check failed: Writer"
0x180054593  mov     [rbp+var_18], rax
0x180054597  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005459c  jmp     short loc_1800545D9
0x18005459e  call    ?Initialize@?$CRtlOneShotTypeDescriptionInit@VCMicrodomWriter@MicrodomWriterImplementation@@@Rtl@Windows@@QEAAJXZ; Windows::Rtl::CRtlOneShotTypeDescriptionInit<MicrodomWriterImplementation::CMicrodomWriter>::Initialize(void)
0x1800545a3  test    eax, eax
0x1800545a5  js      short loc_1800545D9
0x1800545a7  mov     eax, cs:dword_1800D2AB8
0x1800545ad  cmp     eax, 2
0x1800545b0  jz      short loc_1800545C4
0x1800545b2  mov     ecx, 0C00000E5h; Status
0x1800545b7  call    cs:__imp_RtlRaiseStatus
0x1800545be  nop     dword ptr [rax+rax+00h]
0x1800545c3  int     3; Trap to Debugger
0x1800545c4  mov     rcx, cs:?g_pMicrodomWriterTypeDescription@MicrodomWriterImplementation@@3V?$CRtlOneShotTypeDescriptionInit@VCMicrodomWriter@MicrodomWriterImplementation@@@Rtl@Windows@@A; Windows::Rtl::CRtlOneShotTypeDescriptionInit<MicrodomWriterImplementation::CMicrodomWriter> MicrodomWriterImplementation::g_pMicrodomWriterTypeDescription
0x1800545cb  mov     r8, rbx
0x1800545ce  call    ??$CreateInstance@VCMicrodomWriter_IRtlMicrodomXmlWriter@MicrodomWriterImplementation@@HUIRtlMicrodomXmlWriter@Rtl@Microdom@Windows@@@?$CRtlObjectTypeDescription@VCMicrodomWriter@MicrodomWriterImplementation@@@Rtl@Windows@@QEAAJAEBHPEAV?$Auto@PEAUIRtlMicrodomXmlWriter@Rtl@Microdom@Windows@@@2@@Z; Windows::Rtl::CRtlObjectTypeDescription<MicrodomWriterImplementation::CMicrodomWriter>::CreateInstance<MicrodomWriterImplementation::CMicrodomWriter_IRtlMicrodomXmlWriter,int,Windows::Microdom::Rtl::IRtlMicrodomXmlWriter>(int const &,Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodomXmlWriter *> *)
0x1800545d3  test    eax, eax
0x1800545d5  js      short loc_1800545D9
0x1800545d7  xor     eax, eax
0x1800545d9  mov     rcx, [rbp+var_8]
0x1800545dd  xor     rcx, rsp; StackCookie
0x1800545e0  call    __security_check_cookie
0x1800545e5  mov     rbx, [rsp+50h+arg_0]
0x1800545ea  add     rsp, 50h
0x1800545ee  pop     rbp
0x1800545ef  retn
```
