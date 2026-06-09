# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180008adc`
- end: `0x180008b0a`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180008978`
- `0x1800089a8`

## callees

- `0x180008adc`
- `0x18000af8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008b03`

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
0x180008adc  push    rbx
0x180008ade  sub     rsp, 20h
0x180008ae2  mov     rbx, rcx
0x180008ae5  mov     rcx, [rcx+40h]; this
0x180008ae9  mov     qword ptr [rbx+40h], 0
0x180008af1  test    rcx, rcx
0x180008af4  jz      short loc_180008AFB
0x180008af6  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180008afb  mov     rcx, rbx
0x180008afe  add     rsp, 20h
0x180008b02  pop     rbx
0x180008b03  jmp     cs:__imp_DeleteCriticalSection
```
