# PrintDeviceCapabilitiesOM::PwgRasterBacksideTumble::PwgRasterBacksideTumble(Microsoft::WRL::ComPtr<IXMLDOMNode> &,PrintDeviceCapabilitiesOM::Parser::GenericParser *)

- ea: `0x18003cadc`
- end: `0x18003cc34`
- name: `??0PwgRasterBacksideTumble@PrintDeviceCapabilitiesOM@@QEAA@AEAV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEAVGenericParser@Parser@1@@Z`
- size: `344`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180039af8`

## callees

- `0x180002d40`
- `0x180012498`
- `0x180038718`
- `0x1800387fc`
- `0x18003cadc`
- `0x18003cde8`
- `0x18003d548`
- `0x18003e614`
- `0x18003e828`
- `0x18003ebc8`
- `0x18003f368`
- `0x18003f9e4`
- `0x180041024`
- `0x1800421e0`

## string_xrefs

- `0x18003cc18`: `onecoreuap\internal\printscan\inc\private\print\platform\config\DocumentFormatOptions.hxx`
- `0x18003cbf8`: `PwgRasterBacksideTumble`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall PrintDeviceCapabilitiesOM::PwgRasterBacksideTumble::PwgRasterBacksideTumble(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD *inited; // rax
  _QWORD *v7; // rax
  __int64 v8; // rax
  _QWORD *v9; // rax
  __int64 v10; // rax
  __int64 NodeText; // rax
  _QWORD v13[2]; // [rsp+30h] [rbp-39h] BYREF
  __int64 v14; // [rsp+40h] [rbp-29h] BYREF
  std::_Ref_count_base *v15; // [rsp+48h] [rbp-21h]
  __int64 v16; // [rsp+50h] [rbp-19h]
  __int64 v17; // [rsp+58h] [rbp-11h] BYREF
  _BYTE v18[32]; // [rsp+68h] [rbp-1h] BYREF
  _BYTE v19[8]; // [rsp+88h] [rbp+1Fh] BYREF
  std::_Ref_count_base *v20; // [rsp+90h] [rbp+27h]

  v16 = a1;
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  inited = (_QWORD *)PrintDeviceCapabilitiesOM::NamespaceVault::LazyInitNamespaceUri(4);
  v7 = std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(&v17, inited);
  v8 = PrintDeviceCapabilitiesOM::QualifiedName::QualifiedName(v18, L"DuplexType", v7);
  PrintDeviceCapabilitiesOM::Parser::GetAttributeValue(&v14, v8, a2);
  PrintDeviceCapabilitiesOM::QualifiedName::~QualifiedName((PrintDeviceCapabilitiesOM::QualifiedName *)v18);
  if ( !v14 )
  {
    std::wstring::wstring((__int64)v19, (__int64)L"PwgRasterBacksideTumble");
    LODWORD(v13[0]) = 12;
    PrintDeviceCapabilitiesOM::Exception::Throw::Error(
      (unsigned int)v13,
      (unsigned int)v19,
      (unsigned int)L"DuplexType attribute missing",
      (unsigned int)"onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\DocumentFormatOptions.hxx",
      58);
  }
  v9 = std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(v13, &v14);
  v10 = PrintDeviceCapabilitiesOM::Parser::GenericParser::ToQualifiedName(a3, v19, v9);
  std::shared_ptr<PrintDeviceCapabilitiesOM::NamespaceVault>::operator=(a1, v10);
  if ( v20 )
    std::_Ref_count_base::_Decref(v20);
  NodeText = PrintDeviceCapabilitiesOM::Parser::GetNodeText(v19, a2, 0);
  *(_BYTE *)(a1 + 16) = PrintDeviceCapabilitiesOM::Parser::ParseXmlBoolean(NodeText);
  if ( v20 )
    std::_Ref_count_base::_Decref(v20);
  if ( v15 )
    std::_Ref_count_base::_Decref(v15);
  return a1;
}

```

## disassembly

```asm
0x18003cadc  mov     [rsp-8+arg_18], rbx
0x18003cae1  push    rbp
0x18003cae2  push    rsi
0x18003cae3  push    rdi
0x18003cae4  lea     rbp, [rsp-47h]
0x18003cae9  sub     rsp, 0B0h
0x18003caf0  mov     rax, cs:__security_cookie
0x18003caf7  xor     rax, rsp
0x18003cafa  mov     [rbp+57h+var_18], rax
0x18003cafe  mov     rsi, r8
0x18003cb01  mov     rdi, rdx
0x18003cb04  mov     rbx, rcx
0x18003cb07  mov     [rbp+57h+var_70], rcx
0x18003cb0b  mov     qword ptr [rcx], 0
0x18003cb12  mov     qword ptr [rcx+8], 0
0x18003cb1a  mov     ecx, 4
0x18003cb1f  call    ?LazyInitNamespaceUri@NamespaceVault@PrintDeviceCapabilitiesOM@@CAAEBV?$shared_ptr@$$CBVNamespaceUri@PrintDeviceCapabilitiesOM@@@std@@W4NamespaceType@2@@Z; PrintDeviceCapabilitiesOM::NamespaceVault::LazyInitNamespaceUri(PrintDeviceCapabilitiesOM::NamespaceType)
0x18003cb24  mov     rdx, rax
0x18003cb27  lea     rcx, [rbp+57h+var_68]
0x18003cb2b  call    ??0?$shared_ptr@VOption@PrintDeviceCapabilitiesOM@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(std::shared_ptr<PrintDeviceCapabilitiesOM::Option> const &)
0x18003cb30  mov     r8, rax
0x18003cb33  lea     rdx, aDuplextype; "DuplexType"
0x18003cb3a  lea     rcx, [rbp+57h+var_58]
0x18003cb3e  call    ??0QualifiedName@PrintDeviceCapabilitiesOM@@QEAA@PEBGV?$shared_ptr@$$CBVNamespaceUri@PrintDeviceCapabilitiesOM@@@std@@@Z; PrintDeviceCapabilitiesOM::QualifiedName::QualifiedName(ushort const *,std::shared_ptr<PrintDeviceCapabilitiesOM::NamespaceUri const>)
0x18003cb43  nop
0x18003cb44  mov     r8, rdi
0x18003cb47  mov     rdx, rax
0x18003cb4a  lea     rcx, [rbp+57h+var_80]
0x18003cb4e  call    ?GetAttributeValue@Parser@PrintDeviceCapabilitiesOM@@YA?AV?$shared_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@AEBVQualifiedName@2@AEAV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@@Z; PrintDeviceCapabilitiesOM::Parser::GetAttributeValue(PrintDeviceCapabilitiesOM::QualifiedName const &,Microsoft::WRL::ComPtr<IXMLDOMNode> &)
0x18003cb53  nop
0x18003cb54  lea     rcx, [rbp+57h+var_58]; this
0x18003cb58  call    ??1QualifiedName@PrintDeviceCapabilitiesOM@@QEAA@XZ; PrintDeviceCapabilitiesOM::QualifiedName::~QualifiedName(void)
0x18003cb5d  cmp     [rbp+57h+var_80], 0
0x18003cb62  jz      loc_18003CBF8
0x18003cb68  lea     rdx, [rbp+57h+var_80]
0x18003cb6c  lea     rcx, [rbp+57h+var_90]
0x18003cb70  call    ??0?$shared_ptr@VOption@PrintDeviceCapabilitiesOM@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(std::shared_ptr<PrintDeviceCapabilitiesOM::Option> const &)
0x18003cb75  mov     r8, rax
0x18003cb78  lea     rdx, [rbp+57h+var_38]
0x18003cb7c  mov     rcx, rsi
0x18003cb7f  call    ?ToQualifiedName@GenericParser@Parser@PrintDeviceCapabilitiesOM@@QEBA?AV?$shared_ptr@$$CBVQualifiedName@PrintDeviceCapabilitiesOM@@@std@@V?$shared_ptr@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@5@@Z; PrintDeviceCapabilitiesOM::Parser::GenericParser::ToQualifiedName(std::shared_ptr<std::wstring const>)
0x18003cb84  mov     rdx, rax
0x18003cb87  mov     rcx, rbx
0x18003cb8a  call    ??4?$shared_ptr@VNamespaceVault@PrintDeviceCapabilitiesOM@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<PrintDeviceCapabilitiesOM::NamespaceVault>::operator=(std::shared_ptr<PrintDeviceCapabilitiesOM::NamespaceVault> &&)
0x18003cb8f  mov     rcx, [rbp+57h+var_30]; this
0x18003cb93  test    rcx, rcx
0x18003cb96  jz      short loc_18003CB9D
0x18003cb98  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003cb9d  xor     r8d, r8d
0x18003cba0  mov     rdx, rdi
0x18003cba3  lea     rcx, [rbp+57h+var_38]
0x18003cba7  call    ?GetNodeText@Parser@PrintDeviceCapabilitiesOM@@YA?AV?$shared_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@AEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEBG@Z; PrintDeviceCapabilitiesOM::Parser::GetNodeText(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort const *)
0x18003cbac  nop
0x18003cbad  mov     rcx, rax
0x18003cbb0  call    ?ParseXmlBoolean@Parser@PrintDeviceCapabilitiesOM@@YA_NAEBV?$shared_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@Z; PrintDeviceCapabilitiesOM::Parser::ParseXmlBoolean(std::shared_ptr<std::wstring> const &)
0x18003cbb5  mov     [rbx+10h], al
0x18003cbb8  mov     rcx, [rbp+57h+var_30]; this
0x18003cbbc  test    rcx, rcx
0x18003cbbf  jz      short loc_18003CBC7
0x18003cbc1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003cbc6  nop
0x18003cbc7  mov     rcx, [rbp+57h+var_78]; this
0x18003cbcb  test    rcx, rcx
0x18003cbce  jz      short loc_18003CBD6
0x18003cbd0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003cbd5  nop
0x18003cbd6  mov     rax, rbx
0x18003cbd9  mov     rcx, [rbp+57h+var_18]
0x18003cbdd  xor     rcx, rsp; StackCookie
0x18003cbe0  call    __security_check_cookie
0x18003cbe5  mov     rbx, [rsp+0C0h+arg_18]
0x18003cbed  add     rsp, 0B0h
0x18003cbf4  pop     rdi
0x18003cbf5  pop     rsi
0x18003cbf6  pop     rbp
0x18003cbf7  retn
0x18003cbf8  lea     rdx, aPwgrasterbacks; "PwgRasterBacksideTumble"
0x18003cbff  lea     rcx, [rbp+57h+var_38]
0x18003cc03  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003cc08  nop
0x18003cc09  mov     [rbp+57h+var_90], 0Ch
0x18003cc10  mov     [rsp+0C0h+var_A0], 3Ah ; ':'
0x18003cc18  lea     r9, aOnecoreuapInte; "onecoreuap\\internal\\printscan\\inc\\p"...
0x18003cc1f  lea     r8, aDuplextypeAttr; "DuplexType attribute missing"
0x18003cc26  lea     rdx, [rbp+57h+var_38]
0x18003cc2a  lea     rcx, [rbp+57h+var_90]
0x18003cc2e  call    ?Error@Throw@Exception@PrintDeviceCapabilitiesOM@@YAXAEBW4ElementType@23@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGPEBDI@Z; PrintDeviceCapabilitiesOM::Exception::Throw::Error(PrintDeviceCapabilitiesOM::Exception::ElementType const &,std::wstring const &,ushort const *,char const *,uint)
```
