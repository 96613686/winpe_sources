# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180007744`
- end: `0x180007814`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180007610`

## callees

- `0x180007548`
- `0x180007744`
- `0x180007a48`
- `0x180008ee4`
- `0x18000a52c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800077f1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800077f1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800077d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800077d6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800077e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800077e4`

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
0x180007744  mov     [rsp+arg_0], rbx
0x180007749  mov     [rsp+arg_8], rsi
0x18000774e  push    rdi
0x18000774f  sub     rsp, 0E0h
0x180007756  mov     rbx, rcx
0x180007759  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000775e  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180007763  cmp     byte ptr [rbx+40h], 0
0x180007767  jz      short loc_180007777
0x180007769  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x18000776d  lea     rcx, [rsp+0E8h+var_C8]; this
0x180007772  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180007777  cmp     byte ptr [rbx+80h], 0
0x18000777e  jz      short loc_18000778E
0x180007780  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180007784  lea     rcx, [rsp+0E8h+var_88]; this
0x180007789  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000778e  cmp     byte ptr [rbx+0C0h], 0
0x180007795  jz      short loc_1800077AB
0x180007797  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000779e  lea     rcx, [rsp+0E8h+var_48]; this
0x1800077a6  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800077ab  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800077b0  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x1800077b5  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800077ba  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x1800077bf  mov     rsi, [rbx+108h]
0x1800077c6  mov     qword ptr [rbx+108h], 0
0x1800077d1  test    rsi, rsi
0x1800077d4  jz      short loc_1800077EA
0x1800077d6  call    cs:__imp_GetProcessHeap
0x1800077dc  mov     rcx, rax; hHeap
0x1800077df  mov     r8, rsi; lpMem
0x1800077e2  xor     edx, edx; dwFlags
0x1800077e4  call    cs:__imp_HeapFree
0x1800077ea  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800077f1  call    cs:__imp_DeleteCriticalSection
0x1800077f7  lea     rcx, [rbx+8]; this
0x1800077fb  lea     r11, [rsp+0E8h+var_8]
0x180007803  mov     rbx, [r11+10h]
0x180007807  mov     rsi, [r11+18h]
0x18000780b  mov     rsp, r11
0x18000780e  pop     rdi
0x18000780f  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
