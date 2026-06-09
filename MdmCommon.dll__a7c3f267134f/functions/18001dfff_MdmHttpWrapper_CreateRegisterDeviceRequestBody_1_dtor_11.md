# _MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor$11

- ea: `0x18001dfff`
- end: `0x18001e00b`
- name: `_MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor$11`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002de8`

## pseudocode

```c
__int64 __fastcall MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor_11(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 464));
}

```

## disassembly

```asm
0x18001dfff  lea     rcx, [rdx+1D0h]
0x18001e006  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
