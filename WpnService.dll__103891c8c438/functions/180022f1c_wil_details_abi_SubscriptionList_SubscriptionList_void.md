# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180022f1c`
- end: `0x180022f4a`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180017b8c`
- `0x180028738`

## callees

- `0x180015b4c`
- `0x180022f1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180022f43`

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
0x180022f1c  push    rbx
0x180022f1e  sub     rsp, 20h
0x180022f22  mov     rbx, rcx
0x180022f25  mov     rcx, [rcx+40h]; this
0x180022f29  mov     qword ptr [rbx+40h], 0
0x180022f31  test    rcx, rcx
0x180022f34  jz      short loc_180022F3B
0x180022f36  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180022f3b  mov     rcx, rbx
0x180022f3e  add     rsp, 20h
0x180022f42  pop     rbx
0x180022f43  jmp     cs:__imp_DeleteCriticalSection
```
