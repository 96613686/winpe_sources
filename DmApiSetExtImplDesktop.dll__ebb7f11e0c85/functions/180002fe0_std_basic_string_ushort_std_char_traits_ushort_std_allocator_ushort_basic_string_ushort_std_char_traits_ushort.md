# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x180002fe0`
- end: `0x180002fea`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `10`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a70c`
- `0x18000a766`
- `0x18000a778`
- `0x18000a78a`

## callees

- `0x180005c60`

## pseudocode

```c
__int64 __fastcall std::wstring::~wstring(void **a1)
{
  return std::wstring::_Tidy(a1, 1, 0);
}

```

## disassembly

```asm
0x180002fe0  xor     r8d, r8d
0x180002fe3  mov     dl, 1
0x180002fe5  jmp     ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
```
