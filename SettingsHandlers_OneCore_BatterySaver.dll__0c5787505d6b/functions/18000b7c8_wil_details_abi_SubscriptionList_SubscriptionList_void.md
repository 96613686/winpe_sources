# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x18000b7c8`
- end: `0x18000b7f6`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b664`
- `0x18000b694`

## callees

- `0x18000b7c8`
- `0x18000c3ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b7ef`

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
0x18000b7c8  push    rbx
0x18000b7ca  sub     rsp, 20h
0x18000b7ce  mov     rbx, rcx
0x18000b7d1  mov     rcx, [rcx+40h]; this
0x18000b7d5  mov     qword ptr [rbx+40h], 0
0x18000b7dd  test    rcx, rcx
0x18000b7e0  jz      short loc_18000B7E7
0x18000b7e2  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000b7e7  mov     rcx, rbx
0x18000b7ea  add     rsp, 20h
0x18000b7ee  pop     rbx
0x18000b7ef  jmp     cs:__imp_DeleteCriticalSection
```
