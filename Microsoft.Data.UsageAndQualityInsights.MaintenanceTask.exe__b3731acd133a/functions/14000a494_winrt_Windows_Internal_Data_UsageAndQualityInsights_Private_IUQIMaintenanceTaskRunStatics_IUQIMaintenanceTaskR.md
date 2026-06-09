# winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::IUQIMaintenanceTaskRunStatics::~IUQIMaintenanceTaskRunStatics(void)

- ea: `0x14000a494`
- end: `0x14000a4a8`
- name: `??1IUQIMaintenanceTaskRunStatics@Private@UsageAndQualityInsights@Data@Internal@Windows@winrt@@QEAA@XZ`
- size: `20`
- prototype: `void __fastcall(winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::IUQIMaintenanceTaskRunStatics *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000b974`

## callees

- `0x14000a494`
- `0x14000b3f0`

## pseudocode

```c
void __fastcall winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::IUQIMaintenanceTaskRunStatics::~IUQIMaintenanceTaskRunStatics(
        winrt::Windows::Internal::Data::UsageAndQualityInsights::Private::IUQIMaintenanceTaskRunStatics *this)
{
  if ( *(_QWORD *)this )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(this);
}

```

## disassembly

```asm
0x14000a494  sub     rsp, 28h
0x14000a498  cmp     qword ptr [rcx], 0
0x14000a49c  jz      short loc_14000A4A3
0x14000a49e  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x14000a4a3  add     rsp, 28h
0x14000a4a7  retn
```
