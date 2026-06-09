# _CBatteryNotificationManager::CreateToastXmlDocumentForBatteryNotification_::_1_::dtor$0

- ea: `0x18000cd56`
- end: `0x18000cd7f`
- name: `_CBatteryNotificationManager::CreateToastXmlDocumentForBatteryNotification_::_1_::dtor$0`
- size: `41`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180005540`
- `0x18000cd56`

## pseudocode

```c
void __fastcall CBatteryNotificationManager::CreateToastXmlDocumentForBatteryNotification_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 32) & 1) != 0 )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    winrt::Windows::Data::Xml::Dom::XmlElement::~XmlElement(*(winrt::Windows::Data::Xml::Dom::XmlElement **)(a2 + 176));
  }
}

```

## disassembly

```asm
0x18000cd56  push    rbp
0x18000cd58  sub     rsp, 20h
0x18000cd5c  mov     rbp, rdx
0x18000cd5f  mov     eax, [rbp+20h]
0x18000cd62  and     eax, 1
0x18000cd65  test    eax, eax
0x18000cd67  jz      short loc_18000CD79
0x18000cd69  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x18000cd6d  mov     rcx, [rbp+0B0h]; this
0x18000cd74  call    ??1XmlElement@Dom@Xml@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Xml::Dom::XmlElement::~XmlElement(void)
0x18000cd79  add     rsp, 20h
0x18000cd7d  pop     rbp
0x18000cd7e  retn
```
