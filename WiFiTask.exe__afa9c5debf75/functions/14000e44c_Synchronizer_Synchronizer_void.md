# Synchronizer::~Synchronizer(void)

- ea: `0x14000e44c`
- end: `0x14000e46d`
- name: `??1Synchronizer@@AEAA@XZ`
- size: `33`
- prototype: `void __fastcall(Synchronizer *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000e3d8`
- `0x14000e4cc`

## callees

- `0x14000e30c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000e459`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000e459`

## pseudocode

```c
void __fastcall Synchronizer::~Synchronizer(Synchronizer *this)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  std::deque<Synchronizer::QueueRecord>::~deque<Synchronizer::QueueRecord>((char *)this + 56);
}

```

## disassembly

```asm
0x14000e44c  push    rbx
0x14000e44e  sub     rsp, 20h
0x14000e452  mov     rbx, rcx
0x14000e455  add     rcx, 8; lpCriticalSection
0x14000e459  call    cs:__imp_DeleteCriticalSection
0x14000e45f  lea     rcx, [rbx+38h]
0x14000e463  add     rsp, 20h
0x14000e467  pop     rbx
0x14000e468  jmp     ??1?$deque@UQueueRecord@Synchronizer@@V?$allocator@UQueueRecord@Synchronizer@@@std@@@std@@QEAA@XZ; std::deque<Synchronizer::QueueRecord>::~deque<Synchronizer::QueueRecord>(void)
```
