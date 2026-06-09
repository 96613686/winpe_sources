# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x14000f9b4`
- end: `0x14000fa18`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `100`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000f7a4`

## callees

- `0x14000f9b4`
- `0x14000fc3c`
- `0x140010f7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000f9fa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000f9fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000f9f1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000f9f1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f9e3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f9e3`

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
0x14000f9b4  mov     [rsp+arg_0], rbx
0x14000f9b9  mov     [rsp+arg_8], rsi
0x14000f9be  push    rdi
0x14000f9bf  sub     rsp, 20h
0x14000f9c3  mov     rbx, rcx
0x14000f9c6  call    ?ProcessShutdown@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::ProcessShutdown(void)
0x14000f9cb  lea     rdi, [rbx+0C8h]
0x14000f9d2  mov     rsi, [rdi+40h]
0x14000f9d6  mov     qword ptr [rdi+40h], 0
0x14000f9de  test    rsi, rsi
0x14000f9e1  jz      short loc_14000F9F7
0x14000f9e3  call    cs:__imp_GetProcessHeap
0x14000f9e9  mov     rcx, rax; hHeap
0x14000f9ec  mov     r8, rsi; lpMem
0x14000f9ef  xor     edx, edx; dwFlags
0x14000f9f1  call    cs:__imp_HeapFree
0x14000f9f7  mov     rcx, rdi; lpCriticalSection
0x14000f9fa  call    cs:__imp_DeleteCriticalSection
0x14000fa00  lea     rcx, [rbx+8]; this
0x14000fa04  mov     rbx, [rsp+28h+arg_0]
0x14000fa09  mov     rsi, [rsp+28h+arg_8]
0x14000fa0e  add     rsp, 20h
0x14000fa12  pop     rdi
0x14000fa13  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
