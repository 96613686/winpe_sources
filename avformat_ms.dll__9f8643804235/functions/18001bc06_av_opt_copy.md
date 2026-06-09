# av_opt_copy

- ea: `0x18001bc06`
- end: `0x18001bc0c`
- name: `av_opt_copy`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800035d4`

## import_xrefs

- `avutil_ms!av_opt_copy` at `0x18001bc06`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall av_opt_copy(__int64 a1)
{
  return __imp_av_opt_copy(a1);
}

```

## disassembly

```asm
0x18001bc06  jmp     cs:__imp_av_opt_copy
```
