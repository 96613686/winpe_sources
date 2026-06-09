# _MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor$24

- ea: `0x18001e0e9`
- end: `0x18001e0f5`
- name: `_MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor$24`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002de8`

## pseudocode

```c
__int64 __fastcall MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor_24(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 752));
}

```

## disassembly

```asm
0x18001e0e9  lea     rcx, [rdx+2F0h]
0x18001e0f0  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
