# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180052d30`
- end: `0x180052d63`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `51`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180052bc0`
- `0x180052bf0`

## callees

- `0x180052d30`
- `0x180053b84`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180052d57`

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
0x180052d30  push    rbx
0x180052d32  sub     rsp, 20h
0x180052d36  mov     rbx, rcx
0x180052d39  mov     rcx, [rcx+40h]; this
0x180052d3d  mov     qword ptr [rbx+40h], 0
0x180052d45  test    rcx, rcx
0x180052d48  jz      short loc_180052D4F
0x180052d4a  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180052d4f  mov     rcx, rbx
0x180052d52  add     rsp, 20h
0x180052d56  pop     rbx
0x180052d57  jmp     cs:__imp_DeleteCriticalSection
```
