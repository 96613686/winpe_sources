# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x140006990`
- end: `0x1400069be`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140006858`
- `0x140006888`

## callees

- `0x1400041ac`
- `0x140006990`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400069b7`

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
0x140006990  push    rbx
0x140006992  sub     rsp, 20h
0x140006996  mov     rbx, rcx
0x140006999  mov     rcx, [rcx+40h]; this
0x14000699d  mov     qword ptr [rbx+40h], 0
0x1400069a5  test    rcx, rcx
0x1400069a8  jz      short loc_1400069AF
0x1400069aa  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1400069af  mov     rcx, rbx
0x1400069b2  add     rsp, 20h
0x1400069b6  pop     rbx
0x1400069b7  jmp     cs:__imp_DeleteCriticalSection
```
