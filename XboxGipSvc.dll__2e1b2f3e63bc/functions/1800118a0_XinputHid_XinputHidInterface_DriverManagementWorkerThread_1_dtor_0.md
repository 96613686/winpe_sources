# _XinputHid::XinputHidInterface::DriverManagementWorkerThread_::_1_::dtor$0

- ea: `0x1800118a0`
- end: `0x1800118ac`
- name: `_XinputHid::XinputHidInterface::DriverManagementWorkerThread_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000efb8`

## pseudocode

```c
__int64 __fastcall XinputHid::XinputHidInterface::DriverManagementWorkerThread_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::weak_ptr<XinputHid::XInputHidDevice>::~weak_ptr<XinputHid::XInputHidDevice>(a2 + 160);
}

```

## disassembly

```asm
0x1800118a0  lea     rcx, [rdx+0A0h]
0x1800118a7  jmp     ??1?$weak_ptr@UXInputHidDevice@XinputHid@@@std@@QEAA@XZ; std::weak_ptr<XinputHid::XInputHidDevice>::~weak_ptr<XinputHid::XInputHidDevice>(void)
```
