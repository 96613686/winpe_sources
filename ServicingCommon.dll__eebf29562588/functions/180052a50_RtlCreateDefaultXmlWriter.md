# RtlCreateDefaultXmlWriter

- ea: `0x180052a50`
- end: `0x180052bbe`
- name: `RtlCreateDefaultXmlWriter`
- size: `366`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800122fc`
- `0x18001f4ac`
- `0x1800293a0`
- `0x1800528f0`
- `0x180052a50`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x180052b7d`
- `ntdll!RtlRaiseStatus` at `0x180052b7d`

## string_xrefs

- `0x180052b53`: `Not-null check failed: Writer`
- `0x180052a87`: `onecore\base\xml\xml_writer.cpp`
- `0x180052acc`: `onecore\base\xml\xml_writer.cpp`
- `0x180052af8`: `onecore\base\xml\xml_writer.cpp`
- `0x180052b35`: `onecore\base\xml\xml_writer.cpp`
- `0x180052a9a`: `XmlWriterImplementation::RtlCreateDefaultXmlWriter`
- `0x180052adf`: `XmlWriterImplementation::RtlCreateDefaultXmlWriter`
- `0x180052b0b`: `XmlWriterImplementation::RtlCreateDefaultXmlWriter`
- `0x180052b48`: `XmlWriterImplementation::RtlCreateDefaultXmlWriter`
- `0x180052b16`: `Not-null check failed: pStreamToWriteTo`

## pseudocode

```c
__int64 __fastcall RtlCreateDefaultXmlWriter(int a1, const char *a2, __int64 *a3)
{
  const char *v5; // rax
  __int64 result; // rax
  __int64 v7; // rcx
  NTSTATUS v8; // eax
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
    if ( dword_1800D4AC8 != 2 )
      RtlRaiseStatus(-1073741595);
    v8 = Windows::Rtl::CRtlObjectTypeDescription<XmlWriterImplementation::CXmlWriter>::CreateInstance<XmlWriterImplementation::CXmlWriter_IRtlXmlWriter,XmlWriterImplementation::CXmlWriter::InitParams,Windows::Microdom::Rtl::IRtlXmlWriter>(
           (volatile __int32 *)XmlWriterImplementation::g_XmlWriterType,
           (const struct XmlWriterImplementation::CXmlWriter::InitParams *)&v10,
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
0x180052a50  mov     [rsp-8+arg_18], rbx
0x180052a55  push    rbp
0x180052a56  mov     rbp, rsp
0x180052a59  sub     rsp, 50h
0x180052a5d  mov     rax, cs:__security_cookie
0x180052a64  xor     rax, rsp
0x180052a67  mov     [rbp+var_8], rax
0x180052a6b  mov     [rbp+var_10], 0
0x180052a72  mov     rbx, r8
0x180052a75  mov     dword ptr [rbp+var_30+4], 0
0x180052a7c  mov     r8d, ecx
0x180052a7f  test    ecx, 0FFFFFFE0h
0x180052a85  jz      short loc_180052AC2
0x180052a87  lea     rax, aOnecoreBaseXml; "onecore\\base\\xml\\xml_writer.cpp"
0x180052a8e  mov     [rbp+var_20], 2EFh
0x180052a96  mov     [rbp-30h], rax
0x180052a9a  lea     rax, aXmlwriterimple; "XmlWriterImplementation::RtlCreateDefau"...
0x180052aa1  mov     [rbp+var_28], rax
0x180052aa5  lea     rax, aValidFlagsChec; "Valid flags check failed: Flags"
0x180052aac  lea     rdx, [rbp+var_30]
0x180052ab0  mov     [rbp+var_18], rax
0x180052ab4  lea     rcx, [rbp+var_10]
0x180052ab8  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180052abd  jmp     loc_180052BA6
0x180052ac2  and     ecx, 6
0x180052ac5  lea     eax, [rcx-1]
0x180052ac8  test    ecx, eax
0x180052aca  jz      short loc_180052AF3
0x180052acc  lea     rax, aOnecoreBaseXml; "onecore\\base\\xml\\xml_writer.cpp"
0x180052ad3  mov     [rbp+var_20], 2F4h
0x180052adb  mov     [rbp+var_30], rax
0x180052adf  lea     rax, aXmlwriterimple; "XmlWriterImplementation::RtlCreateDefau"...
0x180052ae6  mov     [rbp+var_28], rax
0x180052aea  lea     rax, aNoMoreThanOneF_0; "No more than one flag set check failed:"...
0x180052af1  jmp     short loc_180052AAC
0x180052af3  test    rdx, rdx
0x180052af6  jnz     short loc_180052B30
0x180052af8  lea     rax, aOnecoreBaseXml; "onecore\\base\\xml\\xml_writer.cpp"
0x180052aff  mov     [rbp+var_20], 2F6h
0x180052b07  mov     [rbp+var_30], rax
0x180052b0b  lea     rax, aXmlwriterimple; "XmlWriterImplementation::RtlCreateDefau"...
0x180052b12  mov     [rbp+var_28], rax
0x180052b16  lea     rax, aNotNullCheckFa_38; "Not-null check failed: pStreamToWriteTo"
0x180052b1d  lea     rdx, [rbp+var_30]
0x180052b21  mov     [rbp+var_18], rax
0x180052b25  lea     rcx, [rbp+var_10]
0x180052b29  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180052b2e  jmp     short loc_180052BA6
0x180052b30  test    rbx, rbx
0x180052b33  jnz     short loc_180052B5C
0x180052b35  lea     rax, aOnecoreBaseXml; "onecore\\base\\xml\\xml_writer.cpp"
0x180052b3c  mov     [rbp+var_20], 2F7h
0x180052b44  mov     [rbp+var_30], rax
0x180052b48  lea     rax, aXmlwriterimple; "XmlWriterImplementation::RtlCreateDefau"...
0x180052b4f  mov     [rbp+var_28], rax
0x180052b53  lea     rax, aNotNullCheckFa_114; "Not-null check failed: Writer"
0x180052b5a  jmp     short loc_180052B1D
0x180052b5c  mov     dword ptr [rbp+var_30], r8d
0x180052b60  mov     [rbp+var_28], rdx
0x180052b64  call    ?Initialize@?$CRtlOneShotTypeDescriptionInit@VCXmlWriter@XmlWriterImplementation@@@Rtl@Windows@@QEAAJXZ; Windows::Rtl::CRtlOneShotTypeDescriptionInit<XmlWriterImplementation::CXmlWriter>::Initialize(void)
0x180052b69  test    eax, eax
0x180052b6b  js      short loc_180052BA6
0x180052b6d  mov     eax, cs:dword_1800D4AC8
0x180052b73  cmp     eax, 2
0x180052b76  jz      short loc_180052B8A
0x180052b78  mov     ecx, 0C00000E5h; Status
0x180052b7d  call    cs:__imp_RtlRaiseStatus
0x180052b84  nop     dword ptr [rax+rax+00h]
0x180052b89  int     3; Trap to Debugger
0x180052b8a  mov     rcx, cs:?g_XmlWriterType@XmlWriterImplementation@@3V?$CRtlOneShotTypeDescriptionInit@VCXmlWriter@XmlWriterImplementation@@@Rtl@Windows@@A; Windows::Rtl::CRtlOneShotTypeDescriptionInit<XmlWriterImplementation::CXmlWriter> XmlWriterImplementation::g_XmlWriterType
0x180052b91  lea     rdx, [rbp+var_30]
0x180052b95  mov     r8, rbx
0x180052b98  call    ??$CreateInstance@VCXmlWriter_IRtlXmlWriter@XmlWriterImplementation@@UInitParams@CXmlWriter@2@UIRtlXmlWriter@Rtl@Microdom@Windows@@@?$CRtlObjectTypeDescription@VCXmlWriter@XmlWriterImplementation@@@Rtl@Windows@@QEAAJAEBUInitParams@CXmlWriter@XmlWriterImplementation@@PEAV?$Auto@PEAUIRtlXmlWriter@Rtl@Microdom@Windows@@@2@@Z; Windows::Rtl::CRtlObjectTypeDescription<XmlWriterImplementation::CXmlWriter>::CreateInstance<XmlWriterImplementation::CXmlWriter_IRtlXmlWriter,XmlWriterImplementation::CXmlWriter::InitParams,Windows::Microdom::Rtl::IRtlXmlWriter>(XmlWriterImplementation::CXmlWriter::InitParams const &,Windows::Auto<Windows::Microdom::Rtl::IRtlXmlWriter *> *)
0x180052b9d  xor     ecx, ecx
0x180052b9f  test    eax, eax
0x180052ba1  cmovs   ecx, eax
0x180052ba4  mov     eax, ecx
0x180052ba6  mov     rcx, [rbp+var_8]
0x180052baa  xor     rcx, rsp; StackCookie
0x180052bad  call    __security_check_cookie
0x180052bb2  mov     rbx, [rsp+50h+arg_18]
0x180052bb7  add     rsp, 50h
0x180052bbb  pop     rbp
0x180052bbc  retn
```
