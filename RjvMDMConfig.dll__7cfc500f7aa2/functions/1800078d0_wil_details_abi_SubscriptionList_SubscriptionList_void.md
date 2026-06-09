# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x1800078d0`
- end: `0x180007903`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `51`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800077d4`
- `0x180007804`

## callees

- `0x1800078d0`
- `0x18000a2f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800078f7`

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
0x1800078d0  push    rbx
0x1800078d2  sub     rsp, 20h
0x1800078d6  mov     rbx, rcx
0x1800078d9  mov     rcx, [rcx+40h]; this
0x1800078dd  mov     qword ptr [rbx+40h], 0
0x1800078e5  test    rcx, rcx
0x1800078e8  jz      short loc_1800078EF
0x1800078ea  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1800078ef  mov     rcx, rbx
0x1800078f2  add     rsp, 20h
0x1800078f6  pop     rbx
0x1800078f7  jmp     cs:__imp_DeleteCriticalSection
```
