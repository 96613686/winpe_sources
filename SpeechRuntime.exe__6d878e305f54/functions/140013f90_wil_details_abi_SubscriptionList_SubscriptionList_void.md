# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x140013f90`
- end: `0x140013fbe`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140013e78`
- `0x140013ea8`

## callees

- `0x14000b36c`
- `0x140013f90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140013fb7`

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
0x140013f90  push    rbx
0x140013f92  sub     rsp, 20h
0x140013f96  mov     rbx, rcx
0x140013f99  mov     rcx, [rcx+40h]; this
0x140013f9d  mov     qword ptr [rbx+40h], 0
0x140013fa5  test    rcx, rcx
0x140013fa8  jz      short loc_140013FAF
0x140013faa  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x140013faf  mov     rcx, rbx
0x140013fb2  add     rsp, 20h
0x140013fb6  pop     rbx
0x140013fb7  jmp     cs:__imp_DeleteCriticalSection
```
