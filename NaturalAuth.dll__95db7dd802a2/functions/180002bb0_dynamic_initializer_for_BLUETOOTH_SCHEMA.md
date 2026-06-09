# _dynamic_initializer_for__BLUETOOTH_SCHEMA__

- ea: `0x180002bb0`
- end: `0x180002bd7`
- name: `_dynamic_initializer_for__BLUETOOTH_SCHEMA__`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000452c`
- `0x18001fb2c`

## string_xrefs

- `0x180002bb4`: `<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema" version="1.0">   <xs:complexType name="deviceListType">        <xs:sequence minOccurs="1" maxOccurs="unbounded">           <xs:element name="device">               <xs:complexType>                   <xs:attribute name="id" type="xs:string" use="required"/>               </xs:complexType>           </xs:element>       </xs:sequence>   </xs:complexType>   <xs:simpleType name="scenarioType">       <xs:restriction base="xs:string">           <xs`

## pseudocode

```c
int dynamic_initializer_for__BLUETOOTH_SCHEMA__()
{
  _bstr_t::_bstr_t(
    (_bstr_t *)&qword_18005FA00,
    L"<xs:schema xmlns:xs=\"http://www.w3.org/2001/XMLSchema\" version=\"1.0\">   <xs:complexType name=\"deviceListType\">"
     "        <xs:sequence minOccurs=\"1\" maxOccurs=\"unbounded\">           <xs:element name=\"device\">               "
     "<xs:complexType>                   <xs:attribute name=\"id\" type=\"xs:string\" use=\"required\"/>               </"
     "xs:complexType>           </xs:element>       </xs:sequence>   </xs:complexType>   <xs:simpleType name=\"scenarioTy"
     "pe\">       <xs:restriction base=\"xs:string\">           <xs:enumeration value=\"Dynamic Lock\"/>           <xs:en"
     "umeration value=\"Authentication\"/>       </xs:restriction>   </xs:simpleType>   <xs:simpleType name=\"rssiValueTy"
     "pe\">       <xs:restriction base=\"xs:byte\">           <xs:maxInclusive value=\"0\"/>       </xs:restriction>   </"
     "xs:simpleType>   <xs:element name=\"signal\">       <xs:complexType>           <xs:choice minOccurs=\"0\" maxOccurs"
     "=\"1\">               <xs:element name=\"exclude\" type=\"deviceListType\"/>           </xs:choice>           <xs:a"
     "ttribute name=\"type\"             type=\"xs:string\"       use=\"required\"   fixed=\"bluetooth\" />           <xs"
     ":attribute name=\"scenario\"         type=\"scenarioType\"    use=\"required\"   />           <xs:attribute name=\""
     "classOfDevice\"    type=\"xs:unsignedInt\"  use=\"optional\"   />           <xs:attribute name=\"rssiMin\"         "
     " type=\"rssiValueType\"   use=\"optional\"   />           <xs:attribute name=\"rssiMaxDelta\"     type=\"rssiValueT"
     "ype\"   use=\"optional\"   />           <xs:attribute name=\"sessionId\"        type=\"xs:unsignedInt\"  use=\"opti"
     "onal\"   />       </xs:complexType>   </xs:element></xs:schema>");
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__BLUETOOTH_SCHEMA__);
}

```

## disassembly

```asm
0x180002bb0  sub     rsp, 28h
0x180002bb4  lea     rdx, aXsSchemaXmlnsX; "<xs:schema xmlns:xs=\"http://www.w3.org"...
0x180002bbb  lea     rcx, qword_18005FA00; this
0x180002bc2  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180002bc7  lea     rcx, _dynamic_atexit_destructor_for__BLUETOOTH_SCHEMA__
0x180002bce  add     rsp, 28h
0x180002bd2  jmp     atexit
```
