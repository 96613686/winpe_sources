# _wil::ActivateInstance_Windows::Data::Json::IJsonObject__::_1_::dtor$1

- ea: `0x14001132a`
- end: `0x140011336`
- name: `_wil::ActivateInstance_Windows::Data::Json::IJsonObject__::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000a39c`

## pseudocode

```c
void __fastcall wil::ActivateInstance_Windows::Data::Json::IJsonObject__::_1_::dtor_1(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HStringReference::~HStringReference((Microsoft::WRL::Wrappers::HStringReference *)(a2 + 56));
}

```

## disassembly

```asm
0x14001132a  lea     rcx, [rdx+38h]; this
0x140011331  jmp     ??1HStringReference@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HStringReference::~HStringReference(void)
```
