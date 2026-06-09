# PrintDeviceCapabilitiesOM::PwgRasterDocumentType::PwgRasterDocumentType(Microsoft::WRL::ComPtr<IXMLDOMNode> &,PrintDeviceCapabilitiesOM::Parser::GenericParser *)

- ea: `0x18003cc3c`
- end: `0x18003cde1`
- name: `??0PwgRasterDocumentType@PrintDeviceCapabilitiesOM@@QEAA@AEAV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEAVGenericParser@Parser@1@@Z`
- size: `421`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180039d4c`

## callees

- `0x180002d40`
- `0x180012498`
- `0x180038718`
- `0x1800387fc`
- `0x18003cc3c`
- `0x18003cde8`
- `0x18003d548`
- `0x18003e614`
- `0x18003e828`
- `0x18003ebc8`
- `0x18003f368`
- `0x180041024`
- `0x1800421e0`

## string_xrefs

- `0x18003cd89`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`
- `0x18003cdc5`: `onecoreuap\internal\printscan\inc\private\print\platform\config\PrintDeviceCapabilitiesOM.hxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
_QWORD *__fastcall PrintDeviceCapabilitiesOM::PwgRasterDocumentType::PwgRasterDocumentType(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD *v6; // rdi
  _QWORD *inited; // rax
  _QWORD *v8; // rax
  __int64 v9; // rax
  _QWORD *v10; // rax
  __int64 v11; // rax
  __int64 NodeText; // rax
  _QWORD v14[2]; // [rsp+30h] [rbp-49h] BYREF
  __int64 v15; // [rsp+40h] [rbp-39h] BYREF
  std::_Ref_count_base *v16; // [rsp+48h] [rbp-31h]
  _QWORD *v17; // [rsp+50h] [rbp-29h]
  __int64 v18; // [rsp+58h] [rbp-21h] BYREF
  _BYTE v19[32]; // [rsp+68h] [rbp-11h] BYREF
  _BYTE v20[8]; // [rsp+88h] [rbp+Fh] BYREF
  std::_Ref_count_base *v21; // [rsp+90h] [rbp+17h]

  v17 = a1;
  *a1 = 0;
  a1[1] = 0;
  v6 = a1 + 2;
  a1[2] = 0;
  a1[3] = 0;
  inited = (_QWORD *)PrintDeviceCapabilitiesOM::NamespaceVault::LazyInitNamespaceUri(4);
  v8 = std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(&v18, inited);
  v9 = PrintDeviceCapabilitiesOM::QualifiedName::QualifiedName(v19, L"PageOutputColor", v8);
  PrintDeviceCapabilitiesOM::Parser::GetAttributeValue(&v15, v9, a2);
  PrintDeviceCapabilitiesOM::QualifiedName::~QualifiedName((PrintDeviceCapabilitiesOM::QualifiedName *)v19);
  if ( !v15 )
  {
    std::wstring::wstring((__int64)v20, (__int64)L"PwgRasterDocumentType");
    LODWORD(v14[0]) = 12;
    PrintDeviceCapabilitiesOM::Exception::Throw::Error(
      (unsigned int)v14,
      (unsigned int)v20,
      (unsigned int)L"PageOutputColor attribute missing",
      (unsigned int)"onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOM.hxx",
      750);
  }
  v10 = std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(v14, &v15);
  v11 = PrintDeviceCapabilitiesOM::Parser::GenericParser::ToQualifiedName(a3, v20, v10);
  std::shared_ptr<PrintDeviceCapabilitiesOM::NamespaceVault>::operator=(a1, v11);
  if ( v21 )
    std::_Ref_count_base::_Decref(v21);
  NodeText = PrintDeviceCapabilitiesOM::Parser::GetNodeText(v20, a2, 0);
  std::shared_ptr<PrintDeviceCapabilitiesOM::NamespaceVault>::operator=(v6, NodeText);
  if ( v21 )
    std::_Ref_count_base::_Decref(v21);
  if ( !*v6 )
  {
    std::wstring::wstring((__int64)v20, (__int64)L"PwgRasterDocumentType");
    LODWORD(v14[0]) = 12;
    PrintDeviceCapabilitiesOM::Exception::Throw::Error(
      (unsigned int)v14,
      (unsigned int)v20,
      (unsigned int)L"Color format value missing",
      (unsigned int)"onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\PrintDeviceCapabilitiesOM.hxx",
      758);
  }
  if ( v16 )
    std::_Ref_count_base::_Decref(v16);
  return a1;
}

```

## disassembly

```asm
0x18003cc3c  push    rbp
0x18003cc3e  push    rbx
0x18003cc3f  push    rsi
0x18003cc40  push    rdi
0x18003cc41  push    r14
0x18003cc43  lea     rbp, [rsp-37h]
0x18003cc48  sub     rsp, 0B0h
0x18003cc4f  mov     rax, cs:__security_cookie
0x18003cc56  xor     rax, rsp
0x18003cc59  mov     [rbp+57h+var_28], rax
0x18003cc5d  mov     r14, r8
0x18003cc60  mov     rsi, rdx
0x18003cc63  mov     rbx, rcx
0x18003cc66  mov     [rbp+57h+var_80], rcx
0x18003cc6a  mov     qword ptr [rcx], 0
0x18003cc71  mov     qword ptr [rcx+8], 0
0x18003cc79  lea     rdi, [rcx+10h]
0x18003cc7d  mov     qword ptr [rdi], 0
0x18003cc84  mov     qword ptr [rdi+8], 0
0x18003cc8c  mov     ecx, 4
0x18003cc91  call    ?LazyInitNamespaceUri@NamespaceVault@PrintDeviceCapabilitiesOM@@CAAEBV?$shared_ptr@$$CBVNamespaceUri@PrintDeviceCapabilitiesOM@@@std@@W4NamespaceType@2@@Z; PrintDeviceCapabilitiesOM::NamespaceVault::LazyInitNamespaceUri(PrintDeviceCapabilitiesOM::NamespaceType)
0x18003cc96  mov     rdx, rax
0x18003cc99  lea     rcx, [rbp+57h+var_78]
0x18003cc9d  call    ??0?$shared_ptr@VOption@PrintDeviceCapabilitiesOM@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(std::shared_ptr<PrintDeviceCapabilitiesOM::Option> const &)
0x18003cca2  mov     r8, rax
0x18003cca5  lea     rdx, aPageoutputcolo_0; "PageOutputColor"
0x18003ccac  lea     rcx, [rbp+57h+var_68]
0x18003ccb0  call    ??0QualifiedName@PrintDeviceCapabilitiesOM@@QEAA@PEBGV?$shared_ptr@$$CBVNamespaceUri@PrintDeviceCapabilitiesOM@@@std@@@Z; PrintDeviceCapabilitiesOM::QualifiedName::QualifiedName(ushort const *,std::shared_ptr<PrintDeviceCapabilitiesOM::NamespaceUri const>)
0x18003ccb5  nop
0x18003ccb6  mov     r8, rsi
0x18003ccb9  mov     rdx, rax
0x18003ccbc  lea     rcx, [rbp+57h+var_90]
0x18003ccc0  call    ?GetAttributeValue@Parser@PrintDeviceCapabilitiesOM@@YA?AV?$shared_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@AEBVQualifiedName@2@AEAV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@@Z; PrintDeviceCapabilitiesOM::Parser::GetAttributeValue(PrintDeviceCapabilitiesOM::QualifiedName const &,Microsoft::WRL::ComPtr<IXMLDOMNode> &)
0x18003ccc5  nop
0x18003ccc6  lea     rcx, [rbp+57h+var_68]; this
0x18003ccca  call    ??1QualifiedName@PrintDeviceCapabilitiesOM@@QEAA@XZ; PrintDeviceCapabilitiesOM::QualifiedName::~QualifiedName(void)
0x18003cccf  cmp     [rbp+57h+var_90], 0
0x18003ccd4  jz      loc_18003CDA5
0x18003ccda  lea     rdx, [rbp+57h+var_90]
0x18003ccde  lea     rcx, [rbp+57h+var_A0]
0x18003cce2  call    ??0?$shared_ptr@VOption@PrintDeviceCapabilitiesOM@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(std::shared_ptr<PrintDeviceCapabilitiesOM::Option> const &)
0x18003cce7  mov     r8, rax
0x18003ccea  lea     rdx, [rbp+57h+var_48]
0x18003ccee  mov     rcx, r14
0x18003ccf1  call    ?ToQualifiedName@GenericParser@Parser@PrintDeviceCapabilitiesOM@@QEBA?AV?$shared_ptr@$$CBVQualifiedName@PrintDeviceCapabilitiesOM@@@std@@V?$shared_ptr@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@5@@Z; PrintDeviceCapabilitiesOM::Parser::GenericParser::ToQualifiedName(std::shared_ptr<std::wstring const>)
0x18003ccf6  mov     rdx, rax
0x18003ccf9  mov     rcx, rbx
0x18003ccfc  call    ??4?$shared_ptr@VNamespaceVault@PrintDeviceCapabilitiesOM@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<PrintDeviceCapabilitiesOM::NamespaceVault>::operator=(std::shared_ptr<PrintDeviceCapabilitiesOM::NamespaceVault> &&)
0x18003cd01  mov     rcx, [rbp+57h+var_40]; this
0x18003cd05  test    rcx, rcx
0x18003cd08  jz      short loc_18003CD0F
0x18003cd0a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003cd0f  xor     r8d, r8d
0x18003cd12  mov     rdx, rsi
0x18003cd15  lea     rcx, [rbp+57h+var_48]
0x18003cd19  call    ?GetNodeText@Parser@PrintDeviceCapabilitiesOM@@YA?AV?$shared_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@AEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEBG@Z; PrintDeviceCapabilitiesOM::Parser::GetNodeText(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort const *)
0x18003cd1e  mov     rdx, rax
0x18003cd21  mov     rcx, rdi
0x18003cd24  call    ??4?$shared_ptr@VNamespaceVault@PrintDeviceCapabilitiesOM@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<PrintDeviceCapabilitiesOM::NamespaceVault>::operator=(std::shared_ptr<PrintDeviceCapabilitiesOM::NamespaceVault> &&)
0x18003cd29  mov     rcx, [rbp+57h+var_40]; this
0x18003cd2d  test    rcx, rcx
0x18003cd30  jz      short loc_18003CD37
0x18003cd32  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003cd37  cmp     qword ptr [rdi], 0
0x18003cd3b  jz      short loc_18003CD69
0x18003cd3d  mov     rcx, [rbp+57h+var_88]; this
0x18003cd41  test    rcx, rcx
0x18003cd44  jz      short loc_18003CD4C
0x18003cd46  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003cd4b  nop
0x18003cd4c  mov     rax, rbx
0x18003cd4f  mov     rcx, [rbp+57h+var_28]
0x18003cd53  xor     rcx, rsp; StackCookie
0x18003cd56  call    __security_check_cookie
0x18003cd5b  add     rsp, 0B0h
0x18003cd62  pop     r14
0x18003cd64  pop     rdi
0x18003cd65  pop     rsi
0x18003cd66  pop     rbx
0x18003cd67  pop     rbp
0x18003cd68  retn
0x18003cd69  lea     rdx, aPwgrasterdocum; "PwgRasterDocumentType"
0x18003cd70  lea     rcx, [rbp+57h+var_48]
0x18003cd74  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003cd79  nop
0x18003cd7a  mov     [rbp+57h+var_A0], 0Ch
0x18003cd81  mov     [rsp+0D0h+var_B0], 2F6h
0x18003cd89  lea     r9, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x18003cd90  lea     r8, aColorFormatVal; "Color format value missing"
0x18003cd97  lea     rdx, [rbp+57h+var_48]
0x18003cd9b  lea     rcx, [rbp+57h+var_A0]
0x18003cd9f  call    ?Error@Throw@Exception@PrintDeviceCapabilitiesOM@@YAXAEBW4ElementType@23@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGPEBDI@Z; PrintDeviceCapabilitiesOM::Exception::Throw::Error(PrintDeviceCapabilitiesOM::Exception::ElementType const &,std::wstring const &,ushort const *,char const *,uint)
0x18003cda5  lea     rdx, aPwgrasterdocum; "PwgRasterDocumentType"
0x18003cdac  lea     rcx, [rbp+57h+var_48]
0x18003cdb0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003cdb5  nop
0x18003cdb6  mov     [rbp+57h+var_A0], 0Ch
0x18003cdbd  mov     [rsp+0D0h+var_B0], 2EEh
0x18003cdc5  lea     r9, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x18003cdcc  lea     r8, aPageoutputcolo; "PageOutputColor attribute missing"
0x18003cdd3  lea     rdx, [rbp+57h+var_48]
0x18003cdd7  lea     rcx, [rbp+57h+var_A0]
0x18003cddb  call    ?Error@Throw@Exception@PrintDeviceCapabilitiesOM@@YAXAEBW4ElementType@23@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGPEBDI@Z; PrintDeviceCapabilitiesOM::Exception::Throw::Error(PrintDeviceCapabilitiesOM::Exception::ElementType const &,std::wstring const &,ushort const *,char const *,uint)
```
