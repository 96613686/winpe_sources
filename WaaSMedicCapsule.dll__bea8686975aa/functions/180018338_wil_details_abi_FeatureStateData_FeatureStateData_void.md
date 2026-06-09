# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180018338`
- end: `0x180018408`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180018220`

## callees

- `0x180018158`
- `0x180018338`
- `0x18001863c`
- `0x180019a40`
- `0x18001ab80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800183e5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800183e5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800183d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800183d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800183ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800183ca`

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
0x180018338  mov     [rsp+arg_0], rbx
0x18001833d  mov     [rsp+arg_8], rsi
0x180018342  push    rdi
0x180018343  sub     rsp, 0E0h
0x18001834a  mov     rbx, rcx
0x18001834d  lea     rcx, [rsp+0E8h+var_C8]; this
0x180018352  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180018357  cmp     byte ptr [rbx+40h], 0
0x18001835b  jz      short loc_18001836B
0x18001835d  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180018361  lea     rcx, [rsp+0E8h+var_C8]; this
0x180018366  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18001836b  cmp     byte ptr [rbx+80h], 0
0x180018372  jz      short loc_180018382
0x180018374  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180018378  lea     rcx, [rsp+0E8h+var_88]; this
0x18001837d  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180018382  cmp     byte ptr [rbx+0C0h], 0
0x180018389  jz      short loc_18001839F
0x18001838b  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180018392  lea     rcx, [rsp+0E8h+var_48]; this
0x18001839a  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18001839f  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800183a4  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x1800183a9  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800183ae  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x1800183b3  mov     rsi, [rbx+108h]
0x1800183ba  mov     qword ptr [rbx+108h], 0
0x1800183c5  test    rsi, rsi
0x1800183c8  jz      short loc_1800183DE
0x1800183ca  call    cs:__imp_GetProcessHeap
0x1800183d0  mov     rcx, rax; hHeap
0x1800183d3  mov     r8, rsi; lpMem
0x1800183d6  xor     edx, edx; dwFlags
0x1800183d8  call    cs:__imp_HeapFree
0x1800183de  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800183e5  call    cs:__imp_DeleteCriticalSection
0x1800183eb  lea     rcx, [rbx+8]; this
0x1800183ef  lea     r11, [rsp+0E8h+var_8]
0x1800183f7  mov     rbx, [r11+10h]
0x1800183fb  mov     rsi, [r11+18h]
0x1800183ff  mov     rsp, r11
0x180018402  pop     rdi
0x180018403  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
