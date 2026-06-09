# _MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor$6

- ea: `0x18001d8c5`
- end: `0x18001d8d1`
- name: `_MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor$6`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002eec`

## pseudocode

```c
void __fastcall MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor_6(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HString::~HString((HSTRING *)(a2 + 184));
}

```

## disassembly

```asm
0x18001d8c5  lea     rcx, [rdx+0B8h]; this
0x18001d8cc  jmp     ??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HString::~HString(void)
```
