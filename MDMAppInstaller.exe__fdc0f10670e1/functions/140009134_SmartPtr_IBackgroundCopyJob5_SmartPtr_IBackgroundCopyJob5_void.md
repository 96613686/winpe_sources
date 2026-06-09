# SmartPtr<IBackgroundCopyJob5>::~SmartPtr<IBackgroundCopyJob5>(void)

- ea: `0x140009134`
- end: `0x140009147`
- name: `??1?$SmartPtr@UIBackgroundCopyJob5@@@@UEAA@XZ`
- size: `19`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001b0b8`

## callees

- `0x140009040`

## pseudocode

```c
__int64 __fastcall SmartPtr<IBackgroundCopyJob5>::~SmartPtr<IBackgroundCopyJob5>(_QWORD *a1)
{
  *a1 = &SmartPtr<IBackgroundCopyJob5>::`vftable';
  return ATL::CComPtr<IDeliveryOptimizationJob>::~CComPtr<IDeliveryOptimizationJob>((__int64)(a1 + 1));
}

```

## disassembly

```asm
0x140009134  lea     rax, ??_7?$SmartPtr@UIBackgroundCopyJob5@@@@6B@; const SmartPtr<IBackgroundCopyJob5>::`vftable'
0x14000913b  mov     [rcx], rax
0x14000913e  add     rcx, 8
0x140009142  jmp     ??1?$CComPtr@UIDeliveryOptimizationJob@@@ATL@@QEAA@XZ; ATL::CComPtr<IDeliveryOptimizationJob>::~CComPtr<IDeliveryOptimizationJob>(void)
```
