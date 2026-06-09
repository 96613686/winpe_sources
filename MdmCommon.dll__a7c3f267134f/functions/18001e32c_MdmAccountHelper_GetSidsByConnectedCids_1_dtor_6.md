# _MdmAccountHelper::GetSidsByConnectedCids_::_1_::dtor$6

- ea: `0x18001e32c`
- end: `0x18001e338`
- name: `_MdmAccountHelper::GetSidsByConnectedCids_::_1_::dtor$6`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x180002de8`

## pseudocode

```c
__int64 __fastcall MdmAccountHelper::GetSidsByConnectedCids_::_1_::dtor_6(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 160));
}

```

## disassembly

```asm
0x18001e32c  lea     rcx, [rdx+0A0h]
0x18001e333  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
