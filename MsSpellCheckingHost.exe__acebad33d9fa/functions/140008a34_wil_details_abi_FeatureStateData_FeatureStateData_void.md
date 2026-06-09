# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x140008a34`
- end: `0x140008b04`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140008704`

## callees

- `0x14000849c`
- `0x140008a34`
- `0x140008ea0`
- `0x14000c068`
- `0x14000dfb8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140008ae1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140008ae1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008ad4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008ad4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008ac6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008ac6`

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
0x140008a34  mov     [rsp+arg_0], rbx
0x140008a39  mov     [rsp+arg_8], rsi
0x140008a3e  push    rdi
0x140008a3f  sub     rsp, 0E0h
0x140008a46  mov     rbx, rcx
0x140008a49  lea     rcx, [rsp+0E8h+var_C8]; this
0x140008a4e  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140008a53  cmp     byte ptr [rbx+40h], 0
0x140008a57  jz      short loc_140008A67
0x140008a59  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x140008a5d  lea     rcx, [rsp+0E8h+var_C8]; this
0x140008a62  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140008a67  cmp     byte ptr [rbx+80h], 0
0x140008a6e  jz      short loc_140008A7E
0x140008a70  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x140008a74  lea     rcx, [rsp+0E8h+var_88]; this
0x140008a79  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140008a7e  cmp     byte ptr [rbx+0C0h], 0
0x140008a85  jz      short loc_140008A9B
0x140008a87  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x140008a8e  lea     rcx, [rsp+0E8h+var_48]; this
0x140008a96  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140008a9b  lea     rcx, [rsp+0E8h+var_C8]; this
0x140008aa0  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x140008aa5  lea     rcx, [rsp+0E8h+var_C8]; this
0x140008aaa  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x140008aaf  mov     rsi, [rbx+108h]
0x140008ab6  mov     qword ptr [rbx+108h], 0
0x140008ac1  test    rsi, rsi
0x140008ac4  jz      short loc_140008ADA
0x140008ac6  call    cs:__imp_GetProcessHeap
0x140008acc  mov     rcx, rax; hHeap
0x140008acf  mov     r8, rsi; lpMem
0x140008ad2  xor     edx, edx; dwFlags
0x140008ad4  call    cs:__imp_HeapFree
0x140008ada  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x140008ae1  call    cs:__imp_DeleteCriticalSection
0x140008ae7  lea     rcx, [rbx+8]; this
0x140008aeb  lea     r11, [rsp+0E8h+var_8]
0x140008af3  mov     rbx, [r11+10h]
0x140008af7  mov     rsi, [r11+18h]
0x140008afb  mov     rsp, r11
0x140008afe  pop     rdi
0x140008aff  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
