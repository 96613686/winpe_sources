# _CBatteryNotificationManager::CreateToastXmlDocumentForBatteryNotification_::_1_::dtor$4

- ea: `0x18000cda9`
- end: `0x18000cdb5`
- name: `_CBatteryNotificationManager::CreateToastXmlDocumentForBatteryNotification_::_1_::dtor$4`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800057fc`

## pseudocode

```c
void __fastcall CBatteryNotificationManager::CreateToastXmlDocumentForBatteryNotification_::_1_::dtor_4(
        __int64 a1,
        __int64 a2)
{
  winrt::hstring::~hstring((winrt::hstring *)(a2 + 56));
}

```

## disassembly

```asm
0x18000cda9  lea     rcx, [rdx+38h]; this
0x18000cdb0  jmp     ??1hstring@winrt@@QEAA@XZ; winrt::hstring::~hstring(void)
```
