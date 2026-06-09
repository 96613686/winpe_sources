# _CBatteryNotificationManager::CreateAdaptiveCardJsonForBatteryNotification_::_1_::dtor$17

- ea: `0x18000cd32`
- end: `0x18000cd3e`
- name: `_CBatteryNotificationManager::CreateAdaptiveCardJsonForBatteryNotification_::_1_::dtor$17`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800057b4`

## pseudocode

```c
void __fastcall CBatteryNotificationManager::CreateAdaptiveCardJsonForBatteryNotification_::_1_::dtor_17(
        __int64 a1,
        __int64 a2)
{
  winrt::impl::factory_count_guard::~factory_count_guard((volatile signed __int64 **)(a2 + 160));
}

```

## disassembly

```asm
0x18000cd32  lea     rcx, [rdx+0A0h]; this
0x18000cd39  jmp     ??1factory_count_guard@impl@winrt@@QEAA@XZ; winrt::impl::factory_count_guard::~factory_count_guard(void)
```
