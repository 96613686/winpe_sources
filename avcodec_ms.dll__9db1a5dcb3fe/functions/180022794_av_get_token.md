# av_get_token

- ea: `0x180022794`
- end: `0x18002279a`
- name: `av_get_token`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180005f30`

## import_xrefs

- `avutil_ms!av_get_token` at `0x180022794`

## pseudocode

```c
// attributes: thunk
__int64 av_get_token()
{
  return __imp_av_get_token();
}

```

## disassembly

```asm
0x180022794  jmp     cs:__imp_av_get_token
```
