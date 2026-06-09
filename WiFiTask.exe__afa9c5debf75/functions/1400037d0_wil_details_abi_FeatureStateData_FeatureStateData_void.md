# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x1400037d0`
- end: `0x1400038a0`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140003440`

## callees

- `0x1400031c4`
- `0x1400037d0`
- `0x140003c44`
- `0x140008334`
- `0x14000ab6c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000387d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000387d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003870`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003870`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003862`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003862`

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
0x1400037d0  mov     [rsp+arg_0], rbx
0x1400037d5  mov     [rsp+arg_8], rsi
0x1400037da  push    rdi
0x1400037db  sub     rsp, 0E0h
0x1400037e2  mov     rbx, rcx
0x1400037e5  lea     rcx, [rsp+0E8h+var_C8]; this
0x1400037ea  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1400037ef  cmp     byte ptr [rbx+40h], 0
0x1400037f3  jz      short loc_140003803
0x1400037f5  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x1400037f9  lea     rcx, [rsp+0E8h+var_C8]; this
0x1400037fe  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140003803  cmp     byte ptr [rbx+80h], 0
0x14000380a  jz      short loc_14000381A
0x14000380c  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x140003810  lea     rcx, [rsp+0E8h+var_88]; this
0x140003815  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000381a  cmp     byte ptr [rbx+0C0h], 0
0x140003821  jz      short loc_140003837
0x140003823  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x14000382a  lea     rcx, [rsp+0E8h+var_48]; this
0x140003832  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140003837  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000383c  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x140003841  lea     rcx, [rsp+0E8h+var_C8]; this
0x140003846  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x14000384b  mov     rsi, [rbx+108h]
0x140003852  mov     qword ptr [rbx+108h], 0
0x14000385d  test    rsi, rsi
0x140003860  jz      short loc_140003876
0x140003862  call    cs:__imp_GetProcessHeap
0x140003868  mov     rcx, rax; hHeap
0x14000386b  mov     r8, rsi; lpMem
0x14000386e  xor     edx, edx; dwFlags
0x140003870  call    cs:__imp_HeapFree
0x140003876  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x14000387d  call    cs:__imp_DeleteCriticalSection
0x140003883  lea     rcx, [rbx+8]; this
0x140003887  lea     r11, [rsp+0E8h+var_8]
0x14000388f  mov     rbx, [r11+10h]
0x140003893  mov     rsi, [r11+18h]
0x140003897  mov     rsp, r11
0x14000389a  pop     rdi
0x14000389b  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
