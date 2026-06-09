# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180027e64`
- end: `0x180027e92`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e634`
- `0x180028a18`

## callees

- `0x18000e214`
- `0x180027e64`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180027e8b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180027e64  push    rbx
0x180027e66  sub     rsp, 20h
0x180027e6a  mov     rbx, rcx
0x180027e6d  mov     rcx, [rcx+40h]; this
0x180027e71  mov     qword ptr [rbx+40h], 0
0x180027e79  test    rcx, rcx
0x180027e7c  jz      short loc_180027E83
0x180027e7e  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180027e83  mov     rcx, rbx
0x180027e86  add     rsp, 20h
0x180027e8a  pop     rbx
0x180027e8b  jmp     cs:__imp_DeleteCriticalSection
```
