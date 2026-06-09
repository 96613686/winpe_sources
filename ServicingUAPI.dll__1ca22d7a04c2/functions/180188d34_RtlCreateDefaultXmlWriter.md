# RtlCreateDefaultXmlWriter

- ea: `0x180188d34`
- end: `0x180188f0f`
- name: `RtlCreateDefaultXmlWriter`
- size: `475`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18009ab70`
- `0x1800aa4c8`
- `0x18013cf80`

## callees

- `0x18000aedc`
- `0x1800497c0`
- `0x180187920`
- `0x180188d34`

## import_xrefs

- `ntdll!NtYieldExecution` at `0x180188e98`
- `ntdll!NtYieldExecution` at `0x180188e98`
- `ntdll!RtlRaiseStatus` at `0x180188ecf`
- `ntdll!RtlRaiseStatus` at `0x180188ecf`

## string_xrefs

- `0x180188d56`: `onecore\base\xml\xml_writer.cpp`
- `0x180188da9`: `onecore\base\xml\xml_writer.cpp`
- `0x180188dd5`: `onecore\base\xml\xml_writer.cpp`
- `0x180188e04`: `onecore\base\xml\xml_writer.cpp`
- `0x180188d69`: `XmlWriterImplementation::RtlCreateDefaultXmlWriter`
- `0x180188dbc`: `XmlWriterImplementation::RtlCreateDefaultXmlWriter`
- `0x180188de8`: `XmlWriterImplementation::RtlCreateDefaultXmlWriter`
- `0x180188e17`: `XmlWriterImplementation::RtlCreateDefaultXmlWriter`
- `0x180188e22`: `Not-null check failed: Writer`
- `0x180188df3`: `Not-null check failed: pStreamToWriteTo`

## pseudocode

```c
__int64 __fastcall RtlCreateDefaultXmlWriter(int a1, const char *a2, __int64 a3)
{
  const char *v4; // rax
  signed __int32 v6; // eax
  int v7; // eax
  unsigned int v8; // ecx
  signed __int32 v9[8]; // [rsp+0h] [rbp-40h] BYREF
  const char *v10; // [rsp+20h] [rbp-20h] BYREF
  const char *v11; // [rsp+28h] [rbp-18h]
  __int64 v12; // [rsp+30h] [rbp-10h]
  const char *v13; // [rsp+38h] [rbp-8h]

  HIDWORD(v10) = 0;
  if ( (a1 & 0xFFFFFFE0) != 0 )
  {
    v12 = 751;
    v10 = "onecore\\base\\xml\\xml_writer.cpp";
    v11 = "XmlWriterImplementation::RtlCreateDefaultXmlWriter";
    v4 = "Valid flags check failed: Flags";
LABEL_3:
    v13 = v4;
    RtlReportErrorOrigination(&v10, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
    return 3221225485LL;
  }
  if ( (((a1 & 6) - 1) & a1 & 6) != 0 )
  {
    v12 = 756;
    v10 = "onecore\\base\\xml\\xml_writer.cpp";
    v11 = "XmlWriterImplementation::RtlCreateDefaultXmlWriter";
    v4 = "No more than one flag set check failed: Flags";
    goto LABEL_3;
  }
  if ( !a2 )
  {
    v12 = 758;
    v10 = "onecore\\base\\xml\\xml_writer.cpp";
    v11 = "XmlWriterImplementation::RtlCreateDefaultXmlWriter";
    v4 = "Not-null check failed: pStreamToWriteTo";
    goto LABEL_3;
  }
  if ( !a3 )
  {
    v12 = 759;
    v10 = "onecore\\base\\xml\\xml_writer.cpp";
    v11 = "XmlWriterImplementation::RtlCreateDefaultXmlWriter";
    v4 = "Not-null check failed: Writer";
    goto LABEL_3;
  }
  LODWORD(v10) = a1;
  v11 = a2;
  if ( dword_18023FFB8 != 2 )
  {
    _InterlockedOr(v9, 0);
    v6 = _InterlockedCompareExchange(&dword_18023FFB8, 1, 0);
    if ( v6 )
    {
      if ( v6 == 1 )
      {
        while ( dword_18023FFB8 != 2 )
          NtYieldExecution();
      }
    }
    else
    {
      if ( XmlWriterImplementation::g_XmlWriterType )
      {
LABEL_23:
        INTERNAL_ERROR_ACTION(-1073741595);
        JUMPOUT(0x180188F0ELL);
      }
      dword_18023FFA8 = 0;
      XmlWriterImplementation::g_XmlWriterType = (__int64)&dword_18023FFA8;
      dword_18023FFAC = 0;
      _InterlockedExchange(&dword_18023FFB8, 2);
    }
    _InterlockedOr(v9, 0);
  }
  if ( dword_18023FFB8 != 2 )
    goto LABEL_23;
  v7 = Windows::Rtl::CRtlObjectTypeDescription<XmlWriterImplementation::CXmlWriter>::CreateInstance<XmlWriterImplementation::CXmlWriter_IRtlXmlWriter,XmlWriterImplementation::CXmlWriter::InitParams,Windows::Microdom::Rtl::IRtlXmlWriter>(
         XmlWriterImplementation::g_XmlWriterType,
         &v10,
         a3);
  v8 = 0;
  if ( v7 < 0 )
    return (unsigned int)v7;
  return v8;
}

```

## disassembly

```asm
0x180188d34  mov     [rsp-8+arg_18], rbx
0x180188d39  push    rbp
0x180188d3a  mov     rbp, rsp
0x180188d3d  sub     rsp, 40h
0x180188d41  mov     dword ptr [rbp+var_20+4], 0
0x180188d48  mov     rbx, r8
0x180188d4b  mov     r8d, ecx
0x180188d4e  test    ecx, 0FFFFFFE0h
0x180188d54  jz      short loc_180188D9F
0x180188d56  lea     rax, aOnecoreBaseXml; "onecore\\base\\xml\\xml_writer.cpp"
0x180188d5d  mov     [rbp+var_10], 2EFh
0x180188d65  mov     [rbp-20h], rax
0x180188d69  lea     rax, aXmlwriterimple; "XmlWriterImplementation::RtlCreateDefau"...
0x180188d70  mov     [rbp+var_18], rax
0x180188d74  lea     rax, aValidFlagsChec_0; "Valid flags check failed: Flags"
0x180188d7b  mov     r8d, 0C000000Dh
0x180188d81  mov     [rbp+var_8], rax
0x180188d85  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180188d8c  lea     rcx, [rbp+var_20]
0x180188d90  call    RtlReportErrorOrigination
0x180188d95  mov     eax, 0C000000Dh
0x180188d9a  jmp     loc_180188EF8
0x180188d9f  and     ecx, 6
0x180188da2  lea     eax, [rcx-1]
0x180188da5  test    ecx, eax
0x180188da7  jz      short loc_180188DD0
0x180188da9  lea     rax, aOnecoreBaseXml; "onecore\\base\\xml\\xml_writer.cpp"
0x180188db0  mov     [rbp+var_10], 2F4h
0x180188db8  mov     [rbp+var_20], rax
0x180188dbc  lea     rax, aXmlwriterimple; "XmlWriterImplementation::RtlCreateDefau"...
0x180188dc3  mov     [rbp+var_18], rax
0x180188dc7  lea     rax, aNoMoreThanOneF_0; "No more than one flag set check failed:"...
0x180188dce  jmp     short loc_180188D7B
0x180188dd0  test    rdx, rdx
0x180188dd3  jnz     short loc_180188DFF
0x180188dd5  lea     rax, aOnecoreBaseXml; "onecore\\base\\xml\\xml_writer.cpp"
0x180188ddc  mov     [rbp+var_10], 2F6h
0x180188de4  mov     [rbp+var_20], rax
0x180188de8  lea     rax, aXmlwriterimple; "XmlWriterImplementation::RtlCreateDefau"...
0x180188def  mov     [rbp+var_18], rax
0x180188df3  lea     rax, aNotNullCheckFa_26; "Not-null check failed: pStreamToWriteTo"
0x180188dfa  jmp     loc_180188D7B
0x180188dff  test    rbx, rbx
0x180188e02  jnz     short loc_180188E2E
0x180188e04  lea     rax, aOnecoreBaseXml; "onecore\\base\\xml\\xml_writer.cpp"
0x180188e0b  mov     [rbp+var_10], 2F7h
0x180188e13  mov     [rbp+var_20], rax
0x180188e17  lea     rax, aXmlwriterimple; "XmlWriterImplementation::RtlCreateDefau"...
0x180188e1e  mov     [rbp+var_18], rax
0x180188e22  lea     rax, aNotNullCheckFa_70; "Not-null check failed: Writer"
0x180188e29  jmp     loc_180188D7B
0x180188e2e  mov     eax, cs:dword_18023FFB8
0x180188e34  mov     dword ptr [rbp+var_20], r8d
0x180188e38  mov     [rbp+var_18], rdx
0x180188e3c  cmp     eax, 2
0x180188e3f  jz      short loc_180188EB4
0x180188e41  lock or [rsp+40h+var_40], 0
0x180188e46  mov     ecx, 1
0x180188e4b  xor     eax, eax
0x180188e4d  lock cmpxchg cs:dword_18023FFB8, ecx
0x180188e55  jnz     short loc_180188E92
0x180188e57  cmp     cs:?g_XmlWriterType@XmlWriterImplementation@@3V?$CRtlOneShotTypeDescriptionInit@VCXmlWriter@XmlWriterImplementation@@@Rtl@Windows@@A, 0; Windows::Rtl::CRtlOneShotTypeDescriptionInit<XmlWriterImplementation::CXmlWriter> XmlWriterImplementation::g_XmlWriterType
0x180188e5f  jnz     loc_180188F04
0x180188e65  lea     rax, dword_18023FFA8
0x180188e6c  mov     cs:dword_18023FFA8, 0
0x180188e76  mov     cs:?g_XmlWriterType@XmlWriterImplementation@@3V?$CRtlOneShotTypeDescriptionInit@VCXmlWriter@XmlWriterImplementation@@@Rtl@Windows@@A, rax; Windows::Rtl::CRtlOneShotTypeDescriptionInit<XmlWriterImplementation::CXmlWriter> XmlWriterImplementation::g_XmlWriterType
0x180188e7d  lea     eax, [rcx+1]
0x180188e80  mov     cs:dword_18023FFAC, 0
0x180188e8a  xchg    eax, cs:dword_18023FFB8
0x180188e90  jmp     short loc_180188EAF
0x180188e92  cmp     eax, ecx
0x180188e94  jnz     short loc_180188EAF
0x180188e96  jmp     short loc_180188EA4
0x180188e98  call    cs:__imp_NtYieldExecution
0x180188e9f  nop     dword ptr [rax+rax+00h]
0x180188ea4  mov     eax, cs:dword_18023FFB8
0x180188eaa  cmp     eax, 2
0x180188ead  jnz     short loc_180188E98
0x180188eaf  lock or [rsp+40h+var_40], 0
0x180188eb4  mov     eax, cs:dword_18023FFB8
0x180188eba  cmp     eax, 2
0x180188ebd  jnz     short loc_180188F04
0x180188ebf  mov     eax, cs:dword_18023FFB8
0x180188ec5  cmp     eax, 2
0x180188ec8  jz      short loc_180188EDC
0x180188eca  mov     ecx, 0C00000E5h; Status
0x180188ecf  call    cs:__imp_RtlRaiseStatus
0x180188ed6  nop     dword ptr [rax+rax+00h]
0x180188edb  int     3; Trap to Debugger
0x180188edc  mov     rcx, cs:?g_XmlWriterType@XmlWriterImplementation@@3V?$CRtlOneShotTypeDescriptionInit@VCXmlWriter@XmlWriterImplementation@@@Rtl@Windows@@A; Windows::Rtl::CRtlOneShotTypeDescriptionInit<XmlWriterImplementation::CXmlWriter> XmlWriterImplementation::g_XmlWriterType
0x180188ee3  lea     rdx, [rbp+var_20]
0x180188ee7  mov     r8, rbx
0x180188eea  call    ??$CreateInstance@VCXmlWriter_IRtlXmlWriter@XmlWriterImplementation@@UInitParams@CXmlWriter@2@UIRtlXmlWriter@Rtl@Microdom@Windows@@@?$CRtlObjectTypeDescription@VCXmlWriter@XmlWriterImplementation@@@Rtl@Windows@@QEAAJAEBUInitParams@CXmlWriter@XmlWriterImplementation@@PEAV?$Auto@PEAUIRtlXmlWriter@Rtl@Microdom@Windows@@@2@@Z; Windows::Rtl::CRtlObjectTypeDescription<XmlWriterImplementation::CXmlWriter>::CreateInstance<XmlWriterImplementation::CXmlWriter_IRtlXmlWriter,XmlWriterImplementation::CXmlWriter::InitParams,Windows::Microdom::Rtl::IRtlXmlWriter>(XmlWriterImplementation::CXmlWriter::InitParams const &,Windows::Auto<Windows::Microdom::Rtl::IRtlXmlWriter *> *)
0x180188eef  xor     ecx, ecx
0x180188ef1  test    eax, eax
0x180188ef3  cmovs   ecx, eax
0x180188ef6  mov     eax, ecx
0x180188ef8  mov     rbx, [rsp+40h+arg_18]
0x180188efd  add     rsp, 40h
0x180188f01  pop     rbp
0x180188f02  retn
0x180188f04  mov     ecx, 0C00000E5h; int
0x180188f09  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
