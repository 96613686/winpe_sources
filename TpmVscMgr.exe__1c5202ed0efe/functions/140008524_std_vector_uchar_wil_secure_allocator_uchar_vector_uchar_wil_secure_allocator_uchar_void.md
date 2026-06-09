# std::vector<uchar,wil::secure_allocator<uchar>>::~vector<uchar,wil::secure_allocator<uchar>>(void)

- ea: `0x140008524`
- end: `0x140008529`
- name: `??1?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ`
- size: `5`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x140011988`
- `0x140011c7d`
- `0x140011c8f`
- `0x140011cb3`
- `0x140011de4`
- `0x140011df6`
- `0x140011e08`
- `0x140011e1a`
- `0x140011e2c`
- `0x140011e9e`
- `0x140011ec2`
- `0x14001234c`

## callees

- `0x14000b16c`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall std::vector<unsigned char,wil::secure_allocator<unsigned char>>::~vector<unsigned char,wil::secure_allocator<unsigned char>>(
        __int64 a1)
{
  return std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(a1);
}

```

## disassembly

```asm
0x140008524  jmp     ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
```
