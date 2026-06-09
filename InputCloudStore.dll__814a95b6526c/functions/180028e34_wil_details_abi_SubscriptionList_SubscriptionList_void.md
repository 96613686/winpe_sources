# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180028e34`
- end: `0x180028e62`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180028d38`
- `0x180028d68`

## callees

- `0x1800054fc`
- `0x180028e34`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180028e5b`

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
0x180028e34  push    rbx
0x180028e36  sub     rsp, 20h
0x180028e3a  mov     rbx, rcx
0x180028e3d  mov     rcx, [rcx+40h]; this
0x180028e41  mov     qword ptr [rbx+40h], 0
0x180028e49  test    rcx, rcx
0x180028e4c  jz      short loc_180028E53
0x180028e4e  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180028e53  mov     rcx, rbx
0x180028e56  add     rsp, 20h
0x180028e5a  pop     rbx
0x180028e5b  jmp     cs:__imp_DeleteCriticalSection
```
