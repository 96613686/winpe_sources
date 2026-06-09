# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180005a4c`
- end: `0x180005aba`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `110`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180005758`

## callees

- `0x180005a4c`
- `0x180005fb0`
- `0x180008a2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005a9c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005a9c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005a85`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005a85`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005a93`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005a93`

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
0x180005a4c  push    rdi
0x180005a4e  sub     rsp, 30h
0x180005a52  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180005a5b  mov     [rsp+38h+arg_0], rbx
0x180005a60  mov     [rsp+38h+arg_8], rsi
0x180005a65  mov     rbx, rcx
0x180005a68  call    ?ProcessShutdown@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::ProcessShutdown(void)
0x180005a6d  lea     rdi, [rbx+0C8h]
0x180005a74  mov     rsi, [rdi+40h]
0x180005a78  mov     qword ptr [rdi+40h], 0
0x180005a80  test    rsi, rsi
0x180005a83  jz      short loc_180005A99
0x180005a85  call    cs:__imp_GetProcessHeap
0x180005a8b  mov     rcx, rax; hHeap
0x180005a8e  mov     r8, rsi; lpMem
0x180005a91  xor     edx, edx; dwFlags
0x180005a93  call    cs:__imp_HeapFree
0x180005a99  mov     rcx, rdi; lpCriticalSection
0x180005a9c  call    cs:__imp_DeleteCriticalSection
0x180005aa2  lea     rcx, [rbx+8]; this
0x180005aa6  mov     rbx, [rsp+38h+arg_0]
0x180005aab  mov     rsi, [rsp+38h+arg_8]
0x180005ab0  add     rsp, 30h
0x180005ab4  pop     rdi
0x180005ab5  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
