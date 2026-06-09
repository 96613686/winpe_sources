# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180008614`
- end: `0x180008642`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180008418`
- `0x180008448`

## callees

- `0x180008614`
- `0x180009f2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000863b`

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
0x180008614  push    rbx
0x180008616  sub     rsp, 20h
0x18000861a  mov     rbx, rcx
0x18000861d  mov     rcx, [rcx+40h]; this
0x180008621  mov     qword ptr [rbx+40h], 0
0x180008629  test    rcx, rcx
0x18000862c  jz      short loc_180008633
0x18000862e  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180008633  mov     rcx, rbx
0x180008636  add     rsp, 20h
0x18000863a  pop     rbx
0x18000863b  jmp     cs:__imp_DeleteCriticalSection
```
