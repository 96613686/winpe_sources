# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180011b18`
- end: `0x180011b46`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800117c4`
- `0x1800117f4`

## callees

- `0x180006cbc`
- `0x180011b18`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011b3f`

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
0x180011b18  push    rbx
0x180011b1a  sub     rsp, 20h
0x180011b1e  mov     rbx, rcx
0x180011b21  mov     rcx, [rcx+40h]; this
0x180011b25  mov     qword ptr [rbx+40h], 0
0x180011b2d  test    rcx, rcx
0x180011b30  jz      short loc_180011B37
0x180011b32  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180011b37  mov     rcx, rbx
0x180011b3a  add     rsp, 20h
0x180011b3e  pop     rbx
0x180011b3f  jmp     cs:__imp_DeleteCriticalSection
```
