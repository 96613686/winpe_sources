# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180036984`
- end: `0x1800369b8`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `52`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800368a8`
- `0x1800368d8`

## callees

- `0x180009888`
- `0x180036984`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800369ac`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180036984  push    rbx
0x180036986  sub     rsp, 20h
0x18003698a  mov     rbx, rcx
0x18003698d  mov     rcx, [rcx+40h]; this
0x180036991  mov     qword ptr [rbx+40h], 0
0x180036999  test    rcx, rcx
0x18003699c  jz      short loc_1800369A4
0x18003699e  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1800369a3  nop
0x1800369a4  mov     rcx, rbx
0x1800369a7  add     rsp, 20h
0x1800369ab  pop     rbx
0x1800369ac  jmp     cs:__imp_DeleteCriticalSection
```
