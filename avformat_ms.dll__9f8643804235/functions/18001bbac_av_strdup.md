# av_strdup

- ea: `0x18001bbac`
- end: `0x18001bbb2`
- name: `av_strdup`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x1800023d8`
- `0x180002e8c`
- `0x180003294`
- `0x180007900`
- `0x180011cac`
- `0x1800124c0`
- `0x180013478`

## import_xrefs

- `avutil_ms!av_strdup` at `0x18001bbac`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall av_strdup(__int64 a1)
{
  return __imp_av_strdup(a1);
}

```

## disassembly

```asm
0x18001bbac  jmp     cs:__imp_av_strdup
```
