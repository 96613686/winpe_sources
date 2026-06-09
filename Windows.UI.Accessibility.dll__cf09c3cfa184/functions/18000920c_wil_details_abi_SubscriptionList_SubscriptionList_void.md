# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x18000920c`
- end: `0x18000923a`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800090d8`
- `0x180009108`

## callees

- `0x18000920c`
- `0x180009efc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009233`

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
0x18000920c  push    rbx
0x18000920e  sub     rsp, 20h
0x180009212  mov     rbx, rcx
0x180009215  mov     rcx, [rcx+40h]; this
0x180009219  mov     qword ptr [rbx+40h], 0
0x180009221  test    rcx, rcx
0x180009224  jz      short loc_18000922B
0x180009226  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000922b  mov     rcx, rbx
0x18000922e  add     rsp, 20h
0x180009232  pop     rbx
0x180009233  jmp     cs:__imp_DeleteCriticalSection
```
