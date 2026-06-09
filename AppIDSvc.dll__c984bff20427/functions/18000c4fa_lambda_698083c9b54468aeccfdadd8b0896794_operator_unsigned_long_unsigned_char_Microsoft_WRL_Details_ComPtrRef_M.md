# __lambda_698083c9b54468aeccfdadd8b0896794_::operator()_unsigned_long_unsigned_char___Microsoft::WRL::Details::ComPtrRef_Microsoft::WRL::ComPtr_Windows::Data::Json::IJsonValue______::_1_::dtor$1

- ea: `0x18000c4fa`
- end: `0x18000c506`
- name: `__lambda_698083c9b54468aeccfdadd8b0896794_::operator()_unsigned_long_unsigned_char___Microsoft::WRL::Details::ComPtrRef_Microsoft::WRL::ComPtr_Windows::Data::Json::IJsonValue______::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180006218`

## pseudocode

```c
void __fastcall _lambda_698083c9b54468aeccfdadd8b0896794_::operator()_unsigned_long_unsigned_char___Microsoft::WRL::Details::ComPtrRef_Microsoft::WRL::ComPtr_Windows::Data::Json::IJsonValue______::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  Microsoft::WRL::Wrappers::HStringReference::~HStringReference((Microsoft::WRL::Wrappers::HStringReference *)(a2 + 80));
}

```

## disassembly

```asm
0x18000c4fa  lea     rcx, [rdx+50h]; this
0x18000c501  jmp     ??1HStringReference@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HStringReference::~HStringReference(void)
```
