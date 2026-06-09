# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180003410`
- end: `0x1800034e0`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800032f8`

## callees

- `0x180002f54`
- `0x180003410`
- `0x180003884`
- `0x180005f28`
- `0x180007e18`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800034bd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800034bd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800034b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800034b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800034a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800034a2`

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
0x180003410  mov     [rsp+arg_0], rbx
0x180003415  mov     [rsp+arg_8], rsi
0x18000341a  push    rdi
0x18000341b  sub     rsp, 0E0h
0x180003422  mov     rbx, rcx
0x180003425  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000342a  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000342f  cmp     byte ptr [rbx+40h], 0
0x180003433  jz      short loc_180003443
0x180003435  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180003439  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000343e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180003443  cmp     byte ptr [rbx+80h], 0
0x18000344a  jz      short loc_18000345A
0x18000344c  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180003450  lea     rcx, [rsp+0E8h+var_88]; this
0x180003455  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000345a  cmp     byte ptr [rbx+0C0h], 0
0x180003461  jz      short loc_180003477
0x180003463  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000346a  lea     rcx, [rsp+0E8h+var_48]; this
0x180003472  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180003477  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000347c  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180003481  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003486  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000348b  mov     rsi, [rbx+108h]
0x180003492  mov     qword ptr [rbx+108h], 0
0x18000349d  test    rsi, rsi
0x1800034a0  jz      short loc_1800034B6
0x1800034a2  call    cs:__imp_GetProcessHeap
0x1800034a8  mov     rcx, rax; hHeap
0x1800034ab  mov     r8, rsi; lpMem
0x1800034ae  xor     edx, edx; dwFlags
0x1800034b0  call    cs:__imp_HeapFree
0x1800034b6  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800034bd  call    cs:__imp_DeleteCriticalSection
0x1800034c3  lea     rcx, [rbx+8]; this
0x1800034c7  lea     r11, [rsp+0E8h+var_8]
0x1800034cf  mov     rbx, [r11+10h]
0x1800034d3  mov     rsi, [r11+18h]
0x1800034d7  mov     rsp, r11
0x1800034da  pop     rdi
0x1800034db  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
