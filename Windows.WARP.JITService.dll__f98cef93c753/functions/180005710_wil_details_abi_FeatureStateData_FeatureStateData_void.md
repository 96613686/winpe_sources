# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180005710`
- end: `0x1800057e0`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180007bf4`

## callees

- `0x1800044ec`
- `0x18000531c`
- `0x1800053e4`
- `0x180005710`
- `0x180005880`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800057bd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800057bd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800057b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800057b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800057a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800057a2`

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
0x180005710  mov     [rsp+arg_0], rbx
0x180005715  mov     [rsp+arg_8], rsi
0x18000571a  push    rdi
0x18000571b  sub     rsp, 0E0h
0x180005722  mov     rbx, rcx
0x180005725  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000572a  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000572f  cmp     byte ptr [rbx+40h], 0
0x180005733  jz      short loc_180005743
0x180005735  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180005739  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000573e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180005743  cmp     byte ptr [rbx+80h], 0
0x18000574a  jz      short loc_18000575A
0x18000574c  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180005750  lea     rcx, [rsp+0E8h+var_88]; this
0x180005755  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000575a  cmp     byte ptr [rbx+0C0h], 0
0x180005761  jz      short loc_180005777
0x180005763  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000576a  lea     rcx, [rsp+0E8h+var_48]; this
0x180005772  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180005777  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000577c  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180005781  lea     rcx, [rsp+0E8h+var_C8]; this
0x180005786  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000578b  mov     rsi, [rbx+108h]
0x180005792  mov     qword ptr [rbx+108h], 0
0x18000579d  test    rsi, rsi
0x1800057a0  jz      short loc_1800057B6
0x1800057a2  call    cs:__imp_GetProcessHeap
0x1800057a8  mov     rcx, rax; hHeap
0x1800057ab  mov     r8, rsi; lpMem
0x1800057ae  xor     edx, edx; dwFlags
0x1800057b0  call    cs:__imp_HeapFree
0x1800057b6  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800057bd  call    cs:__imp_DeleteCriticalSection
0x1800057c3  lea     rcx, [rbx+8]; this
0x1800057c7  lea     r11, [rsp+0E8h+var_8]
0x1800057cf  mov     rbx, [r11+10h]
0x1800057d3  mov     rsi, [r11+18h]
0x1800057d7  mov     rsp, r11
0x1800057da  pop     rdi
0x1800057db  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
