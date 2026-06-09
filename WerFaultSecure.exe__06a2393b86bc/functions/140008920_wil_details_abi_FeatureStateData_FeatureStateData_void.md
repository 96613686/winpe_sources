# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x140008920`
- end: `0x1400089f0`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400087e8`

## callees

- `0x140008654`
- `0x140008920`
- `0x140008ca8`
- `0x14000af58`
- `0x14000c754`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400089b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400089b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400089c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400089c0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400089cd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400089cd`

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
0x140008920  mov     [rsp+arg_0], rbx
0x140008925  mov     [rsp+arg_8], rsi
0x14000892a  push    rdi
0x14000892b  sub     rsp, 0E0h
0x140008932  mov     rbx, rcx
0x140008935  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000893a  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x14000893f  cmp     byte ptr [rbx+40h], 0
0x140008943  jz      short loc_140008953
0x140008945  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x140008949  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000894e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140008953  cmp     byte ptr [rbx+80h], 0
0x14000895a  jz      short loc_14000896A
0x14000895c  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x140008960  lea     rcx, [rsp+0E8h+var_88]; this
0x140008965  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000896a  cmp     byte ptr [rbx+0C0h], 0
0x140008971  jz      short loc_140008987
0x140008973  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x14000897a  lea     rcx, [rsp+0E8h+var_48]; this
0x140008982  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140008987  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000898c  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x140008991  lea     rcx, [rsp+0E8h+var_C8]; this
0x140008996  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x14000899b  mov     rsi, [rbx+108h]
0x1400089a2  mov     qword ptr [rbx+108h], 0
0x1400089ad  test    rsi, rsi
0x1400089b0  jz      short loc_1400089C6
0x1400089b2  call    cs:__imp_GetProcessHeap
0x1400089b8  mov     rcx, rax; hHeap
0x1400089bb  mov     r8, rsi; lpMem
0x1400089be  xor     edx, edx; dwFlags
0x1400089c0  call    cs:__imp_HeapFree
0x1400089c6  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1400089cd  call    cs:__imp_DeleteCriticalSection
0x1400089d3  lea     rcx, [rbx+8]; this
0x1400089d7  lea     r11, [rsp+0E8h+var_8]
0x1400089df  mov     rbx, [r11+10h]
0x1400089e3  mov     rsi, [r11+18h]
0x1400089e7  mov     rsp, r11
0x1400089ea  pop     rdi
0x1400089eb  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
