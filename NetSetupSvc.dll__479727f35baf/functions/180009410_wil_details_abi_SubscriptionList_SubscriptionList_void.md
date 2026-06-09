# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180009410`
- end: `0x18000943e`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800090d4`
- `0x180009104`

## callees

- `0x1800046d0`
- `0x180009410`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009437`

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
0x180009410  push    rbx
0x180009412  sub     rsp, 20h
0x180009416  mov     rbx, rcx
0x180009419  mov     rcx, [rcx+40h]; this
0x18000941d  mov     qword ptr [rbx+40h], 0
0x180009425  test    rcx, rcx
0x180009428  jz      short loc_18000942F
0x18000942a  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000942f  mov     rcx, rbx
0x180009432  add     rsp, 20h
0x180009436  pop     rbx
0x180009437  jmp     cs:__imp_DeleteCriticalSection
```
