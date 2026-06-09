# std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ulong>::~pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ulong>(void)

- ea: `0x140003c10`
- end: `0x140003c1a`
- name: `??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ`
- size: `10`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `46`
- callee_count: `1`
- tags: ``

## callers

- `0x14001ab8c`
- `0x14001ab9e`
- `0x14001abb4`
- `0x14001abca`
- `0x14001abe0`
- `0x14001abf9`
- `0x14001ac2b`
- `0x14001ac44`
- `0x14001ac5d`
- `0x14001ac76`
- `0x14001ac8f`
- `0x14001ad4a`
- `0x14001ad5c`
- `0x14001ae09`
- `0x14001ae1b`
- `0x14001ae31`
- `0x14001ae47`
- `0x14001ae5d`
- `0x14001ae76`
- `0x14001aec5`
- `0x14001aefb`
- `0x14001af0d`
- `0x14001af1f`
- `0x14001af43`
- `0x14001af55`
- `0x14001af79`
- `0x14001af8b`
- `0x14001af9d`
- `0x14001afcc`
- `0x14001b016`
- `0x14001b028`
- `0x14001b03a`
- `0x14001b04c`
- `0x14001b05e`
- `0x14001b124`
- `0x14001b148`
- `0x14001b15a`
- `0x14001b16c`
- `0x14001b17e`
- `0x14001b1c6`
- `0x14001b1d8`
- `0x14001b1ea`
- `0x14001b1fc`
- `0x14001b228`
- `0x14001b27b`
- `0x14001b2a7`

## callees

- `0x140006480`

## pseudocode

```c
__int64 __fastcall std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>(__int64 a1, __int64 a2)
{
  LOBYTE(a2) = 1;
  return std::wstring::_Tidy(a1, a2, 0);
}

```

## disassembly

```asm
0x140003c10  xor     r8d, r8d
0x140003c13  mov     dl, 1
0x140003c15  jmp     ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
```
