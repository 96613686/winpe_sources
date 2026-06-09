# _MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor$14

- ea: `0x18001d955`
- end: `0x18001d961`
- name: `_MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor$14`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002eec`

## pseudocode

```c
void __fastcall MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor_14(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HString::~HString((HSTRING *)(a2 + 168));
}

```

## disassembly

```asm
0x18001d955  lea     rcx, [rdx+0A8h]; this
0x18001d95c  jmp     ??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HString::~HString(void)
```
