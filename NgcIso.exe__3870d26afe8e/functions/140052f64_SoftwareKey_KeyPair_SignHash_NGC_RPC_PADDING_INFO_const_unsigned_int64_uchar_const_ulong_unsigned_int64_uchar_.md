# SoftwareKey::KeyPair::SignHash(_NGC_RPC_PADDING_INFO const *,unsigned __int64,uchar const *,ulong,unsigned __int64,uchar *,unsigned __int64 *)

- ea: `0x140052f64`
- end: `0x140053072`
- name: `?SignHash@KeyPair@SoftwareKey@@QEBAJPEBU_NGC_RPC_PADDING_INFO@@_KPEBEK1PEAEPEA_K@Z`
- size: `270`
- prototype: `int(SoftwareKey::KeyPair *__hidden this, const struct _NGC_RPC_PADDING_INFO *, unsigned __int64, const unsigned __int8 *, unsigned int, unsigned __int64, unsigned __int8 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000b3b8`

## callees

- `0x14000e034`
- `0x14002bdcc`
- `0x140052e88`
- `0x140052f64`

## import_xrefs

- `bcrypt!BCryptSignHash` at `0x140053040`
- `bcrypt!BCryptSignHash` at `0x140053040`

## string_xrefs

- `0x140052feb`: `onecore\ds\security\ngc\ctnrsvc\iso\container\lib\softwarekey.cpp`
- `0x140053052`: `onecore\ds\security\ngc\ctnrsvc\iso\container\lib\softwarekey.cpp`

## pseudocode

```c

```
