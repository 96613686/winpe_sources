# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x1800082bc`
- end: `0x18000838c`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180008104`

## callees

- `0x18000800c`
- `0x1800082bc`
- `0x1800085c0`
- `0x18000a9ac`
- `0x18000c4dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008369`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008369`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000835c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000835c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000834e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000834e`

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
0x1800082bc  mov     [rsp+arg_0], rbx
0x1800082c1  mov     [rsp+arg_8], rsi
0x1800082c6  push    rdi
0x1800082c7  sub     rsp, 0E0h
0x1800082ce  mov     rbx, rcx
0x1800082d1  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800082d6  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800082db  cmp     byte ptr [rbx+40h], 0
0x1800082df  jz      short loc_1800082EF
0x1800082e1  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x1800082e5  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800082ea  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800082ef  cmp     byte ptr [rbx+80h], 0
0x1800082f6  jz      short loc_180008306
0x1800082f8  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x1800082fc  lea     rcx, [rsp+0E8h+var_88]; this
0x180008301  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180008306  cmp     byte ptr [rbx+0C0h], 0
0x18000830d  jz      short loc_180008323
0x18000830f  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180008316  lea     rcx, [rsp+0E8h+var_48]; this
0x18000831e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180008323  lea     rcx, [rsp+0E8h+var_C8]; this
0x180008328  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x18000832d  lea     rcx, [rsp+0E8h+var_C8]; this
0x180008332  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180008337  mov     rsi, [rbx+108h]
0x18000833e  mov     qword ptr [rbx+108h], 0
0x180008349  test    rsi, rsi
0x18000834c  jz      short loc_180008362
0x18000834e  call    cs:__imp_GetProcessHeap
0x180008354  mov     rcx, rax; hHeap
0x180008357  mov     r8, rsi; lpMem
0x18000835a  xor     edx, edx; dwFlags
0x18000835c  call    cs:__imp_HeapFree
0x180008362  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180008369  call    cs:__imp_DeleteCriticalSection
0x18000836f  lea     rcx, [rbx+8]; this
0x180008373  lea     r11, [rsp+0E8h+var_8]
0x18000837b  mov     rbx, [r11+10h]
0x18000837f  mov     rsi, [r11+18h]
0x180008383  mov     rsp, r11
0x180008386  pop     rdi
0x180008387  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
