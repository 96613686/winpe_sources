# _CreateObjectServerTaskBase::Start_::_1_::dtor$0

- ea: `0x1400099c7`
- end: `0x1400099d3`
- name: `_CreateObjectServerTaskBase::Start_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140007354`

## pseudocode

```c
__int64 __fastcall CreateObjectServerTaskBase::Start_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<IElevationBrokerContext>::~ComPtr<IElevationBrokerContext>(a2 + 88);
}

```

## disassembly

```asm
0x1400099c7  lea     rcx, [rdx+58h]
0x1400099ce  jmp     ??1?$ComPtr@UIElevationBrokerContext@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IElevationBrokerContext>::~ComPtr<IElevationBrokerContext>(void)
```
