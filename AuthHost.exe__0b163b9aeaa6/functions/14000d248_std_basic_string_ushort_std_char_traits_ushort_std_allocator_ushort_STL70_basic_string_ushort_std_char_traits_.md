# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>,_STL70>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>,_STL70>(void)

- ea: `0x14000d248`
- end: `0x14000d252`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAA@XZ`
- size: `10`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140013591`
- `0x1400135a3`
- `0x1400135d9`
- `0x1400135eb`
- `0x1400136b1`

## callees

- `0x14000fa04`

## pseudocode

```c
__int64 __fastcall std::wstring::~wstring(__int64 a1)
{
  return std::wstring::_Tidy(a1, 1, 0);
}

```

## disassembly

```asm
0x14000d248  xor     r8d, r8d
0x14000d24b  mov     dl, 1
0x14000d24d  jmp     ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
```
