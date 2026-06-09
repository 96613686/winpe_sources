# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x1800061b8`
- end: `0x180006288`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000a0f8`

## callees

- `0x180005df8`
- `0x1800061b8`
- `0x180006694`
- `0x1800090c4`
- `0x18000b2d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006265`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006265`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000624a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000624a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006258`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006258`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
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
0x1800061b8  mov     [rsp+arg_0], rbx
0x1800061bd  mov     [rsp+arg_8], rsi
0x1800061c2  push    rdi
0x1800061c3  sub     rsp, 0E0h
0x1800061ca  mov     rbx, rcx
0x1800061cd  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800061d2  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800061d7  cmp     byte ptr [rbx+40h], 0
0x1800061db  jz      short loc_1800061EB
0x1800061dd  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x1800061e1  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800061e6  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800061eb  cmp     byte ptr [rbx+80h], 0
0x1800061f2  jz      short loc_180006202
0x1800061f4  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x1800061f8  lea     rcx, [rsp+0E8h+var_88]; this
0x1800061fd  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180006202  cmp     byte ptr [rbx+0C0h], 0
0x180006209  jz      short loc_18000621F
0x18000620b  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180006212  lea     rcx, [rsp+0E8h+var_48]; this
0x18000621a  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000621f  lea     rcx, [rsp+0E8h+var_C8]; this
0x180006224  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180006229  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000622e  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180006233  mov     rsi, [rbx+108h]
0x18000623a  mov     qword ptr [rbx+108h], 0
0x180006245  test    rsi, rsi
0x180006248  jz      short loc_18000625E
0x18000624a  call    cs:__imp_GetProcessHeap
0x180006250  mov     rcx, rax; hHeap
0x180006253  mov     r8, rsi; lpMem
0x180006256  xor     edx, edx; dwFlags
0x180006258  call    cs:__imp_HeapFree
0x18000625e  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180006265  call    cs:__imp_DeleteCriticalSection
0x18000626b  lea     rcx, [rbx+8]; this
0x18000626f  lea     r11, [rsp+0E8h+var_8]
0x180006277  mov     rbx, [r11+10h]
0x18000627b  mov     rsi, [r11+18h]
0x18000627f  mov     rsp, r11
0x180006282  pop     rdi
0x180006283  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
