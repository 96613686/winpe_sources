# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::~basic_string<char,std::char_traits<char>,std::allocator<char>>(void)

- ea: `0x140003370`
- end: `0x14000337a`
- name: `??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ`
- size: `10`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000a391`
- `0x14000a3a3`
- `0x14000a3c7`

## callees

- `0x1400075a8`

## pseudocode

```c
void __fastcall std::string::~string(void **a1)
{
  std::string::_Tidy(a1, 1, 0);
}

```

## disassembly

```asm
0x140003370  xor     r8d, r8d
0x140003373  mov     dl, 1
0x140003375  jmp     ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
```
