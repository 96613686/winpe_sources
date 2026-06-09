# av_opt_set_defaults

- ea: `0x180022740`
- end: `0x180022746`
- name: `av_opt_set_defaults`
- size: `6`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180004150`
- `0x1800055d0`
- `0x180005ac0`
- `0x18000e838`

## import_xrefs

- `avutil_ms!av_opt_set_defaults` at `0x180022740`

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
0x180022740  jmp     cs:__imp_av_opt_set_defaults
```
