# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x140008090`
- end: `0x140008160`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140007f78`

## callees

- `0x140007dac`
- `0x140008090`
- `0x140008504`
- `0x14000a228`
- `0x14000be1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000813d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000813d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008130`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008130`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008122`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008122`

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
0x140008090  mov     [rsp+arg_0], rbx
0x140008095  mov     [rsp+arg_8], rsi
0x14000809a  push    rdi
0x14000809b  sub     rsp, 0E0h
0x1400080a2  mov     rbx, rcx
0x1400080a5  lea     rcx, [rsp+0E8h+var_C8]; this
0x1400080aa  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1400080af  cmp     byte ptr [rbx+40h], 0
0x1400080b3  jz      short loc_1400080C3
0x1400080b5  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x1400080b9  lea     rcx, [rsp+0E8h+var_C8]; this
0x1400080be  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1400080c3  cmp     byte ptr [rbx+80h], 0
0x1400080ca  jz      short loc_1400080DA
0x1400080cc  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x1400080d0  lea     rcx, [rsp+0E8h+var_88]; this
0x1400080d5  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1400080da  cmp     byte ptr [rbx+0C0h], 0
0x1400080e1  jz      short loc_1400080F7
0x1400080e3  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x1400080ea  lea     rcx, [rsp+0E8h+var_48]; this
0x1400080f2  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1400080f7  lea     rcx, [rsp+0E8h+var_C8]; this
0x1400080fc  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x140008101  lea     rcx, [rsp+0E8h+var_C8]; this
0x140008106  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x14000810b  mov     rsi, [rbx+108h]
0x140008112  mov     qword ptr [rbx+108h], 0
0x14000811d  test    rsi, rsi
0x140008120  jz      short loc_140008136
0x140008122  call    cs:__imp_GetProcessHeap
0x140008128  mov     rcx, rax; hHeap
0x14000812b  mov     r8, rsi; lpMem
0x14000812e  xor     edx, edx; dwFlags
0x140008130  call    cs:__imp_HeapFree
0x140008136  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x14000813d  call    cs:__imp_DeleteCriticalSection
0x140008143  lea     rcx, [rbx+8]; this
0x140008147  lea     r11, [rsp+0E8h+var_8]
0x14000814f  mov     rbx, [r11+10h]
0x140008153  mov     rsi, [r11+18h]
0x140008157  mov     rsp, r11
0x14000815a  pop     rdi
0x14000815b  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
