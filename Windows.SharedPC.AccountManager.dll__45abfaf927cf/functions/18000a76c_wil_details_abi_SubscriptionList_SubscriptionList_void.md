# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x18000a76c`
- end: `0x18000a79a`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a670`
- `0x18000a6a0`

## callees

- `0x180007a54`
- `0x18000a76c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a793`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
0x18000a76c  push    rbx
0x18000a76e  sub     rsp, 20h
0x18000a772  mov     rbx, rcx
0x18000a775  mov     rcx, [rcx+40h]; this
0x18000a779  mov     qword ptr [rbx+40h], 0
0x18000a781  test    rcx, rcx
0x18000a784  jz      short loc_18000A78B
0x18000a786  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000a78b  mov     rcx, rbx
0x18000a78e  add     rsp, 20h
0x18000a792  pop     rbx
0x18000a793  jmp     cs:__imp_DeleteCriticalSection
```
