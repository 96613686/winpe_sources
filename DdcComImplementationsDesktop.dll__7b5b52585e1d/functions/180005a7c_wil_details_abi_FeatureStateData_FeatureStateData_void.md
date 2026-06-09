# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180005a7c`
- end: `0x180005b4c`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180005964`

## callees

- `0x1800057d0`
- `0x180005a7c`
- `0x180005ef0`
- `0x1800084f0`
- `0x18000a228`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005b1c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005b1c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005b0e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005b0e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005b29`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005b29`

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
0x180005a7c  mov     [rsp+arg_0], rbx
0x180005a81  mov     [rsp+arg_8], rsi
0x180005a86  push    rdi
0x180005a87  sub     rsp, 0E0h
0x180005a8e  mov     rbx, rcx
0x180005a91  lea     rcx, [rsp+0E8h+var_C8]; this
0x180005a96  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180005a9b  cmp     byte ptr [rbx+40h], 0
0x180005a9f  jz      short loc_180005AAF
0x180005aa1  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180005aa5  lea     rcx, [rsp+0E8h+var_C8]; this
0x180005aaa  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180005aaf  cmp     byte ptr [rbx+80h], 0
0x180005ab6  jz      short loc_180005AC6
0x180005ab8  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180005abc  lea     rcx, [rsp+0E8h+var_88]; this
0x180005ac1  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180005ac6  cmp     byte ptr [rbx+0C0h], 0
0x180005acd  jz      short loc_180005AE3
0x180005acf  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180005ad6  lea     rcx, [rsp+0E8h+var_48]; this
0x180005ade  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180005ae3  lea     rcx, [rsp+0E8h+var_C8]; this
0x180005ae8  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180005aed  lea     rcx, [rsp+0E8h+var_C8]; this
0x180005af2  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180005af7  mov     rsi, [rbx+108h]
0x180005afe  mov     qword ptr [rbx+108h], 0
0x180005b09  test    rsi, rsi
0x180005b0c  jz      short loc_180005B22
0x180005b0e  call    cs:__imp_GetProcessHeap
0x180005b14  mov     rcx, rax; hHeap
0x180005b17  mov     r8, rsi; lpMem
0x180005b1a  xor     edx, edx; dwFlags
0x180005b1c  call    cs:__imp_HeapFree
0x180005b22  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180005b29  call    cs:__imp_DeleteCriticalSection
0x180005b2f  lea     rcx, [rbx+8]; this
0x180005b33  lea     r11, [rsp+0E8h+var_8]
0x180005b3b  mov     rbx, [r11+10h]
0x180005b3f  mov     rsi, [r11+18h]
0x180005b43  mov     rsp, r11
0x180005b46  pop     rdi
0x180005b47  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
