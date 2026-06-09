# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180003224`
- end: `0x1800032f4`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180003130`

## callees

- `0x180002f9c`
- `0x180003224`
- `0x180003574`
- `0x180005b1c`
- `0x180007280`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800032d1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800032d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800032b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800032b6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800032c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800032c4`

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
0x180003224  mov     [rsp+arg_0], rbx
0x180003229  mov     [rsp+arg_8], rsi
0x18000322e  push    rdi
0x18000322f  sub     rsp, 0E0h
0x180003236  mov     rbx, rcx
0x180003239  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000323e  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180003243  cmp     byte ptr [rbx+40h], 0
0x180003247  jz      short loc_180003257
0x180003249  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x18000324d  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003252  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180003257  cmp     byte ptr [rbx+80h], 0
0x18000325e  jz      short loc_18000326E
0x180003260  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180003264  lea     rcx, [rsp+0E8h+var_88]; this
0x180003269  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000326e  cmp     byte ptr [rbx+0C0h], 0
0x180003275  jz      short loc_18000328B
0x180003277  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000327e  lea     rcx, [rsp+0E8h+var_48]; this
0x180003286  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000328b  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003290  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180003295  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000329a  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000329f  mov     rsi, [rbx+108h]
0x1800032a6  mov     qword ptr [rbx+108h], 0
0x1800032b1  test    rsi, rsi
0x1800032b4  jz      short loc_1800032CA
0x1800032b6  call    cs:__imp_GetProcessHeap
0x1800032bc  mov     r8, rsi; lpMem
0x1800032bf  xor     edx, edx; dwFlags
0x1800032c1  mov     rcx, rax; hHeap
0x1800032c4  call    cs:__imp_HeapFree
0x1800032ca  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800032d1  call    cs:__imp_DeleteCriticalSection
0x1800032d7  lea     rcx, [rbx+8]; this
0x1800032db  lea     r11, [rsp+0E8h+var_8]
0x1800032e3  mov     rbx, [r11+10h]
0x1800032e7  mov     rsi, [r11+18h]
0x1800032eb  mov     rsp, r11
0x1800032ee  pop     rdi
0x1800032ef  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
