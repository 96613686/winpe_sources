# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x18000a580`
- end: `0x18000a5ae`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a484`
- `0x18000a4b4`

## callees

- `0x180005d4c`
- `0x18000a580`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a5a7`

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
0x18000a580  push    rbx
0x18000a582  sub     rsp, 20h
0x18000a586  mov     rbx, rcx
0x18000a589  mov     rcx, [rcx+40h]; this
0x18000a58d  mov     qword ptr [rbx+40h], 0
0x18000a595  test    rcx, rcx
0x18000a598  jz      short loc_18000A59F
0x18000a59a  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000a59f  mov     rcx, rbx
0x18000a5a2  add     rsp, 20h
0x18000a5a6  pop     rbx
0x18000a5a7  jmp     cs:__imp_DeleteCriticalSection
```
