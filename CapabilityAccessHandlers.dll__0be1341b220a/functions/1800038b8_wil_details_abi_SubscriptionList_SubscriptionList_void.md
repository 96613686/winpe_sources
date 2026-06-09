# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x1800038b8`
- end: `0x1800038e6`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800037f8`
- `0x18000b3ec`

## callees

- `0x1800038b8`
- `0x180007a4c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800038df`

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
0x1800038b8  push    rbx
0x1800038ba  sub     rsp, 20h
0x1800038be  mov     rbx, rcx
0x1800038c1  mov     rcx, [rcx+40h]; this
0x1800038c5  mov     qword ptr [rbx+40h], 0
0x1800038cd  test    rcx, rcx
0x1800038d0  jz      short loc_1800038D7
0x1800038d2  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1800038d7  mov     rcx, rbx
0x1800038da  add     rsp, 20h
0x1800038de  pop     rbx
0x1800038df  jmp     cs:__imp_DeleteCriticalSection
```
