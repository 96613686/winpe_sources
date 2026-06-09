# _MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor$15

- ea: `0x18001e047`
- end: `0x18001e053`
- name: `_MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor$15`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002de8`

## pseudocode

```c
__int64 __fastcall MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor_15(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 432));
}

```

## disassembly

```asm
0x18001e047  lea     rcx, [rdx+1B0h]
0x18001e04e  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
