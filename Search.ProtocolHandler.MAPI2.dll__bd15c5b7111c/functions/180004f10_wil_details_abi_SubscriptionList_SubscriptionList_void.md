# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180004f10`
- end: `0x180004f3e`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004dac`
- `0x180004ddc`

## callees

- `0x180004f10`
- `0x180005afc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004f37`

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
0x180004f10  push    rbx
0x180004f12  sub     rsp, 20h
0x180004f16  mov     rbx, rcx
0x180004f19  mov     rcx, [rcx+40h]; this
0x180004f1d  mov     qword ptr [rbx+40h], 0
0x180004f25  test    rcx, rcx
0x180004f28  jz      short loc_180004F2F
0x180004f2a  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180004f2f  mov     rcx, rbx
0x180004f32  add     rsp, 20h
0x180004f36  pop     rbx
0x180004f37  jmp     cs:__imp_DeleteCriticalSection
```
