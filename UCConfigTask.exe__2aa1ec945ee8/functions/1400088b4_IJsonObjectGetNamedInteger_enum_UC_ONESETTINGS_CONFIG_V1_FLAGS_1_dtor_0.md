# _IJsonObjectGetNamedInteger_enum__UC_ONESETTINGS_CONFIG_V1_FLAGS__::_1_::dtor$0

- ea: `0x1400088b4`
- end: `0x1400088c0`
- name: `_IJsonObjectGetNamedInteger_enum__UC_ONESETTINGS_CONFIG_V1_FLAGS__::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140007e9c`

## pseudocode

```c
void __fastcall IJsonObjectGetNamedInteger_enum__UC_ONESETTINGS_CONFIG_V1_FLAGS__::_1_::dtor_0(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HStringReference::~HStringReference((Microsoft::WRL::Wrappers::HStringReference *)(a2 + 48));
}

```

## disassembly

```asm
0x1400088b4  lea     rcx, [rdx+30h]; this
0x1400088bb  jmp     ??1HStringReference@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HStringReference::~HStringReference(void)
```
