# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x180002cec`
- end: `0x180002cf6`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `10`
- prototype: ``
- caller_count: `75`
- callee_count: `1`
- tags: ``

## callers

- `0x18001f83f`
- `0x18001f851`
- `0x18001f863`
- `0x18001fc57`
- `0x18001fce8`
- `0x18001fcfa`
- `0x18001fd0c`
- `0x18001fd39`
- `0x18001fd4b`
- `0x18001fd5d`
- `0x18001fd6f`
- `0x18001fd81`
- `0x18001fd93`
- `0x18001fda5`
- `0x18001fdb7`
- `0x18001fdc9`
- `0x18001fddb`
- `0x18001fded`
- `0x18001fdff`
- `0x180020001`
- `0x180020013`
- `0x180020029`
- `0x18002003f`
- `0x180020093`
- `0x1800200a9`
- `0x1800200db`
- `0x180020107`
- `0x18002011d`
- `0x180020173`
- `0x180020185`
- `0x180020197`
- `0x1800201bb`
- `0x1800201f1`
- `0x180020203`
- `0x18002026f`
- `0x180020281`
- `0x1800202a5`
- `0x1800202b7`
- `0x180020359`
- `0x18002036b`
- `0x18002037d`
- `0x18002038f`
- `0x1800203a1`
- `0x1800203c5`
- `0x1800203e9`
- `0x1800203fb`
- `0x18002040d`
- `0x180020438`
- `0x180020489`
- `0x1800204e3`

## callees

- `0x1800062ac`

## pseudocode

```c
__int64 __fastcall std::wstring::~wstring(void **a1)
{
  return std::wstring::_Tidy(a1, 1, 0);
}

```

## disassembly

```asm
0x180002cec  xor     r8d, r8d
0x180002cef  mov     dl, 1
0x180002cf1  jmp     ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
```
