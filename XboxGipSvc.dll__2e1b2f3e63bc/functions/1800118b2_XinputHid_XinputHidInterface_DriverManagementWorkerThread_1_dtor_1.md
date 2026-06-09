# _XinputHid::XinputHidInterface::DriverManagementWorkerThread_::_1_::dtor$1

- ea: `0x1800118b2`
- end: `0x1800118be`
- name: `_XinputHid::XinputHidInterface::DriverManagementWorkerThread_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000efb8`

## pseudocode

```c
__int64 __fastcall XinputHid::XinputHidInterface::DriverManagementWorkerThread_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::weak_ptr<XinputHid::XInputHidDevice>::~weak_ptr<XinputHid::XInputHidDevice>(a2 + 176);
}

```

## disassembly

```asm
0x1800118b2  lea     rcx, [rdx+0B0h]
0x1800118b9  jmp     ??1?$weak_ptr@UXInputHidDevice@XinputHid@@@std@@QEAA@XZ; std::weak_ptr<XinputHid::XInputHidDevice>::~weak_ptr<XinputHid::XInputHidDevice>(void)
```
