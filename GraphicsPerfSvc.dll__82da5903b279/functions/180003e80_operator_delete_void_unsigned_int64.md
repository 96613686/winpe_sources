# operator delete(void *,unsigned __int64)

- ea: `0x180003e80`
- end: `0x180003e85`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `51`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180006090`
- `0x1800060d0`
- `0x180006110`
- `0x180006150`
- `0x18000b550`
- `0x18000b890`
- `0x18000b8d0`
- `0x18000c6b0`
- `0x18000c6e0`
- `0x18000c710`
- `0x18000c750`
- `0x18000c790`
- `0x18000c7d0`
- `0x18000c810`
- `0x18000dfa8`
- `0x18000e720`
- `0x18000e9f0`
- `0x18000ea20`
- `0x18000ea50`
- `0x18000ea90`
- `0x18000ead0`
- `0x18000eb10`
- `0x18000eb50`
- `0x18000eb90`
- `0x18000ebc0`
- `0x180011f40`
- `0x1800134f0`
- `0x180014ab0`
- `0x180018250`
- `0x180018860`
- `0x18001fd10`
- `0x18001fd50`
- `0x18001fd90`
- `0x180021420`
- `0x180021520`
- `0x1800215a0`
- `0x180024030`
- `0x180024070`
- `0x180025730`
- `0x1800269d8`
- `0x1800290b0`
- `0x18002f55d`
- `0x18002f711`
- `0x18002f9ea`
- `0x18002fb3f`
- `0x18002fb86`
- `0x18002fcf4`
- `0x18002ffb2`
- `0x18002ffd5`
- `0x1800306fa`

## callees

- `0x180003f24`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x180003e80  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
