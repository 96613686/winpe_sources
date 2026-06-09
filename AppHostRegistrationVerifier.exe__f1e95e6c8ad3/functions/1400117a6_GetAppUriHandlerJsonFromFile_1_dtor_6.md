# _GetAppUriHandlerJsonFromFile_::_1_::dtor$6

- ea: `0x1400117a6`
- end: `0x1400117b2`
- name: `_GetAppUriHandlerJsonFromFile_::_1_::dtor$6`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x14000a39c`

## pseudocode

```c
void __fastcall GetAppUriHandlerJsonFromFile_::_1_::dtor_6(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HStringReference::~HStringReference((Microsoft::WRL::Wrappers::HStringReference *)(a2 + 592));
}

```

## disassembly

```asm
0x1400117a6  lea     rcx, [rdx+250h]; this
0x1400117ad  jmp     ??1HStringReference@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HStringReference::~HStringReference(void)
```
