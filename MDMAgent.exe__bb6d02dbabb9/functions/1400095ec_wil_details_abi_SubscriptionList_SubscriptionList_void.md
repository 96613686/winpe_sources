# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x1400095ec`
- end: `0x14000961f`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `51`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140009518`
- `0x140009548`

## callees

- `0x140005344`
- `0x1400095ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140009613`

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
0x1400095ec  push    rbx
0x1400095ee  sub     rsp, 20h
0x1400095f2  mov     rbx, rcx
0x1400095f5  mov     rcx, [rcx+40h]; this
0x1400095f9  mov     qword ptr [rbx+40h], 0
0x140009601  test    rcx, rcx
0x140009604  jz      short loc_14000960B
0x140009606  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x14000960b  mov     rcx, rbx
0x14000960e  add     rsp, 20h
0x140009612  pop     rbx
0x140009613  jmp     cs:__imp_DeleteCriticalSection
```
