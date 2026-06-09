# _CBatteryNotificationManager::CreateAdaptiveCardJsonForBatteryNotification_::_1_::dtor$13

- ea: `0x18000cd20`
- end: `0x18000cd2c`
- name: `_CBatteryNotificationManager::CreateAdaptiveCardJsonForBatteryNotification_::_1_::dtor$13`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180005540`

## pseudocode

```c
void __fastcall CBatteryNotificationManager::CreateAdaptiveCardJsonForBatteryNotification_::_1_::dtor_13(
        __int64 a1,
        __int64 a2)
{
  winrt::Windows::Data::Xml::Dom::XmlElement::~XmlElement((winrt::Windows::Data::Xml::Dom::XmlElement *)(a2 + 128));
}

```

## disassembly

```asm
0x18000cd20  lea     rcx, [rdx+80h]; this
0x18000cd27  jmp     ??1XmlElement@Dom@Xml@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Xml::Dom::XmlElement::~XmlElement(void)
```
