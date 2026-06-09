# _MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor$10

- ea: `0x18001dfed`
- end: `0x18001dff9`
- name: `_MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor$10`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002ef0`

## pseudocode

```c
void __fastcall MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor_10(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HString::~HString((HSTRING *)(a2 + 176));
}

```

## disassembly

```asm
0x18001dfed  lea     rcx, [rdx+0B0h]; this
0x18001dff4  jmp     ??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HString::~HString(void)
```
