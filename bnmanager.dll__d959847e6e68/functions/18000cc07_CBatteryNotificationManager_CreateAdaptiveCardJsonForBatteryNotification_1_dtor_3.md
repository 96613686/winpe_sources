# _CBatteryNotificationManager::CreateAdaptiveCardJsonForBatteryNotification_::_1_::dtor$3

- ea: `0x18000cc07`
- end: `0x18000cc13`
- name: `_CBatteryNotificationManager::CreateAdaptiveCardJsonForBatteryNotification_::_1_::dtor$3`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180005540`

## pseudocode

```c
void __fastcall CBatteryNotificationManager::CreateAdaptiveCardJsonForBatteryNotification_::_1_::dtor_3(
        __int64 a1,
        __int64 a2)
{
  winrt::Windows::Data::Xml::Dom::XmlElement::~XmlElement((winrt::Windows::Data::Xml::Dom::XmlElement *)(a2 + 144));
}

```

## disassembly

```asm
0x18000cc07  lea     rcx, [rdx+90h]; this
0x18000cc0e  jmp     ??1XmlElement@Dom@Xml@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Xml::Dom::XmlElement::~XmlElement(void)
```
