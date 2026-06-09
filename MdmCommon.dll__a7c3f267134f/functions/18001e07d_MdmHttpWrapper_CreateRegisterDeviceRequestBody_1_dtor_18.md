# _MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor$18

- ea: `0x18001e07d`
- end: `0x18001e089`
- name: `_MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor$18`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002ef0`

## pseudocode

```c
void __fastcall MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor_18(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HString::~HString((HSTRING *)(a2 + 160));
}

```

## disassembly

```asm
0x18001e07d  lea     rcx, [rdx+0A0h]; this
0x18001e084  jmp     ??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HString::~HString(void)
```
