# _GetJsonFromUrl_::_1_::dtor$11

- ea: `0x1400119e3`
- end: `0x1400119ef`
- name: `_GetJsonFromUrl_::_1_::dtor$11`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000a39c`

## pseudocode

```c
void __fastcall GetJsonFromUrl_::_1_::dtor_11(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HStringReference::~HStringReference((Microsoft::WRL::Wrappers::HStringReference *)(a2 + 136));
}

```

## disassembly

```asm
0x1400119e3  lea     rcx, [rdx+88h]; this
0x1400119ea  jmp     ??1HStringReference@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HStringReference::~HStringReference(void)
```
