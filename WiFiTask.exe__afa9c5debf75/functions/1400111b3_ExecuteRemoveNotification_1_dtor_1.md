# _ExecuteRemoveNotification_::_1_::dtor$1

- ea: `0x1400111b3`
- end: `0x1400111bf`
- name: `_ExecuteRemoveNotification_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000ea30`

## pseudocode

```c
__int64 __fastcall ExecuteRemoveNotification_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<IApplicationActivationManager>::~CComPtr<IApplicationActivationManager>((__int64 *)(a2 + 64));
}

```

## disassembly

```asm
0x1400111b3  lea     rcx, [rdx+40h]
0x1400111ba  jmp     ??1?$CComPtr@UIApplicationActivationManager@@@ATL@@QEAA@XZ; ATL::CComPtr<IApplicationActivationManager>::~CComPtr<IApplicationActivationManager>(void)
```
