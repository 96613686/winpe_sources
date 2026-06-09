# ClientAuth::InternalRemoveKeyRefCount(std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x140041500`
- end: `0x1400416ba`
- name: `?InternalRemoveKeyRefCount@ClientAuth@@AEAAJAEBV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `442`
- prototype: `__int64 __fastcall(PSRWLOCK SRWLock)`
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x140023e00`

## callees

- `0x140009fa0`
- `0x14000b3a0`
- `0x14000cbe4`
- `0x14000e034`
- `0x14000f6a0`
- `0x14001a62c`
- `0x14001a91c`
- `0x14001ad8c`
- `0x14001b5fc`
- `0x14001ca34`
- `0x140040460`
- `0x140040b48`
- `0x140041500`
- `0x140041dc4`
- `0x140042190`
- `0x1400435fc`
- `0x1400436b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14004155f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14004155f`

## string_xrefs

- `0x1400415c3`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\clientauth.cpp`
- `0x140041534`: `ClientAuthRemoveKeyRefCount`

## pseudocode

```c

```
