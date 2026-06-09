# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x1800094b0`
- end: `0x180009580`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000916c`

## callees

- `0x180009088`
- `0x1800094b0`
- `0x1800097d4`
- `0x18000b0b0`
- `0x18000c6cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000955d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000955d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009542`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009542`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009550`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009550`

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
0x1800094b0  mov     [rsp+arg_0], rbx
0x1800094b5  mov     [rsp+arg_8], rsi
0x1800094ba  push    rdi
0x1800094bb  sub     rsp, 0E0h
0x1800094c2  mov     rbx, rcx
0x1800094c5  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800094ca  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800094cf  cmp     byte ptr [rbx+40h], 0
0x1800094d3  jz      short loc_1800094E3
0x1800094d5  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x1800094d9  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800094de  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800094e3  cmp     byte ptr [rbx+80h], 0
0x1800094ea  jz      short loc_1800094FA
0x1800094ec  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x1800094f0  lea     rcx, [rsp+0E8h+var_88]; this
0x1800094f5  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800094fa  cmp     byte ptr [rbx+0C0h], 0
0x180009501  jz      short loc_180009517
0x180009503  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000950a  lea     rcx, [rsp+0E8h+var_48]; this
0x180009512  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180009517  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000951c  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180009521  lea     rcx, [rsp+0E8h+var_C8]; this
0x180009526  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000952b  mov     rsi, [rbx+108h]
0x180009532  mov     qword ptr [rbx+108h], 0
0x18000953d  test    rsi, rsi
0x180009540  jz      short loc_180009556
0x180009542  call    cs:__imp_GetProcessHeap
0x180009548  mov     rcx, rax; hHeap
0x18000954b  mov     r8, rsi; lpMem
0x18000954e  xor     edx, edx; dwFlags
0x180009550  call    cs:__imp_HeapFree
0x180009556  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18000955d  call    cs:__imp_DeleteCriticalSection
0x180009563  lea     rcx, [rbx+8]; this
0x180009567  lea     r11, [rsp+0E8h+var_8]
0x18000956f  mov     rbx, [r11+10h]
0x180009573  mov     rsi, [r11+18h]
0x180009577  mov     rsp, r11
0x18000957a  pop     rdi
0x18000957b  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
