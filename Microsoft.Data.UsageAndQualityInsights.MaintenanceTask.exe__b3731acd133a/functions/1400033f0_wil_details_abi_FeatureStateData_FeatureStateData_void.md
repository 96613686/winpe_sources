# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x1400033f0`
- end: `0x1400034c0`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140003178`

## callees

- `0x140002fac`
- `0x1400033f0`
- `0x140003864`
- `0x1400060fc`
- `0x140008144`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000349d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000349d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003482`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003482`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003490`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003490`

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
0x1400033f0  mov     [rsp+arg_0], rbx
0x1400033f5  mov     [rsp+arg_8], rsi
0x1400033fa  push    rdi
0x1400033fb  sub     rsp, 0E0h
0x140003402  mov     rbx, rcx
0x140003405  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000340a  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x14000340f  cmp     byte ptr [rbx+40h], 0
0x140003413  jz      short loc_140003423
0x140003415  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x140003419  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000341e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140003423  cmp     byte ptr [rbx+80h], 0
0x14000342a  jz      short loc_14000343A
0x14000342c  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x140003430  lea     rcx, [rsp+0E8h+var_88]; this
0x140003435  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000343a  cmp     byte ptr [rbx+0C0h], 0
0x140003441  jz      short loc_140003457
0x140003443  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x14000344a  lea     rcx, [rsp+0E8h+var_48]; this
0x140003452  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140003457  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000345c  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x140003461  lea     rcx, [rsp+0E8h+var_C8]; this
0x140003466  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x14000346b  mov     rsi, [rbx+108h]
0x140003472  mov     qword ptr [rbx+108h], 0
0x14000347d  test    rsi, rsi
0x140003480  jz      short loc_140003496
0x140003482  call    cs:__imp_GetProcessHeap
0x140003488  mov     rcx, rax; hHeap
0x14000348b  mov     r8, rsi; lpMem
0x14000348e  xor     edx, edx; dwFlags
0x140003490  call    cs:__imp_HeapFree
0x140003496  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x14000349d  call    cs:__imp_DeleteCriticalSection
0x1400034a3  lea     rcx, [rbx+8]; this
0x1400034a7  lea     r11, [rsp+0E8h+var_8]
0x1400034af  mov     rbx, [r11+10h]
0x1400034b3  mov     rsi, [r11+18h]
0x1400034b7  mov     rsp, r11
0x1400034ba  pop     rdi
0x1400034bb  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
