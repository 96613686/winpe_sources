# GetXSPHeap(void)

- ea: `0x180002fa4`
- end: `0x180002fac`
- name: `?GetXSPHeap@@YAPEAXXZ`
- size: `8`
- prototype: `void *(void)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18000318c`
- `0x1800031c4`
- `0x1800031fc`

## pseudocode

```c
HANDLE GetXSPHeap(void)
{
  return g_hXSPHeap;
}

```

## disassembly

```asm
0x180002fa4  mov     rax, cs:?g_hXSPHeap@@3PEAXEA; void * g_hXSPHeap
0x180002fab  retn
```
