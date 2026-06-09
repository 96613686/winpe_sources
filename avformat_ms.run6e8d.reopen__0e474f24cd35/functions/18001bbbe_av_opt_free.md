# av_opt_free

- ea: `0x18001bbbe`
- end: `0x18001bbc4`
- name: `av_opt_free`
- size: `6`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180001810`
- `0x180002268`
- `0x180002a30`
- `0x180002c90`
- `0x180002e8c`
- `0x18000320c`
- `0x1800122a0`

## import_xrefs

- `avutil_ms!av_opt_free` at `0x18001bbbe`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall av_opt_free(__int64 a1)
{
  return __imp_av_opt_free(a1);
}

```

## disassembly

```asm
0x18001bbbe  jmp     cs:__imp_av_opt_free
```
