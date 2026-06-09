# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180008930`
- end: `0x18000895e`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180008804`
- `0x180008834`

## callees

- `0x180005bbc`
- `0x180008930`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008957`

## pseudocode

```c
void __fastcall wil::details_abi::SubscriptionList::~SubscriptionList(struct _RTL_CRITICAL_SECTION *this)
{
  HANDLE LockSemaphore; // rcx

  LockSemaphore = this[1].LockSemaphore;
  this[1].LockSemaphore = 0;
  if ( LockSemaphore )
    MemoryFree(LockSemaphore);
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x180008930  push    rbx
0x180008932  sub     rsp, 20h
0x180008936  mov     rbx, rcx
0x180008939  mov     rcx, [rcx+40h]; void *
0x18000893d  mov     qword ptr [rbx+40h], 0
0x180008945  test    rcx, rcx
0x180008948  jz      short loc_18000894F
0x18000894a  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x18000894f  mov     rcx, rbx
0x180008952  add     rsp, 20h
0x180008956  pop     rbx
0x180008957  jmp     cs:__imp_DeleteCriticalSection
```
