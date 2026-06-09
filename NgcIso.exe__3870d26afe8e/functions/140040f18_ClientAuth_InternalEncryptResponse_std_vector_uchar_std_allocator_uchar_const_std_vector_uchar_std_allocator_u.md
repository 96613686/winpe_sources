# ClientAuth::InternalEncryptResponse(std::vector<uchar,std::allocator<uchar>> const &,std::vector<uchar,std::allocator<uchar>> const &,unsigned __int64,std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x140040f18`
- end: `0x140041076`
- name: `?InternalEncryptResponse@ClientAuth@@AEAAJAEBV?$vector@EV?$allocator@E@std@@@std@@0_KAEAV23@@Z`
- size: `350`
- prototype: `__int64 __usercall@<rax>(PSRWLOCK SRWLock@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x140022790`

## callees

- `0x140009fa0`
- `0x14000b3a0`
- `0x14000cbe4`
- `0x14000e034`
- `0x14000f6a0`
- `0x140016eb8`
- `0x140039058`
- `0x14003fdc4`
- `0x1400403b0`
- `0x140040800`
- `0x140040b48`
- `0x140040f18`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140040f62`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140040f62`

## string_xrefs

- `0x140040fc7`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\clientauth.cpp`
- `0x14004100d`: `onecore\ds\security\enclave\inc\Vtl1MutualAuth.h`

## pseudocode

```c

```
