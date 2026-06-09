# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x1800142f8`
- end: `0x18001435c`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `100`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180014018`

## callees

- `0x1800142f8`
- `0x180014700`
- `0x180016d18`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001433e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001433e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014335`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014335`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014327`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014327`

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
0x1800142f8  mov     [rsp+arg_0], rbx
0x1800142fd  mov     [rsp+arg_8], rsi
0x180014302  push    rdi
0x180014303  sub     rsp, 20h
0x180014307  mov     rbx, rcx
0x18001430a  call    ?ProcessShutdown@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::ProcessShutdown(void)
0x18001430f  lea     rdi, [rbx+0C8h]
0x180014316  mov     rsi, [rdi+40h]
0x18001431a  mov     qword ptr [rdi+40h], 0
0x180014322  test    rsi, rsi
0x180014325  jz      short loc_18001433B
0x180014327  call    cs:__imp_GetProcessHeap
0x18001432d  mov     rcx, rax; hHeap
0x180014330  mov     r8, rsi; lpMem
0x180014333  xor     edx, edx; dwFlags
0x180014335  call    cs:__imp_HeapFree
0x18001433b  mov     rcx, rdi; lpCriticalSection
0x18001433e  call    cs:__imp_DeleteCriticalSection
0x180014344  lea     rcx, [rbx+8]; this
0x180014348  mov     rbx, [rsp+28h+arg_0]
0x18001434d  mov     rsi, [rsp+28h+arg_8]
0x180014352  add     rsp, 20h
0x180014356  pop     rdi
0x180014357  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
