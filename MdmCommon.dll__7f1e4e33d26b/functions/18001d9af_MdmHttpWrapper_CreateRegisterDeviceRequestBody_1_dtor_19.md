# _MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor$19

- ea: `0x18001d9af`
- end: `0x18001d9bb`
- name: `_MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor$19`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002de4`

## pseudocode

```c
__int64 __fastcall MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor_19(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 400));
}

```

## disassembly

```asm
0x18001d9af  lea     rcx, [rdx+190h]
0x18001d9b6  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
