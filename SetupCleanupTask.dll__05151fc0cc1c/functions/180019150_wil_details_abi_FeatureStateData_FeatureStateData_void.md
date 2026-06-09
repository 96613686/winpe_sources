# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180019150`
- end: `0x180019220`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001905c`

## callees

- `0x180018ec8`
- `0x180019150`
- `0x18001963c`
- `0x180020d04`
- `0x180023450`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800191fd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800191fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800191e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800191e2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800191f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800191f0`

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
0x180019150  mov     [rsp+arg_0], rbx
0x180019155  mov     [rsp+arg_8], rsi
0x18001915a  push    rdi
0x18001915b  sub     rsp, 0E0h
0x180019162  mov     rbx, rcx
0x180019165  lea     rcx, [rsp+0E8h+var_C8]; this
0x18001916a  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18001916f  cmp     byte ptr [rbx+40h], 0
0x180019173  jz      short loc_180019183
0x180019175  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180019179  lea     rcx, [rsp+0E8h+var_C8]; this
0x18001917e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180019183  cmp     byte ptr [rbx+80h], 0
0x18001918a  jz      short loc_18001919A
0x18001918c  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180019190  lea     rcx, [rsp+0E8h+var_88]; this
0x180019195  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18001919a  cmp     byte ptr [rbx+0C0h], 0
0x1800191a1  jz      short loc_1800191B7
0x1800191a3  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x1800191aa  lea     rcx, [rsp+0E8h+var_48]; this
0x1800191b2  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800191b7  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800191bc  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x1800191c1  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800191c6  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x1800191cb  mov     rsi, [rbx+108h]
0x1800191d2  mov     qword ptr [rbx+108h], 0
0x1800191dd  test    rsi, rsi
0x1800191e0  jz      short loc_1800191F6
0x1800191e2  call    cs:__imp_GetProcessHeap
0x1800191e8  mov     r8, rsi; lpMem
0x1800191eb  xor     edx, edx; dwFlags
0x1800191ed  mov     rcx, rax; hHeap
0x1800191f0  call    cs:__imp_HeapFree
0x1800191f6  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800191fd  call    cs:__imp_DeleteCriticalSection
0x180019203  lea     rcx, [rbx+8]; this
0x180019207  lea     r11, [rsp+0E8h+var_8]
0x18001920f  mov     rbx, [r11+10h]
0x180019213  mov     rsi, [r11+18h]
0x180019217  mov     rsp, r11
0x18001921a  pop     rdi
0x18001921b  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
