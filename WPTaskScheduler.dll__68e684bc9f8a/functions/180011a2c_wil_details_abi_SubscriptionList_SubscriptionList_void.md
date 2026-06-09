# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180011a2c`
- end: `0x180011a5a`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800118d0`
- `0x180011900`

## callees

- `0x180011a2c`
- `0x18001246c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011a53`

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
0x180011a2c  push    rbx
0x180011a2e  sub     rsp, 20h
0x180011a32  mov     rbx, rcx
0x180011a35  mov     rcx, [rcx+40h]; this
0x180011a39  mov     qword ptr [rbx+40h], 0
0x180011a41  test    rcx, rcx
0x180011a44  jz      short loc_180011A4B
0x180011a46  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180011a4b  mov     rcx, rbx
0x180011a4e  add     rsp, 20h
0x180011a52  pop     rbx
0x180011a53  jmp     cs:__imp_DeleteCriticalSection
```
