# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x140009504`
- end: `0x140009532`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140009408`
- `0x140009438`

## callees

- `0x14000438c`
- `0x140009504`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14000952b`

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
0x140009504  push    rbx
0x140009506  sub     rsp, 20h
0x14000950a  mov     rbx, rcx
0x14000950d  mov     rcx, [rcx+40h]; this
0x140009511  mov     qword ptr [rbx+40h], 0
0x140009519  test    rcx, rcx
0x14000951c  jz      short loc_140009523
0x14000951e  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x140009523  mov     rcx, rbx
0x140009526  add     rsp, 20h
0x14000952a  pop     rbx
0x14000952b  jmp     cs:__imp_DeleteCriticalSection
```
