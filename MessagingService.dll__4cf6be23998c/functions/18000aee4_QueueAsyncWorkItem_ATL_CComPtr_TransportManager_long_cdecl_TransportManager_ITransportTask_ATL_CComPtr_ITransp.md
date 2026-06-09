# _QueueAsyncWorkItem_ATL::CComPtr_TransportManager__long_(__cdecl_TransportManager::_)(ITransportTask__)_ATL::CComPtr_ITransportTask____::_1_::dtor$0

- ea: `0x18000aee4`
- end: `0x18000aef0`
- name: `_QueueAsyncWorkItem_ATL::CComPtr_TransportManager__long_(__cdecl_TransportManager::_)(ITransportTask__)_ATL::CComPtr_ITransportTask____::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002f7c`

## pseudocode

```c
__int64 __fastcall QueueAsyncWorkItem_ATL::CComPtr_TransportManager__long____cdecl_TransportManager::___ITransportTask____ATL::CComPtr_ITransportTask____::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  return ATL::CComPtr<IAsyncWorkQueue>::~CComPtr<IAsyncWorkQueue>((__int64 *)(a2 + 56));
}

```

## disassembly

```asm
0x18000aee4  lea     rcx, [rdx+38h]
0x18000aeeb  jmp     ??1?$CComPtr@UIAsyncWorkQueue@@@ATL@@QEAA@XZ; ATL::CComPtr<IAsyncWorkQueue>::~CComPtr<IAsyncWorkQueue>(void)
```
