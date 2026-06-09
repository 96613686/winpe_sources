# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x1800049cc`
- end: `0x1800049fa`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004868`
- `0x180004898`

## callees

- `0x1800049cc`
- `0x180005eac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800049f3`

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
0x1800049cc  push    rbx
0x1800049ce  sub     rsp, 20h
0x1800049d2  mov     rbx, rcx
0x1800049d5  mov     rcx, [rcx+40h]; this
0x1800049d9  mov     qword ptr [rbx+40h], 0
0x1800049e1  test    rcx, rcx
0x1800049e4  jz      short loc_1800049EB
0x1800049e6  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1800049eb  mov     rcx, rbx
0x1800049ee  add     rsp, 20h
0x1800049f2  pop     rbx
0x1800049f3  jmp     cs:__imp_DeleteCriticalSection
```
