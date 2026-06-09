# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x18001e624`
- end: `0x18001e652`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800192e4`
- `0x18001ff94`

## callees

- `0x18001e624`
- `0x1800231cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001e64b`

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
0x18001e624  push    rbx
0x18001e626  sub     rsp, 20h
0x18001e62a  mov     rbx, rcx
0x18001e62d  mov     rcx, [rcx+40h]; this
0x18001e631  mov     qword ptr [rbx+40h], 0
0x18001e639  test    rcx, rcx
0x18001e63c  jz      short loc_18001E643
0x18001e63e  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18001e643  mov     rcx, rbx
0x18001e646  add     rsp, 20h
0x18001e64a  pop     rbx
0x18001e64b  jmp     cs:__imp_DeleteCriticalSection
```
