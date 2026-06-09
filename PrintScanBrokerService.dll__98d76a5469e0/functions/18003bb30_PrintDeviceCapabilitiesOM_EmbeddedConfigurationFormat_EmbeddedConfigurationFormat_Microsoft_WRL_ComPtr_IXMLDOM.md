# PrintDeviceCapabilitiesOM::EmbeddedConfigurationFormat::EmbeddedConfigurationFormat(Microsoft::WRL::ComPtr<IXMLDOMNode> &,PrintDeviceCapabilitiesOM::Parser::GenericParser *)

- ea: `0x18003bb30`
- end: `0x18003bca5`
- name: `??0EmbeddedConfigurationFormat@PrintDeviceCapabilitiesOM@@QEAA@AEAV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEAVGenericParser@Parser@1@@Z`
- size: `373`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180038d5c`

## callees

- `0x180002d40`
- `0x180012498`
- `0x180038718`
- `0x1800387fc`
- `0x18003bb30`
- `0x18003cde8`
- `0x18003d548`
- `0x18003e614`
- `0x18003e828`
- `0x18003ebc8`
- `0x18003f368`
- `0x18003f6d0`
- `0x1800421e0`

## string_xrefs

- `0x18003bc2d`: `EmbeddedConfigurationFormat`
- `0x18003bc69`: `EmbeddedConfigurationFormat`
- `0x18003bc4d`: `onecoreuap\internal\printscan\inc\private\print\platform\config\DocumentFormatOptions.hxx`
- `0x18003bc89`: `onecoreuap\internal\printscan\inc\private\print\platform\config\DocumentFormatOptions.hxx`
- `0x18003bbc8`: `psf2:EmbeddedConfigurationFormat`

## pseudocode

```c
__int64 __fastcall PrintDeviceCapabilitiesOM::EmbeddedConfigurationFormat::EmbeddedConfigurationFormat(
        __int64 a1,
        __int64 a2)
{
  _QWORD *inited; // rax
  _QWORD *v5; // rax
  __int64 v6; // rax
  __int64 NodeText; // rax
  _QWORD v9[2]; // [rsp+30h] [rbp-19h] BYREF
  __int64 v10; // [rsp+40h] [rbp-9h] BYREF
  std::_Ref_count_base *v11; // [rsp+48h] [rbp-1h]
  __int64 v12; // [rsp+50h] [rbp+7h]
  _BYTE v13[32]; // [rsp+58h] [rbp+Fh] BYREF
  _BYTE v14[8]; // [rsp+78h] [rbp+2Fh] BYREF
  std::_Ref_count_base *v15; // [rsp+80h] [rbp+37h]

  v12 = a1;
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  inited = (_QWORD *)PrintDeviceCapabilitiesOM::NamespaceVault::LazyInitNamespaceUri(4);
  v5 = std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(v9, inited);
  v6 = PrintDeviceCapabilitiesOM::QualifiedName::QualifiedName(v13, L"pdl", v5);
  PrintDeviceCapabilitiesOM::Parser::GetAttributeValue(&v10, v6, a2);
  PrintDeviceCapabilitiesOM::QualifiedName::~QualifiedName((PrintDeviceCapabilitiesOM::QualifiedName *)v13);
  if ( !v10 )
  {
    std::wstring::wstring((__int64)v14, (__int64)L"EmbeddedConfigurationFormat");
    LODWORD(v9[0]) = 12;
    PrintDeviceCapabilitiesOM::Exception::Throw::Error(
      (unsigned int)v9,
      (unsigned int)v14,
      (unsigned int)L"pdl attribute missing",
      (unsigned int)"onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\DocumentFormatOptions.hxx",
      20);
  }
  *(_DWORD *)(a1 + 16) = PrintDeviceCapabilitiesOM::Parser::PrintDeviceCapabilitiesParser::ParsePdl(&v10);
  NodeText = PrintDeviceCapabilitiesOM::Parser::GetNodeText(v14, a2, L"psf2:EmbeddedConfigurationFormat");
  std::shared_ptr<PrintDeviceCapabilitiesOM::NamespaceVault>::operator=(a1, NodeText);
  if ( v15 )
    std::_Ref_count_base::_Decref(v15);
  if ( !*(_QWORD *)a1 )
  {
    std::wstring::wstring((__int64)v14, (__int64)L"EmbeddedConfigurationFormat");
    LODWORD(v9[0]) = 12;
    PrintDeviceCapabilitiesOM::Exception::Throw::Error(
      (unsigned int)v9,
      (unsigned int)v14,
      (unsigned int)L"child node missing",
      (unsigned int)"onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\config\\DocumentFormatOptions.hxx",
      28);
  }
  if ( v11 )
    std::_Ref_count_base::_Decref(v11);
  return a1;
}

```

## disassembly

```asm
0x18003bb30  mov     [rsp-8+arg_10], rbx
0x18003bb35  mov     [rsp-8+arg_18], rdi
0x18003bb3a  push    rbp
0x18003bb3b  lea     rbp, [rsp-57h]
0x18003bb40  sub     rsp, 0A0h
0x18003bb47  mov     rax, cs:__security_cookie
0x18003bb4e  xor     rax, rsp
0x18003bb51  mov     [rbp+57h+var_8], rax
0x18003bb55  mov     rdi, rdx
0x18003bb58  mov     rbx, rcx
0x18003bb5b  mov     [rbp+57h+var_50], rcx
0x18003bb5f  mov     qword ptr [rcx], 0
0x18003bb66  mov     qword ptr [rcx+8], 0
0x18003bb6e  mov     ecx, 4
0x18003bb73  call    ?LazyInitNamespaceUri@NamespaceVault@PrintDeviceCapabilitiesOM@@CAAEBV?$shared_ptr@$$CBVNamespaceUri@PrintDeviceCapabilitiesOM@@@std@@W4NamespaceType@2@@Z; PrintDeviceCapabilitiesOM::NamespaceVault::LazyInitNamespaceUri(PrintDeviceCapabilitiesOM::NamespaceType)
0x18003bb78  mov     rdx, rax
0x18003bb7b  lea     rcx, [rbp+57h+var_70]
0x18003bb7f  call    ??0?$shared_ptr@VOption@PrintDeviceCapabilitiesOM@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PrintDeviceCapabilitiesOM::Option>::shared_ptr<PrintDeviceCapabilitiesOM::Option>(std::shared_ptr<PrintDeviceCapabilitiesOM::Option> const &)
0x18003bb84  mov     r8, rax
0x18003bb87  lea     rdx, aPdl; "pdl"
0x18003bb8e  lea     rcx, [rbp+57h+var_48]
0x18003bb92  call    ??0QualifiedName@PrintDeviceCapabilitiesOM@@QEAA@PEBGV?$shared_ptr@$$CBVNamespaceUri@PrintDeviceCapabilitiesOM@@@std@@@Z; PrintDeviceCapabilitiesOM::QualifiedName::QualifiedName(ushort const *,std::shared_ptr<PrintDeviceCapabilitiesOM::NamespaceUri const>)
0x18003bb97  nop
0x18003bb98  mov     r8, rdi
0x18003bb9b  mov     rdx, rax
0x18003bb9e  lea     rcx, [rbp+57h+var_60]
0x18003bba2  call    ?GetAttributeValue@Parser@PrintDeviceCapabilitiesOM@@YA?AV?$shared_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@AEBVQualifiedName@2@AEAV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@@Z; PrintDeviceCapabilitiesOM::Parser::GetAttributeValue(PrintDeviceCapabilitiesOM::QualifiedName const &,Microsoft::WRL::ComPtr<IXMLDOMNode> &)
0x18003bba7  nop
0x18003bba8  lea     rcx, [rbp+57h+var_48]; this
0x18003bbac  call    ??1QualifiedName@PrintDeviceCapabilitiesOM@@QEAA@XZ; PrintDeviceCapabilitiesOM::QualifiedName::~QualifiedName(void)
0x18003bbb1  cmp     [rbp+57h+var_60], 0
0x18003bbb6  jz      loc_18003BC69
0x18003bbbc  lea     rcx, [rbp+57h+var_60]
0x18003bbc0  call    ?ParsePdl@PrintDeviceCapabilitiesParser@Parser@PrintDeviceCapabilitiesOM@@SA?AW4PrintPdl@3@AEBV?$shared_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@Z; PrintDeviceCapabilitiesOM::Parser::PrintDeviceCapabilitiesParser::ParsePdl(std::shared_ptr<std::wstring> const &)
0x18003bbc5  mov     [rbx+10h], eax
0x18003bbc8  lea     r8, aPsf2Embeddedco_0; "psf2:EmbeddedConfigurationFormat"
0x18003bbcf  mov     rdx, rdi
0x18003bbd2  lea     rcx, [rbp+57h+var_28]
0x18003bbd6  call    ?GetNodeText@Parser@PrintDeviceCapabilitiesOM@@YA?AV?$shared_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@AEBV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@PEBG@Z; PrintDeviceCapabilitiesOM::Parser::GetNodeText(Microsoft::WRL::ComPtr<IXMLDOMNode> const &,ushort const *)
0x18003bbdb  mov     rdx, rax
0x18003bbde  mov     rcx, rbx
0x18003bbe1  call    ??4?$shared_ptr@VNamespaceVault@PrintDeviceCapabilitiesOM@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<PrintDeviceCapabilitiesOM::NamespaceVault>::operator=(std::shared_ptr<PrintDeviceCapabilitiesOM::NamespaceVault> &&)
0x18003bbe6  mov     rcx, [rbp+57h+var_20]; this
0x18003bbea  test    rcx, rcx
0x18003bbed  jz      short loc_18003BBF4
0x18003bbef  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003bbf4  cmp     qword ptr [rbx], 0
0x18003bbf8  jz      short loc_18003BC2D
0x18003bbfa  mov     rcx, [rbp+57h+var_58]; this
0x18003bbfe  test    rcx, rcx
0x18003bc01  jz      short loc_18003BC09
0x18003bc03  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003bc08  nop
0x18003bc09  mov     rax, rbx
0x18003bc0c  mov     rcx, [rbp+57h+var_8]
0x18003bc10  xor     rcx, rsp; StackCookie
0x18003bc13  call    __security_check_cookie
0x18003bc18  lea     r11, [rsp+0A0h+var_s0]
0x18003bc20  mov     rbx, [r11+20h]
0x18003bc24  mov     rdi, [r11+28h]
0x18003bc28  mov     rsp, r11
0x18003bc2b  pop     rbp
0x18003bc2c  retn
0x18003bc2d  lea     rdx, aEmbeddedconfig; "EmbeddedConfigurationFormat"
0x18003bc34  lea     rcx, [rbp+57h+var_28]
0x18003bc38  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003bc3d  nop
0x18003bc3e  mov     [rbp+57h+var_70], 0Ch
0x18003bc45  mov     [rsp+0A0h+var_80], 1Ch
0x18003bc4d  lea     r9, aOnecoreuapInte; "onecoreuap\\internal\\printscan\\inc\\p"...
0x18003bc54  lea     r8, aChildNodeMissi; "child node missing"
0x18003bc5b  lea     rdx, [rbp+57h+var_28]
0x18003bc5f  lea     rcx, [rbp+57h+var_70]
0x18003bc63  call    ?Error@Throw@Exception@PrintDeviceCapabilitiesOM@@YAXAEBW4ElementType@23@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGPEBDI@Z; PrintDeviceCapabilitiesOM::Exception::Throw::Error(PrintDeviceCapabilitiesOM::Exception::ElementType const &,std::wstring const &,ushort const *,char const *,uint)
0x18003bc69  lea     rdx, aEmbeddedconfig; "EmbeddedConfigurationFormat"
0x18003bc70  lea     rcx, [rbp+57h+var_28]
0x18003bc74  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003bc79  nop
0x18003bc7a  mov     [rbp+57h+var_70], 0Ch
0x18003bc81  mov     [rsp+0A0h+var_80], 14h
0x18003bc89  lea     r9, aOnecoreuapInte; "onecoreuap\\internal\\printscan\\inc\\p"...
0x18003bc90  lea     r8, aPdlAttributeMi; "pdl attribute missing"
0x18003bc97  lea     rdx, [rbp+57h+var_28]
0x18003bc9b  lea     rcx, [rbp+57h+var_70]
0x18003bc9f  call    ?Error@Throw@Exception@PrintDeviceCapabilitiesOM@@YAXAEBW4ElementType@23@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGPEBDI@Z; PrintDeviceCapabilitiesOM::Exception::Throw::Error(PrintDeviceCapabilitiesOM::Exception::ElementType const &,std::wstring const &,ushort const *,char const *,uint)
```
