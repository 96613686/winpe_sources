# _CBatteryNotificationManager::CreateAdaptiveCardJsonForBatteryNotification_::_1_::dtor$1

- ea: `0x18000ccbb`
- end: `0x18000cce4`
- name: `_CBatteryNotificationManager::CreateAdaptiveCardJsonForBatteryNotification_::_1_::dtor$1`
- size: `41`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180005540`
- `0x18000ccbb`

## pseudocode

```c
void __fastcall CBatteryNotificationManager::CreateAdaptiveCardJsonForBatteryNotification_::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 120) & 1) != 0 )
  {
    *(_DWORD *)(a2 + 120) &= ~1u;
    winrt::Windows::Data::Xml::Dom::XmlElement::~XmlElement(*(winrt::Windows::Data::Xml::Dom::XmlElement **)(a2 + 272));
  }
}

```

## disassembly

```asm
0x18000ccbb  push    rbp
0x18000ccbd  sub     rsp, 20h
0x18000ccc1  mov     rbp, rdx
0x18000ccc4  mov     eax, [rbp+78h]
0x18000ccc7  and     eax, 1
0x18000ccca  test    eax, eax
0x18000cccc  jz      short loc_18000CCDE
0x18000ccce  and     dword ptr [rbp+78h], 0FFFFFFFEh
0x18000ccd2  mov     rcx, [rbp+110h]; this
0x18000ccd9  call    ??1XmlElement@Dom@Xml@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Xml::Dom::XmlElement::~XmlElement(void)
0x18000ccde  add     rsp, 20h
0x18000cce2  pop     rbp
0x18000cce3  retn
```
