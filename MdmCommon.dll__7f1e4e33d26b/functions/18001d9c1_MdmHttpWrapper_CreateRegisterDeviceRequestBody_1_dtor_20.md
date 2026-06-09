# _MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor$20

- ea: `0x18001d9c1`
- end: `0x18001d9cd`
- name: `_MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor$20`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002de4`

## pseudocode

```c
__int64 __fastcall MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor_20(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 592));
}

```

## disassembly

```asm
0x18001d9c1  lea     rcx, [rdx+250h]
0x18001d9c8  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
