# av_rescale_q

- ea: `0x1800227ca`
- end: `0x1800227d0`
- name: `av_rescale_q`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180006bd0`
- `0x180007740`
- `0x18000a3cc`
- `0x18000f3a0`

## import_xrefs

- `avutil_ms!av_rescale_q` at `0x1800227ca`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall av_rescale_q(__int64 a1, __int64 a2, __int64 a3)
{
  return __imp_av_rescale_q(a1, a2, a3);
}

```

## disassembly

```asm
0x1800227ca  jmp     cs:__imp_av_rescale_q
```
