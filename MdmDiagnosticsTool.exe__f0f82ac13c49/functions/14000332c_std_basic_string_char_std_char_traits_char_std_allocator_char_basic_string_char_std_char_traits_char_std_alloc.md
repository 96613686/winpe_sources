# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::~basic_string<char,std::char_traits<char>,std::allocator<char>>(void)

- ea: `0x14000332c`
- end: `0x140003336`
- name: `??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ`
- size: `10`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140009d5c`
- `0x140009d6e`
- `0x140009d92`

## callees

- `0x1400071a4`

## pseudocode

```c
__int64 __fastcall std::string::~string(__int64 a1, __int64 a2)
{
  LOBYTE(a2) = 1;
  return std::string::_Tidy(a1, a2, 0);
}

```

## disassembly

```asm
0x14000332c  xor     r8d, r8d
0x14000332f  mov     dl, 1
0x140003331  jmp     ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
```
