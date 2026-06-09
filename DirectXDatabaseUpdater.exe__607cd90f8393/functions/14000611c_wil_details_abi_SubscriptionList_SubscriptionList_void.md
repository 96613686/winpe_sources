# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x14000611c`
- end: `0x14000614a`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140005f8c`
- `0x140005fbc`

## callees

- `0x14000611c`
- `0x14000704c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140006143`

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
0x14000611c  push    rbx
0x14000611e  sub     rsp, 20h
0x140006122  mov     rbx, rcx
0x140006125  mov     rcx, [rcx+40h]; this
0x140006129  mov     qword ptr [rbx+40h], 0
0x140006131  test    rcx, rcx
0x140006134  jz      short loc_14000613B
0x140006136  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x14000613b  mov     rcx, rbx
0x14000613e  add     rsp, 20h
0x140006142  pop     rbx
0x140006143  jmp     cs:__imp_DeleteCriticalSection
```
