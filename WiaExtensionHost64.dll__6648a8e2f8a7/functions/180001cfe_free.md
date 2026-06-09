# free

- ea: `0x180001cfe`
- end: `0x180001d04`
- name: `free`
- size: `6`
- prototype: `void __cdecl(void *Block)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800019b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180001cfe`

## pseudocode

```c
// attributes: thunk
void __cdecl free(void *Block)
{
  __imp_free(Block);
}

```

## disassembly

```asm
0x180001cfe  jmp     cs:__imp_free
```
