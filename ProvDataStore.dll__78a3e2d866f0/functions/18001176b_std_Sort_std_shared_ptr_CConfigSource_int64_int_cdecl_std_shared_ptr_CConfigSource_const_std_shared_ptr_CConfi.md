# _std::_Sort_std::shared_ptr_CConfigSource______int64_int_(__cdecl_)(std::shared_ptr_CConfigSource_const___std::shared_ptr_CConfigSource_const__)_noexcept__::_1_::dtor$2

- ea: `0x18001176b`
- end: `0x180011777`
- name: `_std::_Sort_std::shared_ptr_CConfigSource______int64_int_(__cdecl_)(std::shared_ptr_CConfigSource_const___std::shared_ptr_CConfigSource_const__)_noexcept__::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180008ebc`

## pseudocode

```c
__int64 __fastcall std::_Sort_std::shared_ptr_CConfigSource______int64_int____cdecl___std::shared_ptr_CConfigSource_const___std::shared_ptr_CConfigSource_const____noexcept__::_1_::dtor_2(
        __int64 a1,
        __int64 a2)
{
  return std::shared_ptr<CConfigSet>::~shared_ptr<CConfigSet>(a2 + 80);
}

```

## disassembly

```asm
0x18001176b  lea     rcx, [rdx+50h]
0x180011772  jmp     ??1?$shared_ptr@VCConfigSet@@@std@@QEAA@XZ; std::shared_ptr<CConfigSet>::~shared_ptr<CConfigSet>(void)
```
