# _dynamic_initializer_for__RULE_SCHEMA__

- ea: `0x180002ab0`
- end: `0x180002ad7`
- name: `_dynamic_initializer_for__RULE_SCHEMA__`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000452c`
- `0x18001fb2c`

## string_xrefs

- `0x180002ab4`: `<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema" version="1.0"><xs:complexType name="signalType"><xs:sequence><xs:any minOccurs="0" maxOccurs="unbounded" processContents="lax"/></xs:sequence><xs:attribute name="name" type="xs:string"/><xs:anyAttribute processContents="lax"/></xs:complexType><xs:complexType name="andType"><xs:choice minOccurs="1" maxOccurs="unbounded"><xs:element name="signal" type="signalType"/><xs:element name="or" type="orType"/></xs:choice></xs:complexType><xs:complexTy`

## pseudocode

```c
int dynamic_initializer_for__RULE_SCHEMA__()
{
  _bstr_t::_bstr_t(
    (_bstr_t *)&qword_18005F9B8,
    L"<xs:schema xmlns:xs=\"http://www.w3.org/2001/XMLSchema\" version=\"1.0\"><xs:complexType name=\"signalType\"><xs:seq"
     "uence><xs:any minOccurs=\"0\" maxOccurs=\"unbounded\" processContents=\"lax\"/></xs:sequence><xs:attribute name=\"n"
     "ame\" type=\"xs:string\"/><xs:anyAttribute processContents=\"lax\"/></xs:complexType><xs:complexType name=\"andType"
     "\"><xs:choice minOccurs=\"1\" maxOccurs=\"unbounded\"><xs:element name=\"signal\" type=\"signalType\"/><xs:element "
     "name=\"or\" type=\"orType\"/></xs:choice></xs:complexType><xs:complexType name=\"orType\"><xs:choice minOccurs=\"1\""
     " maxOccurs=\"unbounded\"><xs:element name=\"signal\" type=\"signalType\"/><xs:element name=\"and\" type=\"andType\""
     "/></xs:choice></xs:complexType><xs:element name=\"rule\"><xs:complexType><xs:choice minOccurs=\"1\" maxOccurs=\"1\""
     "><xs:element name=\"signal\" type=\"signalType\"/><xs:element name=\"and\" type=\"andType\"/><xs:element name=\"or\""
     " type=\"orType\"/></xs:choice><xs:attribute name=\"schemaVersion\" type=\"xs:decimal\" fixed=\"1.0\"/></xs:complexT"
     "ype></xs:element></xs:schema>");
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__RULE_SCHEMA__);
}

```

## disassembly

```asm
0x180002ab0  sub     rsp, 28h
0x180002ab4  lea     rdx, aXsSchemaXmlnsX_0; "<xs:schema xmlns:xs=\"http://www.w3.org"...
0x180002abb  lea     rcx, qword_18005F9B8; this
0x180002ac2  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180002ac7  lea     rcx, _dynamic_atexit_destructor_for__RULE_SCHEMA__
0x180002ace  add     rsp, 28h
0x180002ad2  jmp     atexit
```
