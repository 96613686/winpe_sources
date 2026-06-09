# CAPOServiceProvider::GetApoWorkQueueId(void)

- ea: `0x1400662bc`
- end: `0x14006634a`
- name: `?GetApoWorkQueueId@CAPOServiceProvider@@AEAAKXZ`
- size: `142`
- prototype: `unsigned int __fastcall(CAPOServiceProvider *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140036c20`

## callees

- `0x1400060dc`
- `0x14003bd28`
- `0x1400662bc`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140066332`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140066332`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400662d5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400662d5`
- `RTWorkQ!RtwqAllocateWorkQueue` at `0x140066321`
- `RTWorkQ!RtwqAllocateWorkQueue` at `0x140066321`

## pseudocode

```c

```
