# av_reduce

- ea: `0x18001bb64`
- end: `0x18001bb6a`
- name: `av_reduce`
- size: `6`
- prototype: ``
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x180001590`
- `0x180001c10`
- `0x180002000`
- `0x180006390`
- `0x180007ea8`
- `0x180009840`
- `0x18000e06c`
- `0x1800174d0`

## import_xrefs

- `avutil_ms!av_reduce` at `0x18001bb64`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall av_reduce(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  return __imp_av_reduce(a1, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x18001bb64  jmp     cs:__imp_av_reduce
```
