# _InstallPackage_::_1_::dtor$9

- ea: `0x18002089f`
- end: `0x1800208ab`
- name: `_InstallPackage_::_1_::dtor$9`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180015040`

## pseudocode

```c
void __fastcall InstallPackage_::_1_::dtor_9(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HString::~HString((HSTRING *)(a2 + 112));
}

```

## disassembly

```asm
0x18002089f  lea     rcx, [rdx+70h]; this
0x1800208a6  jmp     ??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HString::~HString(void)
```
