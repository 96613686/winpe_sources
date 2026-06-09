# operator delete(void *,unsigned __int64)

- ea: `0x180001a90`
- end: `0x180001a95`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `58`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180008ac0`
- `0x180008b00`
- `0x180008b40`
- `0x180008b80`
- `0x18000de20`
- `0x18000de50`
- `0x18000e330`
- `0x18000edc0`
- `0x18000fbc0`
- `0x18000fc00`
- `0x18000fc40`
- `0x18000fc80`
- `0x18000fcc0`
- `0x180011cd0`
- `0x180011d00`
- `0x180011d40`
- `0x180011d80`
- `0x180011dc0`
- `0x180011e00`
- `0x180011e40`
- `0x180011e80`
- `0x180011ec0`
- `0x180011f00`
- `0x180011f40`
- `0x180011f74`
- `0x180011fc0`
- `0x180011ffc`
- `0x180012040`
- `0x180012080`
- `0x1800120c0`
- `0x180012100`
- `0x180012140`
- `0x180012180`
- `0x1800121c0`
- `0x180012200`
- `0x180012240`
- `0x180012280`
- `0x1800122c0`
- `0x180012300`
- `0x1800149e0`
- `0x180018cc0`
- `0x180018d00`
- `0x180018d40`
- `0x180018d80`
- `0x18001a270`
- `0x18001a4e0`
- `0x18001a520`
- `0x18001a560`
- `0x18001b530`
- `0x18001bfc0`

## callees

- `0x180001af0`

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
0x180001a90  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
