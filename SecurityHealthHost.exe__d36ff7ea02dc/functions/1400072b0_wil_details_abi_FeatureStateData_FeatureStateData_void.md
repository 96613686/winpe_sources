# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x1400072b0`
- end: `0x140007380`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140007198`

## callees

- `0x140007004`
- `0x1400072b0`
- `0x140007724`
- `0x140009574`
- `0x14000b254`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14000735d`
- `KERNEL32!DeleteCriticalSection` at `0x14000735d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007342`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007342`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007350`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007350`

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
0x1400072b0  mov     [rsp+arg_0], rbx
0x1400072b5  mov     [rsp+arg_8], rsi
0x1400072ba  push    rdi
0x1400072bb  sub     rsp, 0E0h
0x1400072c2  mov     rbx, rcx
0x1400072c5  lea     rcx, [rsp+0E8h+var_C8]; this
0x1400072ca  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1400072cf  cmp     byte ptr [rbx+40h], 0
0x1400072d3  jz      short loc_1400072E3
0x1400072d5  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x1400072d9  lea     rcx, [rsp+0E8h+var_C8]; this
0x1400072de  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1400072e3  cmp     byte ptr [rbx+80h], 0
0x1400072ea  jz      short loc_1400072FA
0x1400072ec  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x1400072f0  lea     rcx, [rsp+0E8h+var_88]; this
0x1400072f5  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1400072fa  cmp     byte ptr [rbx+0C0h], 0
0x140007301  jz      short loc_140007317
0x140007303  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x14000730a  lea     rcx, [rsp+0E8h+var_48]; this
0x140007312  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140007317  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000731c  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x140007321  lea     rcx, [rsp+0E8h+var_C8]; this
0x140007326  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x14000732b  mov     rsi, [rbx+108h]
0x140007332  mov     qword ptr [rbx+108h], 0
0x14000733d  test    rsi, rsi
0x140007340  jz      short loc_140007356
0x140007342  call    cs:__imp_GetProcessHeap
0x140007348  mov     rcx, rax; hHeap
0x14000734b  mov     r8, rsi; lpMem
0x14000734e  xor     edx, edx; dwFlags
0x140007350  call    cs:__imp_HeapFree
0x140007356  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x14000735d  call    cs:__imp_DeleteCriticalSection
0x140007363  lea     rcx, [rbx+8]; this
0x140007367  lea     r11, [rsp+0E8h+var_8]
0x14000736f  mov     rbx, [r11+10h]
0x140007373  mov     rsi, [r11+18h]
0x140007377  mov     rsp, r11
0x14000737a  pop     rdi
0x14000737b  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
