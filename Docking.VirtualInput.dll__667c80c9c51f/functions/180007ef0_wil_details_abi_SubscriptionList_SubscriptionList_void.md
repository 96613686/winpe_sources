# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180007ef0`
- end: `0x180007f1e`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180007df4`
- `0x180007e24`

## callees

- `0x18000544c`
- `0x180007ef0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007f17`

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
0x180007ef0  push    rbx
0x180007ef2  sub     rsp, 20h
0x180007ef6  mov     rbx, rcx
0x180007ef9  mov     rcx, [rcx+40h]; this
0x180007efd  mov     qword ptr [rbx+40h], 0
0x180007f05  test    rcx, rcx
0x180007f08  jz      short loc_180007F0F
0x180007f0a  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180007f0f  mov     rcx, rbx
0x180007f12  add     rsp, 20h
0x180007f16  pop     rbx
0x180007f17  jmp     cs:__imp_DeleteCriticalSection
```
