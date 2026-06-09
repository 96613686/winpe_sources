# _MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor$2

- ea: `0x18001df5d`
- end: `0x18001df69`
- name: `_MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002ef0`

## pseudocode

```c
void __fastcall MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HString::~HString((HSTRING *)(a2 + 192));
}

```

## disassembly

```asm
0x18001df5d  lea     rcx, [rdx+0C0h]; this
0x18001df64  jmp     ??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HString::~HString(void)
```
