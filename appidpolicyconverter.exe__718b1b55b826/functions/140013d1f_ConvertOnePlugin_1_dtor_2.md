# _ConvertOnePlugin_::_1_::dtor$2

- ea: `0x140013d1f`
- end: `0x140013d2b`
- name: `_ConvertOnePlugin_::_1_::dtor$2`
- size: `12`
- prototype: `LSTATUS __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140002814`

## pseudocode

```c
LSTATUS __fastcall ConvertOnePlugin_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return std::unique_ptr<HKEY__,release::Deleter<void>>::~unique_ptr<HKEY__,release::Deleter<void>>((HKEY *)(a2 + 144));
}

```

## disassembly

```asm
0x140013d1f  lea     rcx, [rdx+90h]
0x140013d26  jmp     ??1?$unique_ptr@UHKEY__@@U?$Deleter@X@release@@@std@@QEAA@XZ; std::unique_ptr<HKEY__,release::Deleter<void>>::~unique_ptr<HKEY__,release::Deleter<void>>(void)
```
