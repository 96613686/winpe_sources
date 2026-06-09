# av_realloc_array

- ea: `0x18001bb9a`
- end: `0x18001bba0`
- name: `av_realloc_array`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001740`
- `0x180015324`
- `0x180019330`
- `0x180019540`
- `0x1800195f0`

## import_xrefs

- `avutil_ms!av_realloc_array` at `0x18001bb9a`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall av_realloc_array(__int64 a1, __int64 a2, __int64 a3)
{
  return __imp_av_realloc_array(a1, a2, a3);
}

```

## disassembly

```asm
0x18001bb9a  jmp     cs:__imp_av_realloc_array
```
