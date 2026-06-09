# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180012394`
- end: `0x180012464`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180014a78`

## callees

- `0x1800120dc`
- `0x180012394`
- `0x180012698`
- `0x180013be4`
- `0x180015324`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180012441`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180012441`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012434`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012434`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012426`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012426`

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
0x180012394  mov     [rsp+arg_0], rbx
0x180012399  mov     [rsp+arg_8], rsi
0x18001239e  push    rdi
0x18001239f  sub     rsp, 0E0h
0x1800123a6  mov     rbx, rcx
0x1800123a9  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800123ae  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800123b3  cmp     byte ptr [rbx+40h], 0
0x1800123b7  jz      short loc_1800123C7
0x1800123b9  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x1800123bd  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800123c2  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800123c7  cmp     byte ptr [rbx+80h], 0
0x1800123ce  jz      short loc_1800123DE
0x1800123d0  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x1800123d4  lea     rcx, [rsp+0E8h+var_88]; this
0x1800123d9  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800123de  cmp     byte ptr [rbx+0C0h], 0
0x1800123e5  jz      short loc_1800123FB
0x1800123e7  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x1800123ee  lea     rcx, [rsp+0E8h+var_48]; this
0x1800123f6  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800123fb  lea     rcx, [rsp+0E8h+var_C8]; this
0x180012400  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180012405  lea     rcx, [rsp+0E8h+var_C8]; this
0x18001240a  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18001240f  mov     rsi, [rbx+108h]
0x180012416  mov     qword ptr [rbx+108h], 0
0x180012421  test    rsi, rsi
0x180012424  jz      short loc_18001243A
0x180012426  call    cs:__imp_GetProcessHeap
0x18001242c  mov     rcx, rax; hHeap
0x18001242f  mov     r8, rsi; lpMem
0x180012432  xor     edx, edx; dwFlags
0x180012434  call    cs:__imp_HeapFree
0x18001243a  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180012441  call    cs:__imp_DeleteCriticalSection
0x180012447  lea     rcx, [rbx+8]; this
0x18001244b  lea     r11, [rsp+0E8h+var_8]
0x180012453  mov     rbx, [r11+10h]
0x180012457  mov     rsi, [r11+18h]
0x18001245b  mov     rsp, r11
0x18001245e  pop     rdi
0x18001245f  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
