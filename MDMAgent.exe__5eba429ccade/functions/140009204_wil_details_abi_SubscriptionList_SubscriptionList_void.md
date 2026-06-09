# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x140009204`
- end: `0x140009232`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140009130`
- `0x140009160`

## callees

- `0x1400051cc`
- `0x140009204`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000922b`

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
0x140009204  push    rbx
0x140009206  sub     rsp, 20h
0x14000920a  mov     rbx, rcx
0x14000920d  mov     rcx, [rcx+40h]; this
0x140009211  mov     qword ptr [rbx+40h], 0
0x140009219  test    rcx, rcx
0x14000921c  jz      short loc_140009223
0x14000921e  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x140009223  mov     rcx, rbx
0x140009226  add     rsp, 20h
0x14000922a  pop     rbx
0x14000922b  jmp     cs:__imp_DeleteCriticalSection
```
