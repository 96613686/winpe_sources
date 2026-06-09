# winrt::Windows::Data::Xml::Dom::XmlElement::~XmlElement(void)

- ea: `0x18000a850`
- end: `0x18000a855`
- name: `??1XmlElement@Dom@Xml@Data@Windows@winrt@@QEAA@XZ`
- size: `5`
- prototype: `void __fastcall(winrt::Windows::Data::Xml::Dom::XmlElement *__hidden this)`
- caller_count: `21`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180016a24`
- `0x180016b05`
- `0x180016b17`
- `0x180016b8f`
- `0x180016c2d`
- `0x180016cb3`
- `0x180016d35`
- `0x180016d59`
- `0x180016d6b`
- `0x180016d7d`
- `0x180016db3`
- `0x180016dc5`
- `0x1800171e0`
- `0x180017204`
- `0x180017228`
- `0x1800172f1`
- `0x18001741a`
- `0x180017458`
- `0x180017644`
- `0x1800176cb`
- `0x1800176dd`

## callees

- `0x18000a360`

## pseudocode

```c
// attributes: thunk
void __fastcall winrt::Windows::Data::Xml::Dom::XmlElement::~XmlElement(
        winrt::Windows::Data::Xml::Dom::XmlElement *this)
{
  winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation(this);
}

```

## disassembly

```asm
0x18000a850  jmp     ??1IDeviceInformation@Enumeration@Devices@Windows@winrt@@QEAA@XZ; winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation(void)
```
