# av_malloc

- ea: `0x18001bbee`
- end: `0x18001bbf4`
- name: `av_malloc`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `13`
- callee_count: `0`
- tags: ``

## callers

- `0x180002e8c`
- `0x180003e70`
- `0x1800054e0`
- `0x180005e28`
- `0x1800100a0`
- `0x180010730`
- `0x180012cf4`
- `0x180015324`
- `0x1800157e8`
- `0x180015fc4`
- `0x180016180`
- `0x1800184fc`
- `0x18001b6d8`

## import_xrefs

- `avutil_ms!av_malloc` at `0x18001bbee`

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
0x18001bbee  jmp     cs:__imp_av_malloc
```
