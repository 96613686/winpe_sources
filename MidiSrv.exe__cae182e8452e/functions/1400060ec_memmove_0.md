# memmove_0

- ea: `0x1400060ec`
- end: `0x1400060f2`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `38`
- callee_count: `0`
- tags: ``

## callers

- `0x1400125a0`
- `0x14001487c`
- `0x140018a90`
- `0x140018b20`
- `0x140018bb0`
- `0x14001b33c`
- `0x14001ce50`
- `0x14001fcf0`
- `0x14001fe88`
- `0x140021614`
- `0x1400216cc`
- `0x140021c00`
- `0x140021d84`
- `0x14002308c`
- `0x14002663c`
- `0x140026754`
- `0x1400267d4`
- `0x14002698c`
- `0x1400274d8`
- `0x140029064`
- `0x140029568`
- `0x14002b1a0`
- `0x14002efd0`
- `0x14002f77c`
- `0x140032ff4`
- `0x1400351b4`
- `0x14003931c`
- `0x140039d60`
- `0x14003bc20`
- `0x14003d0b0`
- `0x1400484bc`
- `0x14004bc68`
- `0x14004c918`
- `0x14004caf0`
- `0x14004f6d8`
- `0x14004fae0`
- `0x14005213c`
- `0x140053cd0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x1400060ec`

## pseudocode

```c
// attributes: thunk
void *__cdecl memmove_0(void *a1, const void *Src, size_t Size)
{
  return memmove(a1, Src, Size);
}

```

## disassembly

```asm
0x1400060ec  jmp     cs:__imp_memmove
```
