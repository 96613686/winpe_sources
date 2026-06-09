# _MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor$31

- ea: `0x18001da75`
- end: `0x18001da81`
- name: `_MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor$31`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002eec`

## pseudocode

```c
void __fastcall MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor_31(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HString::~HString((HSTRING *)(a2 + 136));
}

```

## disassembly

```asm
0x18001da75  lea     rcx, [rdx+88h]; this
0x18001da7c  jmp     ??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HString::~HString(void)
```
