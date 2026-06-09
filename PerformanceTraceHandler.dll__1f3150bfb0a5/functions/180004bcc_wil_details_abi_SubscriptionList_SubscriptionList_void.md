# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180004bcc`
- end: `0x180004bfa`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004a68`
- `0x180004a98`

## callees

- `0x180004bcc`
- `0x18000575c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004bf3`

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
0x180004bcc  push    rbx
0x180004bce  sub     rsp, 20h
0x180004bd2  mov     rbx, rcx
0x180004bd5  mov     rcx, [rcx+40h]; this
0x180004bd9  mov     qword ptr [rbx+40h], 0
0x180004be1  test    rcx, rcx
0x180004be4  jz      short loc_180004BEB
0x180004be6  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180004beb  mov     rcx, rbx
0x180004bee  add     rsp, 20h
0x180004bf2  pop     rbx
0x180004bf3  jmp     cs:__imp_DeleteCriticalSection
```
