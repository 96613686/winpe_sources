# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x18000406c`
- end: `0x18000409a`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003f08`
- `0x180003f38`

## callees

- `0x18000406c`
- `0x180004cbc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004093`

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
0x18000406c  push    rbx
0x18000406e  sub     rsp, 20h
0x180004072  mov     rbx, rcx
0x180004075  mov     rcx, [rcx+40h]; this
0x180004079  mov     qword ptr [rbx+40h], 0
0x180004081  test    rcx, rcx
0x180004084  jz      short loc_18000408B
0x180004086  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000408b  mov     rcx, rbx
0x18000408e  add     rsp, 20h
0x180004092  pop     rbx
0x180004093  jmp     cs:__imp_DeleteCriticalSection
```
