# PrintDeviceCapabilitiesOM::BacksideTumble::BacksideTumble(Microsoft::WRL::ComPtr<IXMLDOMNode> &,PrintDeviceCapabilitiesOM::Parser::GenericParser *)

- ea: `0x18003b7f4`
- end: `0x18003b94c`
- name: `??0BacksideTumble@PrintDeviceCapabilitiesOM@@QEAA@AEAV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEAVGenericParser@Parser@1@@Z`
- size: `344`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180038b08`

## callees

- `0x180002d40`
- `0x180012498`
- `0x180038718`
- `0x1800387fc`
- `0x18003b7f4`
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

- `0x18003b930`: `onecoreuap\internal\printscan\inc\private\print\platform\config\DocumentFormatOptions.hxx`
- `0x18003b910`: `BacksideTumble`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall PrintDeviceCapabilitiesOM::BacksideTumble::BacksideTumble(__int64 a1, __int64 a2, __int64 a3)
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
    std::wstring::wstring((__int64)v19, (__int64)L"BacksideTumble");
    LODWORD(v13[0]) = 12;
    PrintDeviceCapabilitiesOM::Exception::Throw::Error(
      (unsigned int)v13,
      (unsigned int)v19,
      (unsigned int)L"DuplexType attribute missing",
      (unsigned int)"onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\DocumentFormatOptions.hxx",
      90);
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
0x18003b7f4  mov     [rsp-8+arg_18], rbx
0x18003b7f9  push    rbp
0x18003b7fa  push    rsi
0x18003b7fb  push    rdi
0x18003b7fc  lea     rbp, [rsp-47h]
0x18003b801  sub     rsp, 0B0h
0x18003b808  mov     rax, cs:__security_cookie
0x18003b80f  xor     rax, rsp
0x18003b812  mov     [rbp+57h+var_18], rax
0x18003b816  mov     rsi, r8
0x18003b819  mov     rdi, rdx
0x18003b81c  mov     rbx, rcx
0x18003b81f  mov     [rbp+57h+var_70], rcx
0x18003b823  mov     qword ptr [rcx], 0
0x18003b82a  mov     qword ptr [rcx+8], 0
0x18003b832  mov     ecx, 4
0x18003b837  call    ?LazyInitNamespaceUri@NamespaceVault@PrintDeviceCapabilitiesOM@@CAAEBV?$shared_ptr@$$CBVNamespaceUri@PrintDeviceCapabilitiesOM@@@std@@W4NamespaceType@2@@Z; PrintDeviceCapabilitiesOM::NamespaceVault::LazyInitNamespaceUri(PrintDeviceCapabilitiesOM::NamespaceType)
0x18003b83c  mov     rdx, rax
0x18003b83f  lea     rcx, [rbp+57h+var_68]
0x18003b843  call    ??0?$shared_ptr@VOption@PrintDeviceCapabilitiesOM@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(std::shared_ptr<PrintDeviceCapabilitiesOM::Option> const &)
0x18003b848  mov     r8, rax
0x18003b84b  lea     rdx, aDuplextype; "DuplexType"
0x18003b852  lea     rcx, [rbp+57h+var_58]
0x18003b856  call    ??0QualifiedName@PrintDeviceCapabilitiesOM@@QEAA@PEBGV?$shared_ptr@$$CBVNamespaceUri@PrintDeviceCapabilitiesOM@@@std@@@Z; PrintDeviceCapabilitiesOM::QualifiedName::QualifiedName(ushort const *,std::shared_ptr<PrintDeviceCapabilitiesOM::NamespaceUri const>)
0x18003b85b  nop
0x18003b85c  mov     r8, rdi
0x18003b85f  mov     rdx, rax
0x18003b862  lea     rcx, [rbp+57h+var_80]
0x18003b866  call    ?GetAttributeValue@Parser@PrintDeviceCapabilitiesOM@@YA?AV?$shared_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@AEBVQualifiedName@2@AEAV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@@Z; PrintDeviceCapabilitiesOM::Parser::GetAttributeValue(PrintDeviceCapabilitiesOM::QualifiedName const &,Microsoft::WRL::ComPtr<IXMLDOMNode> &)
0x18003b86b  nop
0x18003b86c  lea     rcx, [rbp+57h+var_58]; this
0x18003b870  call    ??1QualifiedName@PrintDeviceCapabilitiesOM@@QEAA@XZ; PrintDeviceCapabilitiesOM::QualifiedName::~QualifiedName(void)
0x18003b875  cmp     [rbp+57h+var_80], 0
0x18003b87a  jz      loc_18003B910
0x18003b880  lea     rdx, [rbp+57h+var_80]
0x18003b884  lea     rcx, [rbp+57h+var_90]
0x18003b888  call    ??0?$shared_ptr@VOption@PrintDeviceCapabilitiesOM@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(std::shared_ptr<PrintDeviceCapabilitiesOM::Option> const &)
0x18003b88d  mov     r8, rax
0x18003b890  lea     rdx, [rbp+57h+var_38]
0x18003b894  mov     rcx, rsi
0x18003b897  call    ?ToQualifiedName@GenericParser@Parser@PrintDeviceCapabilitiesOM@@QEBA?AV?$shared_ptr@$$CBVQualifiedName@PrintDeviceCapabilitiesOM@@@std@@V?$shared_ptr@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@5@@Z; PrintDeviceCapabilitiesOM::Parser::GenericParser::ToQualifiedName(std::shared_ptr<std::wstring const>)
0x18003b89c  mov     rdx, rax
0x18003b89f  mov     rcx, rbx
0x18003b8a2  call    ??4?$shared_ptr@VNamespaceVault@PrintDeviceCapabilitiesOM@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<PrintDeviceCapabilitiesOM::NamespaceVault>::operator=(std::shared_ptr<PrintDeviceCapabilitiesOM::NamespaceVault> &&)
0x18003b8a7  mov     rcx, [rbp+57h+var_30]; this
0x18003b8ab  test    rcx, rcx
0x18003b8ae  jz      short loc_18003B8B5
0x18003b8b0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003b8b5  xor     r8d, r8d
0x18003b8b8  mov     rdx, rdi
0x18003b8bb  lea     rcx, [rbp+57h+var_38]
0x18003b8bf  call    ?GetNodeText@Parser@PrintDeviceCapabilitiesOM@@YA?AV?$shared_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@AEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEBG@Z; PrintDeviceCapabilitiesOM::Parser::GetNodeText(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort const *)
0x18003b8c4  nop
0x18003b8c5  mov     rcx, rax
0x18003b8c8  call    ?ParseXmlBoolean@Parser@PrintDeviceCapabilitiesOM@@YA_NAEBV?$shared_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@Z; PrintDeviceCapabilitiesOM::Parser::ParseXmlBoolean(std::shared_ptr<std::wstring> const &)
0x18003b8cd  mov     [rbx+10h], al
0x18003b8d0  mov     rcx, [rbp+57h+var_30]; this
0x18003b8d4  test    rcx, rcx
0x18003b8d7  jz      short loc_18003B8DF
0x18003b8d9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003b8de  nop
0x18003b8df  mov     rcx, [rbp+57h+var_78]; this
0x18003b8e3  test    rcx, rcx
0x18003b8e6  jz      short loc_18003B8EE
0x18003b8e8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003b8ed  nop
0x18003b8ee  mov     rax, rbx
0x18003b8f1  mov     rcx, [rbp+57h+var_18]
0x18003b8f5  xor     rcx, rsp; StackCookie
0x18003b8f8  call    __security_check_cookie
0x18003b8fd  mov     rbx, [rsp+0C0h+arg_18]
0x18003b905  add     rsp, 0B0h
0x18003b90c  pop     rdi
0x18003b90d  pop     rsi
0x18003b90e  pop     rbp
0x18003b90f  retn
0x18003b910  lea     rdx, aBacksidetumble; "BacksideTumble"
0x18003b917  lea     rcx, [rbp+57h+var_38]
0x18003b91b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003b920  nop
0x18003b921  mov     [rbp+57h+var_90], 0Ch
0x18003b928  mov     [rsp+0C0h+var_A0], 5Ah ; 'Z'
0x18003b930  lea     r9, aOnecoreuapInte; "onecoreuap\\internal\\printscan\\inc\\p"...
0x18003b937  lea     r8, aDuplextypeAttr; "DuplexType attribute missing"
0x18003b93e  lea     rdx, [rbp+57h+var_38]
0x18003b942  lea     rcx, [rbp+57h+var_90]
0x18003b946  call    ?Error@Throw@Exception@PrintDeviceCapabilitiesOM@@YAXAEBW4ElementType@23@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGPEBDI@Z; PrintDeviceCapabilitiesOM::Exception::Throw::Error(PrintDeviceCapabilitiesOM::Exception::ElementType const &,std::wstring const &,ushort const *,char const *,uint)
```
