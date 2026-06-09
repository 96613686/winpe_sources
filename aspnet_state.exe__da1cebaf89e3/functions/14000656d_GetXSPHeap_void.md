# GetXSPHeap(void)

- ea: `0x14000656d`
- end: `0x140006573`
- name: `?GetXSPHeap@@YAPEAXXZ`
- size: `6`
- prototype: `void *(void)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140004f58`
- `0x140004f90`
- `0x140004fc8`
- `0x140005004`

## import_xrefs

- `webengine4!GetXSPHeap` at `0x14000656d`

## pseudocode

```c
// attributes: thunk
void *GetXSPHeap(void)
{
  return __imp_?GetXSPHeap@@YAPEAXXZ();
}

```

## disassembly

```asm
0x14000656d  jmp     cs:__imp_?GetXSPHeap@@YAPEAXXZ
```
