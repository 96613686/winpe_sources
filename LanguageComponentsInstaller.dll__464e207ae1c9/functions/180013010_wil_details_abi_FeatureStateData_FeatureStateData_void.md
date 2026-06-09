# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180013010`
- end: `0x180013074`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `100`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800122b4`

## callees

- `0x180013010`
- `0x180013540`
- `0x180019518`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180013056`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180013056`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001304d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001304d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001303f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001303f`

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
0x180013010  mov     [rsp+arg_0], rbx
0x180013015  mov     [rsp+arg_8], rsi
0x18001301a  push    rdi
0x18001301b  sub     rsp, 20h
0x18001301f  mov     rbx, rcx
0x180013022  call    ?ProcessShutdown@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::ProcessShutdown(void)
0x180013027  lea     rdi, [rbx+0C8h]
0x18001302e  mov     rsi, [rdi+40h]
0x180013032  mov     qword ptr [rdi+40h], 0
0x18001303a  test    rsi, rsi
0x18001303d  jz      short loc_180013053
0x18001303f  call    cs:__imp_GetProcessHeap
0x180013045  mov     rcx, rax; hHeap
0x180013048  mov     r8, rsi; lpMem
0x18001304b  xor     edx, edx; dwFlags
0x18001304d  call    cs:__imp_HeapFree
0x180013053  mov     rcx, rdi; lpCriticalSection
0x180013056  call    cs:__imp_DeleteCriticalSection
0x18001305c  lea     rcx, [rbx+8]; this
0x180013060  mov     rbx, [rsp+28h+arg_0]
0x180013065  mov     rsi, [rsp+28h+arg_8]
0x18001306a  add     rsp, 20h
0x18001306e  pop     rdi
0x18001306f  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
