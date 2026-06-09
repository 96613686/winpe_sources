# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x140003c44`
- end: `0x140003c72`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140003ae8`
- `0x140003b18`

## callees

- `0x140003c44`
- `0x1400061ec`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140003c6b`

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
0x140003c44  push    rbx
0x140003c46  sub     rsp, 20h
0x140003c4a  mov     rbx, rcx
0x140003c4d  mov     rcx, [rcx+40h]; this
0x140003c51  mov     qword ptr [rbx+40h], 0
0x140003c59  test    rcx, rcx
0x140003c5c  jz      short loc_140003C63
0x140003c5e  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x140003c63  mov     rcx, rbx
0x140003c66  add     rsp, 20h
0x140003c6a  pop     rbx
0x140003c6b  jmp     cs:__imp_DeleteCriticalSection
```
