# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x18000fb38`
- end: `0x18000fb42`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `10`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18001c1de`
- `0x18001c354`
- `0x18001c366`
- `0x18001c39c`
- `0x18001c3e4`
- `0x18001c54d`
- `0x18001c55f`

## callees

- `0x1800124fc`

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
0x18000fb38  xor     r8d, r8d
0x18000fb3b  mov     dl, 1
0x18000fb3d  jmp     ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
```
