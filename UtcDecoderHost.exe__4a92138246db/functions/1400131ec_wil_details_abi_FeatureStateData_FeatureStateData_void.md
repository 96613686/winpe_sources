# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x1400131ec`
- end: `0x1400132bc`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140012e1c`

## callees

- `0x140012d54`
- `0x1400131ec`
- `0x1400134f0`
- `0x140014984`
- `0x140015d64`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140013299`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140013299`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001328c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001328c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001327e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001327e`

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
0x1400131ec  mov     [rsp+arg_0], rbx
0x1400131f1  mov     [rsp+arg_8], rsi
0x1400131f6  push    rdi
0x1400131f7  sub     rsp, 0E0h
0x1400131fe  mov     rbx, rcx
0x140013201  lea     rcx, [rsp+0E8h+var_C8]; this
0x140013206  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x14001320b  cmp     byte ptr [rbx+40h], 0
0x14001320f  jz      short loc_14001321F
0x140013211  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x140013215  lea     rcx, [rsp+0E8h+var_C8]; this
0x14001321a  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14001321f  cmp     byte ptr [rbx+80h], 0
0x140013226  jz      short loc_140013236
0x140013228  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x14001322c  lea     rcx, [rsp+0E8h+var_88]; this
0x140013231  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140013236  cmp     byte ptr [rbx+0C0h], 0
0x14001323d  jz      short loc_140013253
0x14001323f  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x140013246  lea     rcx, [rsp+0E8h+var_48]; this
0x14001324e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140013253  lea     rcx, [rsp+0E8h+var_C8]; this
0x140013258  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x14001325d  lea     rcx, [rsp+0E8h+var_C8]; this
0x140013262  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x140013267  mov     rsi, [rbx+108h]
0x14001326e  mov     qword ptr [rbx+108h], 0
0x140013279  test    rsi, rsi
0x14001327c  jz      short loc_140013292
0x14001327e  call    cs:__imp_GetProcessHeap
0x140013284  mov     rcx, rax; hHeap
0x140013287  mov     r8, rsi; lpMem
0x14001328a  xor     edx, edx; dwFlags
0x14001328c  call    cs:__imp_HeapFree
0x140013292  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x140013299  call    cs:__imp_DeleteCriticalSection
0x14001329f  lea     rcx, [rbx+8]; this
0x1400132a3  lea     r11, [rsp+0E8h+var_8]
0x1400132ab  mov     rbx, [r11+10h]
0x1400132af  mov     rsi, [r11+18h]
0x1400132b3  mov     rsp, r11
0x1400132b6  pop     rdi
0x1400132b7  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
