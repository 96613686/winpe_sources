# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x140005f0c`
- end: `0x140005fdc`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140005ca0`

## callees

- `0x140005ba8`
- `0x140005f0c`
- `0x14000627c`
- `0x14001004c`
- `0x14001175c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140005fb9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140005fb9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005f9e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005f9e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005fac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005fac`

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
0x140005f0c  mov     [rsp+arg_0], rbx
0x140005f11  mov     [rsp+arg_8], rsi
0x140005f16  push    rdi
0x140005f17  sub     rsp, 0E0h
0x140005f1e  mov     rbx, rcx
0x140005f21  lea     rcx, [rsp+0E8h+var_C8]; this
0x140005f26  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140005f2b  cmp     byte ptr [rbx+40h], 0
0x140005f2f  jz      short loc_140005F3F
0x140005f31  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x140005f35  lea     rcx, [rsp+0E8h+var_C8]; this
0x140005f3a  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140005f3f  cmp     byte ptr [rbx+80h], 0
0x140005f46  jz      short loc_140005F56
0x140005f48  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x140005f4c  lea     rcx, [rsp+0E8h+var_88]; this
0x140005f51  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140005f56  cmp     byte ptr [rbx+0C0h], 0
0x140005f5d  jz      short loc_140005F73
0x140005f5f  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x140005f66  lea     rcx, [rsp+0E8h+var_48]; this
0x140005f6e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140005f73  lea     rcx, [rsp+0E8h+var_C8]; this
0x140005f78  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x140005f7d  lea     rcx, [rsp+0E8h+var_C8]; this
0x140005f82  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x140005f87  mov     rsi, [rbx+108h]
0x140005f8e  mov     qword ptr [rbx+108h], 0
0x140005f99  test    rsi, rsi
0x140005f9c  jz      short loc_140005FB2
0x140005f9e  call    cs:__imp_GetProcessHeap
0x140005fa4  mov     r8, rsi; lpMem
0x140005fa7  xor     edx, edx; dwFlags
0x140005fa9  mov     rcx, rax; hHeap
0x140005fac  call    cs:__imp_HeapFree
0x140005fb2  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x140005fb9  call    cs:__imp_DeleteCriticalSection
0x140005fbf  lea     rcx, [rbx+8]; this
0x140005fc3  lea     r11, [rsp+0E8h+var_8]
0x140005fcb  mov     rbx, [r11+10h]
0x140005fcf  mov     rsi, [r11+18h]
0x140005fd3  mov     rsp, r11
0x140005fd6  pop     rdi
0x140005fd7  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
