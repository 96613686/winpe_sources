# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x18001473c`
- end: `0x18001480c`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180014624`

## callees

- `0x180014490`
- `0x18001473c`
- `0x180014bb0`
- `0x1800171d0`
- `0x180018dcc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800147e9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800147e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800147dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800147dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800147ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800147ce`

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
0x18001473c  mov     [rsp+arg_0], rbx
0x180014741  mov     [rsp+arg_8], rsi
0x180014746  push    rdi
0x180014747  sub     rsp, 0E0h
0x18001474e  mov     rbx, rcx
0x180014751  lea     rcx, [rsp+0E8h+var_C8]; this
0x180014756  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18001475b  cmp     byte ptr [rbx+40h], 0
0x18001475f  jz      short loc_18001476F
0x180014761  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180014765  lea     rcx, [rsp+0E8h+var_C8]; this
0x18001476a  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18001476f  cmp     byte ptr [rbx+80h], 0
0x180014776  jz      short loc_180014786
0x180014778  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x18001477c  lea     rcx, [rsp+0E8h+var_88]; this
0x180014781  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180014786  cmp     byte ptr [rbx+0C0h], 0
0x18001478d  jz      short loc_1800147A3
0x18001478f  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180014796  lea     rcx, [rsp+0E8h+var_48]; this
0x18001479e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800147a3  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800147a8  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x1800147ad  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800147b2  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x1800147b7  mov     rsi, [rbx+108h]
0x1800147be  mov     qword ptr [rbx+108h], 0
0x1800147c9  test    rsi, rsi
0x1800147cc  jz      short loc_1800147E2
0x1800147ce  call    cs:__imp_GetProcessHeap
0x1800147d4  mov     rcx, rax; hHeap
0x1800147d7  mov     r8, rsi; lpMem
0x1800147da  xor     edx, edx; dwFlags
0x1800147dc  call    cs:__imp_HeapFree
0x1800147e2  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800147e9  call    cs:__imp_DeleteCriticalSection
0x1800147ef  lea     rcx, [rbx+8]; this
0x1800147f3  lea     r11, [rsp+0E8h+var_8]
0x1800147fb  mov     rbx, [r11+10h]
0x1800147ff  mov     rsi, [r11+18h]
0x180014803  mov     rsp, r11
0x180014806  pop     rdi
0x180014807  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
