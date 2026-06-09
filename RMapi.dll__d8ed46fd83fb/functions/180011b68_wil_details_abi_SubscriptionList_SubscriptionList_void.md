# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180011b68`
- end: `0x180011b96`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180011a28`
- `0x180011a58`

## callees

- `0x18000fb1c`
- `0x180011b68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011b8f`

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
0x180011b68  push    rbx
0x180011b6a  sub     rsp, 20h
0x180011b6e  mov     rbx, rcx
0x180011b71  mov     rcx, [rcx+40h]; this
0x180011b75  mov     qword ptr [rbx+40h], 0
0x180011b7d  test    rcx, rcx
0x180011b80  jz      short loc_180011B87
0x180011b82  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180011b87  mov     rcx, rbx
0x180011b8a  add     rsp, 20h
0x180011b8e  pop     rbx
0x180011b8f  jmp     cs:__imp_DeleteCriticalSection
```
