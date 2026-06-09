# av_malloc

- ea: `0x1800228dc`
- end: `0x1800228e2`
- name: `av_malloc`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x18000e740`
- `0x18000ed70`
- `0x18000f200`
- `0x18000f760`
- `0x18000fa70`
- `0x180015020`
- `0x18001794c`
- `0x18001826c`
- `0x18001bd00`

## import_xrefs

- `avutil_ms!av_malloc` at `0x1800228dc`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall av_malloc(__int64 a1)
{
  return __imp_av_malloc(a1);
}

```

## disassembly

```asm
0x1800228dc  jmp     cs:__imp_av_malloc
```
