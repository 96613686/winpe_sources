# NgcIsoContainer::InternalDeriveKey(_GUID,unsigned __int64,ushort const *,_NCryptRpcBufferDesc *,uchar *,ulong,ulong *,ulong)

- ea: `0x180022f50`
- end: `0x180023043`
- name: `?InternalDeriveKey@NgcIsoContainer@@AEAAJU_GUID@@_KPEBGPEAU_NCryptRpcBufferDesc@@PEAEKPEAKK@Z`
- size: `243`
- prototype: `int(NgcIsoContainer *__hidden this, struct _GUID *__struct_ptr, unsigned __int64, const unsigned __int16 *, struct _NCryptRpcBufferDesc *, unsigned __int8 *, unsigned int, unsigned int *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800084a4`
- `0x18000a188`
- `0x18000d62c`
- `0x180022f50`
- `0x1800665f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180022fab`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180022fab`

## string_xrefs

- `0x180022f8e`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x180023019`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`

## pseudocode

```c

```
