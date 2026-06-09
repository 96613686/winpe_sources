# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x18000a2cc`
- end: `0x18000a2fa`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a07c`
- `0x18000a0ac`

## callees

- `0x18000a2cc`
- `0x18000b52c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a2f3`

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
0x18000a2cc  push    rbx
0x18000a2ce  sub     rsp, 20h
0x18000a2d2  mov     rbx, rcx
0x18000a2d5  mov     rcx, [rcx+40h]; this
0x18000a2d9  mov     qword ptr [rbx+40h], 0
0x18000a2e1  test    rcx, rcx
0x18000a2e4  jz      short loc_18000A2EB
0x18000a2e6  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000a2eb  mov     rcx, rbx
0x18000a2ee  add     rsp, 20h
0x18000a2f2  pop     rbx
0x18000a2f3  jmp     cs:__imp_DeleteCriticalSection
```
