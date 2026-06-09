# av_refstruct_replace

- ea: `0x18002282a`
- end: `0x180022830`
- name: `av_refstruct_replace`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180007f44`
- `0x180011810`
- `0x18001bb80`

## import_xrefs

- `avutil_ms!av_refstruct_replace` at `0x18002282a`

## pseudocode

```c
// attributes: thunk
__int64 av_refstruct_replace()
{
  return __imp_av_refstruct_replace();
}

```

## disassembly

```asm
0x18002282a  jmp     cs:__imp_av_refstruct_replace
```
