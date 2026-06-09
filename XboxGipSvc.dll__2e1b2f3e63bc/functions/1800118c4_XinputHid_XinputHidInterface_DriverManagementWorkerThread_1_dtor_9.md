# _XinputHid::XinputHidInterface::DriverManagementWorkerThread_::_1_::dtor$9

- ea: `0x1800118c4`
- end: `0x1800118d0`
- name: `_XinputHid::XinputHidInterface::DriverManagementWorkerThread_::_1_::dtor$9`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000ef20`

## pseudocode

```c
__int64 __fastcall XinputHid::XinputHidInterface::DriverManagementWorkerThread_::_1_::dtor_9(__int64 a1, __int64 a2)
{
  return std::shared_ptr<XinputHid::XInputHidDevice>::~shared_ptr<XinputHid::XInputHidDevice>(a2 + 96);
}

```

## disassembly

```asm
0x1800118c4  lea     rcx, [rdx+60h]
0x1800118cb  jmp     ??1?$shared_ptr@UXInputHidDevice@XinputHid@@@std@@QEAA@XZ; std::shared_ptr<XinputHid::XInputHidDevice>::~shared_ptr<XinputHid::XInputHidDevice>(void)
```
