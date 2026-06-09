# _WindowsMidiServicesInternal::CalculateEndpointDevicePrimaryName_::_1_::dtor$16

- ea: `0x18001225b`
- end: `0x180012267`
- name: `_WindowsMidiServicesInternal::CalculateEndpointDevicePrimaryName_::_1_::dtor$16`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000b7fc`

## pseudocode

```c
__int64 __fastcall WindowsMidiServicesInternal::CalculateEndpointDevicePrimaryName_::_1_::dtor_16(
        __int64 a1,
        __int64 a2)
{
  return std::wstring::~wstring(*(char ***)(a2 + 40));
}

```

## disassembly

```asm
0x18001225b  mov     rcx, [rdx+28h]
0x180012262  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
