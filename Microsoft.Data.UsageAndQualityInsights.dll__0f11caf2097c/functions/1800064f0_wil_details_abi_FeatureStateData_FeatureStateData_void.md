# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x1800064f0`
- end: `0x1800065c0`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000a4b8`

## callees

- `0x180005ffc`
- `0x1800064f0`
- `0x1800069cc`
- `0x180009484`
- `0x18000b700`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000659d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000659d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006590`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006590`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006582`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006582`

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
0x1800064f0  mov     [rsp+arg_0], rbx
0x1800064f5  mov     [rsp+arg_8], rsi
0x1800064fa  push    rdi
0x1800064fb  sub     rsp, 0E0h
0x180006502  mov     rbx, rcx
0x180006505  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000650a  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000650f  cmp     byte ptr [rbx+40h], 0
0x180006513  jz      short loc_180006523
0x180006515  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180006519  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000651e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180006523  cmp     byte ptr [rbx+80h], 0
0x18000652a  jz      short loc_18000653A
0x18000652c  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180006530  lea     rcx, [rsp+0E8h+var_88]; this
0x180006535  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000653a  cmp     byte ptr [rbx+0C0h], 0
0x180006541  jz      short loc_180006557
0x180006543  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000654a  lea     rcx, [rsp+0E8h+var_48]; this
0x180006552  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180006557  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000655c  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180006561  lea     rcx, [rsp+0E8h+var_C8]; this
0x180006566  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000656b  mov     rsi, [rbx+108h]
0x180006572  mov     qword ptr [rbx+108h], 0
0x18000657d  test    rsi, rsi
0x180006580  jz      short loc_180006596
0x180006582  call    cs:__imp_GetProcessHeap
0x180006588  mov     rcx, rax; hHeap
0x18000658b  mov     r8, rsi; lpMem
0x18000658e  xor     edx, edx; dwFlags
0x180006590  call    cs:__imp_HeapFree
0x180006596  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18000659d  call    cs:__imp_DeleteCriticalSection
0x1800065a3  lea     rcx, [rbx+8]; this
0x1800065a7  lea     r11, [rsp+0E8h+var_8]
0x1800065af  mov     rbx, [r11+10h]
0x1800065b3  mov     rsi, [r11+18h]
0x1800065b7  mov     rsp, r11
0x1800065ba  pop     rdi
0x1800065bb  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
