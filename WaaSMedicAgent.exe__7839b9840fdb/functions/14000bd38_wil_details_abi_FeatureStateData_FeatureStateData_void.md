# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x14000bd38`
- end: `0x14000bda6`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `110`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000bb68`

## callees

- `0x14000bd38`
- `0x14000bfe4`
- `0x14000d0cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000bd88`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000bd88`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000bd7f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000bd7f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000bd71`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000bd71`

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
0x14000bd38  push    rdi
0x14000bd3a  sub     rsp, 30h
0x14000bd3e  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x14000bd47  mov     [rsp+38h+arg_0], rbx
0x14000bd4c  mov     [rsp+38h+arg_8], rsi
0x14000bd51  mov     rbx, rcx
0x14000bd54  call    ?ProcessShutdown@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::ProcessShutdown(void)
0x14000bd59  lea     rdi, [rbx+0C8h]
0x14000bd60  mov     rsi, [rdi+40h]
0x14000bd64  mov     qword ptr [rdi+40h], 0
0x14000bd6c  test    rsi, rsi
0x14000bd6f  jz      short loc_14000BD85
0x14000bd71  call    cs:__imp_GetProcessHeap
0x14000bd77  mov     rcx, rax; hHeap
0x14000bd7a  mov     r8, rsi; lpMem
0x14000bd7d  xor     edx, edx; dwFlags
0x14000bd7f  call    cs:__imp_HeapFree
0x14000bd85  mov     rcx, rdi; lpCriticalSection
0x14000bd88  call    cs:__imp_DeleteCriticalSection
0x14000bd8e  lea     rcx, [rbx+8]; this
0x14000bd92  mov     rbx, [rsp+38h+arg_0]
0x14000bd97  mov     rsi, [rsp+38h+arg_8]
0x14000bd9c  add     rsp, 30h
0x14000bda0  pop     rdi
0x14000bda1  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
