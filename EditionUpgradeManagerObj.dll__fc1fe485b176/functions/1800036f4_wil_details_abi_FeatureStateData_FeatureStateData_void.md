# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x1800036f4`
- end: `0x1800037c4`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800034b4`

## callees

- `0x180003320`
- `0x1800036f4`
- `0x180003a44`
- `0x180006288`
- `0x180007d58`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800037a1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800037a1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003794`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003794`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003786`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003786`

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
0x1800036f4  mov     [rsp+arg_0], rbx
0x1800036f9  mov     [rsp+arg_8], rsi
0x1800036fe  push    rdi
0x1800036ff  sub     rsp, 0E0h
0x180003706  mov     rbx, rcx
0x180003709  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000370e  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180003713  cmp     byte ptr [rbx+40h], 0
0x180003717  jz      short loc_180003727
0x180003719  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x18000371d  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003722  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180003727  cmp     byte ptr [rbx+80h], 0
0x18000372e  jz      short loc_18000373E
0x180003730  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180003734  lea     rcx, [rsp+0E8h+var_88]; this
0x180003739  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000373e  cmp     byte ptr [rbx+0C0h], 0
0x180003745  jz      short loc_18000375B
0x180003747  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000374e  lea     rcx, [rsp+0E8h+var_48]; this
0x180003756  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000375b  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003760  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180003765  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000376a  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000376f  mov     rsi, [rbx+108h]
0x180003776  mov     qword ptr [rbx+108h], 0
0x180003781  test    rsi, rsi
0x180003784  jz      short loc_18000379A
0x180003786  call    cs:__imp_GetProcessHeap
0x18000378c  mov     r8, rsi; lpMem
0x18000378f  xor     edx, edx; dwFlags
0x180003791  mov     rcx, rax; hHeap
0x180003794  call    cs:__imp_HeapFree
0x18000379a  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800037a1  call    cs:__imp_DeleteCriticalSection
0x1800037a7  lea     rcx, [rbx+8]; this
0x1800037ab  lea     r11, [rsp+0E8h+var_8]
0x1800037b3  mov     rbx, [r11+10h]
0x1800037b7  mov     rsi, [r11+18h]
0x1800037bb  mov     rsp, r11
0x1800037be  pop     rdi
0x1800037bf  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
