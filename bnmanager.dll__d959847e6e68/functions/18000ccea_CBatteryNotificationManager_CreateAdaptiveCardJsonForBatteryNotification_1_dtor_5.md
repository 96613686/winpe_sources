# _CBatteryNotificationManager::CreateAdaptiveCardJsonForBatteryNotification_::_1_::dtor$5

- ea: `0x18000ccea`
- end: `0x18000ccf6`
- name: `_CBatteryNotificationManager::CreateAdaptiveCardJsonForBatteryNotification_::_1_::dtor$5`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180005540`

## pseudocode

```c
void __fastcall CBatteryNotificationManager::CreateAdaptiveCardJsonForBatteryNotification_::_1_::dtor_5(
        __int64 a1,
        __int64 a2)
{
  winrt::Windows::Data::Xml::Dom::XmlElement::~XmlElement((winrt::Windows::Data::Xml::Dom::XmlElement *)(a2 + 296));
}

```

## disassembly

```asm
0x18000ccea  lea     rcx, [rdx+128h]; this
0x18000ccf1  jmp     ??1XmlElement@Dom@Xml@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Xml::Dom::XmlElement::~XmlElement(void)
```
