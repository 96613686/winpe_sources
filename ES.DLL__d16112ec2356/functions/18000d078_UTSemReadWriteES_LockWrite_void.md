# UTSemReadWriteES::LockWrite(void)

- ea: `0x18000d078`
- end: `0x18000d156`
- name: `?LockWrite@UTSemReadWriteES@@QEAAXXZ`
- size: `222`
- prototype: `void __fastcall(UTSemReadWriteES *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000c940`
- `0x18000cab0`
- `0x18000cd8c`
- `0x18000cf88`
- `0x180040210`

## callees

- `0x18000d078`
- `0x180012654`
- `0x180028c88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000d10e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000d10e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000d0df`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000d0df`

## string_xrefs

- `0x18000d125`: `com\complus\src\events\shared\utsem.cpp`
- `0x18000d145`: `com\complus\src\events\shared\utsem.cpp`
- `0x18000d139`: `(m_dwFlag & WRITERS_MASK) == WRITERS_INCR`
- `0x18000d119`: `(m_dwFlag & READERS_MASK) == 0`

## pseudocode

```c

```
