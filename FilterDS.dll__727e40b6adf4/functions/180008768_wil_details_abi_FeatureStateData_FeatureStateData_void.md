# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180008768`
- end: `0x180008838`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800082b0`

## callees

- `0x180008198`
- `0x180008768`
- `0x180008a6c`
- `0x18000aa70`
- `0x18000bd6c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008815`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008815`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800087fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800087fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008808`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008808`

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
0x180008768  mov     [rsp+arg_0], rbx
0x18000876d  mov     [rsp+arg_8], rsi
0x180008772  push    rdi
0x180008773  sub     rsp, 0E0h
0x18000877a  mov     rbx, rcx
0x18000877d  lea     rcx, [rsp+0E8h+var_C8]; this
0x180008782  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180008787  cmp     byte ptr [rbx+40h], 0
0x18000878b  jz      short loc_18000879B
0x18000878d  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180008791  lea     rcx, [rsp+0E8h+var_C8]; this
0x180008796  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000879b  cmp     byte ptr [rbx+80h], 0
0x1800087a2  jz      short loc_1800087B2
0x1800087a4  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x1800087a8  lea     rcx, [rsp+0E8h+var_88]; this
0x1800087ad  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800087b2  cmp     byte ptr [rbx+0C0h], 0
0x1800087b9  jz      short loc_1800087CF
0x1800087bb  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x1800087c2  lea     rcx, [rsp+0E8h+var_48]; this
0x1800087ca  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800087cf  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800087d4  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x1800087d9  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800087de  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x1800087e3  mov     rsi, [rbx+108h]
0x1800087ea  mov     qword ptr [rbx+108h], 0
0x1800087f5  test    rsi, rsi
0x1800087f8  jz      short loc_18000880E
0x1800087fa  call    cs:__imp_GetProcessHeap
0x180008800  mov     rcx, rax; hHeap
0x180008803  mov     r8, rsi; lpMem
0x180008806  xor     edx, edx; dwFlags
0x180008808  call    cs:__imp_HeapFree
0x18000880e  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180008815  call    cs:__imp_DeleteCriticalSection
0x18000881b  lea     rcx, [rbx+8]; this
0x18000881f  lea     r11, [rsp+0E8h+var_8]
0x180008827  mov     rbx, [r11+10h]
0x18000882b  mov     rsi, [r11+18h]
0x18000882f  mov     rsp, r11
0x180008832  pop     rdi
0x180008833  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
