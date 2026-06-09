# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180004dac`
- end: `0x180004dda`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004c48`
- `0x180004c78`

## callees

- `0x180004dac`
- `0x1800058bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004dd3`

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
0x180004dac  push    rbx
0x180004dae  sub     rsp, 20h
0x180004db2  mov     rbx, rcx
0x180004db5  mov     rcx, [rcx+40h]; this
0x180004db9  mov     qword ptr [rbx+40h], 0
0x180004dc1  test    rcx, rcx
0x180004dc4  jz      short loc_180004DCB
0x180004dc6  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180004dcb  mov     rcx, rbx
0x180004dce  add     rsp, 20h
0x180004dd2  pop     rbx
0x180004dd3  jmp     cs:__imp_DeleteCriticalSection
```
