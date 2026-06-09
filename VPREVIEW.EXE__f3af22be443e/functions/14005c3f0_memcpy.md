# memcpy

- ea: `0x14005c3f0`
- end: `0x14005c3f6`
- name: `memcpy`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `35`
- callee_count: `0`
- tags: ``

## callers

- `0x140004114`
- `0x140004248`
- `0x14000442c`
- `0x14000461c`
- `0x140005114`
- `0x140005f50`
- `0x140007014`
- `0x1400071b0`
- `0x140007aa0`
- `0x140008210`
- `0x1400093e0`
- `0x140009660`
- `0x140009e2c`
- `0x14000d27c`
- `0x1400101b8`
- `0x14001f3d0`
- `0x140020010`
- `0x140026ea0`
- `0x140027838`
- `0x14002da1c`
- `0x14002feec`
- `0x1400306f0`
- `0x140037ddc`
- `0x14003869c`
- `0x140040870`
- `0x1400410c0`
- `0x1400416c0`
- `0x140041804`
- `0x14004e388`
- `0x14004e490`
- `0x140052828`
- `0x140052a64`
- `0x140052c54`
- `0x140052f64`
- `0x1400541f0`

## import_xrefs

- `VCRUNTIME140!memcpy` at `0x14005c3f0`

## pseudocode

```c
// attributes: thunk
void *__cdecl memcpy(void *a1, const void *Src, size_t Size)
{
  return __imp_memcpy(a1, Src, Size);
}

```

## disassembly

```asm
0x14005c3f0  jmp     cs:__imp_memcpy
```
