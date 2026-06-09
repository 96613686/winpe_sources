# _CNgcNode::Uninstall_::_1_::dtor$2

- ea: `0x18001f255`
- end: `0x18001f261`
- name: `_CNgcNode::Uninstall_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000841c`

## pseudocode

```c
__int64 __fastcall CNgcNode::Uninstall_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits>::~HandleT<ScDeviceEnum::SwDeviceHandleTraits>(a2 + 80);
}

```

## disassembly

```asm
0x18001f255  lea     rcx, [rdx+50h]
0x18001f25c  jmp     ??1?$HandleT@USwDeviceHandleTraits@ScDeviceEnum@@@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits>::~HandleT<ScDeviceEnum::SwDeviceHandleTraits>(void)
```
