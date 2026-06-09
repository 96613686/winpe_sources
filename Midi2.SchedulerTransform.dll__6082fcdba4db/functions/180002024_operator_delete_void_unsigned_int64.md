# operator delete(void *,unsigned __int64)

- ea: `0x180002024`
- end: `0x180002029`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `29`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800035a4`
- `0x1800038e0`
- `0x180003950`
- `0x1800039c0`
- `0x180003a00`
- `0x180003a40`
- `0x180003e5c`
- `0x180004930`
- `0x180004e80`
- `0x180007600`
- `0x180008d4c`
- `0x180008ee0`
- `0x180008f40`
- `0x180008fc0`
- `0x180009020`
- `0x18000a050`
- `0x18000a2a0`
- `0x18000a3e0`
- `0x18000a83c`
- `0x18000a8d4`
- `0x18000a99c`
- `0x18000abe0`
- `0x18000ba70`
- `0x18000be34`
- `0x18000c1a0`
- `0x18000c628`
- `0x18000c694`
- `0x18000c710`
- `0x18000c740`

## callees

- `0x180001fe4`

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
0x180002024  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
