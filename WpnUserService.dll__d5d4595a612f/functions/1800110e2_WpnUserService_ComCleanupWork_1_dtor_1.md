# _WpnUserService::_ComCleanupWork_::_1_::dtor$1

- ea: `0x1800110e2`
- end: `0x1800110ee`
- name: `_WpnUserService::_ComCleanupWork_::_1_::dtor$1`
- size: `12`
- prototype: `_QWORD *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800080d4`

## pseudocode

```c
_QWORD *__fastcall WpnUserService::_ComCleanupWork_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<IWpnPlatformInternal>::~ComPtr<IWpnPlatformInternal>((_QWORD *)(a2 + 168));
}

```

## disassembly

```asm
0x1800110e2  lea     rcx, [rdx+0A8h]
0x1800110e9  jmp     ??1?$ComPtr@UIWpnPlatformInternal@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IWpnPlatformInternal>::~ComPtr<IWpnPlatformInternal>(void)
```
