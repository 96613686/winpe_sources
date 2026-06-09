# _TransportManager::ScheduleTask_::_1_::dtor$1

- ea: `0x18000af3e`
- end: `0x18000af4a`
- name: `_TransportManager::ScheduleTask_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002be4`

## pseudocode

```c
__int64 __fastcall TransportManager::ScheduleTask_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<TransportManager>::~CComPtr<TransportManager>((__int64 *)(a2 + 80));
}

```

## disassembly

```asm
0x18000af3e  lea     rcx, [rdx+50h]
0x18000af45  jmp     ??1?$CComPtr@VTransportManager@@@ATL@@QEAA@XZ; ATL::CComPtr<TransportManager>::~CComPtr<TransportManager>(void)
```
