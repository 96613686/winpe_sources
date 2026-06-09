# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x18000870c`
- end: `0x1800087dc`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000a898`

## callees

- `0x180008414`
- `0x18000870c`
- `0x180008a10`
- `0x180009a08`
- `0x18000afb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800087b9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800087b9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000879e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000879e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800087ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800087ac`

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
0x18000870c  mov     [rsp+arg_0], rbx
0x180008711  mov     [rsp+arg_8], rsi
0x180008716  push    rdi
0x180008717  sub     rsp, 0E0h
0x18000871e  mov     rbx, rcx
0x180008721  lea     rcx, [rsp+0E8h+var_C8]; this
0x180008726  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000872b  cmp     byte ptr [rbx+40h], 0
0x18000872f  jz      short loc_18000873F
0x180008731  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180008735  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000873a  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000873f  cmp     byte ptr [rbx+80h], 0
0x180008746  jz      short loc_180008756
0x180008748  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x18000874c  lea     rcx, [rsp+0E8h+var_88]; this
0x180008751  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180008756  cmp     byte ptr [rbx+0C0h], 0
0x18000875d  jz      short loc_180008773
0x18000875f  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180008766  lea     rcx, [rsp+0E8h+var_48]; this
0x18000876e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180008773  lea     rcx, [rsp+0E8h+var_C8]; this
0x180008778  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x18000877d  lea     rcx, [rsp+0E8h+var_C8]; this
0x180008782  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180008787  mov     rsi, [rbx+108h]
0x18000878e  mov     qword ptr [rbx+108h], 0
0x180008799  test    rsi, rsi
0x18000879c  jz      short loc_1800087B2
0x18000879e  call    cs:__imp_GetProcessHeap
0x1800087a4  mov     rcx, rax; hHeap
0x1800087a7  mov     r8, rsi; lpMem
0x1800087aa  xor     edx, edx; dwFlags
0x1800087ac  call    cs:__imp_HeapFree
0x1800087b2  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800087b9  call    cs:__imp_DeleteCriticalSection
0x1800087bf  lea     rcx, [rbx+8]; this
0x1800087c3  lea     r11, [rsp+0E8h+var_8]
0x1800087cb  mov     rbx, [r11+10h]
0x1800087cf  mov     rsi, [r11+18h]
0x1800087d3  mov     rsp, r11
0x1800087d6  pop     rdi
0x1800087d7  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
