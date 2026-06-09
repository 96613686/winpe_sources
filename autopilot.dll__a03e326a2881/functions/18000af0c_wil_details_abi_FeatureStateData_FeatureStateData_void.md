# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x18000af0c`
- end: `0x18000afdc`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000fed0`

## callees

- `0x18000aaec`
- `0x18000af0c`
- `0x18000b3f8`
- `0x18000eda0`
- `0x180011590`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000afb9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000afb9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000af9e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000af9e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000afac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000afac`

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
0x18000af0c  mov     [rsp+arg_0], rbx
0x18000af11  mov     [rsp+arg_8], rsi
0x18000af16  push    rdi
0x18000af17  sub     rsp, 0E0h
0x18000af1e  mov     rbx, rcx
0x18000af21  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000af26  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000af2b  cmp     byte ptr [rbx+40h], 0
0x18000af2f  jz      short loc_18000AF3F
0x18000af31  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x18000af35  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000af3a  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000af3f  cmp     byte ptr [rbx+80h], 0
0x18000af46  jz      short loc_18000AF56
0x18000af48  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x18000af4c  lea     rcx, [rsp+0E8h+var_88]; this
0x18000af51  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000af56  cmp     byte ptr [rbx+0C0h], 0
0x18000af5d  jz      short loc_18000AF73
0x18000af5f  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000af66  lea     rcx, [rsp+0E8h+var_48]; this
0x18000af6e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000af73  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000af78  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x18000af7d  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000af82  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000af87  mov     rsi, [rbx+108h]
0x18000af8e  mov     qword ptr [rbx+108h], 0
0x18000af99  test    rsi, rsi
0x18000af9c  jz      short loc_18000AFB2
0x18000af9e  call    cs:__imp_GetProcessHeap
0x18000afa4  mov     rcx, rax; hHeap
0x18000afa7  mov     r8, rsi; lpMem
0x18000afaa  xor     edx, edx; dwFlags
0x18000afac  call    cs:__imp_HeapFree
0x18000afb2  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18000afb9  call    cs:__imp_DeleteCriticalSection
0x18000afbf  lea     rcx, [rbx+8]; this
0x18000afc3  lea     r11, [rsp+0E8h+var_8]
0x18000afcb  mov     rbx, [r11+10h]
0x18000afcf  mov     rsi, [r11+18h]
0x18000afd3  mov     rsp, r11
0x18000afd6  pop     rdi
0x18000afd7  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
