# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x18002819c`
- end: `0x18002826c`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180027e84`

## callees

- `0x180027bfc`
- `0x18002819c`
- `0x1800287d8`
- `0x18002c4b8`
- `0x18002f104`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180028249`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180028249`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002823c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002823c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002822e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002822e`

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
0x18002819c  mov     [rsp+arg_0], rbx
0x1800281a1  mov     [rsp+arg_8], rsi
0x1800281a6  push    rdi
0x1800281a7  sub     rsp, 0E0h
0x1800281ae  mov     rbx, rcx
0x1800281b1  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800281b6  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800281bb  cmp     byte ptr [rbx+40h], 0
0x1800281bf  jz      short loc_1800281CF
0x1800281c1  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x1800281c5  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800281ca  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800281cf  cmp     byte ptr [rbx+80h], 0
0x1800281d6  jz      short loc_1800281E6
0x1800281d8  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x1800281dc  lea     rcx, [rsp+0E8h+var_88]; this
0x1800281e1  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800281e6  cmp     byte ptr [rbx+0C0h], 0
0x1800281ed  jz      short loc_180028203
0x1800281ef  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x1800281f6  lea     rcx, [rsp+0E8h+var_48]; this
0x1800281fe  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180028203  lea     rcx, [rsp+0E8h+var_C8]; this
0x180028208  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x18002820d  lea     rcx, [rsp+0E8h+var_C8]; this
0x180028212  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180028217  mov     rsi, [rbx+108h]
0x18002821e  mov     qword ptr [rbx+108h], 0
0x180028229  test    rsi, rsi
0x18002822c  jz      short loc_180028242
0x18002822e  call    cs:__imp_GetProcessHeap
0x180028234  mov     rcx, rax; hHeap
0x180028237  mov     r8, rsi; lpMem
0x18002823a  xor     edx, edx; dwFlags
0x18002823c  call    cs:__imp_HeapFree
0x180028242  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180028249  call    cs:__imp_DeleteCriticalSection
0x18002824f  lea     rcx, [rbx+8]; this
0x180028253  lea     r11, [rsp+0E8h+var_8]
0x18002825b  mov     rbx, [r11+10h]
0x18002825f  mov     rsi, [r11+18h]
0x180028263  mov     rsp, r11
0x180028266  pop     rdi
0x180028267  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
