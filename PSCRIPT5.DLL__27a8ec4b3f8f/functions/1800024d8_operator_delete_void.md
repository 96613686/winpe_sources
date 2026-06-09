# operator delete(void *)

- ea: `0x1800024d8`
- end: `0x1800024dd`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `16`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001f70`
- `0x1800325c0`
- `0x180035700`
- `0x1800357c0`
- `0x180035860`
- `0x1800358a0`
- `0x1800358d0`
- `0x180035930`
- `0x180035a2c`
- `0x180035c30`
- `0x180036570`
- `0x180037634`
- `0x180037748`
- `0x18003791c`
- `0x180037ac0`
- `0x180037bc8`

## callees

- `0x1800028cc`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  free(Block);
}

```

## disassembly

```asm
0x1800024d8  jmp     free
```
