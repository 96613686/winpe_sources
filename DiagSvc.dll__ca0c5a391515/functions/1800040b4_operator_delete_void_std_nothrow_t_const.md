# operator delete(void *,std::nothrow_t const &)

- ea: `0x1800040b4`
- end: `0x1800040b9`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `55`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800052d4`
- `0x180005490`
- `0x1800065e0`
- `0x18000959c`
- `0x18000a440`
- `0x18000a490`
- `0x18000a4c0`
- `0x18000a500`
- `0x18000a540`
- `0x18000a580`
- `0x18000a5c0`
- `0x18000a600`
- `0x18000a640`
- `0x18000a680`
- `0x180013b10`
- `0x1800163c0`
- `0x180016400`
- `0x180016440`
- `0x180016474`
- `0x1800164b0`
- `0x1800164f0`
- `0x180016530`
- `0x180016570`
- `0x1800165b0`
- `0x1800165f0`
- `0x180016630`
- `0x180016670`
- `0x18001a840`
- `0x18001e360`
- `0x18001e790`
- `0x18001e7d0`
- `0x18001e810`
- `0x18001e860`
- `0x18001e8b0`
- `0x18001e900`
- `0x18001e940`
- `0x18001e980`
- `0x18001e9c0`
- `0x18001ea00`
- `0x18001ea40`
- `0x18001ea80`
- `0x18001eac0`
- `0x18001eb00`
- `0x18001eb40`
- `0x18001eb68`
- `0x18001eba0`
- `0x18001ebe0`
- `0x18001ec20`
- `0x180023078`
- `0x180024cb0`

## callees

- `0x180003bc4`

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
0x1800040b4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
