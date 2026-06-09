# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180008940`
- end: `0x18000896e`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800087dc`
- `0x18000880c`

## callees

- `0x180008940`
- `0x1800093fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008967`

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
0x180008940  push    rbx
0x180008942  sub     rsp, 20h
0x180008946  mov     rbx, rcx
0x180008949  mov     rcx, [rcx+40h]; this
0x18000894d  mov     qword ptr [rbx+40h], 0
0x180008955  test    rcx, rcx
0x180008958  jz      short loc_18000895F
0x18000895a  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000895f  mov     rcx, rbx
0x180008962  add     rsp, 20h
0x180008966  pop     rbx
0x180008967  jmp     cs:__imp_DeleteCriticalSection
```
