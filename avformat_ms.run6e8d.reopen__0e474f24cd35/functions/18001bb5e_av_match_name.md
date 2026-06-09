# av_match_name

- ea: `0x18001bb5e`
- end: `0x18001bb64`
- name: `av_match_name`
- size: `6`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180001c10`
- `0x18000f940`
- `0x18000f990`
- `0x18000fa10`
- `0x18000fae0`
- `0x18000fe00`

## import_xrefs

- `avutil_ms!av_match_name` at `0x18001bb5e`

## pseudocode

```c
// attributes: thunk
__int64 av_match_name()
{
  return __imp_av_match_name();
}

```

## disassembly

```asm
0x18001bb5e  jmp     cs:__imp_av_match_name
```
