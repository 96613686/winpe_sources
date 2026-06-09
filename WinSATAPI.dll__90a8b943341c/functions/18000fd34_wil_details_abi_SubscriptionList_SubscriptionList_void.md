# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x18000fd34`
- end: `0x18000fd64`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `48`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000fc28`
- `0x180023454`

## callees

- `0x18000fd34`
- `0x180024a2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000fd58`

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
0x18000fd34  push    rbx
0x18000fd36  sub     rsp, 20h
0x18000fd3a  mov     rbx, rcx
0x18000fd3d  mov     rcx, [rcx+40h]; this
0x18000fd41  and     qword ptr [rbx+40h], 0
0x18000fd46  test    rcx, rcx
0x18000fd49  jz      short loc_18000FD50
0x18000fd4b  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000fd50  mov     rcx, rbx
0x18000fd53  add     rsp, 20h
0x18000fd57  pop     rbx
0x18000fd58  jmp     cs:__imp_DeleteCriticalSection
```
