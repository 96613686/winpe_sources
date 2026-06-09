# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180053f48`
- end: `0x180053f7b`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `51`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180053e50`
- `0x180078608`

## callees

- `0x180053f48`
- `0x18006cff0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180053f6f`

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
0x180053f48  push    rbx
0x180053f4a  sub     rsp, 20h
0x180053f4e  mov     rbx, rcx
0x180053f51  mov     rcx, [rcx+40h]; this
0x180053f55  mov     qword ptr [rbx+40h], 0
0x180053f5d  test    rcx, rcx
0x180053f60  jz      short loc_180053F67
0x180053f62  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180053f67  mov     rcx, rbx
0x180053f6a  add     rsp, 20h
0x180053f6e  pop     rbx
0x180053f6f  jmp     cs:__imp_DeleteCriticalSection
```
