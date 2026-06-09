# SoftwareKey::GenRandom(unsigned __int64,uchar *)

- ea: `0x1400520fc`
- end: `0x140052137`
- name: `?GenRandom@SoftwareKey@@YAJ_KPEAE@Z`
- size: `59`
- prototype: `__int64 __fastcall(ULONG cbBuffer, unsigned __int64, unsigned __int8 *)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14003d41c`
- `0x140046f6c`
- `0x140048110`
- `0x140051840`
- `0x1400522cc`
- `0x1400538c8`

## callees

- `0x14002bdcc`
- `0x1400520fc`

## import_xrefs

- `bcrypt!BCryptGenRandom` at `0x140052109`
- `bcrypt!BCryptGenRandom` at `0x140052109`

## string_xrefs

- `0x140052118`: `onecore\ds\security\ngc\ctnrsvc\iso\container\lib\softwarekey.cpp`

## pseudocode

```c

```
