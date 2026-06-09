# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180006450`
- end: `0x18000647e`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180006370`
- `0x18000ae28`

## callees

- `0x180006450`
- `0x180006484`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006477`

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
0x180006450  push    rbx
0x180006452  sub     rsp, 20h
0x180006456  mov     rbx, rcx
0x180006459  mov     rcx, [rcx+40h]; this
0x18000645d  mov     qword ptr [rbx+40h], 0
0x180006465  test    rcx, rcx
0x180006468  jz      short loc_18000646F
0x18000646a  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000646f  mov     rcx, rbx
0x180006472  add     rsp, 20h
0x180006476  pop     rbx
0x180006477  jmp     cs:__imp_DeleteCriticalSection
```
