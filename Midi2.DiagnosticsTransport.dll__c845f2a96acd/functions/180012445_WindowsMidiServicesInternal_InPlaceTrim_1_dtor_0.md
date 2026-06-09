# _WindowsMidiServicesInternal::InPlaceTrim_::_1_::dtor$0

- ea: `0x180012445`
- end: `0x180012451`
- name: `_WindowsMidiServicesInternal::InPlaceTrim_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000b7fc`

## pseudocode

```c
__int64 __fastcall WindowsMidiServicesInternal::InPlaceTrim_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 304));
}

```

## disassembly

```asm
0x180012445  lea     rcx, [rdx+130h]
0x18001244c  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
