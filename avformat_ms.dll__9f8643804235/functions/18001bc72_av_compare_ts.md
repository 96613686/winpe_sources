# av_compare_ts

- ea: `0x18001bc72`
- end: `0x18001bc78`
- name: `av_compare_ts`
- size: `6`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180007d90`
- `0x180013214`
- `0x180013be0`

## import_xrefs

- `avutil_ms!av_compare_ts` at `0x18001bc72`

## pseudocode

```c
// attributes: thunk
__int64 av_compare_ts()
{
  return __imp_av_compare_ts();
}

```

## disassembly

```asm
0x18001bc72  jmp     cs:__imp_av_compare_ts
```
