# _ParseCreateParams_::_1_::dtor$81

- ea: `0x1400123b8`
- end: `0x1400123c4`
- name: `_ParseCreateParams_::_1_::dtor$81`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140008150`

## pseudocode

```c
__int64 __fastcall ParseCreateParams_::_1_::dtor_81(__int64 a1, __int64 a2)
{
  return TpmVscMgrMeta::basic_formatter<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::~basic_formatter<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(a2 + 720);
}

```

## disassembly

```asm
0x1400123b8  lea     rcx, [rdx+2D0h]
0x1400123bf  jmp     ??1?$basic_formatter@GU?$char_traits@G@std@@V?$allocator@G@2@@TpmVscMgrMeta@@QEAA@XZ; TpmVscMgrMeta::basic_formatter<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_formatter<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
```
