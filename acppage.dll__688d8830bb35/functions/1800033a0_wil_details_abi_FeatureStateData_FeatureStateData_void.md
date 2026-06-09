# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x1800033a0`
- end: `0x180003470`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800030b4`

## callees

- `0x180002f20`
- `0x1800033a0`
- `0x1800036f0`
- `0x180006118`
- `0x180007918`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180003440`
- `KERNEL32!HeapFree` at `0x180003440`
- `KERNEL32!DeleteCriticalSection` at `0x18000344d`
- `KERNEL32!DeleteCriticalSection` at `0x18000344d`
- `KERNEL32!GetProcessHeap` at `0x180003432`
- `KERNEL32!GetProcessHeap` at `0x180003432`

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
0x1800033a0  mov     [rsp+arg_0], rbx
0x1800033a5  mov     [rsp+arg_8], rsi
0x1800033aa  push    rdi
0x1800033ab  sub     rsp, 0E0h
0x1800033b2  mov     rbx, rcx
0x1800033b5  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800033ba  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800033bf  cmp     byte ptr [rbx+40h], 0
0x1800033c3  jz      short loc_1800033D3
0x1800033c5  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x1800033c9  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800033ce  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800033d3  cmp     byte ptr [rbx+80h], 0
0x1800033da  jz      short loc_1800033EA
0x1800033dc  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x1800033e0  lea     rcx, [rsp+0E8h+var_88]; this
0x1800033e5  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800033ea  cmp     byte ptr [rbx+0C0h], 0
0x1800033f1  jz      short loc_180003407
0x1800033f3  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x1800033fa  lea     rcx, [rsp+0E8h+var_48]; this
0x180003402  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180003407  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000340c  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180003411  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003416  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000341b  mov     rsi, [rbx+108h]
0x180003422  mov     qword ptr [rbx+108h], 0
0x18000342d  test    rsi, rsi
0x180003430  jz      short loc_180003446
0x180003432  call    cs:__imp_GetProcessHeap
0x180003438  mov     r8, rsi; lpMem
0x18000343b  xor     edx, edx; dwFlags
0x18000343d  mov     rcx, rax; hHeap
0x180003440  call    cs:__imp_HeapFree
0x180003446  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18000344d  call    cs:__imp_DeleteCriticalSection
0x180003453  lea     rcx, [rbx+8]; this
0x180003457  lea     r11, [rsp+0E8h+var_8]
0x18000345f  mov     rbx, [r11+10h]
0x180003463  mov     rsi, [r11+18h]
0x180003467  mov     rsp, r11
0x18000346a  pop     rdi
0x18000346b  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
