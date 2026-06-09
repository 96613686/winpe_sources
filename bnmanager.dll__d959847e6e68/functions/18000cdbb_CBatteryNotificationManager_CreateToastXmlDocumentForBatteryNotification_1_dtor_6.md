# _CBatteryNotificationManager::CreateToastXmlDocumentForBatteryNotification_::_1_::dtor$6

- ea: `0x18000cdbb`
- end: `0x18000cdc7`
- name: `_CBatteryNotificationManager::CreateToastXmlDocumentForBatteryNotification_::_1_::dtor$6`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800057b4`

## pseudocode

```c
void __fastcall CBatteryNotificationManager::CreateToastXmlDocumentForBatteryNotification_::_1_::dtor_6(
        __int64 a1,
        __int64 a2)
{
  winrt::impl::factory_count_guard::~factory_count_guard((volatile signed __int64 **)(a2 + 56));
}

```

## disassembly

```asm
0x18000cdbb  lea     rcx, [rdx+38h]; this
0x18000cdc2  jmp     ??1factory_count_guard@impl@winrt@@QEAA@XZ; winrt::impl::factory_count_guard::~factory_count_guard(void)
```
