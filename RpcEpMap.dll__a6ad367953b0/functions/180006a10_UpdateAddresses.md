# UpdateAddresses

- ea: `0x180006a10`
- end: `0x180006a38`
- name: `UpdateAddresses`
- size: `40`
- prototype: `RPC_ADDRESS_CHANGE_FN`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180008df0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006a1b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006a1b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006a31`

## pseudocode

```c
void __fastcall UpdateAddresses(void *arg)
{
  EnterCriticalSection(&UuidCritSec);
  DealWithDeviceEvent();
  LeaveCriticalSection(&UuidCritSec);
}

```

## disassembly

```asm
0x180006a10  sub     rsp, 28h
0x180006a14  lea     rcx, UuidCritSec; lpCriticalSection
0x180006a1b  call    cs:__imp_EnterCriticalSection
0x180006a21  call    DealWithDeviceEvent
0x180006a26  lea     rcx, UuidCritSec
0x180006a2d  add     rsp, 28h
0x180006a31  jmp     cs:__imp_LeaveCriticalSection
```
