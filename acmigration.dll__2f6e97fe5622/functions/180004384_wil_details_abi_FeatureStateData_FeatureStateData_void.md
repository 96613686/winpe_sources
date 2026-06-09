# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180004384`
- end: `0x1800043f2`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `110`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800040fc`

## callees

- `0x180004384`
- `0x1800047a0`
- `0x180006f00`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1800043bd`
- `KERNEL32!GetProcessHeap` at `0x1800043bd`
- `KERNEL32!DeleteCriticalSection` at `0x1800043d4`
- `KERNEL32!DeleteCriticalSection` at `0x1800043d4`
- `KERNEL32!HeapFree` at `0x1800043cb`
- `KERNEL32!HeapFree` at `0x1800043cb`

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
0x180004384  push    rdi
0x180004386  sub     rsp, 30h
0x18000438a  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180004393  mov     [rsp+38h+arg_0], rbx
0x180004398  mov     [rsp+38h+arg_8], rsi
0x18000439d  mov     rbx, rcx
0x1800043a0  call    ?ProcessShutdown@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::ProcessShutdown(void)
0x1800043a5  lea     rdi, [rbx+0C8h]
0x1800043ac  mov     rsi, [rdi+40h]
0x1800043b0  mov     qword ptr [rdi+40h], 0
0x1800043b8  test    rsi, rsi
0x1800043bb  jz      short loc_1800043D1
0x1800043bd  call    cs:__imp_GetProcessHeap
0x1800043c3  mov     rcx, rax; hHeap
0x1800043c6  mov     r8, rsi; lpMem
0x1800043c9  xor     edx, edx; dwFlags
0x1800043cb  call    cs:__imp_HeapFree
0x1800043d1  mov     rcx, rdi; lpCriticalSection
0x1800043d4  call    cs:__imp_DeleteCriticalSection
0x1800043da  lea     rcx, [rbx+8]; this
0x1800043de  mov     rbx, [rsp+38h+arg_0]
0x1800043e3  mov     rsi, [rsp+38h+arg_8]
0x1800043e8  add     rsp, 30h
0x1800043ec  pop     rdi
0x1800043ed  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
