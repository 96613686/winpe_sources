# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x18001103c`
- end: `0x18001110c`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180010da0`

## callees

- `0x180010cd8`
- `0x18001103c`
- `0x180011340`
- `0x18001428c`
- `0x180015c2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800110e9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800110e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800110ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800110ce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800110dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800110dc`

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
0x18001103c  mov     [rsp+arg_0], rbx
0x180011041  mov     [rsp+arg_8], rsi
0x180011046  push    rdi
0x180011047  sub     rsp, 0E0h
0x18001104e  mov     rbx, rcx
0x180011051  lea     rcx, [rsp+0E8h+var_C8]; this
0x180011056  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18001105b  cmp     byte ptr [rbx+40h], 0
0x18001105f  jz      short loc_18001106F
0x180011061  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180011065  lea     rcx, [rsp+0E8h+var_C8]; this
0x18001106a  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18001106f  cmp     byte ptr [rbx+80h], 0
0x180011076  jz      short loc_180011086
0x180011078  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x18001107c  lea     rcx, [rsp+0E8h+var_88]; this
0x180011081  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180011086  cmp     byte ptr [rbx+0C0h], 0
0x18001108d  jz      short loc_1800110A3
0x18001108f  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180011096  lea     rcx, [rsp+0E8h+var_48]; this
0x18001109e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800110a3  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800110a8  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x1800110ad  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800110b2  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x1800110b7  mov     rsi, [rbx+108h]
0x1800110be  mov     qword ptr [rbx+108h], 0
0x1800110c9  test    rsi, rsi
0x1800110cc  jz      short loc_1800110E2
0x1800110ce  call    cs:__imp_GetProcessHeap
0x1800110d4  mov     rcx, rax; hHeap
0x1800110d7  mov     r8, rsi; lpMem
0x1800110da  xor     edx, edx; dwFlags
0x1800110dc  call    cs:__imp_HeapFree
0x1800110e2  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800110e9  call    cs:__imp_DeleteCriticalSection
0x1800110ef  lea     rcx, [rbx+8]; this
0x1800110f3  lea     r11, [rsp+0E8h+var_8]
0x1800110fb  mov     rbx, [r11+10h]
0x1800110ff  mov     rsi, [r11+18h]
0x180011103  mov     rsp, r11
0x180011106  pop     rdi
0x180011107  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
