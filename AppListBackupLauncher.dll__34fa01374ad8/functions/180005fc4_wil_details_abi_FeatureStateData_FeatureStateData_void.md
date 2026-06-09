# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180005fc4`
- end: `0x180006094`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180005a3c`

## callees

- `0x180004fdc`
- `0x180005fc4`
- `0x1800064b8`
- `0x18000a4c4`
- `0x18000d5fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006071`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006071`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006064`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006064`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006056`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006056`

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
0x180005fc4  mov     [rsp+arg_0], rbx
0x180005fc9  mov     [rsp+arg_8], rsi
0x180005fce  push    rdi
0x180005fcf  sub     rsp, 0E0h
0x180005fd6  mov     rbx, rcx
0x180005fd9  lea     rcx, [rsp+0E8h+var_C8]; this
0x180005fde  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180005fe3  cmp     byte ptr [rbx+40h], 0
0x180005fe7  jz      short loc_180005FF7
0x180005fe9  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180005fed  lea     rcx, [rsp+0E8h+var_C8]; this
0x180005ff2  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180005ff7  cmp     byte ptr [rbx+80h], 0
0x180005ffe  jz      short loc_18000600E
0x180006000  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180006004  lea     rcx, [rsp+0E8h+var_88]; this
0x180006009  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000600e  cmp     byte ptr [rbx+0C0h], 0
0x180006015  jz      short loc_18000602B
0x180006017  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000601e  lea     rcx, [rsp+0E8h+var_48]; this
0x180006026  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000602b  lea     rcx, [rsp+0E8h+var_C8]; this
0x180006030  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180006035  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000603a  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000603f  mov     rsi, [rbx+108h]
0x180006046  mov     qword ptr [rbx+108h], 0
0x180006051  test    rsi, rsi
0x180006054  jz      short loc_18000606A
0x180006056  call    cs:__imp_GetProcessHeap
0x18000605c  mov     rcx, rax; hHeap
0x18000605f  mov     r8, rsi; lpMem
0x180006062  xor     edx, edx; dwFlags
0x180006064  call    cs:__imp_HeapFree
0x18000606a  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180006071  call    cs:__imp_DeleteCriticalSection
0x180006077  lea     rcx, [rbx+8]; this
0x18000607b  lea     r11, [rsp+0E8h+var_8]
0x180006083  mov     rbx, [r11+10h]
0x180006087  mov     rsi, [r11+18h]
0x18000608b  mov     rsp, r11
0x18000608e  pop     rdi
0x18000608f  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
