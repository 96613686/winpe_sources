# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x18000bf74`
- end: `0x18000bfa2`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000be18`
- `0x18000be48`

## callees

- `0x18000bf74`
- `0x18000de80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000bf9b`

## pseudocode

```c
void __fastcall wil::details_abi::SubscriptionList::~SubscriptionList(struct _RTL_CRITICAL_SECTION *this)
{
  HANDLE LockSemaphore; // rcx

  LockSemaphore = this[1].LockSemaphore;
  this[1].LockSemaphore = 0;
  if ( LockSemaphore )
    CspFreeH(LockSemaphore);
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x18000bf74  push    rbx
0x18000bf76  sub     rsp, 20h
0x18000bf7a  mov     rbx, rcx
0x18000bf7d  mov     rcx, [rcx+40h]
0x18000bf81  mov     qword ptr [rbx+40h], 0
0x18000bf89  test    rcx, rcx
0x18000bf8c  jz      short loc_18000BF93
0x18000bf8e  call    CspFreeH
0x18000bf93  mov     rcx, rbx
0x18000bf96  add     rsp, 20h
0x18000bf9a  pop     rbx
0x18000bf9b  jmp     cs:__imp_DeleteCriticalSection
```
