# _MdmAccountHelper::GetSidsByConnectedCids_::_1_::dtor$6

- ea: `0x18001dc4c`
- end: `0x18001dc58`
- name: `_MdmAccountHelper::GetSidsByConnectedCids_::_1_::dtor$6`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x180002de4`

## pseudocode

```c
__int64 __fastcall MdmAccountHelper::GetSidsByConnectedCids_::_1_::dtor_6(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 160));
}

```

## disassembly

```asm
0x18001dc4c  lea     rcx, [rdx+0A0h]
0x18001dc53  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
