# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x14000a260`
- end: `0x14000a28e`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000a18c`
- `0x14000a1bc`

## callees

- `0x1400040bc`
- `0x14000a260`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000a287`

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
0x14000a260  push    rbx
0x14000a262  sub     rsp, 20h
0x14000a266  mov     rbx, rcx
0x14000a269  mov     rcx, [rcx+40h]; this
0x14000a26d  mov     qword ptr [rbx+40h], 0
0x14000a275  test    rcx, rcx
0x14000a278  jz      short loc_14000A27F
0x14000a27a  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x14000a27f  mov     rcx, rbx
0x14000a282  add     rsp, 20h
0x14000a286  pop     rbx
0x14000a287  jmp     cs:__imp_DeleteCriticalSection
```
