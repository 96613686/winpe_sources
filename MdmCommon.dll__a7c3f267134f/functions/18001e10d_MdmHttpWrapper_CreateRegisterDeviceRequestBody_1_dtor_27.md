# _MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor$27

- ea: `0x18001e10d`
- end: `0x18001e119`
- name: `_MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor$27`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002ef0`

## pseudocode

```c
void __fastcall MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor_27(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HString::~HString((HSTRING *)(a2 + 144));
}

```

## disassembly

```asm
0x18001e10d  lea     rcx, [rdx+90h]; this
0x18001e114  jmp     ??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HString::~HString(void)
```
