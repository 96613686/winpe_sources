# operator delete(void *)

- ea: `0x1800010b8`
- end: `0x1800010bd`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `41`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002110`
- `0x180002150`
- `0x180002438`
- `0x180002540`
- `0x180003498`
- `0x1800034f0`
- `0x180003530`
- `0x180003570`
- `0x1800035b0`
- `0x1800035f0`
- `0x180003628`
- `0x180003668`
- `0x180004bdc`
- `0x180004c30`
- `0x1800056a0`
- `0x180006918`
- `0x180006980`
- `0x180006a00`
- `0x180006a40`
- `0x180006a80`
- `0x180006ac0`
- `0x180006af8`
- `0x180006b30`
- `0x180006b68`
- `0x180006ba0`
- `0x180006bd8`
- `0x180006c10`
- `0x180006c50`
- `0x180006c88`
- `0x180006cc0`
- `0x180006d00`
- `0x180006d40`
- `0x180006d78`
- `0x180007fac`
- `0x180008000`
- `0x18000cb64`
- `0x18000e840`
- `0x18000f030`
- `0x180010430`
- `0x180010470`
- `0x180011100`

## callees

- `0x180001796`

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
0x1800010b8  jmp     free_0
```
