# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x18001c188`
- end: `0x18001c1b6`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001c0b4`
- `0x18001c0e4`

## callees

- `0x1800147cc`
- `0x18001c188`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001c1af`

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
0x18001c188  push    rbx
0x18001c18a  sub     rsp, 20h
0x18001c18e  mov     rbx, rcx
0x18001c191  mov     rcx, [rcx+40h]; this
0x18001c195  mov     qword ptr [rbx+40h], 0
0x18001c19d  test    rcx, rcx
0x18001c1a0  jz      short loc_18001C1A7
0x18001c1a2  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18001c1a7  mov     rcx, rbx
0x18001c1aa  add     rsp, 20h
0x18001c1ae  pop     rbx
0x18001c1af  jmp     cs:__imp_DeleteCriticalSection
```
