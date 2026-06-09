# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x1800085cc`
- end: `0x18000869c`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800082ac`

## callees

- `0x1800080e0`
- `0x1800085cc`
- `0x180008a40`
- `0x18000b794`
- `0x18000d9a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008679`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008679`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000865e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000865e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000866c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000866c`

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
0x1800085cc  mov     [rsp+arg_0], rbx
0x1800085d1  mov     [rsp+arg_8], rsi
0x1800085d6  push    rdi
0x1800085d7  sub     rsp, 0E0h
0x1800085de  mov     rbx, rcx
0x1800085e1  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800085e6  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800085eb  cmp     byte ptr [rbx+40h], 0
0x1800085ef  jz      short loc_1800085FF
0x1800085f1  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x1800085f5  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800085fa  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800085ff  cmp     byte ptr [rbx+80h], 0
0x180008606  jz      short loc_180008616
0x180008608  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x18000860c  lea     rcx, [rsp+0E8h+var_88]; this
0x180008611  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180008616  cmp     byte ptr [rbx+0C0h], 0
0x18000861d  jz      short loc_180008633
0x18000861f  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180008626  lea     rcx, [rsp+0E8h+var_48]; this
0x18000862e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180008633  lea     rcx, [rsp+0E8h+var_C8]; this
0x180008638  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x18000863d  lea     rcx, [rsp+0E8h+var_C8]; this
0x180008642  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180008647  mov     rsi, [rbx+108h]
0x18000864e  mov     qword ptr [rbx+108h], 0
0x180008659  test    rsi, rsi
0x18000865c  jz      short loc_180008672
0x18000865e  call    cs:__imp_GetProcessHeap
0x180008664  mov     rcx, rax; hHeap
0x180008667  mov     r8, rsi; lpMem
0x18000866a  xor     edx, edx; dwFlags
0x18000866c  call    cs:__imp_HeapFree
0x180008672  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180008679  call    cs:__imp_DeleteCriticalSection
0x18000867f  lea     rcx, [rbx+8]; this
0x180008683  lea     r11, [rsp+0E8h+var_8]
0x18000868b  mov     rbx, [r11+10h]
0x18000868f  mov     rsi, [r11+18h]
0x180008693  mov     rsp, r11
0x180008696  pop     rdi
0x180008697  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
