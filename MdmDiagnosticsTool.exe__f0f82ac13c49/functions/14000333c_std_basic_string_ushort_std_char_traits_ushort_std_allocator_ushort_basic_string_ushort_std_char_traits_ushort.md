# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x14000333c`
- end: `0x140003346`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `10`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x14000995b`
- `0x140009d02`
- `0x140009d14`
- `0x140009d26`
- `0x140009d38`
- `0x140009d4a`
- `0x140009d80`
- `0x140009da4`

## callees

- `0x140007204`

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
0x14000333c  xor     r8d, r8d
0x14000333f  mov     dl, 1
0x140003341  jmp     ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
```
