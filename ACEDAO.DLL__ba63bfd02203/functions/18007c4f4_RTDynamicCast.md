# __RTDynamicCast

- ea: `0x18007c4f4`
- end: `0x18007c4fa`
- name: `__RTDynamicCast`
- size: `6`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int)`
- caller_count: `45`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18002ff70`
- `0x180069830`
- `0x18006b758`
- `0x18006b9ac`
- `0x18006bc00`
- `0x18006be54`
- `0x18006c0a8`
- `0x18006c2fc`
- `0x18006c550`
- `0x18006c7a4`
- `0x18006c9f8`
- `0x18006cc4c`
- `0x18006cea0`
- `0x18006d0f4`
- `0x18006d348`
- `0x18006d59c`
- `0x18006d7f0`
- `0x18006da44`
- `0x18006dc98`
- `0x18006deec`
- `0x18006e140`
- `0x18006e394`
- `0x18006e5e8`
- `0x18006e83c`
- `0x18006ea90`
- `0x18006ece4`
- `0x18006ef38`
- `0x18006f18c`
- `0x18006f3e0`
- `0x18006f634`
- `0x18006f888`
- `0x18006fae0`
- `0x18006fd34`
- `0x18006ff88`
- `0x1800701dc`
- `0x180070430`
- `0x180070684`
- `0x1800708d8`
- `0x180070b2c`
- `0x180070d80`
- `0x180070fd4`
- `0x180071228`
- `0x18007147c`
- `0x1800716d0`
- `0x180072a70`

## import_xrefs

- `VCRUNTIME140!__RTDynamicCast` at `0x18007c4f4`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall _RTDynamicCast(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5)
{
  return __RTDynamicCast(a1, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x18007c4f4  jmp     cs:__imp___RTDynamicCast
```
