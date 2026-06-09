# NgcIsoContainer::InternalSetClientAttestation(_GUID,ushort const *,uchar const *,ulong)

- ea: `0x180025a20`
- end: `0x180025b01`
- name: `?InternalSetClientAttestation@NgcIsoContainer@@AEAAJU_GUID@@PEBGPEBEK@Z`
- size: `225`
- prototype: `__int64 __usercall@<rax>(NgcIsoContainer *__hidden this@<rcx>, struct _GUID *Buf1@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int8 *@<r9>, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800084a4`
- `0x18000a188`
- `0x18000d62c`
- `0x180023a48`
- `0x180025a20`
- `0x1800693ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180025a78`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180025a78`

## string_xrefs

- `0x180025a5b`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x180025ad4`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`

## pseudocode

```c

```
