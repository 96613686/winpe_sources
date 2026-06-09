# av_mallocz

- ea: `0x18001bb94`
- end: `0x18001bb9a`
- name: `av_mallocz`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `24`
- callee_count: `0`
- tags: ``

## callers

- `0x180001660`
- `0x180002c90`
- `0x1800039f0`
- `0x180005eb4`
- `0x180007900`
- `0x18000952c`
- `0x18000c840`
- `0x18000ca60`
- `0x1800100a0`
- `0x180010290`
- `0x180010550`
- `0x180010730`
- `0x1800124c0`
- `0x180013478`
- `0x1800144ac`
- `0x180015fc4`
- `0x180016f90`
- `0x1800176a0`
- `0x1800179a0`
- `0x180018050`
- `0x180018b68`
- `0x180019290`
- `0x180019330`
- `0x1800195f0`

## import_xrefs

- `avutil_ms!av_mallocz` at `0x18001bb94`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall av_mallocz(__int64 a1)
{
  return __imp_av_mallocz(a1);
}

```

## disassembly

```asm
0x18001bb94  jmp     cs:__imp_av_mallocz
```
