# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x1400096bc`
- end: `0x1400096ea`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400095c0`
- `0x1400095f0`

## callees

- `0x1400096bc`
- `0x14000c65c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1400096e3`

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
0x1400096bc  push    rbx
0x1400096be  sub     rsp, 20h
0x1400096c2  mov     rbx, rcx
0x1400096c5  mov     rcx, [rcx+40h]; this
0x1400096c9  mov     qword ptr [rbx+40h], 0
0x1400096d1  test    rcx, rcx
0x1400096d4  jz      short loc_1400096DB
0x1400096d6  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1400096db  mov     rcx, rbx
0x1400096de  add     rsp, 20h
0x1400096e2  pop     rbx
0x1400096e3  jmp     cs:__imp_DeleteCriticalSection
```
