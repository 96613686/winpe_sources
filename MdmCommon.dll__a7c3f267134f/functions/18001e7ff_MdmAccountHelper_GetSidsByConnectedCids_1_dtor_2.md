# _MdmAccountHelper::GetSidsByConnectedCids_::_1_::dtor$2

- ea: `0x18001e7ff`
- end: `0x18001e80b`
- name: `_MdmAccountHelper::GetSidsByConnectedCids_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x180002e54`

## pseudocode

```c
__int64 __fastcall MdmAccountHelper::GetSidsByConnectedCids_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return std::vector<std::wstring>::~vector<std::wstring>(a2 + 112);
}

```

## disassembly

```asm
0x18001e7ff  lea     rcx, [rdx+70h]
0x18001e806  jmp     ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
```
