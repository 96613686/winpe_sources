# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180003484`
- end: `0x180003554`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800031ec`

## callees

- `0x180002fd8`
- `0x180003484`
- `0x1800038f8`
- `0x180006508`
- `0x1800087c4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003524`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003524`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003516`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003516`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003531`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003531`

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
0x180003484  mov     [rsp+arg_0], rbx
0x180003489  mov     [rsp+arg_8], rsi
0x18000348e  push    rdi
0x18000348f  sub     rsp, 0E0h
0x180003496  mov     rbx, rcx
0x180003499  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000349e  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800034a3  cmp     byte ptr [rbx+40h], 0
0x1800034a7  jz      short loc_1800034B7
0x1800034a9  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x1800034ad  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800034b2  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800034b7  cmp     byte ptr [rbx+80h], 0
0x1800034be  jz      short loc_1800034CE
0x1800034c0  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x1800034c4  lea     rcx, [rsp+0E8h+var_88]; this
0x1800034c9  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800034ce  cmp     byte ptr [rbx+0C0h], 0
0x1800034d5  jz      short loc_1800034EB
0x1800034d7  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x1800034de  lea     rcx, [rsp+0E8h+var_48]; this
0x1800034e6  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800034eb  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800034f0  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x1800034f5  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800034fa  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x1800034ff  mov     rsi, [rbx+108h]
0x180003506  mov     qword ptr [rbx+108h], 0
0x180003511  test    rsi, rsi
0x180003514  jz      short loc_18000352A
0x180003516  call    cs:__imp_GetProcessHeap
0x18000351c  mov     rcx, rax; hHeap
0x18000351f  mov     r8, rsi; lpMem
0x180003522  xor     edx, edx; dwFlags
0x180003524  call    cs:__imp_HeapFree
0x18000352a  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180003531  call    cs:__imp_DeleteCriticalSection
0x180003537  lea     rcx, [rbx+8]; this
0x18000353b  lea     r11, [rsp+0E8h+var_8]
0x180003543  mov     rbx, [r11+10h]
0x180003547  mov     rsi, [r11+18h]
0x18000354b  mov     rsp, r11
0x18000354e  pop     rdi
0x18000354f  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
