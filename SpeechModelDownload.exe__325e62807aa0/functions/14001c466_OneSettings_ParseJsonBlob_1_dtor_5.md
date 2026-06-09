# _OneSettings::ParseJsonBlob_::_1_::dtor$5

- ea: `0x14001c466`
- end: `0x14001c472`
- name: `_OneSettings::ParseJsonBlob_::_1_::dtor$5`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140004bac`

## pseudocode

```c
void __fastcall OneSettings::ParseJsonBlob_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HStringReference::~HStringReference((Microsoft::WRL::Wrappers::HStringReference *)(a2 + 56));
}

```

## disassembly

```asm
0x14001c466  lea     rcx, [rdx+38h]; this
0x14001c46d  jmp     ??1HStringReference@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HStringReference::~HStringReference(void)
```
