# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x1800133c0`
- end: `0x1800133e3`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `35`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005590`
- `0x180015ff0`

## callees

- `0x180004cd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800133dc`

## pseudocode

```c
void __fastcall wil::details_abi::SubscriptionList::~SubscriptionList(struct _RTL_CRITICAL_SECTION *this)
{
  wistd::unique_ptr<void,wil::process_heap_deleter>::reset(&this[1].LockSemaphore, 0);
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x1800133c0  push    rbx
0x1800133c2  sub     rsp, 20h
0x1800133c6  mov     rbx, rcx
0x1800133c9  xor     edx, edx
0x1800133cb  add     rcx, 40h ; '@'
0x1800133cf  call    ?reset@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAXPEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::reset(void *)
0x1800133d4  mov     rcx, rbx
0x1800133d7  add     rsp, 20h
0x1800133db  pop     rbx
0x1800133dc  jmp     cs:__imp_DeleteCriticalSection
```
