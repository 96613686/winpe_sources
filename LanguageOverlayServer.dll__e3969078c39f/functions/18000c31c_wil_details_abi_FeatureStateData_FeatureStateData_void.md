# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x18000c31c`
- end: `0x18000c380`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `100`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ffbc`

## callees

- `0x18000c31c`
- `0x18000c794`
- `0x18000e804`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c362`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c362`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c359`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c359`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c34b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c34b`

## pseudocode

```c
void __fastcall wil::details_abi::FeatureStateData::~FeatureStateData(struct _RTL_CRITICAL_SECTION *this)
{
  HANDLE LockSemaphore; // rsi
  HANDLE ProcessHeap; // rax

  wil::details_abi::FeatureStateData::ProcessShutdown((wil::details_abi::FeatureStateData *)this);
  LockSemaphore = this[6].LockSemaphore;
  this[6].LockSemaphore = 0;
  if ( LockSemaphore )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, LockSemaphore);
  }
  DeleteCriticalSection(this + 5);
  wil::details_abi::UsageIndexes::~UsageIndexes((wil::details_abi::UsageIndexes *)&this->LockCount);
}

```

## disassembly

```asm
0x18000c31c  mov     [rsp+arg_0], rbx
0x18000c321  mov     [rsp+arg_8], rsi
0x18000c326  push    rdi
0x18000c327  sub     rsp, 20h
0x18000c32b  mov     rbx, rcx
0x18000c32e  call    ?ProcessShutdown@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::ProcessShutdown(void)
0x18000c333  lea     rdi, [rbx+0C8h]
0x18000c33a  mov     rsi, [rdi+40h]
0x18000c33e  mov     qword ptr [rdi+40h], 0
0x18000c346  test    rsi, rsi
0x18000c349  jz      short loc_18000C35F
0x18000c34b  call    cs:__imp_GetProcessHeap
0x18000c351  mov     rcx, rax; hHeap
0x18000c354  mov     r8, rsi; lpMem
0x18000c357  xor     edx, edx; dwFlags
0x18000c359  call    cs:__imp_HeapFree
0x18000c35f  mov     rcx, rdi; lpCriticalSection
0x18000c362  call    cs:__imp_DeleteCriticalSection
0x18000c368  lea     rcx, [rbx+8]; this
0x18000c36c  mov     rbx, [rsp+28h+arg_0]
0x18000c371  mov     rsi, [rsp+28h+arg_8]
0x18000c376  add     rsp, 20h
0x18000c37a  pop     rdi
0x18000c37b  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
