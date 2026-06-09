# _MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor$13

- ea: `0x18001d943`
- end: `0x18001d94f`
- name: `_MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor$13`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002de4`

## pseudocode

```c
__int64 __fastcall MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor_13(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 880));
}

```

## disassembly

```asm
0x18001d943  lea     rcx, [rdx+370h]
0x18001d94a  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
