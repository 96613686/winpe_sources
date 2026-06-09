# _UpdateAppUriHandlerRegistrationForFile_::_1_::dtor$9

- ea: `0x140011b45`
- end: `0x140011b51`
- name: `_UpdateAppUriHandlerRegistrationForFile_::_1_::dtor$9`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x14000a39c`

## pseudocode

```c
void __fastcall UpdateAppUriHandlerRegistrationForFile_::_1_::dtor_9(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HStringReference::~HStringReference((Microsoft::WRL::Wrappers::HStringReference *)(a2 + 144));
}

```

## disassembly

```asm
0x140011b45  lea     rcx, [rdx+90h]; this
0x140011b4c  jmp     ??1HStringReference@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HStringReference::~HStringReference(void)
```
