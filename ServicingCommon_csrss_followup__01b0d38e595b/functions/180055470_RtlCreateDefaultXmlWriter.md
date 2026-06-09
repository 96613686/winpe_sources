# RtlCreateDefaultXmlWriter

- ea: `0x180055470`
- end: `0x1800555de`
- name: `RtlCreateDefaultXmlWriter`
- size: `366`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180019738`
- `0x18001f1d8`
- `0x18002d2b0`
- `0x1800551b0`
- `0x180055470`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x18005559d`
- `ntdll!RtlRaiseStatus` at `0x18005559d`

## string_xrefs

- `0x180055573`: `Not-null check failed: Writer`
- `0x1800554a7`: `onecore\base\xml\xml_writer.cpp`
- `0x1800554ec`: `onecore\base\xml\xml_writer.cpp`
- `0x180055518`: `onecore\base\xml\xml_writer.cpp`
- `0x180055555`: `onecore\base\xml\xml_writer.cpp`
- `0x1800554ba`: `XmlWriterImplementation::RtlCreateDefaultXmlWriter`
- `0x1800554ff`: `XmlWriterImplementation::RtlCreateDefaultXmlWriter`
- `0x18005552b`: `XmlWriterImplementation::RtlCreateDefaultXmlWriter`
- `0x180055568`: `XmlWriterImplementation::RtlCreateDefaultXmlWriter`
- `0x180055536`: `Not-null check failed: pStreamToWriteTo`

## pseudocode

```c
__int64 __fastcall RtlCreateDefaultXmlWriter(int a1, const char *a2, __int64 a3)
{
  const char *v5; // rax
  __int64 result; // rax
  __int64 v7; // rcx
  int v8; // eax
  unsigned int v9; // ecx
  const char *v10; // [rsp+20h] [rbp-30h] BYREF
  const char *v11; // [rsp+28h] [rbp-28h]
  __int64 v12; // [rsp+30h] [rbp-20h]
  const char *v13; // [rsp+38h] [rbp-18h]
  int v14; // [rsp+40h] [rbp-10h] BYREF

  v14 = 0;
  HIDWORD(v10) = 0;
  if ( (a1 & 0xFFFFFFE0) != 0 )
  {
    v12 = 751;
    v10 = "onecore\\base\\xml\\xml_writer.cpp";
    v11 = "XmlWriterImplementation::RtlCreateDefaultXmlWriter";
    v5 = "Valid flags check failed: Flags";
LABEL_3:
    v13 = v5;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v14,
             &v10);
  }
  v7 = a1 & 6;
  if ( (((_DWORD)v7 - 1) & (unsigned int)v7) != 0 )
  {
    v12 = 756;
    v10 = "onecore\\base\\xml\\xml_writer.cpp";
    v11 = "XmlWriterImplementation::RtlCreateDefaultXmlWriter";
    v5 = "No more than one flag set check failed: Flags";
    goto LABEL_3;
  }
  if ( !a2 )
  {
    v12 = 758;
    v10 = "onecore\\base\\xml\\xml_writer.cpp";
    v11 = "XmlWriterImplementation::RtlCreateDefaultXmlWriter";
    v5 = "Not-null check failed: pStreamToWriteTo";
    goto LABEL_3;
  }
  if ( !a3 )
  {
    v12 = 759;
    v10 = "onecore\\base\\xml\\xml_writer.cpp";
    v11 = "XmlWriterImplementation::RtlCreateDefaultXmlWriter";
    v5 = "Not-null check failed: Writer";
    goto LABEL_3;
  }
  LODWORD(v10) = a1;
  v11 = a2;
  result = Windows::Rtl::CRtlOneShotTypeDescriptionInit<XmlWriterImplementation::CXmlWriter>::Initialize(v7, a2);
  if ( (int)result >= 0 )
  {
    if ( dword_1800D2AD8 != 2 )
      RtlRaiseStatus(-1073741595);
    v8 = Windows::Rtl::CRtlObjectTypeDescription<XmlWriterImplementation::CXmlWriter>::CreateInstance<XmlWriterImplementation::CXmlWriter_IRtlXmlWriter,XmlWriterImplementation::CXmlWriter::InitParams,Windows::Microdom::Rtl::IRtlXmlWriter>(
           XmlWriterImplementation::g_XmlWriterType,
           &v10,
           a3);
    v9 = 0;
    if ( v8 < 0 )
      return (unsigned int)v8;
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x180055470  mov     [rsp-8+arg_18], rbx
0x180055475  push    rbp
0x180055476  mov     rbp, rsp
0x180055479  sub     rsp, 50h
0x18005547d  mov     rax, cs:__security_cookie
0x180055484  xor     rax, rsp
0x180055487  mov     [rbp+var_8], rax
0x18005548b  mov     [rbp+var_10], 0
0x180055492  mov     rbx, r8
0x180055495  mov     dword ptr [rbp+var_30+4], 0
0x18005549c  mov     r8d, ecx
0x18005549f  test    ecx, 0FFFFFFE0h
0x1800554a5  jz      short loc_1800554E2
0x1800554a7  lea     rax, aOnecoreBaseXml; "onecore\\base\\xml\\xml_writer.cpp"
0x1800554ae  mov     [rbp+var_20], 2EFh
0x1800554b6  mov     [rbp-30h], rax
0x1800554ba  lea     rax, aXmlwriterimple; "XmlWriterImplementation::RtlCreateDefau"...
0x1800554c1  mov     [rbp+var_28], rax
0x1800554c5  lea     rax, aValidFlagsChec; "Valid flags check failed: Flags"
0x1800554cc  lea     rdx, [rbp+var_30]
0x1800554d0  mov     [rbp+var_18], rax
0x1800554d4  lea     rcx, [rbp+var_10]
0x1800554d8  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x1800554dd  jmp     loc_1800555C6
0x1800554e2  and     ecx, 6
0x1800554e5  lea     eax, [rcx-1]
0x1800554e8  test    ecx, eax
0x1800554ea  jz      short loc_180055513
0x1800554ec  lea     rax, aOnecoreBaseXml; "onecore\\base\\xml\\xml_writer.cpp"
0x1800554f3  mov     [rbp+var_20], 2F4h
0x1800554fb  mov     [rbp+var_30], rax
0x1800554ff  lea     rax, aXmlwriterimple; "XmlWriterImplementation::RtlCreateDefau"...
0x180055506  mov     [rbp+var_28], rax
0x18005550a  lea     rax, aNoMoreThanOneF_0; "No more than one flag set check failed:"...
0x180055511  jmp     short loc_1800554CC
0x180055513  test    rdx, rdx
0x180055516  jnz     short loc_180055550
0x180055518  lea     rax, aOnecoreBaseXml; "onecore\\base\\xml\\xml_writer.cpp"
0x18005551f  mov     [rbp+var_20], 2F6h
0x180055527  mov     [rbp+var_30], rax
0x18005552b  lea     rax, aXmlwriterimple; "XmlWriterImplementation::RtlCreateDefau"...
0x180055532  mov     [rbp+var_28], rax
0x180055536  lea     rax, aNotNullCheckFa_38; "Not-null check failed: pStreamToWriteTo"
0x18005553d  lea     rdx, [rbp+var_30]
0x180055541  mov     [rbp+var_18], rax
0x180055545  lea     rcx, [rbp+var_10]
0x180055549  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005554e  jmp     short loc_1800555C6
0x180055550  test    rbx, rbx
0x180055553  jnz     short loc_18005557C
0x180055555  lea     rax, aOnecoreBaseXml; "onecore\\base\\xml\\xml_writer.cpp"
0x18005555c  mov     [rbp+var_20], 2F7h
0x180055564  mov     [rbp+var_30], rax
0x180055568  lea     rax, aXmlwriterimple; "XmlWriterImplementation::RtlCreateDefau"...
0x18005556f  mov     [rbp+var_28], rax
0x180055573  lea     rax, aNotNullCheckFa_114; "Not-null check failed: Writer"
0x18005557a  jmp     short loc_18005553D
0x18005557c  mov     dword ptr [rbp+var_30], r8d
0x180055580  mov     [rbp+var_28], rdx
0x180055584  call    ?Initialize@?$CRtlOneShotTypeDescriptionInit@VCXmlWriter@XmlWriterImplementation@@@Rtl@Windows@@QEAAJXZ; Windows::Rtl::CRtlOneShotTypeDescriptionInit<XmlWriterImplementation::CXmlWriter>::Initialize(void)
0x180055589  test    eax, eax
0x18005558b  js      short loc_1800555C6
0x18005558d  mov     eax, cs:dword_1800D2AD8
0x180055593  cmp     eax, 2
0x180055596  jz      short loc_1800555AA
0x180055598  mov     ecx, 0C00000E5h; Status
0x18005559d  call    cs:__imp_RtlRaiseStatus
0x1800555a4  nop     dword ptr [rax+rax+00h]
0x1800555a9  int     3; Trap to Debugger
0x1800555aa  mov     rcx, cs:?g_XmlWriterType@XmlWriterImplementation@@3V?$CRtlOneShotTypeDescriptionInit@VCXmlWriter@XmlWriterImplementation@@@Rtl@Windows@@A; Windows::Rtl::CRtlOneShotTypeDescriptionInit<XmlWriterImplementation::CXmlWriter> XmlWriterImplementation::g_XmlWriterType
0x1800555b1  lea     rdx, [rbp+var_30]
0x1800555b5  mov     r8, rbx
0x1800555b8  call    ??$CreateInstance@VCXmlWriter_IRtlXmlWriter@XmlWriterImplementation@@UInitParams@CXmlWriter@2@UIRtlXmlWriter@Rtl@Microdom@Windows@@@?$CRtlObjectTypeDescription@VCXmlWriter@XmlWriterImplementation@@@Rtl@Windows@@QEAAJAEBUInitParams@CXmlWriter@XmlWriterImplementation@@PEAV?$Auto@PEAUIRtlXmlWriter@Rtl@Microdom@Windows@@@2@@Z; Windows::Rtl::CRtlObjectTypeDescription<XmlWriterImplementation::CXmlWriter>::CreateInstance<XmlWriterImplementation::CXmlWriter_IRtlXmlWriter,XmlWriterImplementation::CXmlWriter::InitParams,Windows::Microdom::Rtl::IRtlXmlWriter>(XmlWriterImplementation::CXmlWriter::InitParams const &,Windows::Auto<Windows::Microdom::Rtl::IRtlXmlWriter *> *)
0x1800555bd  xor     ecx, ecx
0x1800555bf  test    eax, eax
0x1800555c1  cmovs   ecx, eax
0x1800555c4  mov     eax, ecx
0x1800555c6  mov     rcx, [rbp+var_8]
0x1800555ca  xor     rcx, rsp; StackCookie
0x1800555cd  call    __security_check_cookie
0x1800555d2  mov     rbx, [rsp+50h+arg_18]
0x1800555d7  add     rsp, 50h
0x1800555db  pop     rbp
0x1800555dc  retn
```
