# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180010890`
- end: `0x180010960`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800102c0`

## callees

- `0x18000fb04`
- `0x180010890`
- `0x180010c78`
- `0x18001674c`
- `0x18001c44c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001093d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001093d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010922`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010922`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010930`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010930`

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
0x180010890  mov     [rsp+arg_0], rbx
0x180010895  mov     [rsp+arg_8], rsi
0x18001089a  push    rdi
0x18001089b  sub     rsp, 0E0h
0x1800108a2  mov     rbx, rcx
0x1800108a5  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800108aa  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800108af  cmp     byte ptr [rbx+40h], 0
0x1800108b3  jz      short loc_1800108C3
0x1800108b5  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x1800108b9  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800108be  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800108c3  cmp     byte ptr [rbx+80h], 0
0x1800108ca  jz      short loc_1800108DA
0x1800108cc  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x1800108d0  lea     rcx, [rsp+0E8h+var_88]; this
0x1800108d5  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800108da  cmp     byte ptr [rbx+0C0h], 0
0x1800108e1  jz      short loc_1800108F7
0x1800108e3  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x1800108ea  lea     rcx, [rsp+0E8h+var_48]; this
0x1800108f2  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800108f7  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800108fc  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180010901  lea     rcx, [rsp+0E8h+var_C8]; this
0x180010906  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18001090b  mov     rsi, [rbx+108h]
0x180010912  mov     qword ptr [rbx+108h], 0
0x18001091d  test    rsi, rsi
0x180010920  jz      short loc_180010936
0x180010922  call    cs:__imp_GetProcessHeap
0x180010928  mov     rcx, rax; hHeap
0x18001092b  mov     r8, rsi; lpMem
0x18001092e  xor     edx, edx; dwFlags
0x180010930  call    cs:__imp_HeapFree
0x180010936  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18001093d  call    cs:__imp_DeleteCriticalSection
0x180010943  lea     rcx, [rbx+8]; this
0x180010947  lea     r11, [rsp+0E8h+var_8]
0x18001094f  mov     rbx, [r11+10h]
0x180010953  mov     rsi, [r11+18h]
0x180010957  mov     rsp, r11
0x18001095a  pop     rdi
0x18001095b  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
