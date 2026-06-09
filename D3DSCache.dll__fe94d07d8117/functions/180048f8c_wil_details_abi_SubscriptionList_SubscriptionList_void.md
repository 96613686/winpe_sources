# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180048f8c`
- end: `0x180048fba`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180048e68`
- `0x180048e98`

## callees

- `0x180048f8c`
- `0x18004a84c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180048fb3`

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
0x180048f8c  push    rbx
0x180048f8e  sub     rsp, 20h
0x180048f92  mov     rbx, rcx
0x180048f95  mov     rcx, [rcx+40h]; this
0x180048f99  mov     qword ptr [rbx+40h], 0
0x180048fa1  test    rcx, rcx
0x180048fa4  jz      short loc_180048FAB
0x180048fa6  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180048fab  mov     rcx, rbx
0x180048fae  add     rsp, 20h
0x180048fb2  pop     rbx
0x180048fb3  jmp     cs:__imp_DeleteCriticalSection
```
