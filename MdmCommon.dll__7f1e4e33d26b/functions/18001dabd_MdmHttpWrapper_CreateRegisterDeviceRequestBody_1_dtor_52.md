# _MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor$52

- ea: `0x18001dabd`
- end: `0x18001dac9`
- name: `_MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor$52`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000ae14`

## pseudocode

```c
void __fastcall MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor_52(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HStringReference::~HStringReference((Microsoft::WRL::Wrappers::HStringReference *)(a2 + 304));
}

```

## disassembly

```asm
0x18001dabd  lea     rcx, [rdx+130h]; this
0x18001dac4  jmp     ??1HStringReference@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HStringReference::~HStringReference(void)
```
