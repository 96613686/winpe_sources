# winrt::Windows::Data::Xml::Dom::XmlElement::~XmlElement(void)

- ea: `0x180005540`
- end: `0x180005554`
- name: `??1XmlElement@Dom@Xml@Data@Windows@winrt@@QEAA@XZ`
- size: `20`
- prototype: `void __fastcall(winrt::Windows::Data::Xml::Dom::XmlElement *__hidden this)`
- caller_count: `15`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000cc07`
- `0x18000cc2b`
- `0x18000cc4f`
- `0x18000cc61`
- `0x18000cc73`
- `0x18000cc85`
- `0x18000cca9`
- `0x18000ccbb`
- `0x18000ccea`
- `0x18000ccfc`
- `0x18000cd0e`
- `0x18000cd20`
- `0x18000cd56`
- `0x18000cd85`
- `0x18000cd97`

## callees

- `0x180005540`
- `0x18000c010`

## pseudocode

```c
void __fastcall winrt::Windows::Data::Xml::Dom::XmlElement::~XmlElement(
        winrt::Windows::Data::Xml::Dom::XmlElement *this)
{
  if ( *(_QWORD *)this )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(this);
}

```

## disassembly

```asm
0x180005540  sub     rsp, 28h
0x180005544  cmp     qword ptr [rcx], 0
0x180005548  jz      short loc_18000554F
0x18000554a  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x18000554f  add     rsp, 28h
0x180005553  retn
```
