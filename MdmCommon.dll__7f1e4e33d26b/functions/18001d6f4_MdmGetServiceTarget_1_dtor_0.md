# _MdmGetServiceTarget_::_1_::dtor$0

- ea: `0x18001d6f4`
- end: `0x18001d700`
- name: `_MdmGetServiceTarget_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180002de4`

## pseudocode

```c
__int64 __fastcall MdmGetServiceTarget_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 56));
}

```

## disassembly

```asm
0x18001d6f4  lea     rcx, [rdx+38h]
0x18001d6fb  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
