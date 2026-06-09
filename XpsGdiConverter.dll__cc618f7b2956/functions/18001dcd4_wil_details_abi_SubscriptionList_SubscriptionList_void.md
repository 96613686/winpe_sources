# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x18001dcd4`
- end: `0x18001dd02`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001db8c`
- `0x18001dbbc`

## callees

- `0x18000af9c`
- `0x18001dcd4`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001dcfb`

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
0x18001dcd4  push    rbx
0x18001dcd6  sub     rsp, 20h
0x18001dcda  mov     rbx, rcx
0x18001dcdd  mov     rcx, [rcx+40h]; this
0x18001dce1  mov     qword ptr [rbx+40h], 0
0x18001dce9  test    rcx, rcx
0x18001dcec  jz      short loc_18001DCF3
0x18001dcee  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18001dcf3  mov     rcx, rbx
0x18001dcf6  add     rsp, 20h
0x18001dcfa  pop     rbx
0x18001dcfb  jmp     cs:__imp_DeleteCriticalSection
```
