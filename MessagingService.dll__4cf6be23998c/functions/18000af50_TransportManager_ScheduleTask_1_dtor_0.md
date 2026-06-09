# _TransportManager::_ScheduleTask_::_1_::dtor$0

- ea: `0x18000af50`
- end: `0x18000af5c`
- name: `_TransportManager::_ScheduleTask_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002f7c`

## pseudocode

```c
__int64 __fastcall TransportManager::_ScheduleTask_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<IAsyncWorkQueue>::~CComPtr<IAsyncWorkQueue>((__int64 *)(a2 + 72));
}

```

## disassembly

```asm
0x18000af50  lea     rcx, [rdx+48h]
0x18000af57  jmp     ??1?$CComPtr@UIAsyncWorkQueue@@@ATL@@QEAA@XZ; ATL::CComPtr<IAsyncWorkQueue>::~CComPtr<IAsyncWorkQueue>(void)
```
