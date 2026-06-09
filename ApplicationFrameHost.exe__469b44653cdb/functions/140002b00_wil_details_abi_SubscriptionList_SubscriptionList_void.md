# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x140002b00`
- end: `0x140002b46`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `70`
- prototype: `void __fastcall(wil::details_abi::SubscriptionList *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140004fa0`

## callees

- `0x140002b00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140002b3f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002b2c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002b2c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002b1e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002b1e`

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
0x140002b00  mov     [rsp+arg_0], rbx
0x140002b05  push    rdi
0x140002b06  sub     rsp, 20h
0x140002b0a  mov     rdi, [rcx+40h]
0x140002b0e  mov     rbx, rcx
0x140002b11  mov     qword ptr [rcx+40h], 0
0x140002b19  test    rdi, rdi
0x140002b1c  jz      short loc_140002B32
0x140002b1e  call    cs:__imp_GetProcessHeap
0x140002b24  mov     r8, rdi; lpMem
0x140002b27  xor     edx, edx; dwFlags
0x140002b29  mov     rcx, rax; hHeap
0x140002b2c  call    cs:__imp_HeapFree
0x140002b32  mov     rcx, rbx
0x140002b35  mov     rbx, [rsp+28h+arg_0]
0x140002b3a  add     rsp, 20h
0x140002b3e  pop     rdi
0x140002b3f  jmp     cs:__imp_DeleteCriticalSection
```
