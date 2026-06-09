# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180016f00`
- end: `0x180016f2e`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180016e40`
- `0x18002417c`

## callees

- `0x180014dc0`
- `0x180016f00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016f27`

## pseudocode

```c
void __fastcall wil::details_abi::SubscriptionList::~SubscriptionList(struct _RTL_CRITICAL_SECTION *this)
{
  const unsigned __int16 *LockSemaphore; // rcx

  LockSemaphore = (const unsigned __int16 *)this[1].LockSemaphore;
  this[1].LockSemaphore = 0;
  if ( LockSemaphore )
    ConstStringHeapFree(LockSemaphore);
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x180016f00  push    rbx
0x180016f02  sub     rsp, 20h
0x180016f06  mov     rbx, rcx
0x180016f09  mov     rcx, [rcx+40h]; unsigned __int16 *
0x180016f0d  mov     qword ptr [rbx+40h], 0
0x180016f15  test    rcx, rcx
0x180016f18  jz      short loc_180016F1F
0x180016f1a  call    ?ConstStringHeapFree@@YAXPEBG@Z; ConstStringHeapFree(ushort const *)
0x180016f1f  mov     rcx, rbx
0x180016f22  add     rsp, 20h
0x180016f26  pop     rbx
0x180016f27  jmp     cs:__imp_DeleteCriticalSection
```
