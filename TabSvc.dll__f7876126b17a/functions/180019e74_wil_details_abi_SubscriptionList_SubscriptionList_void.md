# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180019e74`
- end: `0x180019ea2`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180013e6c`
- `0x18001f25c`

## callees

- `0x180018e70`
- `0x180019e74`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180019e9b`

## pseudocode

```c
void __fastcall wil::details_abi::SubscriptionList::~SubscriptionList(struct _RTL_CRITICAL_SECTION *this)
{
  HANDLE LockSemaphore; // rcx

  LockSemaphore = this[1].LockSemaphore;
  this[1].LockSemaphore = 0;
  if ( LockSemaphore )
    MemoryFree(LockSemaphore);
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x180019e74  push    rbx
0x180019e76  sub     rsp, 20h
0x180019e7a  mov     rbx, rcx
0x180019e7d  mov     rcx, [rcx+40h]; void *
0x180019e81  mov     qword ptr [rbx+40h], 0
0x180019e89  test    rcx, rcx
0x180019e8c  jz      short loc_180019E93
0x180019e8e  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x180019e93  mov     rcx, rbx
0x180019e96  add     rsp, 20h
0x180019e9a  pop     rbx
0x180019e9b  jmp     cs:__imp_DeleteCriticalSection
```
