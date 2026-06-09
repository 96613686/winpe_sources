# _TransportManager::ScheduleTask_::_1_::dtor$0

- ea: `0x18000af2c`
- end: `0x18000af38`
- name: `_TransportManager::ScheduleTask_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002f7c`

## pseudocode

```c
__int64 __fastcall TransportManager::ScheduleTask_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<IAsyncWorkQueue>::~CComPtr<IAsyncWorkQueue>((__int64 *)(a2 + 96));
}

```

## disassembly

```asm
0x18000af2c  lea     rcx, [rdx+60h]
0x18000af33  jmp     ??1?$CComPtr@UIAsyncWorkQueue@@@ATL@@QEAA@XZ; ATL::CComPtr<IAsyncWorkQueue>::~CComPtr<IAsyncWorkQueue>(void)
```
