# __DeviceHelperAccessCheck_::_1_::dtor$3

- ea: `0x180013893`
- end: `0x18001389f`
- name: `__DeviceHelperAccessCheck_::_1_::dtor$3`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18001031c`

## pseudocode

```c
void __fastcall _DeviceHelperAccessCheck_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HStringReference::~HStringReference((Microsoft::WRL::Wrappers::HStringReference *)(a2 + 112));
}

```

## disassembly

```asm
0x180013893  lea     rcx, [rdx+70h]; this
0x18001389a  jmp     ??1HStringReference@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HStringReference::~HStringReference(void)
```
