# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x18000d1e4`
- end: `0x18000d212`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d0e8`
- `0x180010574`

## callees

- `0x18000d1e4`
- `0x180010f9c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d20b`

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
0x18000d1e4  push    rbx
0x18000d1e6  sub     rsp, 20h
0x18000d1ea  mov     rbx, rcx
0x18000d1ed  mov     rcx, [rcx+40h]; this
0x18000d1f1  mov     qword ptr [rbx+40h], 0
0x18000d1f9  test    rcx, rcx
0x18000d1fc  jz      short loc_18000D203
0x18000d1fe  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000d203  mov     rcx, rbx
0x18000d206  add     rsp, 20h
0x18000d20a  pop     rbx
0x18000d20b  jmp     cs:__imp_DeleteCriticalSection
```
