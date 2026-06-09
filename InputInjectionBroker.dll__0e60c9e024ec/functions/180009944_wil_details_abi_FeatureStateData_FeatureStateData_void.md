# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180009944`
- end: `0x180009a14`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800097e4`

## callees

- `0x18000971c`
- `0x180009944`
- `0x180009d24`
- `0x18000cf90`
- `0x18000e1f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800099f1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800099f1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800099d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800099d6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800099e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800099e4`

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
0x180009944  mov     [rsp+arg_0], rbx
0x180009949  mov     [rsp+arg_8], rsi
0x18000994e  push    rdi
0x18000994f  sub     rsp, 0E0h
0x180009956  mov     rbx, rcx
0x180009959  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000995e  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180009963  cmp     byte ptr [rbx+40h], 0
0x180009967  jz      short loc_180009977
0x180009969  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x18000996d  lea     rcx, [rsp+0E8h+var_C8]; this
0x180009972  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180009977  cmp     byte ptr [rbx+80h], 0
0x18000997e  jz      short loc_18000998E
0x180009980  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180009984  lea     rcx, [rsp+0E8h+var_88]; this
0x180009989  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000998e  cmp     byte ptr [rbx+0C0h], 0
0x180009995  jz      short loc_1800099AB
0x180009997  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000999e  lea     rcx, [rsp+0E8h+var_48]; this
0x1800099a6  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800099ab  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800099b0  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x1800099b5  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800099ba  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x1800099bf  mov     rsi, [rbx+108h]
0x1800099c6  mov     qword ptr [rbx+108h], 0
0x1800099d1  test    rsi, rsi
0x1800099d4  jz      short loc_1800099EA
0x1800099d6  call    cs:__imp_GetProcessHeap
0x1800099dc  mov     rcx, rax; hHeap
0x1800099df  mov     r8, rsi; lpMem
0x1800099e2  xor     edx, edx; dwFlags
0x1800099e4  call    cs:__imp_HeapFree
0x1800099ea  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800099f1  call    cs:__imp_DeleteCriticalSection
0x1800099f7  lea     rcx, [rbx+8]; this
0x1800099fb  lea     r11, [rsp+0E8h+var_8]
0x180009a03  mov     rbx, [r11+10h]
0x180009a07  mov     rsi, [r11+18h]
0x180009a0b  mov     rsp, r11
0x180009a0e  pop     rdi
0x180009a0f  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
