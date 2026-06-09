# _MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor$17

- ea: `0x18001d98b`
- end: `0x18001d997`
- name: `_MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor$17`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002de4`

## pseudocode

```c
__int64 __fastcall MdmHttpWrapper::CreateRegisterDeviceRequestBody_::_1_::dtor_17(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 848));
}

```

## disassembly

```asm
0x18001d98b  lea     rcx, [rdx+350h]
0x18001d992  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
