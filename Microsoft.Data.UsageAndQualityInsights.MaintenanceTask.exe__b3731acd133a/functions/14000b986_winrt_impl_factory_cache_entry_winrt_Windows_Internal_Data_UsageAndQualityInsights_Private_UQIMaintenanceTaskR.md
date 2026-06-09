# _winrt::impl::factory_cache_entry_winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun_winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::IUQIMaintenanceTaskRunStatics_::call_void_(__cdecl_)(winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::IUQIMaintenanceTaskRunStatics_const_&)__::_1_::dtor$2

- ea: `0x14000b986`
- end: `0x14000b992`
- name: `_winrt::impl::factory_cache_entry_winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun_winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::IUQIMaintenanceTaskRunStatics_::call_void_(__cdecl_)(winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::IUQIMaintenanceTaskRunStatics_const_&)__::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x14000a4cc`

## pseudocode

```c
void __fastcall winrt::impl::factory_cache_entry_winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::UQIMaintenanceTaskRun_winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::IUQIMaintenanceTaskRunStatics_::call_void____cdecl___winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::IUQIMaintenanceTaskRunStatics_const_____::_1_::dtor_2(
        __int64 a1,
        __int64 a2)
{
  winrt::impl::factory_count_guard::~factory_count_guard((winrt::impl::factory_count_guard *)(a2 + 112));
}

```

## disassembly

```asm
0x14000b986  lea     rcx, [rdx+70h]; this
0x14000b98d  jmp     ??1factory_count_guard@impl@winrt@@QEAA@XZ; winrt::impl::factory_count_guard::~factory_count_guard(void)
```
