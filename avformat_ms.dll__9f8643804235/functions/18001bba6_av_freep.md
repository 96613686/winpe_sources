# av_freep

- ea: `0x18001bba6`
- end: `0x18001bbac`
- name: `av_freep`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `45`
- callee_count: `0`
- tags: ``

## callers

- `0x180001810`
- `0x18000219c`
- `0x180002268`
- `0x1800023d8`
- `0x180002a30`
- `0x180002b10`
- `0x180002bf0`
- `0x180002c90`
- `0x180002e8c`
- `0x18000320c`
- `0x1800039f0`
- `0x180003c8c`
- `0x180003f00`
- `0x180003f70`
- `0x1800056f0`
- `0x1800059b8`
- `0x180006390`
- `0x180009840`
- `0x18000a724`
- `0x18000fb50`
- `0x180010060`
- `0x180010270`
- `0x180010290`
- `0x180010530`
- `0x180010550`
- `0x180010710`
- `0x180010730`
- `0x180010898`
- `0x180010bf4`
- `0x180011b7c`
- `0x180011cac`
- `0x1800122a0`
- `0x1800146b0`
- `0x180014700`
- `0x180014de0`
- `0x180015324`
- `0x180015db0`
- `0x180015eb0`
- `0x180016310`
- `0x180017ff0`
- `0x180018050`
- `0x1800184fc`
- `0x1800187e0`
- `0x180018b68`
- `0x18001b6d8`

## import_xrefs

- `avutil_ms!av_freep` at `0x18001bba6`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall av_freep(__int64 a1)
{
  return __imp_av_freep(a1);
}

```

## disassembly

```asm
0x18001bba6  jmp     cs:__imp_av_freep
```
