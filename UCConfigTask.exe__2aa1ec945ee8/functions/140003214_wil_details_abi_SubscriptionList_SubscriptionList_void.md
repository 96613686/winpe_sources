# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x140003214`
- end: `0x140003242`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400030b0`
- `0x1400030e0`

## callees

- `0x140003214`
- `0x140003ccc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000323b`

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
0x140003214  push    rbx
0x140003216  sub     rsp, 20h
0x14000321a  mov     rbx, rcx
0x14000321d  mov     rcx, [rcx+40h]; this
0x140003221  mov     qword ptr [rbx+40h], 0
0x140003229  test    rcx, rcx
0x14000322c  jz      short loc_140003233
0x14000322e  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x140003233  mov     rcx, rbx
0x140003236  add     rsp, 20h
0x14000323a  pop     rbx
0x14000323b  jmp     cs:__imp_DeleteCriticalSection
```
