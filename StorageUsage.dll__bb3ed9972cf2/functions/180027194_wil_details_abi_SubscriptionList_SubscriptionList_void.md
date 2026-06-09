# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180027194`
- end: `0x1800271c2`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180027094`
- `0x1800270c4`

## callees

- `0x18001165c`
- `0x180027194`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800271bb`

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
0x180027194  push    rbx
0x180027196  sub     rsp, 20h
0x18002719a  mov     rbx, rcx
0x18002719d  mov     rcx, [rcx+40h]; this
0x1800271a1  mov     qword ptr [rbx+40h], 0
0x1800271a9  test    rcx, rcx
0x1800271ac  jz      short loc_1800271B3
0x1800271ae  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1800271b3  mov     rcx, rbx
0x1800271b6  add     rsp, 20h
0x1800271ba  pop     rbx
0x1800271bb  jmp     cs:__imp_DeleteCriticalSection
```
