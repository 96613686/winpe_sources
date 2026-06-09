# operator delete[](void *)

- ea: `0x180023168`
- end: `0x18002316d`
- name: `??_V@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `52`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003860`
- `0x180004c8c`
- `0x180005b2c`
- `0x180006030`
- `0x1800063c0`
- `0x180006d30`
- `0x180007910`
- `0x180009da0`
- `0x18000a310`
- `0x18000d2f0`
- `0x18000dca0`
- `0x18000f2a0`
- `0x18000fcf0`
- `0x180011410`
- `0x18001241c`
- `0x1800125e0`
- `0x180012740`
- `0x1800136a0`
- `0x180013740`
- `0x180013f80`
- `0x1800144e0`
- `0x180014b88`
- `0x180014c20`
- `0x180014dec`
- `0x180014f78`
- `0x180015790`
- `0x1800174e8`
- `0x180017664`
- `0x180017768`
- `0x1800178d4`
- `0x1800179b0`
- `0x180018a68`
- `0x180019640`
- `0x180019a40`
- `0x18001a390`
- `0x18001a748`
- `0x18001af40`
- `0x18001b304`
- `0x18001b5cc`
- `0x18001b814`
- `0x180024330`
- `0x180029600`
- `0x18002965c`
- `0x180029f78`
- `0x18002e628`
- `0x18002fe68`
- `0x1800319e4`
- `0x180031a40`
- `0x180031d10`
- `0x1800320a0`

## callees

- `0x18001c370`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete[](void *Block)
{
  operator delete(Block);
}

```

## disassembly

```asm
0x180023168  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
