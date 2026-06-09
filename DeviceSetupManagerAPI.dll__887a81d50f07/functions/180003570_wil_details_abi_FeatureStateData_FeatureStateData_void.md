# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180003570`
- end: `0x180003640`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180003440`

## callees

- `0x180003274`
- `0x180003570`
- `0x1800039e4`
- `0x180006020`
- `0x180007d58`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000361d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000361d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003602`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003602`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003610`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003610`

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
0x180003570  mov     [rsp+arg_0], rbx
0x180003575  mov     [rsp+arg_8], rsi
0x18000357a  push    rdi
0x18000357b  sub     rsp, 0E0h
0x180003582  mov     rbx, rcx
0x180003585  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000358a  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000358f  cmp     byte ptr [rbx+40h], 0
0x180003593  jz      short loc_1800035A3
0x180003595  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180003599  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000359e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800035a3  cmp     byte ptr [rbx+80h], 0
0x1800035aa  jz      short loc_1800035BA
0x1800035ac  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x1800035b0  lea     rcx, [rsp+0E8h+var_88]; this
0x1800035b5  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800035ba  cmp     byte ptr [rbx+0C0h], 0
0x1800035c1  jz      short loc_1800035D7
0x1800035c3  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x1800035ca  lea     rcx, [rsp+0E8h+var_48]; this
0x1800035d2  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800035d7  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800035dc  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x1800035e1  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800035e6  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x1800035eb  mov     rsi, [rbx+108h]
0x1800035f2  mov     qword ptr [rbx+108h], 0
0x1800035fd  test    rsi, rsi
0x180003600  jz      short loc_180003616
0x180003602  call    cs:__imp_GetProcessHeap
0x180003608  mov     rcx, rax; hHeap
0x18000360b  mov     r8, rsi; lpMem
0x18000360e  xor     edx, edx; dwFlags
0x180003610  call    cs:__imp_HeapFree
0x180003616  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18000361d  call    cs:__imp_DeleteCriticalSection
0x180003623  lea     rcx, [rbx+8]; this
0x180003627  lea     r11, [rsp+0E8h+var_8]
0x18000362f  mov     rbx, [r11+10h]
0x180003633  mov     rsi, [r11+18h]
0x180003637  mov     rsp, r11
0x18000363a  pop     rdi
0x18000363b  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
