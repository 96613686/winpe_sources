# _MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor$22

- ea: `0x18001e0c5`
- end: `0x18001e0d1`
- name: `_MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor$22`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002ef0`

## pseudocode

```c
void __fastcall MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor_22(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HString::~HString((HSTRING *)(a2 + 152));
}

```

## disassembly

```asm
0x18001e0c5  lea     rcx, [rdx+98h]; this
0x18001e0cc  jmp     ??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HString::~HString(void)
```
