# _MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor$21

- ea: `0x18001d9d3`
- end: `0x18001d9df`
- name: `_MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor$21`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002de4`

## pseudocode

```c
__int64 __fastcall MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor_21(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 816));
}

```

## disassembly

```asm
0x18001d9d3  lea     rcx, [rdx+330h]
0x18001d9da  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
