# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180005880`
- end: `0x1800058ae`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800056c4`
- `0x1800056f4`

## callees

- `0x180005880`
- `0x18000678c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800058a7`

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
0x180005880  push    rbx
0x180005882  sub     rsp, 20h
0x180005886  mov     rbx, rcx
0x180005889  mov     rcx, [rcx+40h]; this
0x18000588d  mov     qword ptr [rbx+40h], 0
0x180005895  test    rcx, rcx
0x180005898  jz      short loc_18000589F
0x18000589a  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000589f  mov     rcx, rbx
0x1800058a2  add     rsp, 20h
0x1800058a6  pop     rbx
0x1800058a7  jmp     cs:__imp_DeleteCriticalSection
```
