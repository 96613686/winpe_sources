# av_opt_set_defaults

- ea: `0x18001bbfa`
- end: `0x18001bc00`
- name: `av_opt_set_defaults`
- size: `6`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x1800039f0`
- `0x180007900`
- `0x1800124c0`
- `0x180013478`
- `0x180019290`
- `0x1800195f0`

## import_xrefs

- `avutil_ms!av_opt_set_defaults` at `0x18001bbfa`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall av_opt_set_defaults(__int64 a1)
{
  return __imp_av_opt_set_defaults(a1);
}

```

## disassembly

```asm
0x18001bbfa  jmp     cs:__imp_av_opt_set_defaults
```
