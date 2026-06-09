# PrintDeviceCapabilitiesOM::InvalidCombinationEntry::InvalidCombinationEntry(Microsoft::WRL::ComPtr<IXMLDOMNode> &,PrintDeviceCapabilitiesOM::Parser::GenericParser *)

- ea: `0x18003bfd4`
- end: `0x18003c1d7`
- name: `??0InvalidCombinationEntry@PrintDeviceCapabilitiesOM@@QEAA@AEAV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEAVGenericParser@Parser@1@@Z`
- size: `515`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800393fc`

## callees

- `0x180002d40`
- `0x18001031c`
- `0x180012498`
- `0x180038718`
- `0x1800387fc`
- `0x18003bfd4`
- `0x18003cde8`
- `0x18003d548`
- `0x18003e614`
- `0x18003e828`
- `0x18003f368`
- `0x180041024`
- `0x1800421e0`

## string_xrefs

- `0x18003c183`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`
- `0x18003c1bb`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`
- `0x18003c18a`: `InvalidCombinationEntry missing psf2:option entry`
- `0x18003c19b`: `InvalidCombinationEntry`

## pseudocode

```c
_QWORD *__fastcall PrintDeviceCapabilitiesOM::InvalidCombinationEntry::InvalidCombinationEntry(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD *inited; // rax
  _QWORD *v7; // rax
  _QWORD *v8; // rax
  _QWORD *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  _QWORD *v13; // rax
  __int64 v14; // rax
  _QWORD *v15; // rax
  __int64 v16; // rax
  int v18; // eax
  __int64 v19; // [rsp+30h] [rbp-69h] BYREF
  std::_Ref_count_base *v20; // [rsp+38h] [rbp-61h]
  __int64 v21; // [rsp+40h] [rbp-59h] BYREF
  std::_Ref_count_base *v22; // [rsp+48h] [rbp-51h]
  __int64 v23; // [rsp+50h] [rbp-49h] BYREF
  std::_Ref_count_base *v24; // [rsp+58h] [rbp-41h]
  _QWORD *v25; // [rsp+60h] [rbp-39h]
  _BYTE v26[32]; // [rsp+68h] [rbp-31h] BYREF
  _BYTE v27[32]; // [rsp+88h] [rbp-11h] BYREF
  __int64 v28; // [rsp+A8h] [rbp+Fh] BYREF
  std::_Ref_count_base *v29; // [rsp+B0h] [rbp+17h]

  v25 = a1;
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  a1[3] = 0;
  inited = (_QWORD *)PrintDeviceCapabilitiesOM::NamespaceVault::LazyInitNamespaceUri(4);
  v7 = std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(&v21, inited);
  PrintDeviceCapabilitiesOM::QualifiedName::QualifiedName(v27, L"feature", v7);
  v8 = (_QWORD *)PrintDeviceCapabilitiesOM::NamespaceVault::LazyInitNamespaceUri(4);
  v9 = std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(&v19, v8);
  PrintDeviceCapabilitiesOM::QualifiedName::QualifiedName(v26, L"option", v9);
  PrintDeviceCapabilitiesOM::Parser::GetAttributeValue(&v23, v27, a2);
  PrintDeviceCapabilitiesOM::Parser::GetAttributeValue(&v21, v26, a2);
  if ( !v23 )
  {
    std::wstring::wstring((__int64)&v28, (__int64)L"InvalidCombinationEntry");
    LODWORD(v19) = 13;
    PrintDeviceCapabilitiesOM::Exception::Throw::Error(
      (unsigned int)&v19,
      (unsigned int)&v28,
      (unsigned int)L"missing psf2:feature entry",
      (unsigned int)"onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOM.hxx",
      3128);
  }
  if ( !v21 )
  {
    LODWORD(v19) = 13;
    v18 = std::shared_ptr<std::wstring>::operator*<std::wstring,0>(&v23, v10, v11, v12);
    PrintDeviceCapabilitiesOM::Exception::Throw::Error(
      (unsigned int)&v19,
      v18,
      (unsigned int)L"InvalidCombinationEntry missing psf2:option entry",
      (unsigned int)"onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOM.hxx",
      3132);
  }
  v13 = std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(&v19, &v23);
  v14 = PrintDeviceCapabilitiesOM::Parser::GenericParser::ToQualifiedName(a3, &v28, v13);
  std::shared_ptr<PrintDeviceCapabilitiesOM::NamespaceVault>::operator=(a1, v14);
  if ( v29 )
    std::_Ref_count_base::_Decref(v29);
  v15 = std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(&v28, &v21);
  v16 = PrintDeviceCapabilitiesOM::Parser::GenericParser::ToQualifiedName(a3, &v19, v15);
  std::shared_ptr<PrintDeviceCapabilitiesOM::NamespaceVault>::operator=(a1 + 2, v16);
  if ( v20 )
    std::_Ref_count_base::_Decref(v20);
  if ( v22 )
    std::_Ref_count_base::_Decref(v22);
  if ( v24 )
    std::_Ref_count_base::_Decref(v24);
  PrintDeviceCapabilitiesOM::QualifiedName::~QualifiedName((PrintDeviceCapabilitiesOM::QualifiedName *)v26);
  PrintDeviceCapabilitiesOM::QualifiedName::~QualifiedName((PrintDeviceCapabilitiesOM::QualifiedName *)v27);
  return a1;
}

```

## disassembly

```asm
0x18003bfd4  push    rbp
0x18003bfd6  push    rbx
0x18003bfd7  push    rsi
0x18003bfd8  push    rdi
0x18003bfd9  push    r14
0x18003bfdb  lea     rbp, [rsp-37h]
0x18003bfe0  sub     rsp, 0D0h
0x18003bfe7  mov     rax, cs:__security_cookie
0x18003bfee  xor     rax, rsp
0x18003bff1  mov     [rbp+57h+var_28], rax
0x18003bff5  mov     rsi, r8
0x18003bff8  mov     rbx, rdx
0x18003bffb  mov     rdi, rcx
0x18003bffe  mov     [rbp+57h+var_90], rcx
0x18003c002  mov     qword ptr [rcx], 0
0x18003c009  mov     qword ptr [rcx+8], 0
0x18003c011  mov     qword ptr [rcx+10h], 0
0x18003c019  mov     qword ptr [rcx+18h], 0
0x18003c021  mov     ecx, 4
0x18003c026  call    ?LazyInitNamespaceUri@NamespaceVault@PrintDeviceCapabilitiesOM@@CAAEBV?$shared_ptr@$$CBVNamespaceUri@PrintDeviceCapabilitiesOM@@@std@@W4NamespaceType@2@@Z; PrintDeviceCapabilitiesOM::NamespaceVault::LazyInitNamespaceUri(PrintDeviceCapabilitiesOM::NamespaceType)
0x18003c02b  mov     rdx, rax
0x18003c02e  lea     rcx, [rbp+57h+var_B0]
0x18003c032  call    ??0?$shared_ptr@VOption@PrintDeviceCapabilitiesOM@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(std::shared_ptr<PrintDeviceCapabilitiesOM::Option> const &)
0x18003c037  mov     r8, rax
0x18003c03a  lea     rdx, aFeature; "feature"
0x18003c041  lea     rcx, [rbp+57h+var_68]
0x18003c045  call    ??0QualifiedName@PrintDeviceCapabilitiesOM@@QEAA@PEBGV?$shared_ptr@$$CBVNamespaceUri@PrintDeviceCapabilitiesOM@@@std@@@Z; PrintDeviceCapabilitiesOM::QualifiedName::QualifiedName(ushort const *,std::shared_ptr<PrintDeviceCapabilitiesOM::NamespaceUri const>)
0x18003c04a  nop
0x18003c04b  mov     ecx, 4
0x18003c050  call    ?LazyInitNamespaceUri@NamespaceVault@PrintDeviceCapabilitiesOM@@CAAEBV?$shared_ptr@$$CBVNamespaceUri@PrintDeviceCapabilitiesOM@@@std@@W4NamespaceType@2@@Z; PrintDeviceCapabilitiesOM::NamespaceVault::LazyInitNamespaceUri(PrintDeviceCapabilitiesOM::NamespaceType)
0x18003c055  mov     rdx, rax
0x18003c058  lea     rcx, [rbp+57h+var_C0]
0x18003c05c  call    ??0?$shared_ptr@VOption@PrintDeviceCapabilitiesOM@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(std::shared_ptr<PrintDeviceCapabilitiesOM::Option> const &)
0x18003c061  mov     r8, rax
0x18003c064  lea     rdx, aOption_0; "option"
0x18003c06b  lea     rcx, [rbp+57h+var_88]
0x18003c06f  call    ??0QualifiedName@PrintDeviceCapabilitiesOM@@QEAA@PEBGV?$shared_ptr@$$CBVNamespaceUri@PrintDeviceCapabilitiesOM@@@std@@@Z; PrintDeviceCapabilitiesOM::QualifiedName::QualifiedName(ushort const *,std::shared_ptr<PrintDeviceCapabilitiesOM::NamespaceUri const>)
0x18003c074  nop
0x18003c075  mov     r8, rbx
0x18003c078  lea     rdx, [rbp+57h+var_68]
0x18003c07c  lea     rcx, [rbp+57h+var_A0]
0x18003c080  call    ?GetAttributeValue@Parser@PrintDeviceCapabilitiesOM@@YA?AV?$shared_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@AEBVQualifiedName@2@AEAV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@@Z; PrintDeviceCapabilitiesOM::Parser::GetAttributeValue(PrintDeviceCapabilitiesOM::QualifiedName const &,Microsoft::WRL::ComPtr<IXMLDOMNode> &)
0x18003c085  nop
0x18003c086  mov     r8, rbx
0x18003c089  lea     rdx, [rbp+57h+var_88]
0x18003c08d  lea     rcx, [rbp+57h+var_B0]
0x18003c091  call    ?GetAttributeValue@Parser@PrintDeviceCapabilitiesOM@@YA?AV?$shared_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@AEBVQualifiedName@2@AEAV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@@Z; PrintDeviceCapabilitiesOM::Parser::GetAttributeValue(PrintDeviceCapabilitiesOM::QualifiedName const &,Microsoft::WRL::ComPtr<IXMLDOMNode> &)
0x18003c096  nop
0x18003c097  cmp     [rbp+57h+var_A0], 0
0x18003c09c  jz      loc_18003C19B
0x18003c0a2  cmp     [rbp+57h+var_B0], 0
0x18003c0a7  jz      loc_18003C168
0x18003c0ad  lea     rdx, [rbp+57h+var_A0]
0x18003c0b1  lea     rcx, [rbp+57h+var_C0]
0x18003c0b5  call    ??0?$shared_ptr@VOption@PrintDeviceCapabilitiesOM@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(std::shared_ptr<PrintDeviceCapabilitiesOM::Option> const &)
0x18003c0ba  mov     r8, rax
0x18003c0bd  lea     rdx, [rbp+57h+var_48]
0x18003c0c1  mov     rcx, rsi
0x18003c0c4  call    ?ToQualifiedName@GenericParser@Parser@PrintDeviceCapabilitiesOM@@QEBA?AV?$shared_ptr@$$CBVQualifiedName@PrintDeviceCapabilitiesOM@@@std@@V?$shared_ptr@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@5@@Z; PrintDeviceCapabilitiesOM::Parser::GenericParser::ToQualifiedName(std::shared_ptr<std::wstring const>)
0x18003c0c9  mov     rdx, rax
0x18003c0cc  mov     rcx, rdi
0x18003c0cf  call    ??4?$shared_ptr@VNamespaceVault@PrintDeviceCapabilitiesOM@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<PrintDeviceCapabilitiesOM::NamespaceVault>::operator=(std::shared_ptr<PrintDeviceCapabilitiesOM::NamespaceVault> &&)
0x18003c0d4  mov     rcx, [rbp+57h+var_40]; this
0x18003c0d8  test    rcx, rcx
0x18003c0db  jz      short loc_18003C0E2
0x18003c0dd  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003c0e2  lea     rdx, [rbp+57h+var_B0]
0x18003c0e6  lea     rcx, [rbp+57h+var_48]
0x18003c0ea  call    ??0?$shared_ptr@VOption@PrintDeviceCapabilitiesOM@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(std::shared_ptr<PrintDeviceCapabilitiesOM::Option> const &)
0x18003c0ef  mov     r8, rax
0x18003c0f2  lea     rdx, [rbp+57h+var_C0]
0x18003c0f6  mov     rcx, rsi
0x18003c0f9  call    ?ToQualifiedName@GenericParser@Parser@PrintDeviceCapabilitiesOM@@QEBA?AV?$shared_ptr@$$CBVQualifiedName@PrintDeviceCapabilitiesOM@@@std@@V?$shared_ptr@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@5@@Z; PrintDeviceCapabilitiesOM::Parser::GenericParser::ToQualifiedName(std::shared_ptr<std::wstring const>)
0x18003c0fe  mov     rdx, rax
0x18003c101  lea     rcx, [rdi+10h]
0x18003c105  call    ??4?$shared_ptr@VNamespaceVault@PrintDeviceCapabilitiesOM@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<PrintDeviceCapabilitiesOM::NamespaceVault>::operator=(std::shared_ptr<PrintDeviceCapabilitiesOM::NamespaceVault> &&)
0x18003c10a  mov     rcx, [rbp+57h+var_B8]; this
0x18003c10e  test    rcx, rcx
0x18003c111  jz      short loc_18003C119
0x18003c113  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003c118  nop
0x18003c119  mov     rcx, [rbp+57h+var_A8]; this
0x18003c11d  test    rcx, rcx
0x18003c120  jz      short loc_18003C128
0x18003c122  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003c127  nop
0x18003c128  mov     rcx, [rbp+57h+var_98]; this
0x18003c12c  test    rcx, rcx
0x18003c12f  jz      short loc_18003C137
0x18003c131  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003c136  nop
0x18003c137  lea     rcx, [rbp+57h+var_88]; this
0x18003c13b  call    ??1QualifiedName@PrintDeviceCapabilitiesOM@@QEAA@XZ; PrintDeviceCapabilitiesOM::QualifiedName::~QualifiedName(void)
0x18003c140  nop
0x18003c141  lea     rcx, [rbp+57h+var_68]; this
0x18003c145  call    ??1QualifiedName@PrintDeviceCapabilitiesOM@@QEAA@XZ; PrintDeviceCapabilitiesOM::QualifiedName::~QualifiedName(void)
0x18003c14a  nop
0x18003c14b  mov     rax, rdi
0x18003c14e  mov     rcx, [rbp+57h+var_28]
0x18003c152  xor     rcx, rsp; StackCookie
0x18003c155  call    __security_check_cookie
0x18003c15a  add     rsp, 0D0h
0x18003c161  pop     r14
0x18003c163  pop     rdi
0x18003c164  pop     rsi
0x18003c165  pop     rbx
0x18003c166  pop     rbp
0x18003c167  retn
0x18003c168  mov     dword ptr [rbp+57h+var_C0], 0Dh
0x18003c16f  lea     rcx, [rbp+57h+var_A0]
0x18003c173  call    ??$?DV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0A@@?$shared_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEBAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@XZ; std::shared_ptr<std::wstring>::operator*<std::wstring,0>(void)
0x18003c178  mov     rdx, rax
0x18003c17b  mov     [rsp+0F0h+var_D0], 0C3Ch
0x18003c183  lea     r9, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x18003c18a  lea     r8, aInvalidcombina; "InvalidCombinationEntry missing psf2:op"...
0x18003c191  lea     rcx, [rbp+57h+var_C0]
0x18003c195  call    ?Error@Throw@Exception@PrintDeviceCapabilitiesOM@@YAXAEBW4ElementType@23@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGPEBDI@Z; PrintDeviceCapabilitiesOM::Exception::Throw::Error(PrintDeviceCapabilitiesOM::Exception::ElementType const &,std::wstring const &,ushort const *,char const *,uint)
0x18003c19b  lea     rdx, aInvalidcombina_1; "InvalidCombinationEntry"
0x18003c1a2  lea     rcx, [rbp+57h+var_48]
0x18003c1a6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003c1ab  nop
0x18003c1ac  mov     dword ptr [rbp+57h+var_C0], 0Dh
0x18003c1b3  mov     [rsp+0F0h+var_D0], 0C38h
0x18003c1bb  lea     r9, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x18003c1c2  lea     r8, aMissingPsf2Fea; "missing psf2:feature entry"
0x18003c1c9  lea     rdx, [rbp+57h+var_48]
0x18003c1cd  lea     rcx, [rbp+57h+var_C0]
0x18003c1d1  call    ?Error@Throw@Exception@PrintDeviceCapabilitiesOM@@YAXAEBW4ElementType@23@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGPEBDI@Z; PrintDeviceCapabilitiesOM::Exception::Throw::Error(PrintDeviceCapabilitiesOM::Exception::ElementType const &,std::wstring const &,ushort const *,char const *,uint)
```
