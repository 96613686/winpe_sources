# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x18000b5c8`
- end: `0x18000b5f6`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b4d0`
- `0x18000f5cc`

## callees

- `0x18000b5c8`
- `0x18000fc4c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b5ef`

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
0x18000b5c8  push    rbx
0x18000b5ca  sub     rsp, 20h
0x18000b5ce  mov     rbx, rcx
0x18000b5d1  mov     rcx, [rcx+40h]; this
0x18000b5d5  mov     qword ptr [rbx+40h], 0
0x18000b5dd  test    rcx, rcx
0x18000b5e0  jz      short loc_18000B5E7
0x18000b5e2  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000b5e7  mov     rcx, rbx
0x18000b5ea  add     rsp, 20h
0x18000b5ee  pop     rbx
0x18000b5ef  jmp     cs:__imp_DeleteCriticalSection
```
