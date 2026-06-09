# operator delete(void *)

- ea: `0x180001084`
- end: `0x180001089`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `46`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001a60`
- `0x1800058e0`
- `0x180005910`
- `0x180005950`
- `0x180005990`
- `0x1800059c0`
- `0x180005a10`
- `0x180005a50`
- `0x180005a90`
- `0x180005ad0`
- `0x180005b20`
- `0x180005b70`
- `0x180007410`
- `0x180007440`
- `0x180007498`
- `0x18000bdd0`
- `0x18000daf0`
- `0x18000db30`
- `0x18000db70`
- `0x18000dbb0`
- `0x18000dbf0`
- `0x18000dc30`
- `0x18000dc70`
- `0x18000dcb0`
- `0x18000f120`
- `0x18000f160`
- `0x18000f1a0`
- `0x18000f1e0`
- `0x1800187f0`
- `0x18001bd50`
- `0x18001ca1c`
- `0x18001e3e0`
- `0x18001ed60`
- `0x1800256d0`
- `0x180025710`
- `0x1800296b0`
- `0x18002cdd8`
- `0x18002ce40`
- `0x18002cfb8`
- `0x18002d62c`
- `0x18002d974`
- `0x18002fd2c`
- `0x18002ffb0`
- `0x18002ffec`
- `0x180030180`
- `0x180031948`

## callees

- `0x180001756`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  free_0(Block);
}

```

## disassembly

```asm
0x180001084  jmp     free_0
```
