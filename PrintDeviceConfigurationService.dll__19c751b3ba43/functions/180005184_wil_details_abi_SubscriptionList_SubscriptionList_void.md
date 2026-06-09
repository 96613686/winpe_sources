# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180005184`
- end: `0x1800051b2`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180005020`
- `0x180005050`

## callees

- `0x180005184`
- `0x180005dbc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800051ab`

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
0x180005184  push    rbx
0x180005186  sub     rsp, 20h
0x18000518a  mov     rbx, rcx
0x18000518d  mov     rcx, [rcx+40h]; this
0x180005191  mov     qword ptr [rbx+40h], 0
0x180005199  test    rcx, rcx
0x18000519c  jz      short loc_1800051A3
0x18000519e  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1800051a3  mov     rcx, rbx
0x1800051a6  add     rsp, 20h
0x1800051aa  pop     rbx
0x1800051ab  jmp     cs:__imp_DeleteCriticalSection
```
