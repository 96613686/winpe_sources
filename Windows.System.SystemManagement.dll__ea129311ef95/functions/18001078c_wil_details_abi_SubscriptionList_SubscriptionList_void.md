# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x18001078c`
- end: `0x1800107ba`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180010680`
- `0x1800106b0`

## callees

- `0x18000644c`
- `0x18001078c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800107b3`

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
0x18001078c  push    rbx
0x18001078e  sub     rsp, 20h
0x180010792  mov     rbx, rcx
0x180010795  mov     rcx, [rcx+40h]; this
0x180010799  mov     qword ptr [rbx+40h], 0
0x1800107a1  test    rcx, rcx
0x1800107a4  jz      short loc_1800107AB
0x1800107a6  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1800107ab  mov     rcx, rbx
0x1800107ae  add     rsp, 20h
0x1800107b2  pop     rbx
0x1800107b3  jmp     cs:__imp_DeleteCriticalSection
```
