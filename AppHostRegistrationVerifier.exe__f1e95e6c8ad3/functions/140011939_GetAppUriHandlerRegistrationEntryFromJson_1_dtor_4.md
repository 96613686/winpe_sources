# _GetAppUriHandlerRegistrationEntryFromJson_::_1_::dtor$4

- ea: `0x140011939`
- end: `0x140011945`
- name: `_GetAppUriHandlerRegistrationEntryFromJson_::_1_::dtor$4`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x14000a39c`

## pseudocode

```c
void __fastcall GetAppUriHandlerRegistrationEntryFromJson_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HStringReference::~HStringReference((Microsoft::WRL::Wrappers::HStringReference *)(a2 + 80));
}

```

## disassembly

```asm
0x140011939  lea     rcx, [rdx+50h]; this
0x140011940  jmp     ??1HStringReference@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HStringReference::~HStringReference(void)
```
