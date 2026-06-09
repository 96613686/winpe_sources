# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x18002e420`
- end: `0x18002e44e`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18002e310`
- `0x18002e340`

## callees

- `0x18000768c`
- `0x18002e420`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002e447`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
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
0x18002e420  push    rbx
0x18002e422  sub     rsp, 20h
0x18002e426  mov     rbx, rcx
0x18002e429  mov     rcx, [rcx+40h]; this
0x18002e42d  mov     qword ptr [rbx+40h], 0
0x18002e435  test    rcx, rcx
0x18002e438  jz      short loc_18002E43F
0x18002e43a  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18002e43f  mov     rcx, rbx
0x18002e442  add     rsp, 20h
0x18002e446  pop     rbx
0x18002e447  jmp     cs:__imp_DeleteCriticalSection
```
