# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180005274`
- end: `0x180005344`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800050f0`

## callees

- `0x180004800`
- `0x180005274`
- `0x180005704`
- `0x1800092e0`
- `0x18000b2a0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005314`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005314`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005306`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005306`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005321`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005321`

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
0x180005274  mov     [rsp+arg_0], rbx
0x180005279  mov     [rsp+arg_8], rsi
0x18000527e  push    rdi
0x18000527f  sub     rsp, 0E0h
0x180005286  mov     rbx, rcx
0x180005289  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000528e  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180005293  cmp     byte ptr [rbx+40h], 0
0x180005297  jz      short loc_1800052A7
0x180005299  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x18000529d  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800052a2  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800052a7  cmp     byte ptr [rbx+80h], 0
0x1800052ae  jz      short loc_1800052BE
0x1800052b0  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x1800052b4  lea     rcx, [rsp+0E8h+var_88]; this
0x1800052b9  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800052be  cmp     byte ptr [rbx+0C0h], 0
0x1800052c5  jz      short loc_1800052DB
0x1800052c7  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x1800052ce  lea     rcx, [rsp+0E8h+var_48]; this
0x1800052d6  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800052db  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800052e0  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x1800052e5  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800052ea  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x1800052ef  mov     rsi, [rbx+108h]
0x1800052f6  mov     qword ptr [rbx+108h], 0
0x180005301  test    rsi, rsi
0x180005304  jz      short loc_18000531A
0x180005306  call    cs:__imp_GetProcessHeap
0x18000530c  mov     rcx, rax; hHeap
0x18000530f  mov     r8, rsi; lpMem
0x180005312  xor     edx, edx; dwFlags
0x180005314  call    cs:__imp_HeapFree
0x18000531a  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180005321  call    cs:__imp_DeleteCriticalSection
0x180005327  lea     rcx, [rbx+8]; this
0x18000532b  lea     r11, [rsp+0E8h+var_8]
0x180005333  mov     rbx, [r11+10h]
0x180005337  mov     rsi, [r11+18h]
0x18000533b  mov     rsp, r11
0x18000533e  pop     rdi
0x18000533f  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
