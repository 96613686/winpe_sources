# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x140003380`
- end: `0x14000338a`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `10`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x140009f90`
- `0x14000a337`
- `0x14000a349`
- `0x14000a35b`
- `0x14000a36d`
- `0x14000a37f`
- `0x14000a3b5`
- `0x14000a3d9`

## callees

- `0x140007610`

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
0x140003380  xor     r8d, r8d
0x140003383  mov     dl, 1
0x140003385  jmp     ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
```
