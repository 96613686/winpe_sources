# av_rescale

- ea: `0x18001bc5a`
- end: `0x18001bc60`
- name: `av_rescale`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x180008068`
- `0x180008b78`
- `0x18000a920`
- `0x18000c4d0`
- `0x18000ca60`
- `0x180012cf4`
- `0x180017390`
- `0x180019f50`
- `0x18001a314`
- `0x18001b08c`

## import_xrefs

- `avutil_ms!av_rescale` at `0x18001bc5a`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall av_rescale(__int64 a1, __int64 a2, __int64 a3)
{
  return __imp_av_rescale(a1, a2, a3);
}

```

## disassembly

```asm
0x18001bc5a  jmp     cs:__imp_av_rescale
```
