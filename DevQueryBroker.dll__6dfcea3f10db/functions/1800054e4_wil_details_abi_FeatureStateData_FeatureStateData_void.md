# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x1800054e4`
- end: `0x1800055b4`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800053f0`

## callees

- `0x18000525c`
- `0x1800054e4`
- `0x180005834`
- `0x180007d7c`
- `0x180009400`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005591`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005591`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005584`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005584`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005576`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005576`

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
0x1800054e4  mov     [rsp+arg_0], rbx
0x1800054e9  mov     [rsp+arg_8], rsi
0x1800054ee  push    rdi
0x1800054ef  sub     rsp, 0E0h
0x1800054f6  mov     rbx, rcx
0x1800054f9  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800054fe  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180005503  cmp     byte ptr [rbx+40h], 0
0x180005507  jz      short loc_180005517
0x180005509  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x18000550d  lea     rcx, [rsp+0E8h+var_C8]; this
0x180005512  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180005517  cmp     byte ptr [rbx+80h], 0
0x18000551e  jz      short loc_18000552E
0x180005520  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180005524  lea     rcx, [rsp+0E8h+var_88]; this
0x180005529  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000552e  cmp     byte ptr [rbx+0C0h], 0
0x180005535  jz      short loc_18000554B
0x180005537  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000553e  lea     rcx, [rsp+0E8h+var_48]; this
0x180005546  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000554b  lea     rcx, [rsp+0E8h+var_C8]; this
0x180005550  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180005555  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000555a  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000555f  mov     rsi, [rbx+108h]
0x180005566  mov     qword ptr [rbx+108h], 0
0x180005571  test    rsi, rsi
0x180005574  jz      short loc_18000558A
0x180005576  call    cs:__imp_GetProcessHeap
0x18000557c  mov     r8, rsi; lpMem
0x18000557f  xor     edx, edx; dwFlags
0x180005581  mov     rcx, rax; hHeap
0x180005584  call    cs:__imp_HeapFree
0x18000558a  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180005591  call    cs:__imp_DeleteCriticalSection
0x180005597  lea     rcx, [rbx+8]; this
0x18000559b  lea     r11, [rsp+0E8h+var_8]
0x1800055a3  mov     rbx, [r11+10h]
0x1800055a7  mov     rsi, [r11+18h]
0x1800055ab  mov     rsp, r11
0x1800055ae  pop     rdi
0x1800055af  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
