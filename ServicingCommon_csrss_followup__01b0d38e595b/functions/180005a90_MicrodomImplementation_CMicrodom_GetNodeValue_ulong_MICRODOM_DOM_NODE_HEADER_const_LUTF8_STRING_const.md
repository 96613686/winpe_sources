# MicrodomImplementation::CMicrodom::GetNodeValue(ulong,_MICRODOM_DOM_NODE_HEADER const *,_LUTF8_STRING const * *)

- ea: `0x180005a90`
- end: `0x180005c5c`
- name: `?GetNodeValue@CMicrodom@MicrodomImplementation@@QEAAJKPEBU_MICRODOM_DOM_NODE_HEADER@@PEAPEBU_LUTF8_STRING@@@Z`
- size: `460`
- prototype: `__int64 __fastcall(MicrodomImplementation::CMicrodom *__hidden this, unsigned int, const struct _MICRODOM_DOM_NODE_HEADER *, const struct _LUTF8_STRING **)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180005300`
- `0x180006304`
- `0x180007040`

## callees

- `0x180004f20`
- `0x180005288`
- `0x180005a90`
- `0x180005c70`
- `0x180009820`
- `0x18002d2b0`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x180005c40`
- `ntdll!RtlRaiseStatus` at `0x180005c40`

## string_xrefs

- `0x180005bed`: `onecore\base\xml\udom_microdom.cpp`
- `0x180005c09`: `MicrodomImplementation::CStringpoolCache::FindString`

## pseudocode

```c

```
