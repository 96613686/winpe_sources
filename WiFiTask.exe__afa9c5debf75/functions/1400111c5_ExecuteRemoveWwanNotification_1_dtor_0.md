# _ExecuteRemoveWwanNotification_::_1_::dtor$0

- ea: `0x1400111c5`
- end: `0x1400111d1`
- name: `_ExecuteRemoveWwanNotification_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000ea30`

## pseudocode

```c
__int64 __fastcall ExecuteRemoveWwanNotification_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<IApplicationActivationManager>::~CComPtr<IApplicationActivationManager>((__int64 *)(a2 + 88));
}

```

## disassembly

```asm
0x1400111c5  lea     rcx, [rdx+58h]
0x1400111cc  jmp     ??1?$CComPtr@UIApplicationActivationManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IApplicationActivationManager>::~CComPtr<IApplicationActivationManager>(void)
```
