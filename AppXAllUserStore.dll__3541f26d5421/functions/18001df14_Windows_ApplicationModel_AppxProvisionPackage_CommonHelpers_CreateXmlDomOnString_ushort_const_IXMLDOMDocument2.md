# Windows::ApplicationModel::AppxProvisionPackage::CommonHelpers::CreateXmlDomOnString(ushort const *,IXMLDOMDocument2 * *)

- ea: `0x18001df14`
- end: `0x18001e005`
- name: `?CreateXmlDomOnString@CommonHelpers@AppxProvisionPackage@ApplicationModel@Windows@@CAJPEBGPEAPEAUIXMLDOMDocument2@@@Z`
- size: `241`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct IXMLDOMDocument2 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e580`

## callees

- `0x180017f50`
- `0x18001ca24`
- `0x18001dcdc`
- `0x18001df14`
- `0x18004d010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001df70`
- `OLEAUT32!__imp_SysAllocString` at `0x18001df70`
- `OLEAUT32!__imp_SysFreeString` at `0x18001df80`
- `OLEAUT32!__imp_SysFreeString` at `0x18001dfe3`
- `OLEAUT32!__imp_SysFreeString` at `0x18001df80`
- `OLEAUT32!__imp_SysFreeString` at `0x18001dfe3`

## string_xrefs

- `0x18001df69`: `<?xml version="1.0" encoding="utf-8"?><xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" targetNamespace="http://schemas.microsoft.com/appx/2013/appxprovisionpackage" xmlns="http://schemas.microsoft.com/appx/2013/appxprovisionpackage" xmlns:m="http://schemas.microsoft.com/appx/2013/appxprovisionpackage" xmlns:xs="http://www.w3.org/2001/XMLSchema"><xs:element name="AppxProvisionList">  <xs:complexType>    <xs:all>      <xs:element name="EndOfLife" type="CT_EndOfLife" min`
- `0x18001df50`: `onecore\base\appmodel\appxprovisionpackage\src\commonhelpers.cpp`
- `0x18001dfbe`: `onecore\base\appmodel\appxprovisionpackage\src\commonhelpers.cpp`

## pseudocode

```c
__int64 __fastcall Windows::ApplicationModel::AppxProvisionPackage::CommonHelpers::CreateXmlDomOnString(
        const unsigned __int16 *a1,
        struct IXMLDOMDocument2 **a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  BSTR v5; // rax
  OLECHAR *v6; // rbx
  struct IXMLDOMDocument2 *v7; // rsi
  int v8; // eax
  unsigned int v9; // edi
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  const unsigned __int16 *v12; // [rsp+40h] [rbp+8h] BYREF
  struct IXMLDOMDocument2 *v13; // [rsp+50h] [rbp+18h] BYREF

  v12 = a1;
  v13 = 0;
  Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v13);
  v3 = Windows::ApplicationModel::AppxProvisionPackage::CommonHelpers::InitializeXmlDom(&v13);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v5 = SysAllocString(
           L"<?xml version=\"1.0\" encoding=\"utf-8\"?><xs:schema attributeFormDefault=\"unqualified\" elementFormDefault="
            "\"qualified\" targetNamespace=\"http://schemas.microsoft.com/appx/2013/appxprovisionpackage\" xmlns=\"http:/"
            "/schemas.microsoft.com/appx/2013/appxprovisionpackage\" xmlns:m=\"http://schemas.microsoft.com/appx/2013/app"
            "xprovisionpackage\" xmlns:xs=\"http://www.w3.org/2001/XMLSchema\"><xs:element name=\"AppxProvisionList\">  <"
            "xs:complexType>    <xs:all>      <xs:element name=\"EndOfLife\" type=\"CT_EndOfLife\" minOccurs=\"0\"/>     "
            " <xs:element name=\"Provisioned\" type=\"CT_Provisioned\" minOccurs=\"0\"/>    </xs:all>  </xs:complexType> "
            " <xs:unique name=\"Package_FamilyName\">    <xs:selector xpath=\"m:EndOfLife/m:Package\"/>    <xs:field xpat"
            "h=\"@FamilyName\"/>  </xs:unique>  <xs:unique name=\"Package_FullName\">    <xs:selector xpath=\"m:Provision"
            "ed/m:Package\"/>    <xs:field xpath=\"@FullName\"/>  </xs:unique></xs:element><xs:complexType name=\"CT_EndO"
            "fLife\">  <xs:sequence>    <xs:element name=\"Package\" maxOccurs=\"unbounded\">      <xs:complexType>      "
            "  <xs:attribute name=\"FamilyName\" type=\"ST_FamilyName\" use=\"required\"/>      </xs:complexType>    </xs"
            ":element>  </xs:sequence></xs:complexType><xs:complexType name=\"CT_Provisioned\">  <xs:sequence>    <xs:ele"
            "ment name=\"Package\" maxOccurs=\"unbounded\">      <xs:complexType>        <xs:attribute name=\"FullName\" "
            "type=\"ST_FullName\" use=\"required\"/>        <xs:attribute name=\"PackageType\" type=\"ST_PackageType\"/> "
            "       <xs:attribute name=\"ProvisionSourceIsBundle\" type=\"xs:boolean\"/>        <xs:attribute name=\"IsLO"
            "BApp\" type=\"xs:boolean\"/>      </xs:complexType>    </xs:element>  </xs:sequence></xs:complexType><xs:sim"
            "pleType name=\"ST_FamilyName\">  <xs:restriction base=\"xs:string\">    <xs:minLength value=\"17\"/>    <xs:"
            "maxLength value=\"64\"/>  </xs:restriction></xs:simpleType><xs:simpleType name=\"ST_FullName\">  <xs:restric"
            "tion base=\"xs:string\">    <xs:minLength value=\"30\"/>    <xs:maxLength value=\"127\"/>  </xs:restriction>"
            "</xs:simpleType><xs:simpleType name=\"ST_PackageType\">  <xs:restriction base=\"xs:string\">    <xs:enumerat"
            "ion value=\"resource\"/>    <xs:enumeration value=\"framework\"/>    <xs:enumeration value=\"bundle\"/>  </x"
            "s:restriction></xs:simpleType></xs:schema>");
    v6 = v5;
    if ( v5 )
    {
      v7 = v13;
      LOWORD(v12) = 0;
      v8 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, BSTR, const unsigned __int16 **))v13->lpVtbl->loadXML)(
             v13,
             v5,
             &v12);
      v9 = v8;
      if ( v8 >= 0 )
      {
        v13 = 0;
        *a2 = v7;
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xAF,
          (int)"onecore\\base\\appmodel\\appxprovisionpackage\\src\\commonhelpers.cpp",
          (const char *)(unsigned int)v8);
      }
      SysFreeString(v6);
      v4 = v9;
    }
    else
    {
      SysFreeString(0);
      v4 = -2147024882;
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xA9,
      (int)"onecore\\base\\appmodel\\appxprovisionpackage\\src\\commonhelpers.cpp",
      (const char *)(unsigned int)v3);
  }
  Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v13);
  return v4;
}

```

## disassembly

```asm
0x18001df14  mov     rax, rsp
0x18001df17  mov     [rax+10h], rbx
0x18001df1b  mov     [rax+8], rcx
0x18001df1f  push    rsi
0x18001df20  push    rdi
0x18001df21  push    r14; int
0x18001df23  sub     rsp, 20h
0x18001df27  lea     rcx, [rax+18h]
0x18001df2b  mov     qword ptr [rax+18h], 0
0x18001df33  mov     r14, rdx
0x18001df36  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001df3b  lea     rcx, [rsp+38h+arg_10]; struct IXMLDOMDocument2 **
0x18001df40  call    ?InitializeXmlDom@CommonHelpers@AppxProvisionPackage@ApplicationModel@Windows@@CAJPEAPEAUIXMLDOMDocument2@@@Z; Windows::ApplicationModel::AppxProvisionPackage::CommonHelpers::InitializeXmlDom(IXMLDOMDocument2 * *)
0x18001df45  mov     ebx, eax
0x18001df47  test    eax, eax
0x18001df49  jns     short loc_18001DF69
0x18001df4b  mov     rcx, [rsp+38h]; this
0x18001df50  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\appxprovisionp"...
0x18001df57  mov     r9d, eax; char *
0x18001df5a  mov     edx, 0A9h; void *
0x18001df5f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001df64  jmp     loc_18001DFEB
0x18001df69  lea     rcx, aXmlVersion10En; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x18001df70  call    cs:__imp_SysAllocString
0x18001df76  mov     rbx, rax
0x18001df79  test    rax, rax
0x18001df7c  jnz     short loc_18001DF8D
0x18001df7e  xor     ecx, ecx; bstrString
0x18001df80  call    cs:__imp_SysFreeString
0x18001df86  mov     ebx, 8007000Eh
0x18001df8b  jmp     short loc_18001DFEB
0x18001df8d  mov     rsi, [rsp+38h+arg_10]
0x18001df92  lea     r8, [rsp+38h+arg_0]
0x18001df97  xor     eax, eax
0x18001df99  mov     rdx, rbx
0x18001df9c  mov     word ptr [rsp+38h+arg_0], ax
0x18001dfa1  mov     rcx, rsi
0x18001dfa4  mov     rax, [rsi]
0x18001dfa7  mov     rax, [rax+208h]
0x18001dfae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dfb3  mov     edi, eax
0x18001dfb5  test    eax, eax
0x18001dfb7  jns     short loc_18001DFD4
0x18001dfb9  mov     rcx, [rsp+38h]; this
0x18001dfbe  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\appxprovisionp"...
0x18001dfc5  mov     r9d, eax; char *
0x18001dfc8  mov     edx, 0AFh; void *
0x18001dfcd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001dfd2  jmp     short loc_18001DFE0
0x18001dfd4  mov     [rsp+38h+arg_10], 0
0x18001dfdd  mov     [r14], rsi
0x18001dfe0  mov     rcx, rbx; bstrString
0x18001dfe3  call    cs:__imp_SysFreeString
0x18001dfe9  mov     ebx, edi
0x18001dfeb  lea     rcx, [rsp+38h+arg_10]
0x18001dff0  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001dff5  mov     eax, ebx
0x18001dff7  mov     rbx, [rsp+38h+arg_8]
0x18001dffc  add     rsp, 20h
0x18001e000  pop     r14
0x18001e002  pop     rdi
0x18001e003  pop     rsi
0x18001e004  retn
```
