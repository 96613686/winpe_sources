# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180003594`
- end: `0x180003664`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800032f8`

## callees

- `0x180003164`
- `0x180003594`
- `0x1800038e4`
- `0x1800062cc`
- `0x1800083b4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003634`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003634`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003626`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003626`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003641`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003641`

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
0x180003594  mov     [rsp+arg_0], rbx
0x180003599  mov     [rsp+arg_8], rsi
0x18000359e  push    rdi
0x18000359f  sub     rsp, 0E0h
0x1800035a6  mov     rbx, rcx
0x1800035a9  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800035ae  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800035b3  cmp     byte ptr [rbx+40h], 0
0x1800035b7  jz      short loc_1800035C7
0x1800035b9  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x1800035bd  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800035c2  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800035c7  cmp     byte ptr [rbx+80h], 0
0x1800035ce  jz      short loc_1800035DE
0x1800035d0  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x1800035d4  lea     rcx, [rsp+0E8h+var_88]; this
0x1800035d9  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800035de  cmp     byte ptr [rbx+0C0h], 0
0x1800035e5  jz      short loc_1800035FB
0x1800035e7  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x1800035ee  lea     rcx, [rsp+0E8h+var_48]; this
0x1800035f6  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800035fb  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003600  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180003605  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000360a  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000360f  mov     rsi, [rbx+108h]
0x180003616  mov     qword ptr [rbx+108h], 0
0x180003621  test    rsi, rsi
0x180003624  jz      short loc_18000363A
0x180003626  call    cs:__imp_GetProcessHeap
0x18000362c  mov     r8, rsi; lpMem
0x18000362f  xor     edx, edx; dwFlags
0x180003631  mov     rcx, rax; hHeap
0x180003634  call    cs:__imp_HeapFree
0x18000363a  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180003641  call    cs:__imp_DeleteCriticalSection
0x180003647  lea     rcx, [rbx+8]; this
0x18000364b  lea     r11, [rsp+0E8h+var_8]
0x180003653  mov     rbx, [r11+10h]
0x180003657  mov     rsi, [r11+18h]
0x18000365b  mov     rsp, r11
0x18000365e  pop     rdi
0x18000365f  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
