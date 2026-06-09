# _winrt::impl::factory_cache_entry_winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun_winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::IUQIMaintenanceTaskRunStatics_::call_void_(__cdecl_)(winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::IUQIMaintenanceTaskRunStatics_const_&)__::_1_::dtor$0

- ea: `0x14000b974`
- end: `0x14000b980`
- name: `_winrt::impl::factory_cache_entry_winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun_winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::IUQIMaintenanceTaskRunStatics_::call_void_(__cdecl_)(winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::IUQIMaintenanceTaskRunStatics_const_&)__::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x14000a494`

## pseudocode

```c
void __fastcall winrt::impl::factory_cache_entry_winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun_winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::IUQIMaintenanceTaskRunStatics_::call_void____cdecl___winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::IUQIMaintenanceTaskRunStatics_const_____::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::IUQIMaintenanceTaskRunStatics::~IUQIMaintenanceTaskRunStatics((winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::IUQIMaintenanceTaskRunStatics *)(a2 + 128));
}

```

## disassembly

```asm
0x14000b974  lea     rcx, [rdx+80h]; this
0x14000b97b  jmp     ??1IUQIMaintenanceTaskRunStatics@Private@UsageAndQualityInsights@Data@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::IUQIMaintenanceTaskRunStatics::~IUQIMaintenanceTaskRunStatics(void)
```
