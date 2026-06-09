# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x18000818c`
- end: `0x1800081ba`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180008090`
- `0x1800080c0`

## callees

- `0x180002744`
- `0x18000818c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800081b3`

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
0x18000818c  push    rbx
0x18000818e  sub     rsp, 20h
0x180008192  mov     rbx, rcx
0x180008195  mov     rcx, [rcx+40h]; void *
0x180008199  mov     qword ptr [rbx+40h], 0
0x1800081a1  test    rcx, rcx
0x1800081a4  jz      short loc_1800081AB
0x1800081a6  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x1800081ab  mov     rcx, rbx
0x1800081ae  add     rsp, 20h
0x1800081b2  pop     rbx
0x1800081b3  jmp     cs:__imp_DeleteCriticalSection
```
