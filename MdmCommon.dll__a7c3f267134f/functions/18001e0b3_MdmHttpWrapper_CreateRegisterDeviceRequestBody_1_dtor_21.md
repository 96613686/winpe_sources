# _MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor$21

- ea: `0x18001e0b3`
- end: `0x18001e0bf`
- name: `_MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor$21`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002de8`

## pseudocode

```c
__int64 __fastcall MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor_21(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 816));
}

```

## disassembly

```asm
0x18001e0b3  lea     rcx, [rdx+330h]
0x18001e0ba  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
