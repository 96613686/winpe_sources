# _CNgcNode::Create_::_1_::dtor$1

- ea: `0x18001f20d`
- end: `0x18001f219`
- name: `_CNgcNode::Create_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000841c`

## pseudocode

```c
__int64 __fastcall CNgcNode::Create_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits>::~HandleT<ScDeviceEnum::SwDeviceHandleTraits>(a2 + 56);
}

```

## disassembly

```asm
0x18001f20d  lea     rcx, [rdx+38h]
0x18001f214  jmp     ??1?$HandleT@USwDeviceHandleTraits@ScDeviceEnum@@@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits>::~HandleT<ScDeviceEnum::SwDeviceHandleTraits>(void)
```
