# RtlCreateDefaultMicrodomXmlWriter

- ea: `0x180051850`
- end: `0x180051941`
- name: `RtlCreateDefaultMicrodomXmlWriter`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180057790`

## callees

- `0x18001f4ac`
- `0x1800293a0`
- `0x18004f55c`
- `0x1800504cc`
- `0x180051850`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x180051907`
- `ntdll!RtlRaiseStatus` at `0x180051907`

## string_xrefs

- `0x180051879`: `onecore\base\xml\udom_writer.cpp`
- `0x1800518b6`: `onecore\base\xml\udom_writer.cpp`
- `0x180051890`: `RtlCreateDefaultMicrodomXmlWriter`
- `0x1800518cd`: `RtlCreateDefaultMicrodomXmlWriter`
- `0x1800518dc`: `Not-null check failed: Writer`

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
      if ( dword_1800D4AA8 != 2 )
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
0x180051850  mov     [rsp-8+arg_0], rbx
0x180051855  push    rbp
0x180051856  mov     rbp, rsp
0x180051859  sub     rsp, 50h
0x18005185d  mov     rax, cs:__security_cookie
0x180051864  xor     rax, rsp
0x180051867  mov     [rbp+var_8], rax
0x18005186b  mov     [rbp+var_10], 0
0x180051872  mov     rbx, rdx
0x180051875  test    ecx, ecx
0x180051877  jz      short loc_1800518B1
0x180051879  lea     rax, aOnecoreBaseXml_3; "onecore\\base\\xml\\udom_writer.cpp"
0x180051880  mov     [rbp+var_20], 3C2h
0x180051888  mov     [rbp+var_30], rax
0x18005188c  lea     rdx, [rbp+var_30]
0x180051890  lea     rax, aRtlcreatedefau_1; "RtlCreateDefaultMicrodomXmlWriter"
0x180051897  mov     [rbp+var_28], rax
0x18005189b  lea     rcx, [rbp+var_10]
0x18005189f  lea     rax, aValidFlagsChec; "Valid flags check failed: Flags"
0x1800518a6  mov     [rbp+var_18], rax
0x1800518aa  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x1800518af  jmp     short loc_180051929
0x1800518b1  test    rbx, rbx
0x1800518b4  jnz     short loc_1800518EE
0x1800518b6  lea     rax, aOnecoreBaseXml_3; "onecore\\base\\xml\\udom_writer.cpp"
0x1800518bd  mov     [rbp+var_20], 3C3h
0x1800518c5  mov     [rbp+var_30], rax
0x1800518c9  lea     rdx, [rbp+var_30]
0x1800518cd  lea     rax, aRtlcreatedefau_1; "RtlCreateDefaultMicrodomXmlWriter"
0x1800518d4  mov     [rbp+var_28], rax
0x1800518d8  lea     rcx, [rbp+var_10]
0x1800518dc  lea     rax, aNotNullCheckFa_114; "Not-null check failed: Writer"
0x1800518e3  mov     [rbp+var_18], rax
0x1800518e7  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x1800518ec  jmp     short loc_180051929
0x1800518ee  call    ?Initialize@?$CRtlOneShotTypeDescriptionInit@VCMicrodomWriter@MicrodomWriterImplementation@@@Rtl@Windows@@QEAAJXZ; Windows::Rtl::CRtlOneShotTypeDescriptionInit<MicrodomWriterImplementation::CMicrodomWriter>::Initialize(void)
0x1800518f3  test    eax, eax
0x1800518f5  js      short loc_180051929
0x1800518f7  mov     eax, cs:dword_1800D4AA8
0x1800518fd  cmp     eax, 2
0x180051900  jz      short loc_180051914
0x180051902  mov     ecx, 0C00000E5h; Status
0x180051907  call    cs:__imp_RtlRaiseStatus
0x18005190e  nop     dword ptr [rax+rax+00h]
0x180051913  int     3; Trap to Debugger
0x180051914  mov     rcx, cs:?g_pMicrodomWriterTypeDescription@MicrodomWriterImplementation@@3V?$CRtlOneShotTypeDescriptionInit@VCMicrodomWriter@MicrodomWriterImplementation@@@Rtl@Windows@@A; Windows::Rtl::CRtlOneShotTypeDescriptionInit<MicrodomWriterImplementation::CMicrodomWriter> MicrodomWriterImplementation::g_pMicrodomWriterTypeDescription
0x18005191b  mov     r8, rbx
0x18005191e  call    ??$CreateInstance@VCMicrodomWriter_IRtlMicrodomXmlWriter@MicrodomWriterImplementation@@HUIRtlMicrodomXmlWriter@Rtl@Microdom@Windows@@@?$CRtlObjectTypeDescription@VCMicrodomWriter@MicrodomWriterImplementation@@@Rtl@Windows@@QEAAJAEBHPEAV?$Auto@PEAUIRtlMicrodomXmlWriter@Rtl@Microdom@Windows@@@2@@Z; Windows::Rtl::CRtlObjectTypeDescription<MicrodomWriterImplementation::CMicrodomWriter>::CreateInstance<MicrodomWriterImplementation::CMicrodomWriter_IRtlMicrodomXmlWriter,int,Windows::Microdom::Rtl::IRtlMicrodomXmlWriter>(int const &,Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodomXmlWriter *> *)
0x180051923  test    eax, eax
0x180051925  js      short loc_180051929
0x180051927  xor     eax, eax
0x180051929  mov     rcx, [rbp+var_8]
0x18005192d  xor     rcx, rsp; StackCookie
0x180051930  call    __security_check_cookie
0x180051935  mov     rbx, [rsp+50h+arg_0]
0x18005193a  add     rsp, 50h
0x18005193e  pop     rbp
0x18005193f  retn
```
