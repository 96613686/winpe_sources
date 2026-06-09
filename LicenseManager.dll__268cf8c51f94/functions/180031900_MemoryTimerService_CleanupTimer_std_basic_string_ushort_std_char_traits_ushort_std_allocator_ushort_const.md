# MemoryTimerService::CleanupTimer(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180031900`
- end: `0x180031a11`
- name: `?CleanupTimer@MemoryTimerService@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x180031790`

## callees

- `0x180013b50`
- `0x180017cbc`
- `0x180031900`
- `0x180031a18`
- `0x180031a70`
- `0x180054a54`
- `0x180054a94`
- `0x180054b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031920`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031920`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800319bd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800319bd`

## string_xrefs

- `0x18003198b`: `Removed timer for %s`
- `0x180031997`: `MemoryTimerService::CleanupTimer`

## pseudocode

```c

```
