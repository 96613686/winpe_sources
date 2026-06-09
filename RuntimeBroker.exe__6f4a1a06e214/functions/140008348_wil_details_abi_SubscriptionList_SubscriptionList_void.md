# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x140008348`
- end: `0x140008376`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140007894`
- `0x14000ad30`

## callees

- `0x1400079c4`
- `0x140008348`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000836f`

## pseudocode

```c
void __fastcall wil::details_abi::SubscriptionList::~SubscriptionList(struct _RTL_CRITICAL_SECTION *this, void *a2)
{
  wil::details *LockSemaphore; // rcx

  LockSemaphore = (wil::details *)this[1].LockSemaphore;
  this[1].LockSemaphore = 0;
  if ( LockSemaphore )
    wil::details::FreeProcessHeap(LockSemaphore, a2);
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x140008348  push    rbx
0x14000834a  sub     rsp, 20h
0x14000834e  mov     rbx, rcx
0x140008351  mov     rcx, [rcx+40h]; this
0x140008355  mov     qword ptr [rbx+40h], 0
0x14000835d  test    rcx, rcx
0x140008360  jz      short loc_140008367
0x140008362  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x140008367  mov     rcx, rbx
0x14000836a  add     rsp, 20h
0x14000836e  pop     rbx
0x14000836f  jmp     cs:__imp_DeleteCriticalSection
```
