# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180003328`
- end: `0x18000338c`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `100`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180003048`

## callees

- `0x180003328`
- `0x180003718`
- `0x18000713c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000336e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000336e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003365`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003365`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003357`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003357`

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
0x180003328  mov     [rsp+arg_0], rbx
0x18000332d  mov     [rsp+arg_8], rsi
0x180003332  push    rdi
0x180003333  sub     rsp, 20h
0x180003337  mov     rbx, rcx
0x18000333a  call    ?ProcessShutdown@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::ProcessShutdown(void)
0x18000333f  lea     rdi, [rbx+0C8h]
0x180003346  mov     rsi, [rdi+40h]
0x18000334a  mov     qword ptr [rdi+40h], 0
0x180003352  test    rsi, rsi
0x180003355  jz      short loc_18000336B
0x180003357  call    cs:__imp_GetProcessHeap
0x18000335d  mov     rcx, rax; hHeap
0x180003360  mov     r8, rsi; lpMem
0x180003363  xor     edx, edx; dwFlags
0x180003365  call    cs:__imp_HeapFree
0x18000336b  mov     rcx, rdi; lpCriticalSection
0x18000336e  call    cs:__imp_DeleteCriticalSection
0x180003374  lea     rcx, [rbx+8]; this
0x180003378  mov     rbx, [rsp+28h+arg_0]
0x18000337d  mov     rsi, [rsp+28h+arg_8]
0x180003382  add     rsp, 20h
0x180003386  pop     rdi
0x180003387  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
