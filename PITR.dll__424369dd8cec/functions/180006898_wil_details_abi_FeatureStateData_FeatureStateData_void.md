# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180006898`
- end: `0x1800068fc`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `100`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006170`

## callees

- `0x180006898`
- `0x180006c88`
- `0x180012564`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800068de`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800068de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800068c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800068c7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800068d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800068d5`

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
0x180006898  mov     [rsp+arg_0], rbx
0x18000689d  mov     [rsp+arg_8], rsi
0x1800068a2  push    rdi
0x1800068a3  sub     rsp, 20h
0x1800068a7  mov     rbx, rcx
0x1800068aa  call    ?ProcessShutdown@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::ProcessShutdown(void)
0x1800068af  lea     rdi, [rbx+0C8h]
0x1800068b6  mov     rsi, [rdi+40h]
0x1800068ba  mov     qword ptr [rdi+40h], 0
0x1800068c2  test    rsi, rsi
0x1800068c5  jz      short loc_1800068DB
0x1800068c7  call    cs:__imp_GetProcessHeap
0x1800068cd  mov     rcx, rax; hHeap
0x1800068d0  mov     r8, rsi; lpMem
0x1800068d3  xor     edx, edx; dwFlags
0x1800068d5  call    cs:__imp_HeapFree
0x1800068db  mov     rcx, rdi; lpCriticalSection
0x1800068de  call    cs:__imp_DeleteCriticalSection
0x1800068e4  lea     rcx, [rbx+8]; this
0x1800068e8  mov     rbx, [rsp+28h+arg_0]
0x1800068ed  mov     rsi, [rsp+28h+arg_8]
0x1800068f2  add     rsp, 20h
0x1800068f6  pop     rdi
0x1800068f7  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
