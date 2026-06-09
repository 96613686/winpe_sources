# _CBatteryNotificationManager::CreateToastXmlDocumentForBatteryNotification_::_1_::dtor$2

- ea: `0x18000cd97`
- end: `0x18000cda3`
- name: `_CBatteryNotificationManager::CreateToastXmlDocumentForBatteryNotification_::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180005540`

## pseudocode

```c
void __fastcall CBatteryNotificationManager::CreateToastXmlDocumentForBatteryNotification_::_1_::dtor_2(
        __int64 a1,
        __int64 a2)
{
  winrt::Windows::Data::Xml::Dom::XmlElement::~XmlElement((winrt::Windows::Data::Xml::Dom::XmlElement *)(a2 + 56));
}

```

## disassembly

```asm
0x18000cd97  lea     rcx, [rdx+38h]; this
0x18000cd9e  jmp     ??1XmlElement@Dom@Xml@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Xml::Dom::XmlElement::~XmlElement(void)
```
