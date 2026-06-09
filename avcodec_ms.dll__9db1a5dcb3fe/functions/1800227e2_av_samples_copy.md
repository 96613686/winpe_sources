# av_samples_copy

- ea: `0x1800227e2`
- end: `0x1800227e8`
- name: `av_samples_copy`
- size: `6`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180007740`
- `0x18000aa50`

## import_xrefs

- `avutil_ms!av_samples_copy` at `0x1800227e2`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall av_samples_copy(__int64 a1, __int64 a2, __int64 a3)
{
  return __imp_av_samples_copy(a1, a2, a3);
}

```

## disassembly

```asm
0x1800227e2  jmp     cs:__imp_av_samples_copy
```
