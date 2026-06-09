# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x1800e6470`
- end: `0x1800e6540`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800e61b8`

## callees

- `0x1800e5fec`
- `0x1800e6470`
- `0x1800e68e4`
- `0x1800e94dc`
- `0x1800eba60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800e651d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800e651d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800e6502`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800e6502`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e6510`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800e6510`

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
0x1800e6470  mov     [rsp+arg_0], rbx
0x1800e6475  mov     [rsp+arg_8], rsi
0x1800e647a  push    rdi
0x1800e647b  sub     rsp, 0E0h
0x1800e6482  mov     rbx, rcx
0x1800e6485  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800e648a  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800e648f  cmp     byte ptr [rbx+40h], 0
0x1800e6493  jz      short loc_1800E64A3
0x1800e6495  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x1800e6499  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800e649e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800e64a3  cmp     byte ptr [rbx+80h], 0
0x1800e64aa  jz      short loc_1800E64BA
0x1800e64ac  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x1800e64b0  lea     rcx, [rsp+0E8h+var_88]; this
0x1800e64b5  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800e64ba  cmp     byte ptr [rbx+0C0h], 0
0x1800e64c1  jz      short loc_1800E64D7
0x1800e64c3  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x1800e64ca  lea     rcx, [rsp+0E8h+var_48]; this
0x1800e64d2  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800e64d7  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800e64dc  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x1800e64e1  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800e64e6  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x1800e64eb  mov     rsi, [rbx+108h]
0x1800e64f2  mov     qword ptr [rbx+108h], 0
0x1800e64fd  test    rsi, rsi
0x1800e6500  jz      short loc_1800E6516
0x1800e6502  call    cs:__imp_GetProcessHeap
0x1800e6508  mov     rcx, rax; hHeap
0x1800e650b  mov     r8, rsi; lpMem
0x1800e650e  xor     edx, edx; dwFlags
0x1800e6510  call    cs:__imp_HeapFree
0x1800e6516  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800e651d  call    cs:__imp_DeleteCriticalSection
0x1800e6523  lea     rcx, [rbx+8]; this
0x1800e6527  lea     r11, [rsp+0E8h+var_8]
0x1800e652f  mov     rbx, [r11+10h]
0x1800e6533  mov     rsi, [r11+18h]
0x1800e6537  mov     rsp, r11
0x1800e653a  pop     rdi
0x1800e653b  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
