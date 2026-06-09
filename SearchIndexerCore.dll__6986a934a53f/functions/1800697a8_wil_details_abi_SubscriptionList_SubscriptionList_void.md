# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x1800697a8`
- end: `0x1800697d8`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `48`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800696e4`
- `0x1800a8d94`

## callees

- `0x1800697a8`
- `0x1800a997c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800697cb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800697cb`

## pseudocode

```c
void __fastcall wil::details_abi::SubscriptionList::~SubscriptionList(LPCRITICAL_SECTION lpCriticalSection, void *a2)
{
  wil::details *LockSemaphore; // rcx

  LockSemaphore = (wil::details *)lpCriticalSection[1].LockSemaphore;
  lpCriticalSection[1].LockSemaphore = 0;
  if ( LockSemaphore )
    wil::details::FreeProcessHeap(LockSemaphore, a2);
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x1800697a8  push    rbx
0x1800697aa  sub     rsp, 20h
0x1800697ae  mov     rbx, rcx
0x1800697b1  mov     rcx, [rcx+40h]; this
0x1800697b5  mov     qword ptr [rbx+40h], 0
0x1800697bd  test    rcx, rcx
0x1800697c0  jz      short loc_1800697C8
0x1800697c2  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1800697c7  nop
0x1800697c8  mov     rcx, rbx; lpCriticalSection
0x1800697cb  call    cs:__imp_DeleteCriticalSection
0x1800697d1  nop
0x1800697d2  add     rsp, 20h
0x1800697d6  pop     rbx
0x1800697d7  retn
```
