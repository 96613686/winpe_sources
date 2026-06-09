# CNtAce::Deserialize(uchar *)

- ea: `0x18000f730`
- end: `0x18000f736`
- name: `?Deserialize@CNtAce@@UEAA_NPEAE@Z_0`
- size: `6`
- prototype: `bool(CNtAce *__hidden this, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## import_xrefs

- `wbemcomn!?Deserialize@CNtAce@@UEAA_NPEAE@Z` at `0x18000f730`

## pseudocode

```c
// attributes: thunk
bool __fastcall CNtAce::Deserialize(CNtAce *this, unsigned __int8 *a2)
{
  return __imp_?Deserialize@CNtAce@@UEAA_NPEAE@Z(this, a2);
}

```

## disassembly

```asm
0x18000f730  jmp     cs:__imp_?Deserialize@CNtAce@@UEAA_NPEAE@Z
```
