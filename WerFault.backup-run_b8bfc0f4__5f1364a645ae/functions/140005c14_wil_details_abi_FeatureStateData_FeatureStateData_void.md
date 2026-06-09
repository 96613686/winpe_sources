# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x140005c14`
- end: `0x140005ce4`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000589c`

## callees

- `0x1400056d0`
- `0x140005c14`
- `0x140006088`
- `0x14000924c`
- `0x14000b8ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140005cc1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140005cc1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005cb4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005cb4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005ca6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005ca6`

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
0x140005c14  mov     [rsp+arg_0], rbx
0x140005c19  mov     [rsp+arg_8], rsi
0x140005c1e  push    rdi
0x140005c1f  sub     rsp, 0E0h
0x140005c26  mov     rbx, rcx
0x140005c29  lea     rcx, [rsp+0E8h+var_C8]; this
0x140005c2e  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140005c33  cmp     byte ptr [rbx+40h], 0
0x140005c37  jz      short loc_140005C47
0x140005c39  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x140005c3d  lea     rcx, [rsp+0E8h+var_C8]; this
0x140005c42  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140005c47  cmp     byte ptr [rbx+80h], 0
0x140005c4e  jz      short loc_140005C5E
0x140005c50  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x140005c54  lea     rcx, [rsp+0E8h+var_88]; this
0x140005c59  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140005c5e  cmp     byte ptr [rbx+0C0h], 0
0x140005c65  jz      short loc_140005C7B
0x140005c67  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x140005c6e  lea     rcx, [rsp+0E8h+var_48]; this
0x140005c76  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140005c7b  lea     rcx, [rsp+0E8h+var_C8]; this
0x140005c80  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x140005c85  lea     rcx, [rsp+0E8h+var_C8]; this
0x140005c8a  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x140005c8f  mov     rsi, [rbx+108h]
0x140005c96  mov     qword ptr [rbx+108h], 0
0x140005ca1  test    rsi, rsi
0x140005ca4  jz      short loc_140005CBA
0x140005ca6  call    cs:__imp_GetProcessHeap
0x140005cac  mov     rcx, rax; hHeap
0x140005caf  mov     r8, rsi; lpMem
0x140005cb2  xor     edx, edx; dwFlags
0x140005cb4  call    cs:__imp_HeapFree
0x140005cba  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x140005cc1  call    cs:__imp_DeleteCriticalSection
0x140005cc7  lea     rcx, [rbx+8]; this
0x140005ccb  lea     r11, [rsp+0E8h+var_8]
0x140005cd3  mov     rbx, [r11+10h]
0x140005cd7  mov     rsi, [r11+18h]
0x140005cdb  mov     rsp, r11
0x140005cde  pop     rdi
0x140005cdf  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
