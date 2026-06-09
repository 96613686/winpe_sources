# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x1800761ac`
- end: `0x1800761da`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800760b0`
- `0x1800760e0`

## callees

- `0x1800761ac`
- `0x180076e5c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800761d3`

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
0x1800761ac  push    rbx
0x1800761ae  sub     rsp, 20h
0x1800761b2  mov     rbx, rcx
0x1800761b5  mov     rcx, [rcx+40h]; this
0x1800761b9  mov     qword ptr [rbx+40h], 0
0x1800761c1  test    rcx, rcx
0x1800761c4  jz      short loc_1800761CB
0x1800761c6  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1800761cb  mov     rcx, rbx
0x1800761ce  add     rsp, 20h
0x1800761d2  pop     rbx
0x1800761d3  jmp     cs:__imp_DeleteCriticalSection
```
