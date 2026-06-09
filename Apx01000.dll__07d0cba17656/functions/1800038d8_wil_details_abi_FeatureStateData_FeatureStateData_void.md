# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x1800038d8`
- end: `0x1800039a8`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180003660`

## callees

- `0x180003494`
- `0x1800038d8`
- `0x180003d4c`
- `0x1800065dc`
- `0x180008624`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003985`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003985`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003978`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003978`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000396a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000396a`

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
0x1800038d8  mov     [rsp+arg_0], rbx
0x1800038dd  mov     [rsp+arg_8], rsi
0x1800038e2  push    rdi
0x1800038e3  sub     rsp, 0E0h
0x1800038ea  mov     rbx, rcx
0x1800038ed  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800038f2  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800038f7  cmp     byte ptr [rbx+40h], 0
0x1800038fb  jz      short loc_18000390B
0x1800038fd  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180003901  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003906  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000390b  cmp     byte ptr [rbx+80h], 0
0x180003912  jz      short loc_180003922
0x180003914  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180003918  lea     rcx, [rsp+0E8h+var_88]; this
0x18000391d  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180003922  cmp     byte ptr [rbx+0C0h], 0
0x180003929  jz      short loc_18000393F
0x18000392b  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180003932  lea     rcx, [rsp+0E8h+var_48]; this
0x18000393a  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000393f  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003944  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180003949  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000394e  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180003953  mov     rsi, [rbx+108h]
0x18000395a  mov     qword ptr [rbx+108h], 0
0x180003965  test    rsi, rsi
0x180003968  jz      short loc_18000397E
0x18000396a  call    cs:__imp_GetProcessHeap
0x180003970  mov     rcx, rax; hHeap
0x180003973  mov     r8, rsi; lpMem
0x180003976  xor     edx, edx; dwFlags
0x180003978  call    cs:__imp_HeapFree
0x18000397e  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180003985  call    cs:__imp_DeleteCriticalSection
0x18000398b  lea     rcx, [rbx+8]; this
0x18000398f  lea     r11, [rsp+0E8h+var_8]
0x180003997  mov     rbx, [r11+10h]
0x18000399b  mov     rsi, [r11+18h]
0x18000399f  mov     rsp, r11
0x1800039a2  pop     rdi
0x1800039a3  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
