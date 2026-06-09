# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180008c70`
- end: `0x180008c9e`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180008b0c`
- `0x180008b3c`

## callees

- `0x180008c70`
- `0x1800099ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008c97`

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
0x180008c70  push    rbx
0x180008c72  sub     rsp, 20h
0x180008c76  mov     rbx, rcx
0x180008c79  mov     rcx, [rcx+40h]; this
0x180008c7d  mov     qword ptr [rbx+40h], 0
0x180008c85  test    rcx, rcx
0x180008c88  jz      short loc_180008C8F
0x180008c8a  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180008c8f  mov     rcx, rbx
0x180008c92  add     rsp, 20h
0x180008c96  pop     rbx
0x180008c97  jmp     cs:__imp_DeleteCriticalSection
```
