# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x1800049c8`
- end: `0x1800049fb`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `51`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004864`
- `0x180004894`

## callees

- `0x1800049c8`
- `0x180005b54`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800049ef`

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
0x1800049c8  push    rbx
0x1800049ca  sub     rsp, 20h
0x1800049ce  mov     rbx, rcx
0x1800049d1  mov     rcx, [rcx+40h]; this
0x1800049d5  mov     qword ptr [rbx+40h], 0
0x1800049dd  test    rcx, rcx
0x1800049e0  jz      short loc_1800049E7
0x1800049e2  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1800049e7  mov     rcx, rbx
0x1800049ea  add     rsp, 20h
0x1800049ee  pop     rbx
0x1800049ef  jmp     cs:__imp_DeleteCriticalSection
```
