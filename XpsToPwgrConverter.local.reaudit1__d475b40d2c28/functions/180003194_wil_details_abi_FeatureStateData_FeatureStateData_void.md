# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180003194`
- end: `0x180003264`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000307c`

## callees

- `0x180002eb0`
- `0x180003194`
- `0x180003608`
- `0x180005c88`
- `0x180007b08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003241`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003241`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003234`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003234`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003226`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003226`

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
0x180003194  mov     [rsp+arg_0], rbx
0x180003199  mov     [rsp+arg_8], rsi
0x18000319e  push    rdi
0x18000319f  sub     rsp, 0E0h
0x1800031a6  mov     rbx, rcx
0x1800031a9  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800031ae  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800031b3  cmp     byte ptr [rbx+40h], 0
0x1800031b7  jz      short loc_1800031C7
0x1800031b9  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x1800031bd  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800031c2  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800031c7  cmp     byte ptr [rbx+80h], 0
0x1800031ce  jz      short loc_1800031DE
0x1800031d0  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x1800031d4  lea     rcx, [rsp+0E8h+var_88]; this
0x1800031d9  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800031de  cmp     byte ptr [rbx+0C0h], 0
0x1800031e5  jz      short loc_1800031FB
0x1800031e7  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x1800031ee  lea     rcx, [rsp+0E8h+var_48]; this
0x1800031f6  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800031fb  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003200  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180003205  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000320a  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000320f  mov     rsi, [rbx+108h]
0x180003216  mov     qword ptr [rbx+108h], 0
0x180003221  test    rsi, rsi
0x180003224  jz      short loc_18000323A
0x180003226  call    cs:__imp_GetProcessHeap
0x18000322c  mov     rcx, rax; hHeap
0x18000322f  mov     r8, rsi; lpMem
0x180003232  xor     edx, edx; dwFlags
0x180003234  call    cs:__imp_HeapFree
0x18000323a  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180003241  call    cs:__imp_DeleteCriticalSection
0x180003247  lea     rcx, [rbx+8]; this
0x18000324b  lea     r11, [rsp+0E8h+var_8]
0x180003253  mov     rbx, [r11+10h]
0x180003257  mov     rsi, [r11+18h]
0x18000325b  mov     rsp, r11
0x18000325e  pop     rdi
0x18000325f  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
