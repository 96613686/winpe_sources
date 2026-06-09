# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x140002940`
- end: `0x140002986`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `70`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140007910`

## callees

- `0x140002940`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000297f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000296c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000296c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000295e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000295e`

## pseudocode

```c
void __fastcall wil::details_abi::SubscriptionList::~SubscriptionList(struct _RTL_CRITICAL_SECTION *this)
{
  HANDLE LockSemaphore; // rdi
  HANDLE ProcessHeap; // rax

  LockSemaphore = this[1].LockSemaphore;
  this[1].LockSemaphore = 0;
  if ( LockSemaphore )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, LockSemaphore);
  }
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x140002940  mov     [rsp+arg_0], rbx
0x140002945  push    rdi
0x140002946  sub     rsp, 20h
0x14000294a  mov     rdi, [rcx+40h]
0x14000294e  mov     rbx, rcx
0x140002951  mov     qword ptr [rcx+40h], 0
0x140002959  test    rdi, rdi
0x14000295c  jz      short loc_140002972
0x14000295e  call    cs:__imp_GetProcessHeap
0x140002964  mov     r8, rdi; lpMem
0x140002967  xor     edx, edx; dwFlags
0x140002969  mov     rcx, rax; hHeap
0x14000296c  call    cs:__imp_HeapFree
0x140002972  mov     rcx, rbx
0x140002975  mov     rbx, [rsp+28h+arg_0]
0x14000297a  add     rsp, 20h
0x14000297e  pop     rdi
0x14000297f  jmp     cs:__imp_DeleteCriticalSection
```
