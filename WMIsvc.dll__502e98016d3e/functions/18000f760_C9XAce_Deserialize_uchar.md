# C9XAce::Deserialize(uchar *)

- ea: `0x18000f760`
- end: `0x18000f766`
- name: `?Deserialize@C9XAce@@UEAA_NPEAE@Z_0`
- size: `6`
- prototype: `bool(C9XAce *__hidden this, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## import_xrefs

- `wbemcomn!?Deserialize@C9XAce@@UEAA_NPEAE@Z` at `0x18000f760`

## pseudocode

```c
// attributes: thunk
bool __fastcall C9XAce::Deserialize(C9XAce *this, unsigned __int8 *a2)
{
  return __imp_?Deserialize@C9XAce@@UEAA_NPEAE@Z(this, a2);
}

```

## disassembly

```asm
0x18000f760  jmp     cs:__imp_?Deserialize@C9XAce@@UEAA_NPEAE@Z
```
