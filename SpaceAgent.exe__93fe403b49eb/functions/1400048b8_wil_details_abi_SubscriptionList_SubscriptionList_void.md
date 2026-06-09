# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x1400048b8`
- end: `0x1400048e6`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140004760`
- `0x140004790`

## callees

- `0x1400048b8`
- `0x14000555c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1400048df`

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
0x1400048b8  push    rbx
0x1400048ba  sub     rsp, 20h
0x1400048be  mov     rbx, rcx
0x1400048c1  mov     rcx, [rcx+40h]; this
0x1400048c5  mov     qword ptr [rbx+40h], 0
0x1400048cd  test    rcx, rcx
0x1400048d0  jz      short loc_1400048D7
0x1400048d2  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1400048d7  mov     rcx, rbx
0x1400048da  add     rsp, 20h
0x1400048de  pop     rbx
0x1400048df  jmp     cs:__imp_DeleteCriticalSection
```
