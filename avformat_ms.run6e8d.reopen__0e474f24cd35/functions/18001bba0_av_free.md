# av_free

- ea: `0x18001bba0`
- end: `0x18001bba6`
- name: `av_free`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `21`
- callee_count: `0`
- tags: ``

## callers

- `0x180001660`
- `0x180001810`
- `0x180002bf0`
- `0x180002c90`
- `0x1800054e0`
- `0x1800056f0`
- `0x1800059b8`
- `0x180005e28`
- `0x180006390`
- `0x18000c840`
- `0x18000ca60`
- `0x1800100a0`
- `0x180010e4c`
- `0x1800110fc`
- `0x180011e78`
- `0x180012cf4`
- `0x180013dd0`
- `0x1800144ac`
- `0x1800157e8`
- `0x180015eb0`
- `0x180016180`

## import_xrefs

- `avutil_ms!av_free` at `0x18001bba0`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall av_free(__int64 a1)
{
  return __imp_av_free(a1);
}

```

## disassembly

```asm
0x18001bba0  jmp     cs:__imp_av_free
```
