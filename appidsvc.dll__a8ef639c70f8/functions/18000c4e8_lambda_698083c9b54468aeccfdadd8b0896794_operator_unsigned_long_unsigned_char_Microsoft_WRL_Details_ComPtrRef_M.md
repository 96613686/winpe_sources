# __lambda_698083c9b54468aeccfdadd8b0896794_::operator()_unsigned_long_unsigned_char___Microsoft::WRL::Details::ComPtrRef_Microsoft::WRL::ComPtr_Windows::Data::Json::IJsonValue______::_1_::dtor$0

- ea: `0x18000c4e8`
- end: `0x18000c4f4`
- name: `__lambda_698083c9b54468aeccfdadd8b0896794_::operator()_unsigned_long_unsigned_char___Microsoft::WRL::Details::ComPtrRef_Microsoft::WRL::ComPtr_Windows::Data::Json::IJsonValue______::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800061b4`

## pseudocode

```c
__int64 __fastcall _lambda_698083c9b54468aeccfdadd8b0896794_::operator()_unsigned_long_unsigned_char___Microsoft::WRL::Details::ComPtrRef_Microsoft::WRL::ComPtr_Windows::Data::Json::IJsonValue______::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  return std::vector<unsigned char>::_Tidy(a2 + 56);
}

```

## disassembly

```asm
0x18000c4e8  lea     rcx, [rdx+38h]
0x18000c4ef  jmp     ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@IEAAXXZ; std::vector<uchar>::_Tidy(void)
```
