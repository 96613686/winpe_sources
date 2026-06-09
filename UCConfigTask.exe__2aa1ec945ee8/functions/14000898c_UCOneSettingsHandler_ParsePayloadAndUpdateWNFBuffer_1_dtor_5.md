# _UCOneSettingsHandler::ParsePayloadAndUpdateWNFBuffer_::_1_::dtor$5

- ea: `0x14000898c`
- end: `0x140008998`
- name: `_UCOneSettingsHandler::ParsePayloadAndUpdateWNFBuffer_::_1_::dtor$5`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140007e9c`

## pseudocode

```c
void __fastcall UCOneSettingsHandler::ParsePayloadAndUpdateWNFBuffer_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HStringReference::~HStringReference((Microsoft::WRL::Wrappers::HStringReference *)(a2 + 88));
}

```

## disassembly

```asm
0x14000898c  lea     rcx, [rdx+58h]; this
0x140008993  jmp     ??1HStringReference@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HStringReference::~HStringReference(void)
```
