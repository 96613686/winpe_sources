# ATL::CComPtr<IDeliveryOptimizationJob>::~CComPtr<IDeliveryOptimizationJob>(void)

- ea: `0x140009040`
- end: `0x140009045`
- name: `??1?$CComPtr@UIDeliveryOptimizationJob@@@ATL@@QEAA@XZ`
- size: `5`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `11`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140009134`
- `0x140009a90`
- `0x14001aed7`
- `0x14001aee9`
- `0x14001af67`
- `0x14001b0ca`
- `0x14001b100`
- `0x14001b112`
- `0x14001b1a2`
- `0x14001b1b4`
- `0x14001b257`

## callees

- `0x14000904c`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall ATL::CComPtr<IDeliveryOptimizationJob>::~CComPtr<IDeliveryOptimizationJob>(__int64 a1)
{
  return ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(a1);
}

```

## disassembly

```asm
0x140009040  jmp     ??1?$CComPtrBase@UIClientSecurity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(void)
```
