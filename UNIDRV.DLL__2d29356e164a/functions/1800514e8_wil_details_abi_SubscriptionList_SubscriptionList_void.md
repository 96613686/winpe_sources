# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x1800514e8`
- end: `0x180051516`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180051380`
- `0x1800513b0`

## callees

- `0x1800514e8`
- `0x18005225c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18005150f`

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
0x1800514e8  push    rbx
0x1800514ea  sub     rsp, 20h
0x1800514ee  mov     rbx, rcx
0x1800514f1  mov     rcx, [rcx+40h]; this
0x1800514f5  mov     qword ptr [rbx+40h], 0
0x1800514fd  test    rcx, rcx
0x180051500  jz      short loc_180051507
0x180051502  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180051507  mov     rcx, rbx
0x18005150a  add     rsp, 20h
0x18005150e  pop     rbx
0x18005150f  jmp     cs:__imp_DeleteCriticalSection
```
