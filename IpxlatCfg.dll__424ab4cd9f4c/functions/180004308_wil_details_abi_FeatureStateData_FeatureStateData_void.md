# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180004308`
- end: `0x1800043d8`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180004090`

## callees

- `0x180003ec4`
- `0x180004308`
- `0x18000477c`
- `0x180007064`
- `0x180009214`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800043a8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800043a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000439a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000439a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800043b5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800043b5`

## pseudocode

```c
void __fastcall wil::details_abi::FeatureStateData::~FeatureStateData(wil::details_abi::FeatureStateData *this)
{
  void *v2; // rsi
  HANDLE ProcessHeap; // rax
  _BYTE v4[64]; // [rsp+20h] [rbp-C8h] BYREF
  _BYTE v5[64]; // [rsp+60h] [rbp-88h] BYREF
  _BYTE v6[64]; // [rsp+A0h] [rbp-48h] BYREF

  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)v4);
  if ( *((_BYTE *)this + 64) )
    wil::details_abi::RawUsageIndex::Swap(
      (wil::details_abi::RawUsageIndex *)v4,
      (wil::details_abi::FeatureStateData *)((char *)this + 8));
  if ( *((_BYTE *)this + 128) )
    wil::details_abi::RawUsageIndex::Swap(
      (wil::details_abi::RawUsageIndex *)v5,
      (wil::details_abi::FeatureStateData *)((char *)this + 72));
  if ( *((_BYTE *)this + 192) )
    wil::details_abi::RawUsageIndex::Swap(
      (wil::details_abi::RawUsageIndex *)v6,
      (wil::details_abi::FeatureStateData *)((char *)this + 136));
  wil::details_abi::UsageIndexes::Record((wil::details_abi::UsageIndexes *)v4);
  wil::details_abi::UsageIndexes::~UsageIndexes((wil::details_abi::UsageIndexes *)v4);
  v2 = (void *)*((_QWORD *)this + 33);
  *((_QWORD *)this + 33) = 0;
  if ( v2 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 5);
  wil::details_abi::UsageIndexes::~UsageIndexes((wil::details_abi::FeatureStateData *)((char *)this + 8));
}

```

## disassembly

```asm
0x180004308  mov     [rsp+arg_0], rbx
0x18000430d  mov     [rsp+arg_8], rsi
0x180004312  push    rdi
0x180004313  sub     rsp, 0E0h
0x18000431a  mov     rbx, rcx
0x18000431d  lea     rcx, [rsp+0E8h+var_C8]; this
0x180004322  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180004327  cmp     byte ptr [rbx+40h], 0
0x18000432b  jz      short loc_18000433B
0x18000432d  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180004331  lea     rcx, [rsp+0E8h+var_C8]; this
0x180004336  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000433b  cmp     byte ptr [rbx+80h], 0
0x180004342  jz      short loc_180004352
0x180004344  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180004348  lea     rcx, [rsp+0E8h+var_88]; this
0x18000434d  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180004352  cmp     byte ptr [rbx+0C0h], 0
0x180004359  jz      short loc_18000436F
0x18000435b  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180004362  lea     rcx, [rsp+0E8h+var_48]; this
0x18000436a  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000436f  lea     rcx, [rsp+0E8h+var_C8]; this
0x180004374  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180004379  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000437e  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180004383  mov     rsi, [rbx+108h]
0x18000438a  mov     qword ptr [rbx+108h], 0
0x180004395  test    rsi, rsi
0x180004398  jz      short loc_1800043AE
0x18000439a  call    cs:__imp_GetProcessHeap
0x1800043a0  mov     rcx, rax; hHeap
0x1800043a3  mov     r8, rsi; lpMem
0x1800043a6  xor     edx, edx; dwFlags
0x1800043a8  call    cs:__imp_HeapFree
0x1800043ae  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800043b5  call    cs:__imp_DeleteCriticalSection
0x1800043bb  lea     rcx, [rbx+8]; this
0x1800043bf  lea     r11, [rsp+0E8h+var_8]
0x1800043c7  mov     rbx, [r11+10h]
0x1800043cb  mov     rsi, [r11+18h]
0x1800043cf  mov     rsp, r11
0x1800043d2  pop     rdi
0x1800043d3  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
