# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x140001780`
- end: `0x1400017ae`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140001684`
- `0x140003d40`

## callees

- `0x140001780`
- `0x14000469c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400017a7`

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
0x140001780  push    rbx
0x140001782  sub     rsp, 20h
0x140001786  mov     rbx, rcx
0x140001789  mov     rcx, [rcx+40h]; this
0x14000178d  mov     qword ptr [rbx+40h], 0
0x140001795  test    rcx, rcx
0x140001798  jz      short loc_14000179F
0x14000179a  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x14000179f  mov     rcx, rbx
0x1400017a2  add     rsp, 20h
0x1400017a6  pop     rbx
0x1400017a7  jmp     cs:__imp_DeleteCriticalSection
```
