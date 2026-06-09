# CDlpTask::EnqueueAction(IDlpAction *,ulong,ushort const *)

- ea: `0x140034d90`
- end: `0x1400355fd`
- name: `?EnqueueAction@CDlpTask@@UEAAJPEAVIDlpAction@@KPEBG@Z`
- size: `2157`
- prototype: `__int64 __fastcall(CDlpTask *__hidden this, struct IDlpAction *, unsigned int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `15`
- tags: `service_task`

## callees

- `0x140005b2c`
- `0x1400076c8`
- `0x140008434`
- `0x1400111f0`
- `0x1400135b8`
- `0x140029b38`
- `0x140029c30`
- `0x14002bc70`
- `0x14002bd40`
- `0x14002c07c`
- `0x14002ca54`
- `0x14002db30`
- `0x140034ab4`
- `0x140034d90`
- `0x140082010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1400355ae`
- `KERNEL32!HeapFree` at `0x1400355ae`
- `KERNEL32!HeapAlloc` at `0x1400351c2`
- `KERNEL32!HeapAlloc` at `0x1400351c2`
- `KERNEL32!GetProcessHeap` at `0x1400351ad`
- `KERNEL32!GetProcessHeap` at `0x14003559a`
- `KERNEL32!GetProcessHeap` at `0x1400351ad`
- `KERNEL32!GetProcessHeap` at `0x14003559a`
- `KERNEL32!LeaveCriticalSection` at `0x1400355cc`
- `KERNEL32!LeaveCriticalSection` at `0x1400355cc`
- `KERNEL32!EnterCriticalSection` at `0x140034dcf`
- `KERNEL32!EnterCriticalSection` at `0x140034dcf`

## string_xrefs

- `0x140034e70`: `CDlpTask::EnqueueAction`
- `0x14003550f`: `CDlpTask::EnqueueAction`

## pseudocode

```c

```
