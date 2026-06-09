# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x140007e2c`
- end: `0x140007e36`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `10`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `68`
- callee_count: `1`
- tags: ``

## callers

- `0x140013ed8`
- `0x140013f04`
- `0x140013f28`
- `0x14001424d`
- `0x1400143b9`
- `0x1400143cf`
- `0x1400143e5`
- `0x140014475`
- `0x140014499`
- `0x1400144e5`
- `0x1400144f7`
- `0x1400145b3`
- `0x1400145c5`
- `0x1400145d7`
- `0x1400145fb`
- `0x14001461f`
- `0x140014631`
- `0x140014643`
- `0x140014655`
- `0x140014667`
- `0x140014679`
- `0x14001468b`
- `0x14001469d`
- `0x1400146af`
- `0x1400146c1`
- `0x1400146d3`
- `0x1400146e5`
- `0x1400146f7`
- `0x140014723`
- `0x14001474f`
- `0x140014773`
- `0x1400147b1`
- `0x1400147c7`
- `0x1400147dd`
- `0x140014809`
- `0x14001486e`
- `0x140014880`
- `0x1400148ac`
- `0x1400148be`
- `0x1400148d0`
- `0x1400148e2`
- `0x1400148f4`
- `0x140014973`
- `0x1400149f2`
- `0x140014a04`
- `0x140014a16`
- `0x140014a28`
- `0x140014a3a`
- `0x140014a4c`
- `0x140014a5e`

## callees

- `0x140008368`

## pseudocode

```c
__int64 __fastcall std::wstring::~wstring(__int64 a1, __int64 a2)
{
  LOBYTE(a2) = 1;
  return std::wstring::_Tidy(a1, a2, 0);
}

```

## disassembly

```asm
0x140007e2c  xor     r8d, r8d
0x140007e2f  mov     dl, 1
0x140007e31  jmp     ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
```
