# operator delete(void *,unsigned __int64)

- ea: `0x180002f84`
- end: `0x180002f89`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `13`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004bf0`
- `0x1800057d4`
- `0x180005b10`
- `0x180005b40`
- `0x180005b80`
- `0x180005bc0`
- `0x180005c00`
- `0x180005c30`
- `0x180005c80`
- `0x18000aed0`
- `0x18000df1c`
- `0x18000f670`
- `0x180010200`

## callees

- `0x180002f78`

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
0x180002f84  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
