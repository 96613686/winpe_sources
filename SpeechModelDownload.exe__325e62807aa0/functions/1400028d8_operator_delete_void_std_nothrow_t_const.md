# operator delete(void *,std::nothrow_t const &)

- ea: `0x1400028d8`
- end: `0x1400028dd`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `38`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140004d50`
- `0x140004d90`
- `0x140004df0`
- `0x140004e30`
- `0x140004e90`
- `0x140004ef0`
- `0x140009698`
- `0x140009aac`
- `0x14000b8f0`
- `0x14000b930`
- `0x14000c5f0`
- `0x14000cc9c`
- `0x14000e4c8`
- `0x140013a2c`
- `0x140013d7c`
- `0x1400141a4`
- `0x140014310`
- `0x140014420`
- `0x1400146e4`
- `0x1400147dc`
- `0x1400148e0`
- `0x1400152d8`
- `0x1400153d0`
- `0x1400153f4`
- `0x140015464`
- `0x14001551c`
- `0x1400155e4`
- `0x14001582c`
- `0x140015b60`
- `0x140015da0`
- `0x140016dc0`
- `0x140018680`
- `0x14001a344`
- `0x14001a448`
- `0x14001a72c`
- `0x14001be46`
- `0x14001c093`
- `0x14001c3e4`

## callees

- `0x1400025e8`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x1400028d8  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
