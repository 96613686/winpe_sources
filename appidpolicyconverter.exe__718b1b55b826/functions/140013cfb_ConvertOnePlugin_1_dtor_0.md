# _ConvertOnePlugin_::_1_::dtor$0

- ea: `0x140013cfb`
- end: `0x140013d07`
- name: `_ConvertOnePlugin_::_1_::dtor$0`
- size: `12`
- prototype: `LSTATUS __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140002814`

## pseudocode

```c
LSTATUS __fastcall ConvertOnePlugin_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::unique_ptr<HKEY__,release::Deleter<void>>::~unique_ptr<HKEY__,release::Deleter<void>>((HKEY *)(a2 + 136));
}

```

## disassembly

```asm
0x140013cfb  lea     rcx, [rdx+88h]
0x140013d02  jmp     ??1?$unique_ptr@UHKEY__@@U?$Deleter@X@release@@@std@@QEAA@XZ; std::unique_ptr<HKEY__,release::Deleter<void>>::~unique_ptr<HKEY__,release::Deleter<void>>(void)
```
