# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180011864`
- end: `0x180011892`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180011768`
- `0x180011798`

## callees

- `0x18000c040`
- `0x180011864`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001188b`

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
0x180011864  push    rbx
0x180011866  sub     rsp, 20h
0x18001186a  mov     rbx, rcx
0x18001186d  mov     rcx, [rcx+40h]; this
0x180011871  mov     qword ptr [rbx+40h], 0
0x180011879  test    rcx, rcx
0x18001187c  jz      short loc_180011883
0x18001187e  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180011883  mov     rcx, rbx
0x180011886  add     rsp, 20h
0x18001188a  pop     rbx
0x18001188b  jmp     cs:__imp_DeleteCriticalSection
```
