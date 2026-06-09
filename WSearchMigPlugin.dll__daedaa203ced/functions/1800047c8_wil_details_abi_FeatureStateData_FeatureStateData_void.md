# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x1800047c8`
- end: `0x180004836`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `110`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000452c`

## callees

- `0x1800047c8`
- `0x180004be4`
- `0x180007240`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004818`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004818`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004801`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004801`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000480f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000480f`

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
0x1800047c8  push    rdi
0x1800047ca  sub     rsp, 30h
0x1800047ce  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800047d7  mov     [rsp+38h+arg_0], rbx
0x1800047dc  mov     [rsp+38h+arg_8], rsi
0x1800047e1  mov     rbx, rcx
0x1800047e4  call    ?ProcessShutdown@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::ProcessShutdown(void)
0x1800047e9  lea     rdi, [rbx+0C8h]
0x1800047f0  mov     rsi, [rdi+40h]
0x1800047f4  mov     qword ptr [rdi+40h], 0
0x1800047fc  test    rsi, rsi
0x1800047ff  jz      short loc_180004815
0x180004801  call    cs:__imp_GetProcessHeap
0x180004807  mov     rcx, rax; hHeap
0x18000480a  mov     r8, rsi; lpMem
0x18000480d  xor     edx, edx; dwFlags
0x18000480f  call    cs:__imp_HeapFree
0x180004815  mov     rcx, rdi; lpCriticalSection
0x180004818  call    cs:__imp_DeleteCriticalSection
0x18000481e  lea     rcx, [rbx+8]; this
0x180004822  mov     rbx, [rsp+38h+arg_0]
0x180004827  mov     rsi, [rsp+38h+arg_8]
0x18000482c  add     rsp, 30h
0x180004830  pop     rdi
0x180004831  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
