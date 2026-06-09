# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180017680`
- end: `0x1800176ae`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180017584`
- `0x1800175b4`

## callees

- `0x180017680`
- `0x18001804c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800176a7`

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
0x180017680  push    rbx
0x180017682  sub     rsp, 20h
0x180017686  mov     rbx, rcx
0x180017689  mov     rcx, [rcx+40h]; this
0x18001768d  mov     qword ptr [rbx+40h], 0
0x180017695  test    rcx, rcx
0x180017698  jz      short loc_18001769F
0x18001769a  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18001769f  mov     rcx, rbx
0x1800176a2  add     rsp, 20h
0x1800176a6  pop     rbx
0x1800176a7  jmp     cs:__imp_DeleteCriticalSection
```
