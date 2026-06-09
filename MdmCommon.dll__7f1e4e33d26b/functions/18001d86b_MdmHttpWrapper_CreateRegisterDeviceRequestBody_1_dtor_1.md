# _MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor$1

- ea: `0x18001d86b`
- end: `0x18001d877`
- name: `_MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor$1`
- size: `12`
- prototype: `_QWORD *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002db4`

## pseudocode

```c
_QWORD *__fastcall MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<IEnumUnknown>::~ComPtr<IEnumUnknown>((_QWORD *)(a2 + 296));
}

```

## disassembly

```asm
0x18001d86b  lea     rcx, [rdx+128h]
0x18001d872  jmp     ??1?$ComPtr@UIEnumUnknown@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IEnumUnknown>::~ComPtr<IEnumUnknown>(void)
```
